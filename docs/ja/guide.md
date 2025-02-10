# テーマの使い方

## 使い始める
Theme Academic PP を使うには通常のVivliostyleの作成手順を元にします。  
Vivliostyle公式の[チュートリアル](https://vivliostyle.org/ja/tutorials/)を主には参考に作成してください。

`Create Book`を用いて出版物の雛形を作ります。choose themeのテーマの選択部分で`vivliostyle-theme-academic-pp`を選択します。  
するとTheme Academic PP を用いた出版物を作成することができます。以降はチュートリアルに従って原稿を作成してください。

## 機能たち

Theme Academic PP は @vivliostyle/theme-academic を元に作成しているので @vivliostyle/theme-academic 由来の機能と Theme Academic PP 独自の機能で構成されています。  
基本的にはどちらの機能も使用することができます。

@vivliostyle/theme-academic 由来の機能については以下の @vivliostyle/theme-academic 作者の記事を参照してください。  
[@vivliostyle/theme-academic でレポート書いてみた！](https://vivliostyle.github.io/vivliostyle_doc/ja/vivliostyle-user-group-vol4/artifacts/content/yamasy/index.html)

Theme Academic PP 独自の機能として以下のような機能があります。

- 段組設定
- 画像の並列配置
- 概要表示
- キーワード表示
- フォント選択
- コンパクトモード

### 段組設定
1段組(標準)と2段組の選択をできます。2段組とは文章等を縦方向に2つの団に分割してレイアウトする組版形式です。  

![2段組サンプル](../_img/2columns.png ':size=900')

2段組にする場合、原稿のMarkdownファイルの先頭にYAMLフロントマターを以下のように追加します。1段組の場合は無記述または`column: '1'`を設定してください。

```md
---
body:
  column: '2'
---
```

2段組設定にした際、[概要](ja/guide?id=概要表示)や[キーワード](ja/guide?id=キーワード表示)部分については段組から外され、紙面横幅いっぱいに広がって表示されます。  
また`column-span`という名前のclassを付与すれば、その要素は段組から除外されます。

```md
<div class="column-span">

この文章部分は段組から除外されます。

</div>
```

### 画像の並列配置
複数の画像を並列に配置することができます。

以下のようにclass名が`image-row`のdiv要素内に任意の数の画像を表示させます。このとき、divタグと画像タグの間には1行ずつ間隔を開ける必要があります。

```md
<div class="image-row">

![](画像リンク1)

![](画像リンク2)

</div>
```

?>並列配置する画像枚数に制限はありませんが、画像サイズに応じて2, 3枚を推奨します。

### 概要表示
原稿の概要を記述することができます。

![概要表示サンプル](../_img/abstract-keywords.png ':size=600')

以下のようにclass名が`abstract`のdiv要素内に原稿の概要を記述します。このとき、divタグと文章の間には1行間隔をあける必要があります。

```md
<div class="abstract">

ここに原稿の概要を記述します。。。。。。。

</div>

```

また概要部分のタイトルのカスタマイズもYAMLフロントマターによって設定できます。以下のようにYAMLフロントマターを追加してください。  

```md
---
html:
  abstract-title: 'true'
---
```

設定可能な値は以下の通りです。

|値|タイトル表示有無|言語|備考|
|---|---|---|---|
|true|あり|原稿設定に基づく|初期値|
|false|なし|||
|en|あり|英語||
|ja|あり|日本語||

### キーワード表示
原稿のキーワードを記述することができます。

![キーワード表示サンプル](../_img/abstract-keywords.png ':size=600')

以下のようにclass名が`keywords`のdiv要素内にキーワードを記述します。このとき、divタグとキーワードの間には1行間隔をあける必要があります。

```md

<div class="keywords">

**太字キーワード1**, **太字キーワード2**, キーワード3, キーワード4

</div>

```

例のように`**`で文字を囲むと太字になります。またKEY WORDSという文字の変更はできません。

### コンパクトモード
文章全体をコンパクトにまとめ、紙面の使用量を減らすことができます。本文や見出しの文字サイズを小さくします。

コンパクトモードを有効にするにはYAMLフロントマターで以下のように設定します。  
設定可能な値はtrueとfalseです。初期値はfalse。

```md
---
html:
  compact-text: 'true'
---
```

### フォント設定
見出しに使用されるフォントの種類を設定できます。

YAMLフロントマターで以下のように設定します。  
設定可能な値はゴシック体と明朝体で、それぞれ`sans-serif`と`serif`と設定します。初期値は`sans-serif`です。

```md
---
html:
  section-font: 'serif'
---
```