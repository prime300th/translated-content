---
title: Audio
slug: Web/HTML/Element/audio
translation_of: Web/HTML/Element/audio
original_slug: Web/HTML/Elemento/audio
---
El elemento `audio` se usa para insertar contenido de audio en un documento HTML o XHTML. El elemento `audio` se agregó como parte de HTML 5.

> **Nota:** actualmente Gecko admite solamente Vorbis, en contenedores Ogg, así como formato WAV. Asimismo, el servidor debe servir el archivo mediante el tipo MIME correcto con el fin de que Gecko lo reproduzca correctamente.

Puedes usar las características API de audio mejoradas - que son específicas de Gecko - para generar y manipular directamente secuencias de audio a partir de código JavaScript. Consulta [Manipular sonido a través de la API de audio mejorada](/en/Manipulating_audio_using_the_enhanced_audio_API "en/Manipulating audio using the enhanced audio API") para tener más detalles.

## Contexto de uso

| Contenido permitido            | [Contenido transparente](/en/HTML/Content_categories#transparent_content "en/HTML/Content categories#transparent content"), que contiene bien un atributo **src**, bien uno o más elementos {{ HTMLElement("source") }}, seguido de [contenido dinámico](/en/HTML/Content_categories#flow_content "en/HTML/Content categories#flow content") o [contenido estático](/en/HTML/Content_categories#phrasing_content "en/HTML/Content categories#phrasing content") , sin ningún elemento de {{ HTMLElement("video") }} o `<audio>`. |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Omisión de etiquetas           | Ninguna, deben estar presentes tanto las etiquetas de inicio como las de cierre.                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Elementos primarios permitidos | Cualquier elemento que acepte [contenido dinámico](../../../../en/HTML/Content_categories#flow_content) o cualquier elemento que acepte [contenido estático](../../../../en/HTML/Content_categories#phrasing_content).                                                                                                                                                                                                                                                                                                                              |
| Documento normativo            | [HTML5, sección 4.8.7](http://www.w3.org/TR/html5/video.html#audio)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

## Atributos

- autoplay
  - : Un atributo booleano; si se especifica (incluso aunque el valor sea "false"), el sonido comenzará a reproducirse automáticamente en cuanto sea posible, sin detenerse para terminar de cargar los datos.
- autobuffer {{ obsolete_inline("2.0") }}
  - : Un atributo booleano; si se especifica, el sonido comenzará a reproducirse automáticamente, incluso aunque no se haya configurado para la reproducción automática. Esto continuará hasta que la caché de medios esté llena o se haya descargado el archivo de audio completo, lo que suceda primero. Debería usarse sólo si se espera que el usuario elija reproducir el audio; por ejemplo si el usuario ha navegado hasta una página usando un vínculo de "Reproducir este audio". Este atributo se eliminó de Gecko 2.0 {{ geckoRelease("2.0") }} en favor del atributo preload.
- buffered {{ gecko_minversion_inline("2.0") }}
  - : Un atributo que se puede leer para determinar qué intervalos de tiempo del multimedia se han almacenado en búfer. Este atributo contiene un objeto {{ domxref("TimeRanges") }}.
- controls
  - : Si está presente este atributo, el navegador ofrecerá controles para permitir que el usuario controle la reproducción de audio, incluyendo volumen, búsqueda y pausar/reanudar reproducción.
- loop {{ unimplemented_inline() }} {{ bug(449157) }}
  - : Un atributo booleano; si se especifica, al alcanzar el final del audio, realizaremos la búsqueda automáticamente hasta el principio.
- mozCurrentSampleOffset {{ gecko_minversion_inline("2.0") }} {{ non-standard_inline() }}
  - : La posición de desplazamiento, que se especifica como el número de muestras desde el comienzo de la secuencia de audio, en la cual el audio se está reproduciendo actualmente.
- preload {{ gecko_minversion_inline("2.0") }} {{ bug(548523) }}
  - : El objetivo de este atributo enumerado es proporcionar una sugerencia al navegador sobre qué cree el autor que proporcionará la mejor experiencia para el usuario . Puede tener uno de los siguientes valores:
    - `none`: sugiere bien que el autor cree que el usuario no tendrá que consultar ese video, bien que el servidor desea minimizar su tráfico; es decir, esta sugerencia indica que no se debe almacenar en caché este video;
    - `metadata`: sugiere que aunque el autor piensa que el usuario no tendrá que consultar ese video, es razonable capturar los metadatos (p. ej. longitud);
    - `auto`: sugiere que el usuario necesita tener prioridad; es decir, esta sugerencia indica que, si es necesario, se puede descargar el video completo, incluso aunque el usuario no vaya a usarlo;
    - the _empty string_: que es sinónimo del valor `auto`.

Si no está configurado, su valor predeterminado está definido por el navegador (es decir, cada navegador puede elegir su propio valor predeterminado), aunque la especificación aconseje que se establezca a `metadatos`.

> **Nota:** **Observaciones sobre uso:** 
> - El atributo **autoplay** tiene prioridad sobre éste puesto que si se desea reproducir automáticamente un video, el navegador obviamente tendrá que descargarlo. La especificación permite establecer los atributos **autoplay** y **preload**.
> - La especificación no fuerza al navegador a seguir el valor de este atributo; es tan sólo una sugerencia.

- src
  - : La URL del audio que se va a insertar. Está sujeta a los [Controles de acceso HTTP](/En/HTTP_access_control "En/HTTP access control"). Es opcional; en su lugar puedes usar el elemento [`source`](/en/HTML/Element/Source "En/HTML/Element/Source") dentro del bloque de audio para especificar el audio que se va a insertar.

Las compensaciones de tiempo se especifican como valores float que indican el número de segundos que se va a compensar.

> **Nota:** la definición del valor de compensación de tiempo no se ha completado en HTML 5 aún y está sujeta a cambios.

## Ejemplos

```html
<audio src="https://developer.mozilla.org/@api/deki/files/2926/=AudioTest_(1).ogg"
       autoplay>
  Your browser does not support the <code>audio</code> element.
</audio>
```

Reproduce el fichero de audio adjunto a este artículo.

## Interfaz DOM

- [HTMLAudioElement](/en/DOM/HTMLAudioElement "en/DOM/HTMLAudioElement")

## Consulta también

- [**Formatos multimedia admitidos por los elementos de audio y video**](/es/Formatos_multimedia_admitidos_por_los_elementos_de_video_y_audio "es/Formatos multimedia admitidos por los elementos de video y audio")
- [Manipulating audio using the enhanced audio API](/en/Manipulating_audio_using_the_enhanced_audio_API "en/Manipulating audio using the enhanced audio API")
- [`HTMLAudioElement`](/en/DOM/HTMLAudioElement "en/DOM/HTMLAudioElement")
- [`nsIDOMHTMLMediaElement`](/En/XPCOM_Interface_Reference/NsIDOMHTMLMediaElement "En/NsIDOMHTMLMediaElement")
- [`video`](/en/HTML/Element/Video "En/HTML/Element/Video")
- [Usar audio y video en Firefox](/es/Using_audio_and_video_in_Firefox "Es/Usar audio y video en Firefox")
- [The `audio` element](http://www.whatwg.org/specs/web-apps/current-work/#audio) (HTML 5 specification)
