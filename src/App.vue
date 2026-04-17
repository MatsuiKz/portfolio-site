<script setup lang="ts">
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import WorksSection from './components/WorksSection.vue'
import CareerSection from './components/CareerSection.vue'
import LinksSection from './components/LinksSection.vue'
import ContactSection from './components/ContactSection.vue'
</script>

<template>
  <div class="min-h-screen bg-gray-950 font-sans">
    <NavBar />
    <main>
      <HeroSection />
      <AboutSection />
      <WorksSection />
      <CareerSection />
      <LinksSection />
      <ContactSection />
    </main>
    <footer class="py-6 text-center text-gray-500 text-sm border-t border-gray-800">
      <p>© 2024 Portfolio. Built with Vue 3 + TypeScript + Tailwind CSS.</p>
    </footer>
  </div>
</template>
