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

## 職務経歴書PDFの更新

About セクションからリンクしている職務経歴書は `public/resume.pdf` です。更新手順は以下のとおり。

1. 新しいPDFを `public/resume.pdf` に上書きコピーする（**ファイル名は `resume.pdf` のまま固定**）。

   ```bash
   cp /path/to/新しい職務経歴書.pdf public/resume.pdf
   ```

2. コミットして `main` へ push する。

   ```bash
   git add public/resume.pdf
   git commit -m "職務経歴書PDFを更新"
   git push origin main
   ```

3. push により GitHub Actions が動き、数分後に公開サイトへ反映される。

> - ファイル名を変えると `AboutSection.vue`（`${import.meta.env.BASE_URL}resume.pdf` で参照）がリンク切れになるので変更しないこと。
> - `public/` 配下はそのまま `dist/` にコピーされるため、ビルド設定の変更は不要。

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
