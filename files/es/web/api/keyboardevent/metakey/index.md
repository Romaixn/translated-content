---
title: KeyboardEvent.metaKey
slug: Web/API/KeyboardEvent/metaKey
tags:
  - Evento
  - Referencia
translation_of: Web/API/KeyboardEvent/metaKey
---
{{APIRef("DOM Events")}}

La propiedad **`KeyboardEvent.metaKey`** es de solo lectura y regresa un valor {{jsxref("Boolean")}} que indica si la tecla <kbd>Meta</kbd> estaba presionada (true) o no (false) cuando el evento ocurrio.

> **Nota:** En teclados Macintosh es la tecla comando (<kbd>⌘</kbd>). En teclados Windows la tecla es lla tecla window (<kbd>⊞</kbd>).

## Syntax

    var metaKeyPressed = instanceOfKeyboardEvent.metaKey

### Valor de retorno

{{jsxref("Boolean")}}

## Ejemplo

```js
 function goInput(e) {
 // Revisa si estaba presionada la tecla meta y
   if (e.metaKey) {
        // realiza esto en caso de cierto
     superSizeOutput(e);
   } else {
         //Realiz esto en caso de falso
     doOutput(e);
   }
 }
```

## metaKey

### Contenido HTML

```html
<div id="example" onmousedown="ismetaKey(event);">¡Presiona la tecla meta y dame click!<div>
```

### Contenido Javascript

```js
function ismetaKey(e){
 var el=document.getElementById("example");//Toma el control del div example
 var mK=e.metaKey;//Obtiene el valor de metaKey y lo almacena
 el.innerHTML="¡Presiona la tecla meta y dame click!</br>metaKey:"+mK;//Muestra el valor de metaKey
}
```

{{ EmbedLiveSample('metaKey') }}

## Especificaciones

| Especificación                                                                                               | Status                           | Comentario         |
| ------------------------------------------------------------------------------------------------------------ | -------------------------------- | ------------------ |
| {{SpecName('DOM3 Events','#widl-KeyboardEvent-metaKey','KeyboardEvent.metaKey')}} | {{Spec2('DOM3 Events')}} | Definición inicial |

## Compatibilidad de Navegadores

{{Compat("api.KeyboardEvent.metaKey")}}

## Ver también

- {{ domxref("KeyboardEvent") }}