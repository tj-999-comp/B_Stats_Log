# Issue_ex_001
作成日: 2026-05-26

## 概要
VS Code で Supabase (PostgreSQL) へ接続し、SQLTools でクエリ実行できる状態を整備した。

## 実施内容
- SQLTools 本体と PostgreSQL ドライバの起動・接続状態のログを確認した。
- 接続失敗時の原因を切り分けた。
  - `Password is required`（接続情報に DB パスワード未設定）
  - `self signed certificate in certificate chain`（SSL 検証設定の不一致）
- SQLTools 側の接続設定を見直し、接続状態（緑点、Disconnect 表示、ツリー取得）を確認した。
- クエリ実行導線を整理し、`Run Query` の実行経路（入力実行とエディタ実行）を案内した。
- ユーザーの `keybindings.json` を更新し、`cmd+enter` で SQLTools のエディタ実行を優先する設定を追加した。

## 確認結果
- Supabase DB への接続は成功。
- `Run Query` によるクエリ実行が可能な状態まで到達。

## 備考
- SQL ファイル管理方針（`queries/` 配下で管理）で運用可能。
- 次フェーズはスキーマ SQL の整備（テーブル定義・制約・インデックス）を推奨。
