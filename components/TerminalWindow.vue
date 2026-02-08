<template>
  <div class="terminal-window glass rounded-2xl overflow-hidden">
    <!-- Terminal Header -->
    <div
      class="terminal-header flex items-center justify-between px-4 py-3 bg-[var(--surface)] border-b border-[var(--border)]"
    >
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
    <div class="terminal-content p-6 font-mono text-sm terminal-bg">
      <div class="mb-4">
        <span class="text-[#27c93f]">dev@localhost</span>
        <span class="text-[var(--text-secondary)]">:</span>
        <span class="text-[#6ea8ff]">~</span>
        <span class="text-[var(--text-secondary)]">$</span>
        <span class="text-[var(--text-primary)] ml-2"
          >pragmatic-ai --version</span
        >
      </div>

      <div class="mb-6">
        <div class="text-[#6ea8ff] mb-2">The New Pragmatic Programmer</div>
        <div class="text-[var(--text-secondary)] text-xs">
          AI Age Edition · v2026.1
        </div>
      </div>

      <div class="space-y-5 text-[var(--text-secondary)] leading-relaxed">
        <div>
          <span class="text-[#6ea8ff]">[1]</span>
          <span class="ml-2"
            >understand the prompt, understand the problem</span
          >
        </div>

        <div>
          <span class="text-[#6ea8ff]">[2]</span>
          <span class="ml-2">AI writes code, you write systems</span>
        </div>

        <div>
          <span class="text-[#6ea8ff]">[3]</span>
          <span class="ml-2"
            >review every line like you wrote it, debug like it's yours</span
          >
        </div>

        <div>
          <span class="text-[#6ea8ff]">[4]</span>
          <span class="ml-2">automation amplifies, understanding guides</span>
        </div>

        <div>
          <span class="text-[#6ea8ff]">[5]</span>
          <span class="ml-2"
            >test what matters, not what's easy to generate</span
          >
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
        <span class="text-[#27c93f]">dev@localhost</span>
        <span class="text-[var(--text-secondary)]">:</span>
        <span class="text-[#6ea8ff]">~</span>
        <span class="text-[var(--text-secondary)]">$</span>
        <span class="terminal-cursor ml-2"></span>
      </div>
    </div>
  </div>
</template>

<script setup>
// Static display - all principles shown at once
</script>

<style scoped>
.terminal-window {
  max-width: 900px;
  margin: 0 auto;
}

.terminal-bg {
  background: #0a0e1a;
}

[data-theme="light"] .terminal-bg {
  background: #e8ecf2;
  color: #1e293b;
}

[data-theme="light"] .terminal-bg .text-\[\#27c93f\] {
  color: #16a34a !important;
}

[data-theme="light"] .terminal-bg .text-\[\#6ea8ff\] {
  color: #3b82f6 !important;
}

/* Monochrome theme - terminal colors to grey */
[data-theme="mono"] .terminal-bg .text-\[\#27c93f\] {
  color: #9ca3af !important;
}

[data-theme="mono"] .terminal-bg .text-\[\#6ea8ff\] {
  color: #9ca3af !important;
}

[data-theme="mono"] .terminal-header .bg-\[\#ff5f56\],
[data-theme="mono"] .terminal-header .bg-\[\#ffbd2e\],
[data-theme="mono"] .terminal-header .bg-\[\#27c93f\] {
  background: #6b7280 !important;
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
  0%,
  50% {
    opacity: 1;
  }
  51%,
  100% {
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
