---
title: 始めましょう
slug: Web/SVG/Tutorial/Getting_Started
tags:
  - Beginner
  - NeedsBeginnerUpdate
  - SVG
  - SVG:Tutorial
  - 初心者
translation_of: Web/SVG/Tutorial/Getting_Started
---
{{ PreviousNext("Web/SVG/Tutorial/Introduction", "Web/SVG/Tutorial/Positions") }}

### 簡単な例

簡単な例で正しく始めましょう。下のコードを見てください。

```xml
<svg version="1.1"
     baseProfile="full"
     width="300" height="200"
     xmlns="http://www.w3.org/2000/svg">

  <rect width="100%" height="100%" fill="red" />

  <circle cx="150" cy="100" r="80" fill="green" />

  <text x="150" y="125" font-size="60" text-anchor="middle" fill="white">SVG</text>

</svg>
```

コードをコピーして、ファイル demo1.svg に貼り付けましょう。そして、ファイルを Firefox で開いてください。これは、下のスクリーンショットを表示するようレンダリングします。(Firefox のユーザは [こちら](svgdemo1.xml) をクリックしてください)

![svgdemo1.png](svgdemo1.png)

レンダリングプロセスは以下のように関わります:

1. {{SVGElement("svg")}} ルート要素から始めます:

    - (X)HTML で知られる DOCTYPE 宣言はつけないようにしましょう。なぜなら DTD に基づく SVG のバリデーションは、解決することよりも多くの問題を引き起こします。
    - 他のタイプのバリデーション向けに SVG のバージョンを指定するためには、代わりに `version` や `baseProfile` 属性を使用するべきです。 `version` と `baseProfile` の両方の属性を付けることは SVG 2 では非推奨です。
    - XML の派生として、 SVG は (xmlns 属性で) 正しい名前空間に結び付けなければなりません。[名前空間の速修講座](/ja/docs/Web/SVG/Namespaces_Crash_Course)に詳細が載っていますのでご覧ください。

2. 画像領域全体を覆う長方形 {{SVGElement("rect")}} を描画することで、背景を赤色にします。
3. 半径が 80px の緑色の円 {{SVGElement("circle")}} を赤色の長方形の中心に描画します (内側に 30+120px、上方に 50+50px のオフセット)。
4. 文字列 "SVG" を描画します。各文字の内側は、白色で塗りつぶします。文字列は、中心点にしたい場所にアンカーを設定することで位置づけられます。この例では、中心点を赤色の長方形の中央と一致させましょう。満足する最終結果を得るように、フォントサイズや上下位置の微調整ができます。

### SVG ファイルの基本特性

- まず注意すべき重要なことは、要素のレンダリング順序です。 SVG ファイルで全体的に正当な規則では、*後の要素*が*前の要素の上に*描画されます。より後にある要素が、より見えるようになるでしょう。
- ウェブ上の SVG ファイルはブラウザーで直接表示したり、いくつかの方法で HTML ファイルに埋め込んだりすることができます。

  - HTML が XHTML で、かつ `application/xhtml+xml` タイプで配信された場合は、 SVG を XML ソース内に直接埋め込むことができます。
  - HTML が HTML5 で、かつブラウザーが HTML5 に対応している場合は、同様に SVG を直接埋め込むことができます。ただし、 HTML5 の仕様に適合するよう文法を変えることが必要でしょう。
  - `object` 要素で SVG ファイルを参照することができます。

    ```
            <object data="image.svg" type="image/svg+xml" />
    ```

  - 同様に `iframe` 要素を使用することができます。

    ```
            <iframe src="image.svg"></iframe>
    ```

  - 理論上は `img` 要素も使用できます。ただし、 Firefox 4.0 より前ではこの方法では動作しません。
  - 最終的に SVG は JavaScript を用いて動的に生成したり、 HTML DOM に挿入したりすることができます。これは SVG を処理できないブラウザー向けの代替技術を実装可能にする利点があります。

  このトピックに関する詳細情報については、[こちらの専門記事](/ja/docs/SVG_In_HTML_Introduction)をご覧ください。

- SVG が寸法や単位を管理する方法については[次のページ](/ja/SVG/Tutorial/Positions)で説明します。

### SVG ファイルの種類

SVG ファイルには 2 つの種類があります。普通の SVG ファイルは、SVG マークアップを含むシンプルなテキストファイルです。このファイルの推奨される拡張子は ".svg" (すべて小文字) です。

SVG ファイルは、一部のアプリケーション (例えば、地理情報アプリケーション) で使用される場合、巨大な大きさに達する可能性があるため、 SVG 仕様書では、 gzip 圧縮された SVG ファイルを使用することも許可しています。これらのファイルに推奨されるファイル名の拡張子は ".svgz" (すべて小文字) です。残念ながら、 Microsoft IIS サーバから提供されている場合、すべての SVG 対応ユーザエージェントで gzip 圧縮された SVG ファイルを確実に動作させるには非常に問題があり、 Firefox は gzip 圧縮された SVG をローカルコンピュータから読み込むことができません。 gzip 圧縮された SVG は、正しくサービスを提供してくれることがわかっているウェブサーバに公開する場合を除いては避けてください (以下を参照)。

### ウェブサーバーについて

さて、基本的な SVG ファイルの作成方法がわかったところで、次の段階はウェブサーバにアップロードすることです。この段階ではいくつかの問題があります。通常の SVG ファイルの場合、サーバーは次の HTTP ヘッダーを送信しなければなりません。

```
Content-Type: image/svg+xml
Vary: Accept-Encoding
```

gzip で圧縮された SVG ファイルの場合は、サーバーは、以下の HTTP ヘッダーを送る必要があります。

```
Content-Type: image/svg+xml
Content-Encoding: gzip
Vary: Accept-Encoding
```

サーバーが SVG ファイルで正しい HTTP ヘッダを送信しているかどうかは、[ネットワークモニターパネル](/ja/docs/Tools/Network_Monitor#Headers) や [websniffer.cc](https://websniffer.cc/) などのサイトを使用して確認できます。 SVG ファイルのうちの 1 つの URL を送信し、 HTTP レスポンスヘッダーを確認します。サーバーが上記の値のヘッダーを送信していないことがわかったら、ウェブホストに連絡してください。 SVG 用のサーバーを正しく設定するように説得しにくい場合は、自分で設定するのも良いかもしれません。簡単な解決策については、 w3.org の[サーバー設定ページ](https://www.w3.org/services/svg-server/)を参照してください。

サーバーの設定ミスは SVG の読み込みに失敗する理由として非常に一般的です。サーバーが正しいヘッダーを SVG ファイルと一緒に送信するように設定されていない場合、 Firefox はファイルのマークアップをテキストや文字化けしたゴミとして表示したり、ビューアにアプリケーションを選択して開くように要求したりする可能性が高いです。

{{ PreviousNext("Web/SVG/Tutorial/Introduction", "Web/SVG/Tutorial/Positions") }}
