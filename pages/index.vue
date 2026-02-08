<template>
  <div>
    <ThemeToggle />

    <!-- Hero -->
    <Hero />

    <!-- How I Work / Stack -->
    <section id="work" class="px-6 py-24">
      <div class="max-w-6xl mx-auto">
        <h2 class="text-3xl md:text-4xl font-normal mb-16 text-[var(--text-primary)]">how i work / stack</h2>
        <div class="grid md:grid-cols-2 gap-8">
          <!-- How I Work -->
          <div class="glass rounded-2xl p-8 lg:p-10">
            <ul class="space-y-4">
              <li class="text-[var(--text-secondary)] flex items-start gap-3">
                <span class="text-[var(--text-primary)] opacity-40">—</span>
                <span>clarity-first ux, simple solutions over clever ones</span>
              </li>
              <li class="text-[var(--text-secondary)] flex items-start gap-3">
                <span class="text-[var(--text-primary)] opacity-40">—</span>
                <span>performance matters, measure optimize repeat</span>
              </li>
              <li class="text-[var(--text-secondary)] flex items-start gap-3">
                <span class="text-[var(--text-primary)] opacity-40">—</span>
                <span>maintainable code, future you will thank you</span>
              </li>
              <li class="text-[var(--text-secondary)] flex items-start gap-3">
                <span class="text-[var(--text-primary)] opacity-40">—</span>
                <span>ship small, iterate fast, learn quickly</span>
              </li>
            </ul>
          </div>

          <!-- Stack -->
          <div class="glass rounded-2xl p-8 lg:p-10">
            <div class="space-y-4">
              <div>
                <p class="text-sm text-[var(--text-secondary)] mb-2">frontend</p>
                <div class="flex flex-wrap gap-3">
                  <span v-for="tech in frontendStack" :key="tech" class="px-2.5 py-1 text-sm text-[var(--text-primary)] opacity-70 hover:opacity-100 transition-opacity font-mono border border-[var(--border)] rounded-md">
                    {{ tech }}
                  </span>
                </div>
              </div>
              <div>
                <p class="text-sm text-[var(--text-secondary)] mb-2">backend</p>
                <div class="flex flex-wrap gap-3">
                  <span v-for="tech in backendStack" :key="tech" class="px-2.5 py-1 text-sm text-[var(--text-primary)] opacity-70 hover:opacity-100 transition-opacity font-mono border border-[var(--border)] rounded-md">
                    {{ tech }}
                  </span>
                </div>
              </div>
              <div>
                <p class="text-sm text-[var(--text-secondary)] mb-2">tools</p>
                <div class="flex flex-wrap gap-3">
                  <span v-for="tech in toolsStack" :key="tech" class="px-2.5 py-1 text-sm text-[var(--text-primary)] opacity-70 hover:opacity-100 transition-opacity font-mono border border-[var(--border)] rounded-md">
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
        <h2 class="text-3xl md:text-4xl font-normal mb-16 text-[var(--text-primary)]">projects</h2>
        <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-8">
          <ProjectCard v-for="project in projects" :key="project.title" :project="project" />
        </div>
      </div>
    </section>

    <!-- About -->
    <section id="about" class="px-6 py-24">
      <div class="max-w-4xl mx-auto">
        <h2 class="text-3xl md:text-4xl font-normal mb-12 text-[var(--text-primary)]">about</h2>
        <div class="glass rounded-2xl p-8 lg:p-10">
          <p class="text-lg text-[var(--text-secondary)] leading-relaxed mb-6">
            building systems that work, shipping code that matters
          </p>
          <p class="text-lg text-[var(--text-secondary)] leading-relaxed">
            eager to create impact in a team that values craft and delivery, one commit at a time
          </p>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="px-6 py-16 border-t border-[var(--border)]">
      <div class="max-w-6xl mx-auto">
        <div class="flex flex-col md:flex-row justify-between items-center gap-8">
          <div class="text-[var(--text-secondary)] text-sm">
            2026 · built by @clasei
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
    title: 'flowx',
    description: 'lightweight task tracker with sorting prioritization and clean ui',
    impact: 'keeps things simple yet structured with minimal effort',
    keyDecision: 'priority ranking system as critical focus or pipeline',
    stack: ['angular', 'typescript', 'spring', 'postgresql'],
    liveUrl: 'https://flowx-woad.vercel.app/',
    repoUrl: 'https://github.com/clasei/flowx-client'
  },
  {
    title: 'recup',
    description: 'platform for genuine recommendations cutting through algorithmic noise',
    impact: 'highlights valuable content by real users not algorithms',
    keyDecision: 'user-centered recommendation system for authentic discovery',
    stack: ['mongodb', 'express', 'react', 'node'],
    liveUrl: 'https://just-recup.netlify.app/',
    repoUrl: 'https://github.com/clasei/recup'
  },
  {
    title: 'machinsight',
    description: 'smart maintenance tracker for industrial machines',
    impact: 'streamlines equipment monitoring with csv xlsx data imports',
    keyDecision: 'fastapi converts data to json for seamless backend integration',
    stack: ['react', 'typescript', 'node', 'fastapi', 'python'],
    repoUrl: 'https://github.com/clasei/machinsight-client'
  },
  {
    title: 'galactic hitchhiker',
    description: 'hitchhikers guide inspired experience delivering wisdom',
    impact: 'delivers perspective based on your state of mind',
    keyDecision: 'json data structure for dynamic content delivery',
    stack: ['angular', 'typescript', 'json'],
    liveUrl: 'https://clasei.github.io/galactic-hitchhiker/',
    repoUrl: 'https://github.com/clasei/galactic-hitchhiker'
  },
  {
    title: 'neutron link',
    description: 'spatial simplicity for link sharing',
    impact: 'simple and effective tool with spatial awareness',
    keyDecision: 'firebase for real time link synchronization',
    stack: ['react', 'firebase'],
    liveUrl: 'https://neutron-link-0.web.app/',
    repoUrl: 'https://github.com/clasei/neutron-link'
  },
  {
    title: 'space time',
    description: 'interactive visualization of time using physics based animations',
    impact: 'time motion and particles in sync for immersive experience',
    keyDecision: 'particles js for smooth performant animations',
    stack: ['javascript', 'particles.js'],
    liveUrl: 'https://clasei.github.io/space-time/',
    repoUrl: 'https://github.com/clasei/space-time'
  }
]
</script>
