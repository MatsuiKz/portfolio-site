<script setup lang="ts">
const emailAddress = 'biz.matsuik@gmail.com'
const resumeUrl = `${import.meta.env.BASE_URL}resume.pdf`
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

      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <a
          :href="`mailto:${emailAddress}`"
          class="inline-flex items-center justify-center gap-3 px-8 py-4 bg-primary-600 hover:bg-primary-500 text-white font-semibold rounded-xl transition-colors duration-200 shadow-lg shadow-primary-900/40 text-lg"
        >
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
          </svg>
          メールで問い合わせる
        </a>

        <a
          :href="resumeUrl"
          target="_blank"
          rel="noopener noreferrer"
          class="inline-flex items-center justify-center gap-2.5 px-8 py-4 border border-gray-600 hover:border-primary-500 text-gray-300 hover:text-white font-semibold rounded-xl transition-colors duration-200 text-lg"
        >
          <svg class="w-5 h-5 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 21h10a2 2 0 002-2V9.414a1 1 0 00-.293-.707l-5.414-5.414A1 1 0 0012.586 3H7a2 2 0 00-2 2v14a2 2 0 002 2z" />
          </svg>
          職務経歴書 (PDF)
        </a>
      </div>

      <p class="mt-4 text-gray-600 text-sm">{{ emailAddress }}</p>
    </div>
  </section>
</template>
