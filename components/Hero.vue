<template>
  <section class="min-h-screen flex items-center justify-center px-6 py-20">
    <div class="max-w-6xl w-full grid md:grid-cols-2 gap-16 lg:gap-20 items-center">
      <!-- Left: Info -->
      <div class="space-y-8">
        <div>
          <h1 class="text-4xl md:text-5xl lg:text-6xl font-normal mb-4 text-[var(--text-secondary)] tracking-tight">
            clara seijo
          </h1>
          <p class="text-xl md:text-2xl text-[var(--text-secondary)] mb-3 leading-relaxed">
            software developer · pragmatic systems
          </p>
          <p class="text-lg font-mono text-[var(--accent)]">@clasei</p>
        </div>

        <div class="flex gap-4 pt-2 flex-wrap">
          <a
            href="https://github.com/clasei"
            target="_blank"
            rel="noopener noreferrer"
            class="crystal-link group"
          >
            <span>github</span>
            <svg class="w-4 h-4 group-hover:translate-x-0.5 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
            </svg>
          </a>
          <a
            href="https://linkedin.com/in/claraseijo"
            target="_blank"
            rel="noopener noreferrer"
            class="crystal-link group"
          >
            <span>linkedin</span>
            <svg class="w-4 h-4 group-hover:translate-x-0.5 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
            </svg>
          </a>
          <a
            href="mailto:clasei@proton.me"
            class="crystal-link group"
          >
            <span>email</span>
            <svg class="w-4 h-4 group-hover:translate-x-0.5 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
            </svg>
          </a>
        </div>
      </div>

      <!-- Right: Cube -->
      <div class="flex justify-center md:justify-end md:pr-0">
        <CubeCard />
      </div>
    </div>
  </section>
</template>

<style scoped>
.crystal-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.625rem 1.25rem;
  background: var(--surface);
  border: 1px solid rgba(120, 140, 255, 0.2);
  border-radius: 9999px;
  color: var(--text-secondary);
  box-shadow: 
    0 4px 16px rgba(0, 0, 0, 0.08),
    inset 0 1px 0 rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(20px);
  transition: all 0.25s ease;
}

.crystal-link:hover {
  color: #ffffff;
  border-color: rgba(120, 140, 255, 0.5);
  box-shadow: 
    0 8px 24px rgba(110, 168, 255, 0.2),
    inset 0 1px 0 rgba(255, 255, 255, 0.15);
  transform: translateY(-2px);
}
</style>
