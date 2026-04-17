# Portfolio Site

Vue 3 + TypeScript + Vite + Tailwind CSS で構築したポートフォリオサイトです。

## Tech Stack

- [Vue 3](https://vuejs.org/) — Composition API + `<script setup>`
- [TypeScript](https://www.typescriptlang.org/)
- [Vite](https://vitejs.dev/) — ビルドツール
- [Tailwind CSS v3](https://tailwindcss.com/)
- [GitHub Actions](https://github.com/features/actions) — 自動デプロイ

## ページ構成

| セクション | 内容 |
|---|---|
| Hero | 名前・キャッチコピー |
| About | 自己紹介・スキルバー |
| Works | ミニアプリ紹介 |
| Career | 主要案件タイムライン |
| Links | GitHub リンク |
| Contact | メール問い合わせ |

## Getting Started

```bash
# 依存パッケージのインストール
npm install

# 開発サーバー起動 (http://localhost:5173)
npm run dev

# プロダクションビルド
npm run build

# ビルド結果をプレビュー
npm run preview
```

## GitHub Pages へのデプロイ

`main` ブランチへ push すると GitHub Actions が自動で `gh-pages` ブランチへデプロイします。

### 初回セットアップ

1. リポジトリ名に合わせて `vite.config.ts` の `base` を変更してください。

   ```ts
   // vite.config.ts
   base: '/your-repo-name/',
   ```

2. GitHub リポジトリの **Settings → Pages → Source** を `gh-pages` ブランチに設定してください。

3. `main` ブランチへ push するとデプロイが開始されます。

## カスタマイズ

| ファイル | 変更内容 |
|---|---|
| `src/components/HeroSection.vue` | 名前・キャッチコピー |
| `src/components/AboutSection.vue` | 自己紹介文・スキル |
| `src/components/WorksSection.vue` | 制作物情報・URL |
| `src/components/CareerSection.vue` | 案件情報・Google ドキュメント URL |
| `src/components/LinksSection.vue` | GitHub URL |
| `src/components/ContactSection.vue` | メールアドレス |

## License

MIT
