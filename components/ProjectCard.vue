<template>
  <div class="glass rounded-2xl p-6 hover:shadow-2xl transition-all duration-250 hover:-translate-y-1.5 flex flex-col h-full group">
    <!-- Title -->
    <h3 class="text-xl font-semibold mb-3 text-[var(--text-primary)] group-hover:text-[var(--accent)] transition-colors duration-200">
      {{ project.title }}
    </h3>

    <!-- Description -->
    <p class="text-[var(--text-secondary)] text-sm mb-5 leading-relaxed">
      {{ project.description }}
    </p>

    <!-- Impact & Decision -->
    <ul class="space-y-2 mb-4 flex-grow">
      <li class="text-sm text-[var(--text-secondary)]">
        {{ project.impact }}
      </li>
      <li class="text-sm text-[var(--text-secondary)]">
        {{ project.keyDecision }}
      </li>
    </ul>

    <!-- Stack chips -->
    <div class="flex flex-wrap gap-2.5 mb-4">
      <span
        v-for="tech in project.stack"
        :key="tech"
        class="px-2 py-0.5 text-xs text-[var(--text-primary)] opacity-60 font-mono border border-[var(--border)] rounded-md"
      >
        {{ tech }}
      </span>
    </div>

    <!-- Links -->
    <div class="flex gap-3 pt-2 border-t border-[var(--border)]">
      <a
        v-if="project.liveUrl"
        :href="project.liveUrl"
        target="_blank"
        rel="noopener noreferrer"
        class="group flex items-center gap-1.5 text-sm text-[var(--text-secondary)] hover:text-[var(--accent)] transition-all duration-150"
      >
        <span>live</span>
        <svg class="w-3.5 h-3.5 group-hover:translate-x-0.5 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
        </svg>
      </a>
      <a
        v-if="project.repoUrl"
        :href="project.repoUrl"
        target="_blank"
        rel="noopener noreferrer"
        class="group flex items-center gap-1.5 text-sm text-[var(--text-secondary)] hover:text-[var(--accent)] transition-all duration-150"
      >
        <span>repo</span>
        <svg class="w-3.5 h-3.5 group-hover:translate-x-0.5 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
        </svg>
      </a>
    </div>
  </div>
</template>

<script setup lang="ts">
interface Project {
  title: string
  description: string
  impact: string
  keyDecision: string
  stack: string[]
  liveUrl?: string
  repoUrl?: string
}

defineProps<{
  project: Project
}>()
</script>
