---
title: Function.prototype.toSource()
slug: conflicting/Web/JavaScript/Reference/Global_Objects/Function/toString
translation_of: Web/JavaScript/Reference/Global_Objects/Function/toSource
original_slug: Web/JavaScript/Reference/Global_Objects/Function/toSource
---
{{JSRef}} {{non-standard_header}}

El método **`toSource()`** devuelve un string representando el código fuente del objeto.

## Sintaxis

    function.toSource();
    Function.toSource();

### Parámetros

Ninguno.

## Descripción

El método `toSource` devuelve los siguientes valores:

- For the built-in {{jsxref("Function")}} object, `toSource()` devuelve la siguiente cadena indicando que el código fuente no está disponible:

  ```js
  function Function() {
      [native code]
  }
  ```

- En funciones personalizadas, `toSource()` devuelve el código JavaScript que define el objeto como un string.

Éste método es usado de forma interna por JavaScript y no explicitamente desde el código. Puedes usar `toSource` mientras depuras para examinar el contenido de un objeto.

## Especificaciones

No está reflejado en ningún estándar. Implementaso en JavaScript 1.3.

## Browser compatibility

{{Compat("javascript.builtins.Function.toSource")}}

## Ver también

- {{jsxref("Object.prototype.toSource()")}}
