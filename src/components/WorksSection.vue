<script setup lang="ts">
interface Work {
  title: string
  description: string
  tags: string[]
  url: string
  github?: string
  status: 'live' | 'wip'
}

const works: Work[] = [
  {
    title: 'Note App',
    description:
      'Vue 3 + TypeScript + Firebase で構築したシンプルなノートアプリ。Firestore によるリアルタイムデータ同期、Firebase Auth による認証、Hosting でのデプロイを実装。',
    tags: ['Vue 3', 'TypeScript', 'Firebase', 'Firestore', 'Tailwind CSS'],
    url: 'https://note-app-test-2b9e5.web.app/',
    status: 'live',
  },
]
</script>

<template>
  <section id="works" class="py-24 bg-gray-950">
    <div class="max-w-6xl mx-auto section-padding">
      <!-- Header -->
      <div class="mb-16 text-center">
        <p class="text-primary-400 text-xs font-semibold tracking-[0.3em] uppercase mb-2">Works</p>
        <h2 class="text-3xl sm:text-4xl font-bold text-white">制作物</h2>
      </div>

      <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <article
          v-for="work in works"
          :key="work.title"
          class="group bg-gray-900 border border-gray-800 rounded-xl overflow-hidden hover:border-primary-700/60 transition-all duration-300 hover:-translate-y-1 hover:shadow-xl hover:shadow-primary-900/20"
        >
          <!-- Card header -->
          <div class="h-36 bg-gradient-to-br from-primary-900/40 to-gray-800 flex items-center justify-center relative overflow-hidden">
            <div class="text-5xl font-black text-primary-800/40 select-none">N</div>
            <div class="absolute inset-0 flex items-center justify-center">
              <span class="text-4xl">📝</span>
            </div>
            <span
              :class="[
                'absolute top-3 right-3 text-xs font-medium px-2 py-0.5 rounded-full',
                work.status === 'live'
                  ? 'bg-green-900/60 text-green-400 border border-green-700/40'
                  : 'bg-yellow-900/60 text-yellow-400 border border-yellow-700/40',
              ]"
            >
              {{ work.status === 'live' ? '● Live' : '⚙ WIP' }}
            </span>
          </div>

          <div class="p-6">
            <h3 class="text-lg font-bold text-white mb-2">{{ work.title }}</h3>
            <p class="text-gray-400 text-sm leading-relaxed mb-4">{{ work.description }}</p>

            <div class="flex flex-wrap gap-1.5 mb-5">
              <span
                v-for="tag in work.tags"
                :key="tag"
                class="px-2 py-0.5 bg-gray-800 text-gray-400 text-xs rounded-md border border-gray-700"
              >
                {{ tag }}
              </span>
            </div>

            <div class="flex gap-3">
              <a
                :href="work.url"
                target="_blank"
                rel="noopener noreferrer"
                class="flex-1 text-center py-2 bg-primary-700 hover:bg-primary-600 text-white text-sm rounded-lg transition-colors"
              >
                アプリを見る →
              </a>
            </div>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>
