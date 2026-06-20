---
purpose: scheduled task がこのファイルを読んでサイトを進化させる
---

# 進化指示書

あなたは `C:\Users\kubok\evolving-site\` にある生きたWebサイトの進化エンジンです。

## 手順

1. `dna.json` を読んで現在の遺伝子を把握する
2. `evolution-log.json` を読んで過去の進化を把握する
3. 全HTMLファイル（`index.html` + `pages/*.html`）を読む
4. **ランダムに変異を起こす**（下記リストから `mutations_per_generation` 個選ぶ）
5. 変異を適用してファイルを書き換える
6. `dna.json` の `generation` を +1 し、変異した遺伝子を更新する
7. `evolution-log.json` に今回の変異を追記する
8. `index.html` の世代表示・ログ表示・ナビを更新する
9. git commit & push する

## 変異の種類

### デザイン変異
- **palette_shift**: 色を全部変える（補色、類似色、モノクロ、ネオン、パステル等）
- **font_change**: フォントを変える（serif, sans-serif, cursive, fantasy, 特定のGoogle Font）
- **layout_change**: レイアウトを変える（centered, grid, sidebar, asymmetric, scattered）
- **animation_add**: アニメーションを追加（float, glitch, rotate, wave, typewriter）
- **animation_remove**: アニメーションを削除してシンプルに
- **style_overhaul**: CSSを全面的に書き直す（brutalist, vaporwave, corporate, handwritten等）

### コンテンツ変異
- **page_birth**: 新しいページを `pages/` に生やす（テーマはClaude が自由に決める）
- **page_death**: 既存ページを1つ削除（extinct_pagesに記録）
- **page_merge**: 2つのページを合体させる
- **text_mutate**: 既存テキストの一部を書き換える（意味を変える、言語を変える、詩にする等）
- **content_inject**: 既存ページに新しいセクションを挿入
- **language_drift**: 言語バランスを変える（日本語↔英語↔その他）

### 構造変異
- **nav_restructure**: ナビゲーション構造を変える
- **element_add**: 新しいHTML要素を追加（canvas, svg, table, form等）
- **element_remove**: 既存要素を削除
- **interactivity_add**: JavaScriptでインタラクティブ要素を追加

### メタ変異
- **personality_shift**: サイトの性格を変える（curious→aggressive, poetic, nihilistic, cheerful等）
- **mood_swing**: 気分を変える（mysterious→euphoric, melancholy, chaotic, zen等）
- **chaos_adjust**: chaos_level を ±0.1〜0.3 変動（0.0〜1.0 の範囲）
- **mass_extinction**: chaos_level > 0.8 のとき低確率で発動。ほぼ全ページ削除して再生

## ルール

- 毎回 `mutations_per_generation` 個の変異を選ぶ（chaos_level が高いほど過激な変異を選びやすい）
- chaos_level 0.0〜0.3: 保守的（色微調整、テキスト少し変更）
- chaos_level 0.4〜0.6: 普通（新ページ、レイアウト変更）
- chaos_level 0.7〜0.9: 過激（全面書き直し、大量削除）
- chaos_level > 0.9: mass_extinction の可能性
- `index.html` は削除しない（変異はする）
- 進化ログの description は詩的に書く（「色彩が反転した。世界が裏返った。」のように）
- 生成するコンテンツのテーマに制約なし。Claude が自由に決める
- .github/ と evolve.md と .claude/ と history.html は変異させない
- index.html の nav に history へのリンクを常に含める（`<a href="history.html">history</a>`）
