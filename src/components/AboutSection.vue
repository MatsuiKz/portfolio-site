<script setup lang="ts">
interface Skill {
  category: string
  items: { name: string; level: number }[]
}

const skills: Skill[] = [
  {
    category: 'Language',
    items: [
      { name: 'Java', level: 90 },
      { name: 'TypeScript / JavaScript', level: 88 },
      { name: 'Node.js', level: 85 },
      { name: 'SQL', level: 82 },
      { name: 'PHP', level: 65 },
      { name: 'Shell Script', level: 60 },
    ],
  },
  {
    category: 'Frontend',
    items: [
      { name: 'Vue.js (2/3)', level: 85 },
      { name: 'HTML / CSS', level: 80 },
      { name: 'Tailwind CSS', level: 75 },
    ],
  },
  {
    category: 'Infra / Cloud',
    items: [
      { name: 'Firebase', level: 80 },
      { name: 'PostgreSQL', level: 78 },
      { name: 'GitHub Actions', level: 70 },
      { name: 'Linux / Docker', level: 65 },
    ],
  },
]

const certifications = [
  '基本情報技術者',
  'Oracle認定 Java SE 7 Silver',
]
</script>

<template>
  <section id="about" class="py-24 bg-gray-900">
    <div class="max-w-6xl mx-auto section-padding">
      <!-- Header -->
      <div class="mb-16 text-center">
        <p class="text-primary-400 text-xs font-semibold tracking-[0.3em] uppercase mb-2">About</p>
        <h2 class="text-3xl sm:text-4xl font-bold text-white">自己紹介</h2>
      </div>

      <div class="grid md:grid-cols-2 gap-12 items-start">
        <!-- Bio -->
        <div>
          <div class="inline-flex items-center gap-2 bg-primary-900/30 border border-primary-700/40 rounded-full px-4 py-1.5 mb-6">
            <span class="w-2 h-2 bg-primary-400 rounded-full animate-pulse" />
            <span class="text-primary-300 text-sm">直近：電力取引システムリプレイス</span>
          </div>

          <h3 class="text-2xl font-bold text-white mb-4">フルスタックエンジニア</h3>

          <p class="text-gray-400 leading-relaxed mb-6">
            システム開発経験約18年。Java・Node.js・TypeScript を中心に、基幹システムから Web アプリ・Firebase を活用したサーバーレス開発まで幅広く担当。
          </p>
          <p class="text-gray-400 leading-relaxed mb-6">
            直近では電力取引システムのリプレイスプロジェクトにて TypeScript / Node.js / PostgreSQL を活用したバックエンド開発に従事。
          </p>

          <!-- Certifications -->
          <div class="mb-6">
            <p class="text-sm font-semibold text-gray-300 mb-3">保有資格</p>
            <ul class="flex flex-wrap gap-2">
              <li
                v-for="cert in certifications"
                :key="cert"
                class="px-3 py-1.5 bg-gray-800 border border-gray-700 text-gray-300 text-sm rounded-md"
              >
                {{ cert }}
              </li>
            </ul>
          </div>

          <!-- Resume -->
          <a
            href="/resume.pdf"
            target="_blank"
            rel="noopener noreferrer"
            class="inline-flex items-center gap-2 px-4 py-2.5 border border-gray-600 hover:border-primary-500 text-gray-300 hover:text-white text-sm font-medium rounded-lg transition-colors duration-200"
          >
            <svg class="w-4 h-4 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 21h10a2 2 0 002-2V9.414a1 1 0 00-.293-.707l-5.414-5.414A1 1 0 0012.586 3H7a2 2 0 00-2 2v14a2 2 0 002 2z" />
            </svg>
            職務経歴書 (PDF)
          </a>
        </div>

        <!-- Skills -->
        <div class="space-y-8">
          <div v-for="skillGroup in skills" :key="skillGroup.category">
            <p class="text-xs font-semibold text-primary-400 tracking-widest uppercase mb-4">
              {{ skillGroup.category }}
            </p>
            <ul class="space-y-3">
              <li v-for="skill in skillGroup.items" :key="skill.name" class="space-y-1">
                <div class="flex justify-between text-sm">
                  <span class="text-gray-300">{{ skill.name }}</span>
                  <span class="text-gray-500">{{ skill.level }}%</span>
                </div>
                <div class="h-1.5 bg-gray-800 rounded-full overflow-hidden">
                  <div
                    class="h-full bg-gradient-to-r from-primary-600 to-primary-400 rounded-full transition-all duration-700"
                    :style="{ width: skill.level + '%' }"
                  />
                </div>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
