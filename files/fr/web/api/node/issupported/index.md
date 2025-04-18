---
title: element.isSupported
slug: Web/API/Node/isSupported
tags:
  - API
  - DOM
  - Méthodes
  - Noeuds
translation_of: Web/API/Node/isSupported
---
{{APIRef("DOM")}}{{deprecated_header}}

La méthode **`Node.isSupported()`** renvoie une marque  {{domxref("Boolean","booléenne")}} contenant le résultat du test par lequel est vérifié si une implémentation DOM prend en charge une fonctionnalité spécifique et si celle-ci est supportée par un noeud spécifique.

### Syntaxe

```js
boolValue = element.isSupported(feature, version)
```

### Paramètres

- `feature`
  - : est une  {{domxref("DOMString")}} (_chaîne de caractères_) contenant le nom de la fonctionnalité à tester. C'est le même nom qui peut être passé à la méthode `hasFeature` de [DOMImplementation](/fr/docs/Web/API/Document/implementation). Les valeurs possibles définies dans la spécification DOM core sont listées dans la section [Conformance](http://www.w3.org/TR/DOM-Level-2-Core/introduction.html#ID-Conformance) de DOM Level 2.
- `version`
  - : est une  {{domxref("DOMString")}} (_chaîne de caractères_) contenant le numéro de version de la fonctionnalité à tester. En DOM Level 2, première version, il s'agit de la chaîne «&nbsp;`2.0`&nbsp;». Si la version n'est pas spécifiée, la gestion de n'importe quelle version de la fonctionnalité suffira pour que soit renvoyée la valeur `true`.

## Exemple

```html
<div id="doc">
</div>

<script>
 // Obtenir un élément et vérifier pour voir s'il est pris en charge par les modules HTML DOM2.
 var main = document.getElementById('doc');
 var output = main.isSupported('HTML', '2.0');
</script>
```

## Spécifications

{{Specifications}}

## Compatibilité des navigateurs

{{Compat}}

## Voir aussi

- L'interface {{domxref("Node")}} à laquelle elle appartient.
