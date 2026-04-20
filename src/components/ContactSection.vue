<script setup lang="ts">
const emailAddress = 'biz.matsuik@gmail.com'
</script>

<template>
  <section id="contact" class="py-24 bg-gray-900">
    <div class="max-w-3xl mx-auto section-padding text-center">
      <!-- Header -->
      <p class="text-primary-400 text-xs font-semibold tracking-[0.3em] uppercase mb-2">Contact</p>
      <h2 class="text-3xl sm:text-4xl font-bold text-white mb-4">お問い合わせ</h2>
      <p class="text-gray-400 leading-relaxed mb-10">
        お仕事のご依頼・ご相談はお気軽にメールでご連絡ください。<br class="hidden sm:inline" />
        通常 2〜3 営業日以内にご返信いたします。
      </p>

      <a
        :href="`mailto:${emailAddress}`"
        class="inline-flex items-center gap-3 px-8 py-4 bg-primary-600 hover:bg-primary-500 text-white font-semibold rounded-xl transition-colors duration-200 shadow-lg shadow-primary-900/40 text-lg"
      >
        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
        </svg>
        メールで問い合わせる
      </a>

      <p class="mt-4 text-gray-600 text-sm">{{ emailAddress }}</p>
    </div>
  </section>
</template>
