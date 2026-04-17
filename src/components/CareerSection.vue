<script setup lang="ts">
interface Career {
  period: string
  title: string
  summary: string
  tags: string[]
  detailUrl?: string
}

const careers: Career[] = [
  {
    period: '2024年〜現在',
    title: '電力取引システムリプレイス',
    summary:
      '電力業界向けの基幹取引システムをモダンスタックでリプレイス。TypeScript / Node.js によるバックエンドAPI設計・実装、PostgreSQL のスキーマ設計・クエリ最適化を担当。',
    tags: ['TypeScript', 'Node.js', 'PostgreSQL', 'REST API'],
    detailUrl: 'https://docs.google.com/document/d/your-doc-id-1',
  },
  {
    period: '2023年〜2024年',
    title: '大手SIer案件対応',
    summary:
      '大手 SIer の業務システム開発プロジェクトに参画。Java を用いたバックエンド開発、Vue.js による SPA フロントエンド開発、Node.js を活用した BFF 層の実装を担当。',
    tags: ['Java', 'Vue.js', 'Node.js', 'Spring Boot'],
    detailUrl: 'https://docs.google.com/document/d/your-doc-id-2',
  },
  {
    period: '2021年〜2023年',
    title: '大手キャリア協業システム開発',
    summary:
      '大手通信キャリアとの協業プロジェクト。Java / PHP による大規模 Web アプリ開発、Shell スクリプトを活用したバッチ処理・運用自動化を担当。',
    tags: ['Java', 'PHP', 'Shell Script', 'Linux'],
    detailUrl: 'https://docs.google.com/document/d/your-doc-id-3',
  },
]
</script>

<template>
  <section id="career" class="py-24 bg-gray-900">
    <div class="max-w-6xl mx-auto section-padding">
      <!-- Header -->
      <div class="mb-16 text-center">
        <p class="text-primary-400 text-xs font-semibold tracking-[0.3em] uppercase mb-2">Career</p>
        <h2 class="text-3xl sm:text-4xl font-bold text-white">主要案件</h2>
        <p class="mt-3 text-gray-500 text-sm">詳細は各案件の「詳細を見る」からご確認ください</p>
      </div>

      <!-- Timeline -->
      <div class="relative">
        <!-- Vertical line -->
        <div class="absolute left-4 md:left-1/2 top-0 bottom-0 w-px bg-gray-800 -translate-x-1/2" />

        <div class="space-y-12">
          <div
            v-for="(career, index) in careers"
            :key="career.title"
            :class="[
              'relative flex flex-col md:flex-row gap-8',
              index % 2 === 0 ? 'md:flex-row' : 'md:flex-row-reverse',
            ]"
          >
            <!-- Dot -->
            <div class="absolute left-4 md:left-1/2 top-1 w-3 h-3 bg-primary-500 rounded-full border-2 border-gray-900 -translate-x-1/2 z-10" />

            <!-- Spacer for alternating layout -->
            <div class="hidden md:block md:w-1/2" />

            <!-- Card -->
            <div class="ml-10 md:ml-0 md:w-1/2 md:px-8">
              <div class="bg-gray-950 border border-gray-800 rounded-xl p-6 hover:border-primary-700/50 transition-colors duration-300">
                <span class="text-xs font-medium text-primary-400 bg-primary-900/30 px-2.5 py-1 rounded-full">
                  {{ career.period }}
                </span>
                <h3 class="text-lg font-bold text-white mt-3 mb-2">{{ career.title }}</h3>
                <p class="text-gray-400 text-sm leading-relaxed mb-4">{{ career.summary }}</p>
                <div class="flex flex-wrap gap-1.5 mb-4">
                  <span
                    v-for="tag in career.tags"
                    :key="tag"
                    class="px-2 py-0.5 bg-gray-800 text-gray-400 text-xs rounded border border-gray-700"
                  >
                    {{ tag }}
                  </span>
                </div>
                <a
                  v-if="career.detailUrl"
                  :href="career.detailUrl"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="inline-flex items-center gap-1.5 text-sm text-primary-400 hover:text-primary-300 transition-colors"
                >
                  詳細を見る（Google ドキュメント）
                  <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
                  </svg>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
