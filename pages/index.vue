<template>
  <div>
    <ThemeToggle />

    <!-- Hero -->
    <Hero />

    <!-- Work / Stack -->
    <section id="work" class="px-6 py-24">
      <div class="max-w-6xl mx-auto">
        <h2
          class="text-3xl md:text-4xl font-normal mb-16 text-[var(--text-primary)] cursor-default"
        >
          work / stack
        </h2>

        <!-- Intro -->
        <div class="max-w-4xl mx-auto space-y-4 mb-16 cursor-default">
          <p class="text-lg text-[var(--text-secondary)] leading-relaxed">
            i get things done and build things that work
          </p>
          <p class="text-lg text-[var(--text-secondary)] leading-relaxed">
            clean code and logical structure for user-centered software
          </p>
          <p class="text-lg text-[var(--text-secondary)] leading-relaxed">
            focus on usability that works, simplicity that cuts complexity, and
            efficiency that scales smart
          </p>
        </div>

        <div class="grid md:grid-cols-2 gap-8">
          <!-- How I Work -->
          <div class="glass rounded-2xl p-8 lg:p-10">
            <ul class="space-y-5">
              <li class="text-[var(--text-secondary)] flex items-start gap-3">
                <span class="text-[var(--accent)] opacity-70">→</span>
                <span>clarity-first ux, simple solutions over clever ones</span>
              </li>
              <li class="text-[var(--text-secondary)] flex items-start gap-3">
                <span class="text-[var(--accent)] opacity-70">→</span>
                <span>performance matters, measure optimize repeat</span>
              </li>
              <li class="text-[var(--text-secondary)] flex items-start gap-3">
                <span class="text-[var(--accent)] opacity-70">→</span>
                <span>maintainable code, future you will thank you</span>
              </li>
              <li class="text-[var(--text-secondary)] flex items-start gap-3">
                <span class="text-[var(--accent)] opacity-70">→</span>
                <span>ship small, iterate fast, learn quickly</span>
              </li>
            </ul>
          </div>

          <!-- Stack -->
          <div class="glass rounded-2xl p-8 lg:p-10">
            <div class="space-y-5">
              <div>
                <p class="text-sm text-[var(--accent)] mb-2 font-mono">
                  → frontend
                </p>
                <div class="flex flex-wrap gap-2">
                  <span
                    v-for="tech in frontendStack"
                    :key="tech"
                    class="px-1.5 py-0.5 text-xs text-[var(--text-primary)] opacity-90 hover:opacity-100 transition-opacity font-mono border border-[var(--border)] rounded bg-[var(--surface)]"
                  >
                    {{ tech }}
                  </span>
                </div>
              </div>
              <div>
                <p class="text-sm text-[var(--accent)] mb-2 font-mono">
                  → backend
                </p>
                <div class="flex flex-wrap gap-2">
                  <span
                    v-for="tech in backendStack"
                    :key="tech"
                    class="px-1.5 py-0.5 text-xs text-[var(--text-primary)] opacity-90 hover:opacity-100 transition-opacity font-mono border border-[var(--border)] rounded bg-[var(--surface)]"
                  >
                    {{ tech }}
                  </span>
                </div>
              </div>
              <div>
                <p class="text-sm text-[var(--accent)] mb-2 font-mono">
                  → workflow
                </p>
                <div class="flex flex-wrap gap-2">
                  <span
                    v-for="tech in toolsStack"
                    :key="tech"
                    class="px-1.5 py-0.5 text-xs text-[var(--text-primary)] opacity-90 hover:opacity-100 transition-opacity font-mono border border-[var(--border)] rounded bg-[var(--surface)]"
                  >
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
        <h2
          class="text-3xl md:text-4xl font-normal mb-16 text-[var(--text-primary)] cursor-default"
        >
          projects
        </h2>
        <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-12">
          <ProjectCard
            v-for="project in projects"
            :key="project.title"
            :project="project"
          />
        </div>
      </div>
    </section>

    <!-- About -->
    <section id="about" class="px-6 py-24">
      <div class="max-w-4xl mx-auto">
        <h2
          class="text-3xl md:text-4xl font-normal mb-12 text-[var(--text-primary)] cursor-default"
        >
          about
        </h2>
        <div class="glass rounded-2xl p-8 lg:p-10">
          <div class="flex flex-col md:flex-row gap-8 items-start">
            <img
              src="/assets/media/clasei.png"
              alt="clara seijo"
              class="w-32 h-32 rounded-full object-cover flex-shrink-0"
            />
            <div class="flex-1 space-y-6">
              <p class="text-lg text-[var(--text-secondary)] leading-relaxed">
                learning by building and shipping ideas into working systems
              </p>
              <p class="text-lg text-[var(--text-secondary)] leading-relaxed">
                curious about how tech evolves with ai and the integration of
                tools in software development
              </p>
              <p class="text-lg text-[var(--text-secondary)] leading-relaxed">
                writing maintainable code and choosing simple solutions that get
                the job done reliably
              </p>
              <p class="text-lg text-[var(--text-secondary)] leading-relaxed">
                working alongside a talented team at
                <a
                  href="https://www.sngular.com/"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="font-semibold text-[var(--text-primary)] hover:text-[var(--accent)] transition-colors"
                  >Sngular</a
                >
                where building great software is part of the culture
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Terminal -->
    <section id="pragmatic" class="px-6 py-24 bg-[var(--bg)]">
      <div class="max-w-4xl mx-auto">
        <TerminalWindow />
      </div>
    </section>

    <!-- Footer -->
    <footer class="px-6 py-16 border-t border-[var(--border)]">
      <div class="max-w-6xl mx-auto">
        <div
          class="flex flex-col md:flex-row justify-between items-center gap-8"
        >
          <div class="text-[var(--text-secondary)] text-sm">
            2026 · built by @clasei
          </div>
          <div class="flex gap-6 text-sm">
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
const frontendStack = ["html", "css", "javascript", "typescript", "angular", "vue", "react", "design", "ux"];
const backendStack = ["java", "python", "node.js", "express", "sql", "postgresql", "mongodb"];
const toolsStack = ["git", "firebase", "rest-api", "testing", "ci/cd", "docs"];

const projects = [
  {
    title: "sinner",
    description:
      "cli agent turning messy intent into clean professional output",
    impact: "private by design everything runs locally no cloud no accounts",
    keyDecision: "local llm integration via lm studio for complete privacy",
    stack: ["python", "git", "local-llm"],
    imageUrl:
      "https://github.com/user-attachments/assets/106e2d78-0716-413e-9cf0-687bcfa49ac8",
    liveUrl: "https://clasei.github.io/get-sinner",
    repoUrl: "https://github.com/clasei/sinner",
  },
  {
    title: "flowx",
    description:
      "lightweight task tracker with sorting prioritization and clean ui",
    impact: "keeps things simple yet structured with minimal effort",
    keyDecision: "priority ranking system as critical focus or pipeline",
    stack: ["angular", "typescript", "spring", "postgresql"],
    imageUrl:
      "https://github.com/user-attachments/assets/23bd5ad6-8dd6-4e13-86fe-b299d9811af1",
    liveUrl: "https://flowx-woad.vercel.app/",
    repoUrl: "https://github.com/clasei/flowx-client",
  },
  {
    title: "recup",
    description:
      "platform for genuine recommendations cutting through algorithmic noise",
    impact: "highlights valuable content by real users not algorithms",
    keyDecision: "user-centered recommendation system for authentic discovery",
    stack: ["mongodb", "express", "react", "node"],
    imageUrl:
      "https://github.com/user-attachments/assets/9e853706-03fd-4ce8-9257-c2500064e6b7",
    liveUrl: "https://just-recup.netlify.app/",
    repoUrl: "https://github.com/clasei/recup",
  },
  {
    title: "machinsight",
    description: "smart maintenance tracker for industrial machines",
    impact: "streamlines equipment monitoring with csv xlsx data imports",
    keyDecision:
      "fastapi converts data to json for seamless backend integration",
    stack: ["react", "typescript", "node", "fastapi", "python"],
    imageUrl:
      "https://github.com/user-attachments/assets/b54ad98f-d8e9-4c00-8757-a4ceac56aa06",
    repoUrl: "https://github.com/clasei/machinsight-client",
  },
  {
    title: "galactic hitchhiker",
    description: "hitchhikers guide inspired experience delivering wisdom",
    impact: "delivers perspective based on your state of mind",
    keyDecision: "json data structure for dynamic content delivery",
    stack: ["angular", "typescript", "json"],
    imageUrl:
      "https://github.com/user-attachments/assets/e112572b-235b-408f-b3b5-1d46ad6c9873",
    liveUrl: "https://clasei.github.io/galactic-hitchhiker/",
    repoUrl: "https://github.com/clasei/galactic-hitchhiker",
  },
  {
    title: "neutron link",
    description: "spatial simplicity for link sharing",
    impact: "simple and effective tool with spatial awareness",
    keyDecision: "firebase for real time link synchronization",
    stack: ["react", "firebase"],
    imageUrl:
      "https://github.com/user-attachments/assets/764c90e4-494d-4da9-899f-001661a2841f",
    liveUrl: "https://neutron-link-0.web.app/",
    repoUrl: "https://github.com/clasei/neutron-link",
  },
  {
    title: "quantum cookies",
    description:
      "fortune cookies but with actual sense featuring feynman quotes",
    impact: "quick check in app delivering wisdom from richard feynman",
    keyDecision: "json data structure for quote delivery system",
    stack: ["angular", "typescript", "json"],
    imageUrl:
      "https://github.com/user-attachments/assets/3e915c32-9f93-4032-96eb-5e18033e25c9",
    liveUrl: "https://clasei.github.io/quantum-cookies/",
    repoUrl: "https://github.com/clasei/quantum-cookies",
  },
  {
    title: "space time",
    description:
      "interactive visualization of time using physics based animations",
    impact: "time motion and particles in sync for immersive experience",
    keyDecision: "particles js for smooth performant animations",
    stack: ["javascript", "particles.js"],
    imageUrl:
      "https://github.com/user-attachments/assets/f209dca1-86be-4e28-b2f5-27f8bd591ab0",
    liveUrl: "https://clasei.github.io/space-time/",
    repoUrl: "https://github.com/clasei/space-time",
  },
  {
    title: "matter animation",
    description: "bringing physics based animations to life with matter js",
    impact: "simple accessible way to explore physics driven interactions",
    keyDecision: "matter js engine for realistic physics simulations",
    stack: ["javascript", "matter.js"],
    imageUrl:
      "https://github.com/user-attachments/assets/1dd1c216-b97d-4e11-91c6-c2fc4fd5c62b",
    liveUrl: "https://clasei.github.io/matter-animation/",
    repoUrl: "https://github.com/clasei/matter-animation",
  },
];
</script>
