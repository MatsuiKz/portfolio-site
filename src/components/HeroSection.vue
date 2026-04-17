<script setup lang="ts">
const roles = ['Fullstack Engineer', 'Backend Specialist', 'Cloud & Firebase Developer']
</script>

<template>
  <section
    id="hero"
    class="relative min-h-screen flex items-center justify-center overflow-hidden bg-gray-950"
  >
    <!-- Background grid -->
    <div
      class="absolute inset-0 opacity-10"
      style="background-image: linear-gradient(rgba(14,165,233,0.3) 1px, transparent 1px), linear-gradient(90deg, rgba(14,165,233,0.3) 1px, transparent 1px); background-size: 60px 60px;"
    />
    <!-- Glow -->
    <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[600px] bg-primary-600/10 rounded-full blur-3xl pointer-events-none" />

    <div class="relative z-10 text-center section-padding animate-fade-in-up">
      <p class="text-primary-400 text-sm font-medium tracking-[0.3em] uppercase mb-4">Welcome to my portfolio</p>

      <h1 class="text-5xl sm:text-6xl md:text-7xl font-bold text-white mb-6 leading-tight">
        Fullstack<br />
        <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary-400 to-cyan-400">Engineer</span>
      </h1>

      <p class="text-gray-400 text-lg sm:text-xl max-w-xl mx-auto mb-4 leading-relaxed">
        Java / Node.js / TypeScript / Vue.js / Firebase<br />
        約 <span class="text-white font-semibold">18年</span> の開発経験
      </p>

      <div class="flex flex-wrap justify-center gap-2 mb-10">
        <span
          v-for="role in roles"
          :key="role"
          class="px-3 py-1 bg-primary-900/40 border border-primary-700/50 text-primary-300 text-xs rounded-full"
        >
          {{ role }}
        </span>
      </div>

      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <a
          href="#works"
          class="px-8 py-3 bg-primary-600 hover:bg-primary-500 text-white font-medium rounded-lg transition-colors duration-200 shadow-lg shadow-primary-900/40"
        >
          Works を見る
        </a>
        <a
          href="#contact"
          class="px-8 py-3 border border-gray-600 hover:border-primary-500 text-gray-300 hover:text-white font-medium rounded-lg transition-colors duration-200"
        >
          お問い合わせ
        </a>
      </div>
    </div>

    <!-- Scroll indicator -->
    <div class="absolute bottom-10 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2 text-gray-600 text-xs">
      <span>Scroll</span>
      <div class="w-px h-8 bg-gradient-to-b from-gray-600 to-transparent animate-pulse" />
    </div>
  </section>
</template>
