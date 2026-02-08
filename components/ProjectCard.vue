<template>
  <a
    :href="project.liveUrl || project.repoUrl"
    target="_blank"
    rel="noopener noreferrer"
    :aria-label="`Visit ${project.title}${project.liveUrl ? ' live site' : ' repository'}`"
    class="glass rounded-2xl overflow-hidden hover:shadow-2xl transition-all duration-250 hover:-translate-y-1.5 flex flex-col h-full group block"
  >
    <!-- Image -->
    <img
      v-if="project.imageUrl"
      :src="project.imageUrl"
      :alt="project.title"
      class="w-full h-48 object-cover"
      loading="lazy"
    />

    <div class="p-6 flex flex-col flex-grow">
      <!-- Title -->
      <h3
        class="text-xl font-normal mb-5 text-[var(--text-primary)] group-hover:text-[#d1d9f0] transition-colors duration-200 font-mono cursor-default"
      >
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
      <div class="flex flex-wrap gap-2.5">
        <span
          v-for="tech in project.stack"
          :key="tech"
          class="px-2 py-0.5 text-xs text-[var(--text-primary)] opacity-90 font-mono border border-[var(--border)] rounded-md bg-[var(--surface)]"
        >
          {{ tech }}
        </span>
      </div>
    </div>
  </a>
</template>

<style scoped>
/* No additional styles needed - inherits from global glass class */
</style>

<script setup lang="ts">
interface Project {
  title: string;
  description: string;
  impact: string;
  keyDecision: string;
  stack: string[];
  imageUrl?: string;
  liveUrl?: string;
  repoUrl?: string;
}

defineProps<{
  project: Project;
}>();
</script>
