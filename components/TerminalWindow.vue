<template>
  <div class="terminal-window glass rounded-2xl overflow-hidden">
    <!-- Terminal Header -->
    <div class="terminal-header flex items-center justify-between px-4 py-3 bg-[var(--surface)] border-b border-[var(--border)]">
      <div class="flex gap-2">
        <div class="w-3 h-3 rounded-full bg-[#ff5f56]"></div>
        <div class="w-3 h-3 rounded-full bg-[#ffbd2e]"></div>
        <div class="w-3 h-3 rounded-full bg-[#27c93f]"></div>
      </div>
      <div class="text-xs text-[var(--text-secondary)] font-mono">
        pragmatic.sh
      </div>
      <div class="w-16"></div>
    </div>

    <!-- Terminal Content -->
    <div class="terminal-content p-6 font-mono text-sm bg-[#0a0e1a] relative">
      <div class="mb-4">
        <span class="text-[#27c93f]">clasei@localhost</span>
        <span class="text-[var(--text-secondary)]">:</span>
        <span class="text-[#6ea8ff]">~</span>
        <span class="text-[var(--text-secondary)]">$</span>
        <span class="text-[var(--text-primary)] ml-2">{{ commandText }}</span>
        <span v-if="isTypingCommand" class="terminal-cursor"></span>
      </div>

      <div class="principle-container">
        <div v-if="showPrinciple" class="text-[var(--text-secondary)] leading-relaxed">
          <span class="text-[#6ea8ff]">[{{ currentIndex + 1 }}]</span>
          <span class="ml-2">{{ displayedText }}</span>
          <span v-if="isTypingPrinciple" class="terminal-cursor"></span>
        </div>
      </div>

      <!-- Carousel Navigation -->
      <div class="flex items-center justify-between mt-8">
        <button 
          @click="prevPrinciple"
          class="text-[var(--text-primary)] hover:text-[#6ea8ff] transition-colors disabled:opacity-30 disabled:cursor-not-allowed"
          :disabled="currentIndex === 0"
        >
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"/>
          </svg>
        </button>

        <div class="flex gap-2">
          <button
            v-for="(_, index) in principles"
            :key="index"
            @click="goToPrinciple(index)"
            class="w-2 h-2 rounded-full transition-all"
            :class="index === currentIndex ? 'bg-[#6ea8ff] w-6' : 'bg-[var(--text-secondary)] opacity-30 hover:opacity-50'"
          ></button>
        </div>

        <button 
          @click="nextPrinciple"
          class="text-[var(--text-primary)] hover:text-[#6ea8ff] transition-colors disabled:opacity-30 disabled:cursor-not-allowed"
          :disabled="currentIndex === principles.length - 1"
        >
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const principles = [
  'understand the prompt, understand the problem',
  'AI writes code, you write systems',
  'review every line like you wrote it, debug like it\'s yours',
  'automation amplifies, understanding guides',
  'test what matters, not what\'s easy to generate',
  'your judgment over model confidence',
  'tools evolve fast, fundamentals stay true',
  'pair with AI, ship with intention'
]

const currentIndex = ref(0)
const commandText = ref('')
const displayedText = ref('')
const isTypingCommand = ref(false)
const isTypingPrinciple = ref(false)
const showPrinciple = ref(false)

let typingTimeout = null
let autoAdvanceTimeout = null

const fullCommand = 'cat principle.txt'

const typeCommand = async () => {
  isTypingCommand.value = true
  commandText.value = ''
  
  for (let i = 0; i <= fullCommand.length; i++) {
    commandText.value = fullCommand.slice(0, i)
    await new Promise(resolve => typingTimeout = setTimeout(resolve, 50))
  }
  
  isTypingCommand.value = false
  await new Promise(resolve => typingTimeout = setTimeout(resolve, 300))
  showPrinciple.value = true
  await typePrinciple()
}

const typePrinciple = async () => {
  isTypingPrinciple.value = true
  displayedText.value = ''
  const text = principles[currentIndex.value]
  
  for (let i = 0; i <= text.length; i++) {
    displayedText.value = text.slice(0, i)
    await new Promise(resolve => typingTimeout = setTimeout(resolve, 30))
  }
  
  isTypingPrinciple.value = false
  
  // Auto-advance to next principle after 4 seconds
  if (currentIndex.value < principles.length - 1) {
    autoAdvanceTimeout = setTimeout(() => {
      nextPrinciple()
    }, 4000)
  }
}

const nextPrinciple = () => {
  if (currentIndex.value < principles.length - 1) {
    clearTimeouts()
    currentIndex.value++
    showPrinciple.value = false
    typeCommand()
  }
}

const prevPrinciple = () => {
  if (currentIndex.value > 0) {
    clearTimeouts()
    currentIndex.value--
    showPrinciple.value = false
    typeCommand()
  }
}

const goToPrinciple = (index) => {
  if (index !== currentIndex.value) {
    clearTimeouts()
    currentIndex.value = index
    showPrinciple.value = false
    typeCommand()
  }
}

const clearTimeouts = () => {
  if (typingTimeout) clearTimeout(typingTimeout)
  if (autoAdvanceTimeout) clearTimeout(autoAdvanceTimeout)
}

onMounted(() => {
  typeCommand()
})

onUnmounted(() => {
  clearTimeouts()
})
</script>

<style scoped>
.terminal-window {
  max-w-900px;
  margin: 0 auto;
}

.terminal-content {
  height: 280px;
  display: flex;
  flex-direction: column;
}

.principle-container {
  flex: 1;
  display: flex;
  align-items: center;
  min-height: 120px;
}

.terminal-cursor {
  display: inline-block;
  width: 8px;
  height: 16px;
  background: var(--text-primary);
  animation: blink 1s step-end infinite;
  margin-left: 2px;
}

@keyframes blink {
  0%, 50% {
    opacity: 1;
  }
  51%, 100% {
    opacity: 0;
  }
}

@media (prefers-reduced-motion: reduce) {
  .terminal-cursor {
    animation: none;
    opacity: 1;
  }
}
</style>
