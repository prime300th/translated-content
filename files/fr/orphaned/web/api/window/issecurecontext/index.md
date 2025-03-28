---
title: Window.isSecureContext
slug: orphaned/Web/API/Window/isSecureContext
tags:
  - API
  - Propriété
  - Reference
  - Sécurité
  - Window
translation_of: Web/API/Window/isSecureContext
original_slug: Web/API/Window/isSecureContext
---
{{APIRef}}{{SeeCompatTable}}

La propriété en lecteur seule **`window.isSecureContext`** indique si un contexte est capable d'utiliser des fonctionnalités qui nécessitent des [contextes sécurisés](/fr/docs/Web/Security/Secure_Contexts).

## Syntaxe

```js
var isSecure = window.isSecureContext
```

## Exemples

### Détection des fonctionnalités

Vous pouvez utiliser la détection des fonctionnalités pour vérifier si elles sont dans un contexte sécurisé ou non à l'aide du booléen `isSecureContext` qui est exposé sur la portée globale.

```js
if (window.isSecureContext) {
  // La page est un contexte sécurisé afin que les techniciens de service soient désormais disponibles
  navigator.serviceWorker.register("/offline-worker.js").then(function () {
    ...
  });
}
```

## Spécifications

{{Specifications}}

## Compatibilité des navigateurs

{{Compat}}

## Voir aussi

- [Contextes sécurisés](/fr/docs/Web/Security/Secure_Contexts)
