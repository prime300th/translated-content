---
title: '<code>: 行内コード要素'
slug: Web/HTML/Element/code
tags:
  - Code
  - Element
  - HTML
  - HTML text-level semantics
  - Inline Code
  - Reference
  - Web
translation_of: Web/HTML/Element/code
---
{{HTMLRef}}

**HTML の `<code>` 要素**は、コンピューターコードの短い断片の文字列であると識別できるような外見のコンテンツを表示します。既定では、中の文字列が{{Glossary("user agent", "ユーザーエージェント")}}の既定の等幅フォントを使用して表示されます。

{{EmbedInteractiveExample("pages/tabbed/code.html", "tabbed-shorter")}}

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
        >を受け入れるすべての要素
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
      <td>
        {{domxref("HTMLElement")}}。Gecko 1.9.2 (Firefox 4)
        以前では、この要素には {{domxref("HTMLSpanElement")}}
        インターフェイスが実装されています。
      </td>
    </tr>
  </tbody>
</table>

## 属性

この要素には[グローバル属性](/ja/docs/Web/HTML/Global_attributes)以外の属性はありません。

## 例

`<code>` を含むテキストの段落です。

```html
<p>The function <code>selectAll()</code> highlights all the text in the
input field so the user can, for example, copy or delete the text.</p>
```

この HTML によって生成される出力は以下のようになります。

{{EmbedLiveSample("Example", 640, 70)}}

## 補足

複数行のコードを表すには、 `<code>` 要素を {{HTMLElement("pre")}} 要素の中に入れてください。 `<code>` 要素自身は、コードの単一のフレーズや 1 行のみを表します。

CSS の規則によって、 `code` セレクターを定義して、ブラウザーの既定のフォントを上書きすることができます。ユーザーによる設定を CSS による指定より優先させることもできます。

## 仕様書

| 仕様書                                                                                                               | 状態                             | 備考 |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------- | ---- |
| {{SpecName('HTML WHATWG', 'semantics.html#the-code-element', '&lt;code&gt;')}}             | {{Spec2('HTML WHATWG')}} |      |
| {{SpecName('HTML5 W3C', 'textlevel-semantics.html#the-code-element', '&lt;code&gt;')}} | {{Spec2('HTML5 W3C')}}     |      |
| {{SpecName('HTML4.01', 'struct/text.html#h-9.2.1', '&lt;code&gt;')}}                         | {{Spec2('HTML4.01')}}     |      |

## ブラウザーの互換性

{{Compat("html.elements.code")}}

## 関連情報

- {{HTMLElement("samp")}}
- {{HTMLElement("kbd")}}
- {{HTMLElement("command")}} (非推奨)
- {{HTMLElement("var")}}
- {{HTMLElement("pre")}}
