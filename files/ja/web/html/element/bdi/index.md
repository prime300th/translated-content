---
title: '<bdi>: 書字方向分離要素'
slug: Web/HTML/Element/bdi
tags:
  - BiDi
  - HTML
  - HTML 文字レベルの意味付け
  - HTML:フローコンテンツ
  - HTML:知覚可能コンテンツ
  - HTML:記述コンテンツ
  - Reference
  - i18n
  - ltr
  - rtl
  - ウェブ
  - テキスト
  - リファレンス
  - 右書き
  - 国際化
  - 左書き
  - 書字方向
  - 要素
translation_of: Web/HTML/Element/bdi
---
{{HTMLRef}}

HTML の**書字方向分離要素** (**`<bdi>`**) は、ブラウザーの書字方向アルゴリズムにこのテキストが周囲のテキストから独立していると扱うよう指示します。これは特に、ウェブサイトがテキストを動的に挿入し、挿入されるテキストの書字方向が不明な場合に便利です。

{{EmbedInteractiveExample("pages/tabbed/bdi.html", "tabbed-standard")}}

双方向のテキストとは、文字の並びが左から右 (左書き、LTR) のものと、右から左 (右書き、RTL) のものの両方を含むテキストであり、英語の文字列の中に埋め込まれたアラビア語の引用のようなものです。ブラウザーはこれを扱うために、 [Unicode Bidirectional Algorithm](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics) を実装しています。このアルゴリズムでは、文字には暗黙の書字方向が与えられます。例えば、ラテン文字は左書きとして扱われるのに対し、アラビア文字は右書きとして扱われます。その他の一部の文字 (空白や一部の区切り文字など) は中立として扱われ、周囲の文字に従って書字方向が割り当てられます。

ふつう、書字方向アルゴリズムは特別なマークアップを行わずに正しく動作しますが、時々、アルゴリズムが助けを必要とすることがあります。これが `<bdi>` の出番です。

`<bdi>` 要素はテキストの区間を囲んで、書字方向アルゴリズムにこのテキストが周囲から独立していることを指示します。これは二通りに動作します。

- `<bdi>` で囲まれたテキストの書字方向は、周囲のテキストの書字方向に*影響を与えない*。
- `<bdi>` で囲まれたテキストの書字方向は、周囲のテキストの書字方向から*影響を受けない*。

例えば、以下のようなテキストを想定してください。

```
EMBEDDED-TEXT - 1st place
```

`EMBEDDED-TEXT` が左書きである場合、これは正しく動作します。しかし、 `EMBEDDED-TEXT` が右書きである場合は、 `- 1` は右書きのテキストとして扱われます (中立または弱い文字で構成されているためです)。結果は次のように混乱します。

```
1 - EMBEDDED-TEXTst place
```

さらに、 `EMBEDDED-TEXT` の書字方向が分かる場合は、 {{htmlattrxref("dir")}} 属性のついた {{HTMLElement("span")}} で `EMBEDDED-TEXT` を囲むことでこの問題を修正できます。しかし、書字方向が分からない場合は - 例えば、 `EMBEDDED-TEXT` がデータベースから読み込まれたり、ユーザーに入力されたりするものであれば - `<bdi>` を使用して、 `EMBEDDED-TEXT` の書字方向が周囲に影響されることを防ぐべきです。

同様の視覚効果は、 CSS の {{cssxref("unicode-bidi", "unicode-bidi: isolate")}} を {{HTMLElement("span")}} またはその他の文字書式のための要素に付けることで達成できますが、これは意味が含まれず、ブラウザーは CSS の整形を無視することが許されているので、 HTML ではこのアプローチを使用しないでください。

`<span dir="auto">` に囲まれた文字は、 `<bdi>` を使用するのと同様の効果が得られますが、意味論的には不明確になります。

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/ja/docs/Web/HTML/Content_categories">コンテンツカテゴリ</a>
      </th>
      <td>
        <a href="/ja/docs/Web/HTML/Content_categories#フローコンテンツ"
          >フローコンテンツ</a
        >,
        <a href="/ja/docs/Web/HTML/Content_categories#記述コンテンツ"
          >記述コンテンツ</a
        >, 知覚可能コンテンツ
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている内容</th>
      <td>
        <a href="/ja/docs/Web/HTML/Content_categories#記述コンテンツ"
          >記述コンテンツ</a
        >
      </td>
    </tr>
    <tr>
      <th scope="row">タグの省略</th>
      <td>{{no_tag_omission}}</td>
    </tr>
    <tr>
      <th scope="row">許可されている親要素</th>
      <td>
        <a href="/ja/docs/Web/HTML/Content_categories#記述コンテンツ"
          >記述コンテンツ</a
        >
        を受け入れるすべての要素
      </td>
    </tr>
    <tr>
      <th scope="row">暗黙の ARIA ロール</th>
      <td>
        <a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role"
          >対応するロールなし</a
        >
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている ARIA ロール</th>
      <td>すべて</td>
    </tr>
    <tr>
      <th scope="row">DOM インターフェイス</th>
      <td>{{domxref("HTMLElement")}}</td>
    </tr>
  </tbody>
</table>

## 属性

この要素は、他のすべての HTML 要素と同様に[グローバル属性](/ja/docs/Web/HTML/Global_attributes "HTML/Global attributes")に対応していますが、 **dir** 属性の挙動が普通とは異なります。初期値は `auto` であり、親要素から値を継承しないことを示します。つまり、 `dir` に `rtl` または `ltr` のどちらかの値を指定しない限り、{{Glossary("user agent", "ユーザーエージェント")}}は `<bdi>` の内容に基づいて正しい方向を特定します。

## 例

### \<bdi> がなく左書きのみの場合

この例では、競争の勝者を {{HTMLElement("span")}} のみを使用して列挙しています。名前は左書きのテキストのみが入れば、見栄えが良い結果になります。

```html
<ul>
 <li><span class="name">Henrietta Boffin</span> - 1st place</li>
 <li><span class="name">Jerry Cruncher</span> - 2nd place</li>
</ul>
```

```css hidden
body {
  border: 1px solid #3f87a6;
  max-width: calc(100% - 40px - 6px);
  padding: 20px;
  width: calc(100% - 40px - 6px);
  border-width: 1px 1px 1px 5px;
}
```

{{ EmbedLiveSample('bdi-sample-1','','120','','','bdi-example') }}

### \<bdi> がなく右書きを含むテキストの場合

この例では、競争の勝者を {{HTMLElement("span")}} のみを使用して列挙しており、右書きのテキストから成る名前を含んでいます。この場合、右書きの名前を入れると、書字方向が中立または弱い文字で構成された "`- 1`" の部分は、右書きのテキストの書字方向に合わられ、結果が混乱してしまいます。

```html
<ul>
 <li><span class="name">اَلأَعْشَى</span> - 1st place</li>
 <li><span class="name">Jerry Cruncher</span> - 2nd place</li>
</ul>
```

```css hidden
body {
  border: 1px solid #3f87a6;
  max-width: calc(100% - 40px - 6px);
  padding: 20px;
  width: calc(100% - 40px - 6px);
  border-width: 1px 1px 1px 5px;
}
```

{{ EmbedLiveSample('bdi-sample-2','','120','','','bdi-example') }}

### \<bdi> を使用した左書きと右書きのあるテキストの場合

この例では、競争の勝者を `<bdi>` を使用して列挙しています。これらの要素がブラウザーに、名前を埋め込み先のコンテキストから分離することを指示するので、例の出力は正しく並べられます。

```html
<ul>
 <li><bdi class="name">اَلأَعْشَى</bdi> - 1st place</li>
 <li><bdi class="name">Jerry Cruncher</bdi> - 2nd place</li>
</ul>
```

```css hidden
body {
  border: 1px solid #3f87a6;
  max-width: calc(100% - 40px - 6px);
  padding: 20px;
  width: calc(100% - 40px - 6px);
  border-width: 1px 1px 1px 5px;
}
```

{{ EmbedLiveSample('bdi-sample-3','','120','','','bdi-example') }}

## 仕様書

| 仕様書                                                                                                           | 状態                             | 備考 |
| ---------------------------------------------------------------------------------------------------------------- | -------------------------------- | ---- |
| {{SpecName('HTML WHATWG', 'semantics.html#the-bdi-element', '&lt;bdi&gt;')}}             | {{Spec2('HTML WHATWG')}} |      |
| {{SpecName('HTML5 W3C', 'textlevel-semantics.html#the-bdi-element', '&lt;bdi&gt;')}} | {{Spec2('HTML5 W3C')}}     |      |

## ブラウザーの互換性

{{Compat("html.elements.bdi")}}

## 関連情報

- [Inline markup and bidirectional text in HTML](https://www.w3.org/International/articles/inline-bidi-markup/)
- [Unicode Bidirectional Algorithm basics](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)
- [ローカライズと国際化](/ja/docs/Web/Localization)
- 関連 HTML 要素: {{HTMLElement("bdo")}}
- 関連 CSS プロパティ: {{cssxref("direction")}}, {{cssxref("unicode-bidi")}}
