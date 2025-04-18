---
title: GlobalEventHandlers.onloadend
slug: Web/API/XMLHttpRequest/loadend_event
tags:
  - API
  - DOM
  - Gestionnaires d'évènements
  - Propriétés
  - évènements
translation_of: Web/API/GlobalEventHandlers/onloadend
original_slug: Web/API/GlobalEventHandlers/onloadend
---
{{ApiRef}}

La propriété **`onloadend`** du "mixin" {{domxref("GlobalEventHandlers")}} est un {{event("Event_handlers", "event handler")}} (_gestionnaire d'évènements_) représentant le code à appeler lorsque l'évènement {{event("loadend")}} est déclenché (quand la progression est arrêtée sur le chargement d'une ressource).

## Syntaxe

```js
img.onloadend = funcRef;
```

### Valeur

`funcRef` est la fonction du gestionnaire à appeler quand l'évènement `loadend` de la ressource est déclenché.

## Exemples

### Contenu HTML

```html
<img src="myImage.jpg">
```

### Contenu JavaScript

```js
// 'loadstart' est le premier lancé, puis 'load', puis 'loadend'

image.addEventListener('load', function(e) {
  console.log('Image loaded');
});

image.addEventListener('loadstart', function(e) {
  console.log('Image load started');
});

image.addEventListener('loadend', function(e) {
  console.log('Image load finished');
});
```

## Spécifications

{{Specifications}}

## Compatibilité des navigateurs

{{Compat}}
