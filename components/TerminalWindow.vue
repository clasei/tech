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
    <div class="terminal-content p-6 font-mono text-sm bg-[#0a0e1a]">
      <div class="mb-6">
        <span class="text-[#27c93f]">clasei@localhost</span>
        <span class="text-[var(--text-secondary)]">:</span>
        <span class="text-[#6ea8ff]">~</span>
        <span class="text-[var(--text-secondary)]">$</span>
        <span class="text-[var(--text-primary)] ml-2">cat pragmatic_programmer_ai_free.txt</span>
      </div>

      <div class="space-y-6 text-[var(--text-secondary)] leading-relaxed">
        <div>
          <span class="text-[#6ea8ff]">[1]</span>
          <span class="ml-2">understand the prompt, understand the problem</span>
        </div>

        <div>
          <span class="text-[#6ea8ff]">[2]</span>
          <span class="ml-2">AI writes code, you write systems</span>
        </div>

        <div>
          <span class="text-[#6ea8ff]">[3]</span>
          <span class="ml-2">review every line like you wrote it, debug like it's yours</span>
        </div>

        <div>
          <span class="text-[#6ea8ff]">[4]</span>
          <span class="ml-2">automation amplifies, understanding guides</span>
        </div>

        <div>
          <span class="text-[#6ea8ff]">[5]</span>
          <span class="ml-2">test what matters, not what's easy to generate</span>
        </div>

        <div>
          <span class="text-[#6ea8ff]">[6]</span>
          <span class="ml-2">your judgment over model confidence</span>
        </div>

        <div>
          <span class="text-[#6ea8ff]">[7]</span>
          <span class="ml-2">tools evolve fast, fundamentals stay true</span>
        </div>

        <div>
          <span class="text-[#6ea8ff]">[8]</span>
          <span class="ml-2">pair with AI, ship with intention</span>
        </div>
      </div>

      <div class="mt-6 flex items-center">
        <span class="text-[#27c93f]">clasei@localhost</span>
        <span class="text-[var(--text-secondary)]">:</span>
        <span class="text-[#6ea8ff]">~</span>
        <span class="text-[var(--text-secondary)]">$</span>
        <span class="terminal-cursor ml-2"></span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.terminal-window {
  max-width: 900px;
  margin: 0 auto;
}

.terminal-content {
  min-height: 400px;
}

.terminal-cursor {
  display: inline-block;
  width: 8px;
  height: 16px;
  background: var(--text-primary);
  animation: blink 1s step-end infinite;
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
