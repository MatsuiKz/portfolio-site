<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMenuOpen = ref(false)

const navItems = [
  { label: 'About', href: '#about' },
  { label: 'Works', href: '#works' },
  { label: 'Career', href: '#career' },
  { label: 'Links', href: '#links' },
  { label: 'Contact', href: '#contact' },
]

function handleScroll() {
  isScrolled.value = window.scrollY > 40
}

function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value
}

function closeMenu() {
  isMenuOpen.value = false
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<template>
  <header
    :class="[
      'fixed top-0 left-0 right-0 z-50 transition-all duration-300',
      isScrolled
        ? 'bg-gray-950/95 backdrop-blur-sm shadow-lg shadow-black/20 border-b border-gray-800'
        : 'bg-transparent',
    ]"
  >
    <nav class="max-w-6xl mx-auto px-4 sm:px-8 h-16 flex items-center justify-between">
      <a href="#" class="text-lg font-bold text-primary-400 tracking-wider">&lt;/&gt; Portfolio</a>

      <!-- Desktop nav -->
      <ul class="hidden md:flex items-center gap-8">
        <li v-for="item in navItems" :key="item.href">
          <a
            :href="item.href"
            class="text-sm text-gray-300 hover:text-primary-400 transition-colors duration-200 font-medium"
          >
            {{ item.label }}
          </a>
        </li>
      </ul>

      <!-- Mobile hamburger -->
      <button
        class="md:hidden p-2 text-gray-300 hover:text-white"
        aria-label="メニューを開く"
        @click="toggleMenu"
      >
        <svg v-if="!isMenuOpen" class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
        <svg v-else class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>
    </nav>

    <!-- Mobile menu -->
    <Transition
      enter-active-class="transition-all duration-200 ease-out"
      enter-from-class="opacity-0 -translate-y-2"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition-all duration-150 ease-in"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-2"
    >
      <div v-if="isMenuOpen" class="md:hidden bg-gray-900 border-b border-gray-800">
        <ul class="flex flex-col py-2">
          <li v-for="item in navItems" :key="item.href">
            <a
              :href="item.href"
              class="block px-6 py-3 text-gray-300 hover:text-primary-400 hover:bg-gray-800 transition-colors"
              @click="closeMenu"
            >
              {{ item.label }}
            </a>
          </li>
        </ul>
      </div>
    </Transition>
  </header>
</template>
