<script setup lang="ts">
interface Career {
  period: string
  title: string
  summary: string
  tags: string[]
  detailUrl?: string
  type: 'freelance' | 'employee'
}

const freelanceCareers: Career[] = [
  {
    period: '2025年10月〜2026年3月',
    title: '動画配信サービス保守',
    summary:
      '動画配信サービスのインフラ刷新・長期安定化を担当。AWS（ECS / EC2）移行設計・構築、Java バージョンアップ対応、JMeter を用いた性能試験・長期安定化試験を実施。',
    tags: ['Java', 'Spring Boot', 'Shell', 'AWS', 'Docker', 'JMeter'],
    type: 'freelance',
  },
  {
    period: '2024年5月〜2025年9月',
    title: '電力取引システムリプレイス',
    summary:
      '電力業界向け基幹取引システムのバックエンドを新規構築。GitHub Copilot を活用した開発効率化により Jest テストカバレッジ 100% を維持しながら設計・実装を推進。',
    tags: ['TypeScript', 'Node.js', 'PostgreSQL', 'Jest'],
    type: 'freelance',
  },
  {
    period: '2023年8月〜2024年1月',
    title: '大手SI企業内 複数PJ支援',
    summary:
      '大手 SIer 内の複数プロジェクトを横断支援。Vue.js / Node.js を短期習得してフロントエンド・BFF 開発に参画。テストスケジュールの課題を分析し改善提案を主導。',
    tags: ['Java', 'Vue.js', 'Node.js', 'PHP', 'PostgreSQL'],
    type: 'freelance',
  },
]

const employeeCareers: Career[] = [
  {
    period: '2018年4月〜2023年5月',
    title: '情報配信サービス開発・保守',
    summary:
      '情報配信サービスの開発・保守に長期従事。iOS アプリ開発（Swift）、大手通信キャリア向けバッチ処理の設計〜リリースまで一貫して担当。',
    tags: ['Java', 'Swift', 'PHP', 'Laravel', 'Oracle'],
    type: 'employee',
  },
  {
    period: '2009年9月〜2018年3月',
    title: '受託開発・SE（リーダー経験）',
    summary:
      '受託開発 SE としてチームリーダーを経験。Oracle SQL チューニングにより処理時間を 7 秒→3 秒に改善。新卒エンジニア向け教育スキームの構築・運用も担当。',
    tags: ['Java', 'Oracle', 'Spring'],
    type: 'employee',
  },
]
</script>

<template>
  <section id="career" class="py-24 bg-gray-900">
    <div class="max-w-5xl mx-auto section-padding">
      <!-- Header -->
      <div class="mb-16 text-center">
        <p class="text-primary-400 text-xs font-semibold tracking-[0.3em] uppercase mb-2">Career</p>
        <h2 class="text-3xl sm:text-4xl font-bold text-white">主要案件</h2>
      </div>

      <!-- Freelance -->
      <div class="mb-16">
        <div class="flex items-center gap-3 mb-8">
          <span class="px-3 py-1 bg-primary-900/40 border border-primary-700/50 text-primary-300 text-xs font-semibold rounded-full tracking-widest uppercase">
            Freelance
          </span>
          <div class="flex-1 h-px bg-gray-800" />
        </div>

        <div class="relative pl-6 border-l border-gray-800 space-y-6">
          <div
            v-for="career in freelanceCareers"
            :key="career.title"
            class="relative"
          >
            <div class="absolute -left-[25px] top-1.5 w-3 h-3 bg-primary-500 rounded-full border-2 border-gray-900" />
            <div class="bg-gray-950 border border-gray-800 rounded-xl p-5 hover:border-primary-700/50 transition-colors duration-300">
              <span class="text-xs font-medium text-primary-400 bg-primary-900/30 px-2.5 py-1 rounded-full">
                {{ career.period }}
              </span>
              <h3 class="text-base font-bold text-white mt-3 mb-1.5">{{ career.title }}</h3>
              <p class="text-gray-400 text-sm leading-relaxed mb-3">{{ career.summary }}</p>
              <div class="flex flex-wrap gap-1.5">
                <span
                  v-for="tag in career.tags"
                  :key="tag"
                  class="px-2 py-0.5 bg-gray-800 text-gray-400 text-xs rounded border border-gray-700"
                >
                  {{ tag }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Employee -->
      <div>
        <div class="flex items-center gap-3 mb-8">
          <span class="px-3 py-1 bg-gray-700/50 border border-gray-600/50 text-gray-400 text-xs font-semibold rounded-full tracking-widest uppercase">
            Employee
          </span>
          <div class="flex-1 h-px bg-gray-800" />
        </div>

        <div class="relative pl-6 border-l border-gray-800 space-y-6">
          <div
            v-for="career in employeeCareers"
            :key="career.title"
            class="relative"
          >
            <div class="absolute -left-[25px] top-1.5 w-3 h-3 bg-gray-600 rounded-full border-2 border-gray-900" />
            <div class="bg-gray-950 border border-gray-800 rounded-xl p-5 hover:border-gray-700 transition-colors duration-300">
              <span class="text-xs font-medium text-gray-400 bg-gray-800 px-2.5 py-1 rounded-full">
                {{ career.period }}
              </span>
              <h3 class="text-base font-bold text-white mt-3 mb-1.5">{{ career.title }}</h3>
              <p class="text-gray-400 text-sm leading-relaxed mb-3">{{ career.summary }}</p>
              <div class="flex flex-wrap gap-1.5">
                <span
                  v-for="tag in career.tags"
                  :key="tag"
                  class="px-2 py-0.5 bg-gray-800 text-gray-400 text-xs rounded border border-gray-700"
                >
                  {{ tag }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
