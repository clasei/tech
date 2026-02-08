<template>
  <button
    @click="toggleTheme"
    class="fixed top-6 right-6 z-50 p-3 glass rounded-xl hover:bg-[var(--surface)] hover:bg-opacity-60 transition-all duration-250 hover:-translate-y-1 hover:scale-105"
    aria-label="Toggle theme"
  >
    <!-- Dark theme icon (moon) -->
    <svg
      v-if="theme === 'dark'"
      class="w-5 h-5 text-[var(--text-primary)]"
      fill="none"
      stroke="currentColor"
      viewBox="0 0 24 24"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="2"
        d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"
      />
    </svg>
    <!-- Light theme icon (sun) -->
    <svg
      v-else-if="theme === 'light'"
      class="w-5 h-5 text-[var(--text-primary)]"
      fill="none"
      stroke="currentColor"
      viewBox="0 0 24 24"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="2"
        d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"
      />
    </svg>
    <!-- Mono theme icon (cube / 3d) -->
    <svg
      v-else
      class="w-5 h-5 text-[var(--text-primary)]"
      fill="none"
      stroke="currentColor"
      viewBox="0 0 24 24"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="2"
        d="M20 7l-8-4-8 4m16 0l-8 4m8-4v10l-8 4m0-10L4 7m8 4v10M4 7v10l8 4"
      />
    </svg>
  </button>
</template>

<script setup lang="ts">
const theme = ref("dark");

onMounted(() => {
  // Check localStorage first, then system preference
  const savedTheme = localStorage.getItem("theme");
  if (savedTheme) {
    theme.value = savedTheme;
  } else if (
    window.matchMedia &&
    window.matchMedia("(prefers-color-scheme: light)").matches
  ) {
    theme.value = "light";
  }
  applyTheme();
});

const applyTheme = () => {
  if (theme.value === "light") {
    document.documentElement.setAttribute("data-theme", "light");
  } else if (theme.value === "mono") {
    document.documentElement.setAttribute("data-theme", "mono");
  } else {
    document.documentElement.removeAttribute("data-theme");
  }
};

const toggleTheme = () => {
  // Cycle through: dark -> light -> mono -> dark
  if (theme.value === "dark") {
    theme.value = "light";
  } else if (theme.value === "light") {
    theme.value = "mono";
  } else {
    theme.value = "dark";
  }
  localStorage.setItem("theme", theme.value);
  applyTheme();
};
</script>
