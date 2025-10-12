# スライド資料

このリポジトリには、私が各種イベントで発表に使用したスライド資料を保存しています。

## 技術スタック

- **[Marp](https://marp.app/)**: Markdown Presentation Ecosystem - Markdownでスライド資料を作成できるツール
- **カスタムCSSテーマ**: カバー、セクション、コンテンツ用の専用スタイリングを持つ「lt」テーマ
- **日本語対応**: すべてのスライドは日本語で作成されています

## ディレクトリ構造

スライドは日付とイベント名でディレクトリを整理しています：

- `20250823_pyhack/`: PyHack イベント用スライド
- `20250827_AI コーディングAgent 活用LT会/`: AI コーディングAgent 活用LT会用スライド
- `20250829_水道橋 BeerBash/`: 水道橋 BeerBash 用スライド
- `20251011_情報科学若手の会/`: 情報科学若手の会用スライド
- `cheatsheet/`: Marp使用例やテンプレート
- `images/`: 共通画像アセット
- `styles/`: カスタムMarpテーマ
- `old/`: 古いディレクトリ構造のアーカイブ

各イベントディレクトリには以下が含まれます：
- `.md`ファイル: Markdownスライド
- `.pdf`ファイル: 生成されたPDF
- 画像ファイル: そのスライド専用の画像

## セットアップ

### 必要な環境

- [Visual Studio Code](https://code.visualstudio.com/)
- [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) (VS Codeの拡張機能)

### インストール手順

1. VS Codeをインストール
2. VS Codeの拡張機能から「Marp for VS Code」をインストール
3. このリポジトリをクローン
```bash
git clone https://github.com/eycjur/slides.git
cd slides
```

### PDFの生成

1. VS Codeでスライドファイル（`.md`）を開く
2. Marp拡張機能のプレビューを表示（`Ctrl+K V` または `Cmd+K V`）
3. プレビュー画面右上の「Export Slide Deck」ボタンからPDF形式でエクスポート

または、コマンドパレット（`Ctrl+Shift+P` / `Cmd+Shift+P`）から「Marp: Export Slide Deck」を実行

## 使い方

### 基本設定

スライドファイルの先頭に以下のフロントマターを記述します：

```yaml
---
marp: true
lang: ja
theme: lt
size: 16:9
math: katex
title: "スライドタイトル"
paginate: true
---
```

### 利用可能なCSSクラス

カスタム「lt」テーマでは以下の専用スライドクラスが利用できます：

#### `cover` - カバースライド
```markdown
<!-- _class: cover -->
<!-- _paginate: false -->

# スライドタイトル

##### サブタイトル

2025年1月1日 イベント名
発表者名
```

#### `toc` - 目次スライド
```markdown
<!-- _class: toc -->

## 目次
1. [セクション1](#セクション1)
2. [セクション2](#セクション2)
```

#### `section_title` - セクション区切りスライド
```markdown
<!-- _class: section_title -->

## 1. セクションタイトル
```

#### `full_screen` - 全画面表示スライド
```markdown
<!-- _class: full_screen -->

# <!--fit--> 強調したいメッセージ
```

#### `appendix` - 付録スライド
```markdown
<!-- _class: appendix -->

## Appendix
```

#### `back_cover` - 終了スライド
```markdown
<!-- _class: back_cover -->

## Thank you!
```

### その他の便利なテクニック

#### 文字サイズを変更する
```markdown
<!-- _class: leading-tight -->
<!-- _class: leading-snug -->
<!-- _class: leading-normal -->
<!-- _class: leading-relaxed -->
<!-- _class: leading-loose -->
```

#### 分量が多い場合に自動でフォントサイズを調整する
```markdown
<!-- _class: auto-fit -->
```

#### 2段組にする
```markdown
<div class="column">
<div>
左側のテキスト
</div>
<div>
右側のテキスト
</div>
</div>
```

#### 中央揃えにする
```markdown
<div class="center">
中央揃えのテキスト
</div>
```

#### 画像サイズを指定する
```markdown
![h:400px](image.png)
```

#### 画像を指定した位置に配置する
```markdown
<style scoped>
.image {
  position: absolute;
  top: 120px;
  right: 50px;
}
</style>

<div class="image">

![h:150](image.png)

</div>
```

#### 空白を入れる
```markdown
<br>

<div class="space-xs"></div>
<div class="space-sm"></div>
<div class="space-base"></div>
<div class="space-lg"></div>
<div class="space-xl"></div>
<div class="space-2xl"></div>
```

#### 数式を記述する
```markdown
$$
e^{i\pi} + 1 = 0
$$
```

詳細な使用例は [`cheatsheet/cheatsheet.md`](cheatsheet/cheatsheet.md) を参照してください。

## カスタムテーマについて

このリポジトリでは `styles/lt.css` にカスタムテーマを定義しています。以下の特徴があります：

- 日本語フォントに最適化されたスタイリング
- LT（Lightning Talk）向けのシンプルで視認性の高いデザイン
- 複数のスライドタイプ（カバー、セクション、目次など）のサポート
- レスポンシブな画像配置とレイアウトオプション

### 注意事項

権利の都合上、以下の背景画像ファイルはリポジトリに含まれていません：

- `images/back_cover.jpg`
- `images/cover.jpg`
- `images/section_title.jpg`
- `images/appendix.jpg`

これらのファイルは各スライドクラス（`cover`, `section_title`, `appendix`, `back_cover`）で背景画像として使用されます。ご自身でスライドを作成する際は、適切な背景画像を用意してください。

## リンク

- [Marp公式サイト](https://marp.app/)
- [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)
