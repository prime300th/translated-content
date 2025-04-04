---
title: WindowEventHandlers.onbeforeunload
slug: conflicting/Web/API/Window/beforeunload_event
original_slug: Web/API/WindowEventHandlers/onbeforeunload
---
{{APIRef("HTML DOM")}}

**`onbeforeunload`** は {{domxref("WindowEventHandlers")}} ミックスインのプロパティで、 {{event("beforeunload")}} イベントを処理する {{event("Event_handlers", "event handler")}} です。このイベントはウィンドウでリソースを {{event("unload")}} しようとするときに発生します。この時点では文書はまだ表示されており、イベントはキャンセル可能な状態です。

> **Note:** **メモ:** ブラウザーによっては不要なポップアップを防ぐために、ページで操作が行われない限り、 `beforeunload` イベントハンドラーの中で作られたプロンプトを表示しないことがあります。さらに、ブラウザーによっては全く表示しないかもしれません。

## 構文

```
window.addEventListener("beforeunload", function(event) { ... });
window.onbeforeunload = function(event) { ... };
```

ふつうは、 {{domxref("EventTarget.addEventListener", "window.addEventListener()")}} および {{event("beforeunload")}} イベントを使用したほうが `onbeforeunload` を使用するよりも適切です。

## 例

この例では、ページの終了前にユーザーに確認を取ります。

HTML 仕様書は、ユーザーに確認を取るときに {{domxref("Event.returnValue")}} メソッドの代わりに {{domxref("Event.preventDefault()")}} メソッドを使用するよう明記しています。しかし、これはまだすべてのブラウザーが対応しているわけではありません。

```js
window.addEventListener('beforeunload', function (e) {
  // イベントをキャンセルする
  e.preventDefault();
  // Chrome では returnValue を設定する必要がある
  e.returnValue = '';
});
```

## メモ

ページが JavaScript を使用してコンテンツを表示している場合、ページを離れて元に戻ったときに JavaScript が停止することがあります。 `window.onbeforeunload` をバインドすることで、ブラウザーがページを完全にキャッシュすることを防ぐことができます。そうすると、ページ内の JavaScript は、次回の訪問時に起動され、必要に応じてコンテンツを更新します。

## 仕様書

このイベントは最初に Microsoft Internet Explorer 4 で導入され、HTML5 仕様で標準化されました。

| 仕様書                                                                                                   | 状態                             | 備考 |
| -------------------------------------------------------------------------------------------------------- | -------------------------------- | ---- |
| {{SpecName('HTML WHATWG', '#handler-window-onbeforeunload', 'onbeforeunload')}} | {{Spec2('HTML WHATWG')}} |      |
| {{SpecName('HTML5.1', '#windoweventhandlers', 'GlobalEventHandlers')}}             | {{Spec2('HTML5.1')}}     |      |
| {{SpecName("HTML5 W3C", "#windoweventhandlers", "GlobalEventHandlers")}}         | {{Spec2('HTML5 W3C')}}     |      |

## ブラウザーの対応

{{Compat("api.WindowEventHandlers.onbeforeunload")}}

HTML 仕様書は、ユーザーに確認を取るときに {{domxref("Event.returnValue")}} メソッドの代わりに {{domxref("Event.preventDefault()")}} メソッドを使用するよう明記しています。しかし、これはまだすべてのブラウザーが対応しているわけではありません。

このイベントが `null` でも `undefined` でもない値を返した場合 (または `returnValue` プロパティに設定した場合)、ユーザーに対してページが終了することの確認が行われます。古いブラウザーでは、イベントの返値がダイアログに表示されます。 Firefox 44, Chrome 51, Opera 38, Safari 9.1 以降では、次のように、文字列の返値ではなく、ウェブページからは制御できない一般化された文字列が表示されます。

- 例えば、 Firefox では "This page is asking you to confirm that you want to leave - data you have entered may not be saved." (このページが本当にページから離れるかどうかを確認しています。 - 入力されたデータは保存されない可能性があります) という文字列が表示されます ({{bug("588292")}} を参照)。
- Chrome では "Do you want to leave this site? Changes you made may not be saved" (サイトを離れますか？変更が保存されない可能性があります) という文字列が表示されます ([Chrome Platform Status](https://www.chromestatus.com/feature/5349061406228480) を参照)。

Internet Explorer は `null` の返値を尊重せず、テキストとして "null" をユーザーに表示します。プロンプトをスキップするには、 `undefined` を使用する必要があります。

ブラウザーによっては、このイベント内での {{domxref("window.alert()")}}, {{domxref("window.confirm()")}}, {{domxref("window.prompt()")}} の呼び出しは無視される可能性があります。詳しくは [HTML 仕様書](http://www.w3.org/TR/html5/webappapis.html#user-prompts)を参照して下さい。

また、様々なブラウザーがイベントの結果を無視し、ユーザーにまったく確認を取らないことがあります。このような場合、文書は常に自動的にアンロードされます。 Firefox では about:config の中に `dom.disable_beforeunload` という名前のスイッチがあり、この動作を有効にすることができます。Chrome 60 時点では、フレームまたはページが読み込まれてからユーザーが何も操作を行っていない場合、確認は行われません。
