# Notebook → App Gallery

データサイエンスの成果物を Notebook で終わらせず、再利用可能な小型アプリへ
変換した例を並べる静的ギャラリー。各例に「Before（Notebook の課題）→
After（アプリ化で改善した点）」を示し、実装リポジトリへリンクする。

## 目的

DS 成果物の公開化（Notebook → App）の流れを見せる。分析をインタラクティブな
アプリに変換することで、比較を並べ・パラメータを動かし・前提と制限を常時表示
できることを示す。

## 主要機能

- 3 つの変換例（Notebook → App）を掲載
  - Case 01: Causal Impact Playground（因果推論・実験設計）
  - Case 02: Forecasting Lab（時系列予測・評価）
  - Case 03: RAG Eval Dashboard（RAG 評価・検索方式比較）
- 各例に Before（Notebook の課題）と After（アプリ化後の改善点）を併記
- 各例から実装リポジトリへリンク
- Lessons Learned: 3 例を通した共通教訓
- ビルド不要の静的サイト（index.html を開けば見られる）

## 使用技術

- 素の HTML / CSS（フレームワークなし・ビルドツールなし）
- 画像は SVG（`assets/`、外部 CDN 依存なし）
- システムフォントスタック（Web フォントの読み込みなし）

## データの出所（公開サンプル）

- 本ギャラリー自体はサンプルデータを持たない（静的表示のみ）
- リンク先の各アプリは合成データまたは公開時系列のみを使用
- 会社案件の Notebook は載せない
- スクリーンショット内の数値・グラフはすべて説明用のプレースホルダであり、
  実在の効果・精度・実績を示すものではない

## ローカルでの開き方

ビルド不要。次のいずれかで開ける。

```bash
# 1) ブラウザで直接開く
open index.html          # macOS
xdg-open index.html      # Linux

# 2) 任意の静的サーバで配信（任意）
python3 -m http.server 8000
# → http://localhost:8000 を開く
```

## スクショ置き場（assets/）

- `assets/hero.svg` — ヒーロー画像（Notebook → App の図）
- `assets/causal-impact.svg` — Case 01 のスクリーンショット（プレースホルダ）
- `assets/forecasting-lab.svg` — Case 02 のスクリーンショット（プレースホルダ）
- `assets/rag-eval.svg` — Case 03 のスクリーンショット（プレースホルダ）

各 SVG は差し替え前提のプレースホルダ。実アプリのスクリーンショットと
差し替える場合は、同じファイル名・同じ viewBox 比（1200x750）で置けば
レイアウトを維持できる。

## デプロイ先（GitHub Pages）

GitHub Pages を想定。ルートに `index.html` がある静的構成なので、
リポジトリの Settings → Pages → Source を `main` / root に設定すれば
そのまま公開できる。ビルドステップは不要。

公開先の想定例:
```
https://<user>.github.io/notebook-to-app-gallery/
```

## 制限事項

- MVP 範囲: 認証 / DB / バックエンド / 課金 / 重量級フレームワークは入れない
- スクリーンショットはプレースホルダ（実アプリの画像への差し替え前提）
- 各実装リポジトリへのリンクは公開先の想定 URL を仮置きしている
- 掲載例は合成/公開データに基づくデモであり、実在の因果効果・予測精度・
  RAG 精度を主張するものではない
- 会社案件の Notebook・秘密情報・個人情報・ライセンス不明の画像は含まない
