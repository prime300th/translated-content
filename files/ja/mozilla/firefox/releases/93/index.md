---
title: Firefox 93 for developers
slug: Mozilla/Firefox/Releases/93
---
{{FirefoxSidebar}}

このページでは、開発者に影響する Firefox 93 の変更点をまとめています。Firefox 93 は、2021 年 10 月 5 日にリリースされました。

## ウェブ開発者向けの変更点一覧

### HTML

- ARIA の [`meter`](/ja/docs/Web/Accessibility/ARIA/Roles/meter_role) ロールを実装しました ({{bug(1727616)}})。
- [`<input type="datetime-local">`](/docs/Web/HTML/Element/input/datetime-local) の UI を実装しました ({{bug(1283388)}})。

### CSS

- {{cssxref("font-synthesis")}} プロパティで `small-caps` キーワードをサポートしました ({{bug(1706080)}})。

### JavaScript

- [クラスの `static` 初期化ブロック](/ja/docs/Web/JavaScript/Reference/Classes/Class_static_initialization_blocks) をサポートしました。{{jsxref("Classes/static", "静的")}} プロパティの初期化を、より柔軟に行えます ({{bug(1725689)}})。
- {{domxref("createImageBitmap()")}} メソッドに、`options` オブジェクトを使用して `imageOrientation` および `premultiplyAlpha` プロパティを渡すことが可能になりました ({{bug(1367251)}})。
- 実装でサポートされている値をコードが列挙することを可能にする、{{jsxref("Intl.supportedValuesOf()")}} をサポートしました。これは、例えば欠けているカテゴリーの値に対するポリフィルだけをダウンロードするために使用できます ({{bug(1670033)}})。

### HTTP

- ダイジェストを使用する [HTTP 認証](/ja/docs/Web/HTTP/Authentication) で SHA-256 アルゴリズムをサポートしました。これは、以前から使用できた MD5 アルゴリズムより安全な認証を可能にします ({{bug(1682995)}})。
- _画像_ について、既定の HTTP {{HTTPHeader("ACCEPT")}} ヘッダーを `image/avif,image/webp,*/*` に変更しました ([AVIF](/ja/docs/Web/Media/Formats/Image_types#avif_画像) 画像形式のサポートを追加した結果として) ({{bug(1682995)}})。

### API

- {{domxref("ElementInternals.shadowRoot")}} および {{domxref("HTMLElement.attachInternals")}} をサポートしました ({{bug(1723521)}})。
- {{domxref("ResizeObserver.Observe()")}} の値 `device-pixel-content-box` をサポートしました ({{bug(1587973)}})。
- {{domxref("reportError()")}} グローバル関数をサポートしました。これはスクリプトがコンソールやグローバルイベントハンドラーへエラーを報告できるようにして、キャッチされなかった JavaScript の例外をエミュレートするものです ({{bug(1722448)}})。

#### イベント

- {{domxref("GlobalEventHandlers.onsecuritypolicyviolation","onsecuritypolicyviolation")}} グローバルイベントハンドラープロパティをサポートしました。これは、[Content Security Policy](/ja/docs/Web/HTTP/CSP) の違反があるときに発生する [`securitypolicyviolation`](/ja/docs/Web/API/Element/securitypolicyviolation_event) イベントを処理するハンドラーを割り当てるために使用できます ({{bug(1727302)}})。
- {{domxref("GlobalEventHandlers.onslotchange","GlobalEventHandlers")}} および {{domxref("ShadowRoot.onslotchange","ShadowRoot")}} で `onslotchange` イベントハンドラープロパティをサポートしました。これは、スロットに含まれているノードが変更されたときに {{HTMLElement("slot")}} 要素で発生する [`slotchange`](/ja/docs/Web/API/HTMLSlotElement/slotchange_event) イベントを処理するハンドラーを割り当てるために使用できます ({{bug(1501983)}})。

#### 廃止

- {{domxref("KeyboardEvent.initKeyEvent()")}} を設定項目 `dom.keyboardevent.init_key_event.enabled` で制御するようにして、既定で無効にしました。このメソッドは、他のブラウザーが現在サポートしているどの仕様でも提供されていません ({{bug(1717760)}})。

### WebDriver conformance (Marionette)

- `WebDriver:Print` が大きなドキュメントで失敗していた不具合を修正しました ({{bug(1721982)}})。

## アドオン開発者向けの変更点

- `windowId` を明示したとき、{{WebExtAPIRef("extension.getViews")}} にサイドバーが含まれるようになりました ({{bug(1612390)}})。

## その他

- [AVIF](/ja/docs/Web/Media/Formats/Image_types#avif_画像) 画像のサポートを、デフォルトで有効化しました ({{bug(1682995)}})。この形式は圧縮率が優れており、また特許の制限がありません (これは [Alliance for Open Media](http://aomedia.org/) が開発しています)。Firefox はフルレンジおよびリミテッドレンジの両方の色空間をサポートして静的画像を表示でき、画像の変形や回転も可能です。設定項目 [image.avif.compliance_strictness](/ja/docs/Mozilla/Firefox/Experimental_features#avif_compliance_strictness) で、仕様へどの程度厳密に従うかを調節できます。アニメーション画像は未サポートです。

## 過去のバージョン

{{Firefox_for_developers(92)}}
