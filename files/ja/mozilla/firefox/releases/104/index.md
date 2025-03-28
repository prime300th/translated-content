---
title: Firefox 104 for developers
slug: Mozilla/Firefox/Releases/104
tags:
  - '104'
  - Firefox
  - Mozilla
  - Release
---
{{FirefoxSidebar}}

このページでは、開発者に影響する Firefox 104 の変更点をまとめています。Firefox 104 は、2022 年 8 月 23 日にリリースされました。

## ウェブ開発者向けの変更点一覧

### HTML

変更なし。

### CSS

### JavaScript

- {{jsxref("Array.prototype.findLast()")}}、{{jsxref("Array.prototype.findLastIndex()")}}、{{jsxref("TypedArray.prototype.findLast()")}}、{{jsxref("TypedArray.prototype.findLastIndex()")}} メソッドをサポートしました。
  これらはそれぞれ、{{jsxref("Array")}} または {{jsxref("TypedArray")}} で、与えたテスト関数にマッチする最後の要素の値または添字を発見するために使用します。
  (詳しくは {{bug(1775026)}} をご覧ください)

- [`window.postMessage()`](/ja/docs/Web/API/Window/postMessage) および [`structuredClone()`](/ja/docs/Web/API/structuredClone) で [ネイティブなエラーの型](/ja/docs/Web/JavaScript/Reference/Global_Objects/Error#error_types) を使用したとき、シリアライズした結果に (`stack` を持つエラーの型で) [`stack`](/ja/docs/Web/JavaScript/Reference/Global_Objects/Error/stack) プロパティも含まれるようになりました。
  [`Worker.postMessage()`](/ja/docs/Web/API/Worker/postMessage) など、ほかの API を使用してエラーを送信する場合は、まだ `stack` をシリアライズしません 
  (詳しくは {{bug(1774866)}} をご覧ください)。

### HTTP

変更なし。

### セキュリティ

変更なし。

### API

#### DOM

- [`HTMLElement.focus()`](/ja/docs/Web/API/HTMLElement/focus) で引数 [`option.focusVisible`](/ja/docs/Web/API/HTMLElement/focus#focusvisible) をサポートしました。これは要素にフォーカスした後に、視覚的な表示をブラウザーに強制するために使用できます。
  ブラウザーの実装でアクセシビリティが向上すると判断した場合に、フォーカスした要素へ自動的に視覚的な表示を行う可能性があることに注意してください。
  (詳しくは {{bug(1765083)}} をご覧ください)

#### Media、WebRTC、Web Audio

#### SVG

- SVG の style 要素を有効・無効にしたり、要素の無効状態を確認したりするために使用する、[`SVGStyleElement.disabled`](/ja/docs/Web/API/SVGStyleElement/disabled) プロパティが使用可能になりました。
  これは [`HTMLStyleElement.disabled`](/ja/docs/Web/API/HTMLStyleElement/disabled) の動作を反映したものです。
  (詳しくは {{bug(1712623)}} をご覧ください)

#### 廃止

- [`IDBFactory.open()`](/ja/docs/Web/API/IDBFactory/open) メソッドの引数 `options` を削除しました。
  これは非標準のオプションであり、Firefox だけでデータベースが永続的であることを示す方法でした。
  このオプションは以前から非推奨であり、すでにユーザーはこの機能を {{domxref("StorageManager.persist()")}} に移行することが必要でした。
  (詳しくは {{bug(1354500)}} をご覧ください)

### WebAssembly

#### 廃止

### WebDriver conformance (WebDriver BiDi, Marionette)

#### WebDriver BiDi

- `log.entryAdded` イベントで `source` をサポートしました ({{bug(1770792)}})。
-  新たに開いたブラウジングコンテキストについて、`browsingContext.contextCreated` イベントに送信する `url` を `about:blank` に更新しました ({{bug(1775141)}})。

#### Marionette

- Linux でウィンドウを最小化するときや元のサイズに戻すときの、安定性やパフォーマンスが向上しました ({{bug(1780212)}})。
- `touch` アクションをサポートしました ({{bug(1543337)}})。

## アドオン開発者向けの変更点一覧

#### 廃止

### その他

## 過去のバージョン

{{Firefox_for_developers(103)}}
