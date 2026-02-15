<template>
  <section class="min-h-screen flex items-center justify-center px-6 py-20">
    <div
      class="max-w-6xl w-full grid md:grid-cols-2 gap-16 lg:gap-20 items-center"
    >
      <!-- Left: Info -->
      <div class="space-y-8">
        <div class="select-none">
          <h1
            class="text-4xl md:text-5xl lg:text-6xl font-normal mb-4 text-[var(--text-primary)] opacity-90 tracking-tight cursor-default"
          >
            clara seijo
          </h1>
          <p
            class="text-xl md:text-2xl text-[var(--text-secondary)] mb-1 leading-relaxed cursor-default"
          >
            software developer
          </p>
          <p
            class="text-base md:text-lg text-[var(--text-secondary)] opacity-80 mb-3 leading-relaxed cursor-default"
          >
            pragmatic systems · building blocks
          </p>
          <p class="text-lg font-mono text-[var(--accent)] cursor-default">
            @clasei
          </p>
        </div>

        <div class="flex gap-4 pt-2 pb-6 md:pb-0 flex-wrap">
          <a
            href="https://github.com/clasei"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="GitHub"
            class="icon-link group"
          >
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
              <path
                d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
              />
            </svg>
          </a>
          <a
            href="https://linkedin.com/in/claraseijo"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="LinkedIn"
            class="icon-link group"
          >
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
              <path
                d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
              />
            </svg>
          </a>
          <a
            href="mailto:clasei@proton.me"
            aria-label="Email"
            class="icon-link group"
          >
            <svg
              class="w-5 h-5"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
              stroke-width="2"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
              />
            </svg>
          </a>
        </div>
      </div>

      <!-- Right: Cube -->
      <div class="flex justify-center md:justify-end md:pr-12">
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
  color: var(--text-primary);
  font-weight: 500;
  border-color: rgba(120, 140, 255, 0.5);
  box-shadow:
    0 8px 24px rgba(110, 168, 255, 0.2),
    inset 0 1px 0 rgba(255, 255, 255, 0.15);
  transform: translateY(-2px);
}

.icon-link {
  padding: 0.75rem;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(
    135deg,
    rgba(255, 255, 255, 0.05) 0%,
    rgba(120, 140, 255, 0.05) 100%
  );
  border: 1px solid rgba(120, 140, 255, 0.3);
  border-radius: 9999px;
  color: var(--text-secondary);
  box-shadow:
    0 4px 16px rgba(0, 0, 0, 0.1),
    0 2px 8px rgba(110, 168, 255, 0.1),
    inset 0 1px 0 rgba(255, 255, 255, 0.1),
    inset 0 -1px 0 rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(20px);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  position: relative;
  overflow: hidden;
}

.icon-link::before {
  content: "";
  position: absolute;
  inset: 0;
  border-radius: inherit;
  background: linear-gradient(
    135deg,
    rgba(110, 168, 255, 0) 0%,
    rgba(110, 168, 255, 0.1) 50%,
    rgba(110, 168, 255, 0) 100%
  );
  opacity: 0;
  transition: opacity 0.3s ease;
}

.icon-link:hover::before {
  opacity: 1;
}

.icon-link:hover {
  color: #6ea8ff;
  border-color: rgba(110, 168, 255, 0.6);
  background: linear-gradient(
    135deg,
    rgba(255, 255, 255, 0.08) 0%,
    rgba(120, 140, 255, 0.12) 100%
  );
  box-shadow:
    0 8px 24px rgba(110, 168, 255, 0.25),
    0 4px 12px rgba(110, 168, 255, 0.15),
    inset 0 1px 0 rgba(255, 255, 255, 0.2),
    inset 0 -1px 0 rgba(0, 0, 0, 0.1);
  transform: translateY(-2px);
}

.icon-link:active {
  transform: translateY(0);
  box-shadow:
    0 4px 12px rgba(110, 168, 255, 0.2),
    0 2px 6px rgba(110, 168, 255, 0.1),
    inset 0 1px 0 rgba(255, 255, 255, 0.15);
}
</style>
