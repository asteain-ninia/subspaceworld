# Project「亜空世界」

架空世界「亜空世界」の国家・人物・歴史を記録し、つなげるWikiサイトの実装基盤です。GitHub Pages で公開しつつ、原稿は Obsidian などの外部エディタで執筆し、Pull Request で提出する運用を想定しています。

## 構成

- 原稿とアセット: `content/`
- 画面本体: `index.html`
- 実装コード: `src/`
- 設計資料: `docs/`
- 試作品アーカイブ: `archive/prototypes/`
- 自動テスト: `tests/`

## 実行メモ

- トップページは ES Modules を使っているため、`file://` ではなく `npm run serve` で HTTP 経由起動します
- 既定の起動先は `http://localhost:4173` です
- `content/` の原稿を画面データへ反映するには `npm run build:content` を実行します
- Pages に載せる公開物は `npm run build:site` で `dist/` へ出力します
- 自動テストは `npm test` で実行できます

## GitHub Pages

- デプロイ用ワークフローは [.github/workflows/deploy.yml](.github/workflows/deploy.yml) です
- `main` への push または手動実行で、`build:site` を走らせて GitHub Pages へデプロイします
- リポジトリの `Settings > Pages` で `Source` を `GitHub Actions` に切り替えてください
- 原稿の日付生成で `git log --follow` を使うため、Actions の checkout は履歴を省略しない設定にしています

## ドキュメント

- 仕様たたき台: [docs/spec.md](docs/spec.md)
- 投稿経路: [docs/contribution-workflows.md](docs/contribution-workflows.md)
- 実装アーキテクチャ: [docs/implementation-architecture.md](docs/implementation-architecture.md)
- はじめての記事投稿ガイド: [content/beginner-guide.md](content/beginner-guide.md)
