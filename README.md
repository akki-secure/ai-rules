# 🤖 ai-rules

![License](https://img.shields.io/badge/license-MIT-blue)
![Made for](https://img.shields.io/badge/Made%20for-Claude%20Code-orange)
![Compatible](https://img.shields.io/badge/Compatible-Gemini-4285F4)
![Status](https://img.shields.io/badge/status-template-lightgrey)

Claude Code / Gemini などのAIコーディングエージェントに開発を任せる際に、
共通して守らせたいルールをまとめたテンプレートリポジトリです。

詳細なテンプレート本文は [AI_AGENT_RULES_TEMPLATE.md](./AI_AGENT_RULES_TEMPLATE.md) を参照してください。
`{ }` で囲まれたプレースホルダーを自分のプロジェクトに合わせて書き換えて使用します。

## 📋 ルール項目の目次

1. 要件定義書の作成(ask)→ ブラウザで動く静的モックプロトタイプで確認 → 要件定義書専用mdファイルの作成
2. 開発フロー(Plan Mode): バックエンド→フロントエンド→ガードレール(破壊的操作禁止)+ ログ設計 → 自動テスト → パフォーマンステスト(手動・別枠)
3. 不明な用語があれば必ずユーザーに質問する
4. README.mdとは別のMarkdownファイルに保存する
5. 動作確認前の品質チェック(静的解析)、SQLデータ保護、自動テスト実行(30分以上かかる場合はフリーズを疑い確認)
6. mainブランチはユーザーが作成、AIは別ブランチを作成してpush(mainへの直接pushは禁止)、最初のコミット前に`.gitignore`とLICENSEを整備
7. 完了時の感謝の一言で締めくくる
8. 次の段階に進む前にClaude Codeのセッションを開き直す
9. skillsと`.claude/commands/`フォルダを作成し、`/コマンド`で操作(パフォーマンステスト用の`/performance-test`など)
10. 全体の品質チェックを複数回実施(SQLはXML管理、画像は見るまで断定しない)
11. 最後に自動テストを再実行
12. README.mdに遷移図・モック・ER図・API仕様書を必ず追記し、機能追加のたびに更新
13. 作ったプロジェクトについてAIからユーザーへ質問してもらう
14. デプロイはユーザー確認後、Terraform + AWS等で実行
15. リソース削除前にデータ・ログをバックアップし、確認後に`terraform destroy`

## 📄 ライセンス

このリポジトリは[MITライセンス](./LICENSE)で公開しています。
日本語の参考訳(非公式・法的効力なし)は[LICENSE.ja.md](./LICENSE.ja.md)を参照してください。

## 🚀 使い方

1. このリポジトリをテンプレートとして新しいプロジェクトにコピーする、または `AI_AGENT_RULES_TEMPLATE.md` の内容をプロジェクトのCLAUDE.md等に転記する。
2. プレースホルダー(`{アプリ名}` など)を実際の値に置き換える。
3. AIエージェントとの作業開始時に、このルールを読み込ませてから進める。
