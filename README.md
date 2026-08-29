# パチンコシミュレーター フォーマット

新しいパチンコ機種の疑似遊技シミュレーターを作る際に使う共通フォーマット・仕様テンプレート集。

次に新機種を作りたくなったら、**このリポジトリの `MACHINE-SPEC-TEMPLATE.md` を参照して作ってください**、
とだけ指示すれば、ブレスト・設計をほぼスキップして実装に進められる。

- `MACHINE-SPEC-TEMPLATE.md` — 新機種を作る際に埋める仕様テンプレート。UIシェルの選択（2種類）・
  基本情報・配色パターン集・遊技条件・演出構造・RUSH/LT構造タイプ（カタログ方式）・
  払い出し表（実値/表示値の自動導出式）・演出ON/OFF設定・ヘッダー詳細パネル項目・
  完成後の公開手順（GitHub Pages＋ブログ記事）をこの1ファイルで定義する。

## 使い方

1. `MACHINE-SPEC-TEMPLATE.md` を埋める（機種名・原作・配色・遊技条件・演出構造・RUSH/LT構造・払い出し）
2. 埋めた内容を渡して、セクション0で選んだUIシェルの参照実装をベースに新規プロジェクトを立ち上げる
3. 通常の ブレスト → 設計書 → 実装計画 → 実装 の流れに乗せる（このテンプレートが設計書の大部分を代替する）
4. 実装完了後、テンプレートのセクション8に従ってGitHub Pages公開・ブログ記事(blog.md)作成まで行う

## 参照実装（UIシェル2種類）

- **garo型**: https://github.com/wwi195/pachinko-simulator-garo — ヘッダー3行構成・操作パネル・
  演出ON/OFF設定・モーダルシステム・精算画面・履歴欄。`calc.js`（共通処理）+ `logic.js`（機種固有）の2ファイル構成。
  採用例: `pachinko-simulator-bancho99`
- **ghoul型**: https://github.com/wwi195/pachinko-simulator-ghoul — ステータスバー型ヘッダー・
  状態遷移で画面ごと切り替えるインライン方式。`logic.js`のみ（calc.js相当は無し）。
  採用例: `pachinko-simulator-lycoris`（白ベース）・`pachinko-simulator-oumi5sp`（白+青系）・
  `pachinko-simulator-boukyousei`（黒×赤、ST+保留型RUSH、日またぎ機能、実質/表示出玉表示など最新の実装パターンを多く含む）

どちらを選ぶかの基準・配色パターン集・RUSH/LT構造カタログの詳細は `MACHINE-SPEC-TEMPLATE.md` を参照。
