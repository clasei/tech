<template>
  <div class="glass rounded-2xl p-6 hover:shadow-2xl transition-all duration-250 hover:-translate-y-1.5 flex flex-col h-full group">
    <!-- Title -->
    <h3 class="text-xl font-normal mb-3 text-[var(--text-primary)] group-hover:text-[#d1d9f0] transition-colors duration-200">
      {{ project.title }}
    </h3>

    <!-- Description -->
    <p class="text-[var(--text-secondary)] text-sm mb-5 leading-relaxed">
      {{ project.description }}
    </p>

    <!-- Impact & Decision -->
    <ul class="space-y-2 mb-4 flex-grow">
      <li class="text-sm text-[var(--text-secondary)] flex items-start gap-2">
        <span class="text-[var(--accent)] mt-0.5">→</span>
        <span>{{ project.impact }}</span>
      </li>
      <li class="text-sm text-[var(--text-secondary)] flex items-start gap-2">
        <span class="text-[var(--accent)] mt-0.5">→</span>
        <span>{{ project.keyDecision }}</span>
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
    <div class="flex gap-2 pt-2 border-t border-[var(--border)]">
      <a
        v-if="project.liveUrl"
        :href="project.liveUrl"
        target="_blank"
        rel="noopener noreferrer"
        class="mini-crystal-link"
      >
        live
      </a>
      <a
        v-if="project.repoUrl"
        :href="project.repoUrl"
        target="_blank"
        rel="noopener noreferrer"
        class="mini-crystal-link"
      >
        repo
      </a>
    </div>
  </div>
</template>

<style scoped>
.mini-crystal-link {
  display: inline-flex;
  align-items: center;
  padding: 0.4rem 0.875rem;
  background: var(--surface);
  border: 1px solid rgba(120, 140, 255, 0.2);
  border-radius: 9999px;
  color: var(--text-secondary);
  font-size: 0.8125rem;
  box-shadow: 
    0 2px 8px rgba(0, 0, 0, 0.06),
    inset 0 1px 0 rgba(255, 255, 255, 0.04);
  backdrop-filter: blur(20px);
  transition: all 0.2s ease;
}

.mini-crystal-link:hover {
  color: #ffffff;
  border-color: rgba(120, 140, 255, 0.4);
  box-shadow: 
    0 4px 12px rgba(110, 168, 255, 0.15),
    inset 0 1px 0 rgba(255, 255, 255, 0.08);
  transform: translateY(-1px);
}
</style>

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
