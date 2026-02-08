<template>
  <div>
    <ThemeToggle />

    <!-- Hero -->
    <Hero />

    <!-- How I Work / Stack -->
    <section id="work" class="px-6 py-24">
      <div class="max-w-6xl mx-auto">
        <h2 class="text-3xl md:text-4xl font-bold mb-16 text-[var(--text-primary)]">how i work / stack</h2>
        <div class="grid md:grid-cols-2 gap-8">
          <!-- How I Work -->
          <div class="glass rounded-2xl p-8 lg:p-10">
            <h3 class="text-xl font-semibold mb-6 text-[var(--text-primary)]">how i work</h3>
            <ul class="space-y-4">
              <li class="text-[var(--text-secondary)]">
                clarity-first ux, simple solutions over clever ones
              </li>
              <li class="text-[var(--text-secondary)]">
                performance matters, measure optimize repeat
              </li>
              <li class="text-[var(--text-secondary)]">
                maintainable code, future you will thank you
              </li>
              <li class="text-[var(--text-secondary)]">
                ship small, iterate fast, learn quickly
              </li>
            </ul>
          </div>

          <!-- Stack -->
          <div class="glass rounded-2xl p-8 lg:p-10">
            <h3 class="text-xl font-semibold mb-6 text-[var(--text-primary)]">stack</h3>
            <div class="space-y-4">
              <div>
                <p class="text-sm text-[var(--text-secondary)] mb-2">frontend</p>
                <div class="flex flex-wrap gap-2">
                  <span v-for="tech in frontendStack" :key="tech" class="px-3 py-1.5 text-sm rounded-lg bg-[var(--surface)] border border-[var(--border)] text-[var(--text-primary)] font-medium hover:border-[var(--accent)] transition-colors">
                    {{ tech }}
                  </span>
                </div>
              </div>
              <div>
                <p class="text-sm text-[var(--text-secondary)] mb-2">backend</p>
                <div class="flex flex-wrap gap-2">
                  <span v-for="tech in backendStack" :key="tech" class="px-3 py-1.5 text-sm rounded-lg bg-[var(--surface)] border border-[var(--border)] text-[var(--text-primary)] font-medium hover:border-[var(--accent)] transition-colors">
                    {{ tech }}
                  </span>
                </div>
              </div>
              <div>
                <p class="text-sm text-[var(--text-secondary)] mb-2">tools</p>
                <div class="flex flex-wrap gap-2">
                  <span v-for="tech in toolsStack" :key="tech" class="px-3 py-1.5 text-sm rounded-lg bg-[var(--surface)] border border-[var(--border)] text-[var(--text-primary)] font-medium hover:border-[var(--accent)] transition-colors">
                    {{ tech }}
                  </span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Projects -->
    <section id="projects" class="px-6 py-24 bg-[var(--bg)]">
      <div class="max-w-6xl mx-auto">
        <h2 class="text-3xl md:text-4xl font-bold mb-16 text-[var(--text-primary)]">projects</h2>
        <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-8">
          <ProjectCard v-for="project in projects" :key="project.title" :project="project" />
        </div>
      </div>
    </section>

    <!-- About -->
    <section id="about" class="px-6 py-24">
      <div class="max-w-4xl mx-auto">
        <h2 class="text-3xl md:text-4xl font-bold mb-12 text-[var(--text-primary)]">about</h2>
        <div class="glass rounded-2xl p-8 lg:p-10">
          <p class="text-lg text-[var(--text-secondary)] leading-relaxed mb-6">
            i build interfaces that work — no fluff, no unnecessary complexity, just clean code that solves real problems
          </p>
          <p class="text-lg text-[var(--text-secondary)] leading-relaxed">
            every line matters, every decision counts, focused on craft committed to shipping
          </p>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="px-6 py-16 border-t border-[var(--border)]">
      <div class="max-w-6xl mx-auto">
        <div class="flex flex-col md:flex-row justify-between items-center gap-8">
          <div class="text-[var(--text-secondary)] text-sm">
            clasei
          </div>
          <div class="flex gap-6">
            <a
              href="https://github.com/clasei"
              target="_blank"
              rel="noopener noreferrer"
              class="text-[var(--text-secondary)] hover:text-[var(--accent)] transition-colors duration-200"
            >
              github
            </a>
            <a
              href="https://linkedin.com/in/claraseijo"
              target="_blank"
              rel="noopener noreferrer"
              class="text-[var(--text-secondary)] hover:text-[var(--accent)] transition-colors duration-200"
            >
              linkedin
            </a>
            <a
              href="mailto:clasei@proton.me"
              class="text-[var(--text-secondary)] hover:text-[var(--accent)] transition-colors duration-200"
            >
              email
            </a>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
const frontendStack = ['angular', 'vue', 'react', 'typescript', 'tailwind']
const backendStack = ['node.js', 'spring', 'express']
const toolsStack = ['git', 'testing', 'ci/cd', 'docs']

const projects = [
  {
    title: 'e-commerce platform',
    description: 'full-stack shopping experience with real-time inventory',
    impact: 'reduced load time by 45% with lazy loading and optimized bundles',
    keyDecision: 'chose vue 3 composition api for better type safety and reusability',
    stack: ['vue', 'typescript', 'node', 'mongodb'],
    liveUrl: 'https://example.com',
    repoUrl: 'https://github.com/clasei/project'
  },
  {
    title: 'task management app',
    description: 'collaborative tool for team workflows',
    impact: 'improved user retention by 30% with intuitive drag-and-drop ui',
    keyDecision: 'implemented optimistic updates for instant feedback',
    stack: ['react', 'typescript', 'tailwind', 'supabase'],
    repoUrl: 'https://github.com/clasei/project'
  },
  {
    title: 'analytics dashboard',
    description: 'real-time data visualization for business metrics',
    impact: 'processed 100k+ events/min with efficient data aggregation',
    keyDecision: 'used web workers for heavy calculations without blocking ui',
    stack: ['angular', 'typescript', 'd3.js', 'spring'],
    liveUrl: 'https://example.com',
    repoUrl: 'https://github.com/clasei/project'
  },
  {
    title: 'design system',
    description: 'component library for consistent ui across products',
    impact: 'reduced development time by 40% with reusable components',
    keyDecision: 'built with storybook for isolated component development',
    stack: ['vue', 'typescript', 'storybook', 'vite'],
    repoUrl: 'https://github.com/clasei/project'
  },
  {
    title: 'api gateway',
    description: 'centralized routing and authentication layer',
    impact: 'handled 10m+ requests/day with 99.9% uptime',
    keyDecision: 'implemented rate limiting and caching for performance',
    stack: ['node', 'typescript', 'express', 'redis'],
    repoUrl: 'https://github.com/clasei/project'
  },
  {
    title: 'content cms',
    description: 'headless cms for markdown-based content',
    impact: 'enabled non-technical users to publish content independently',
    keyDecision: 'chose git-based workflow for version control and rollbacks',
    stack: ['nuxt', 'typescript', 'tailwind', 'netlify-cms'],
    liveUrl: 'https://example.com',
    repoUrl: 'https://github.com/clasei/project'
  }
]
</script>
