# 🤯 HEAD

> Una guía simple para elementos HTML `<head>`

[![Contribuidores](https://img.shields.io/github/contributors/joshbuchea/head.svg?style=for-the-badge)](https://github.com/joshbuchea/HEAD/graphs/contributors)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg?style=for-the-badge)](https://creativecommons.org/publicdomain/zero/1.0/)
[![Sígueme @joshbuchea en Mastodon](https://img.shields.io/badge/Follow_@joshbuchea-purple?logo=mastodon&logoColor=white&style=for-the-badge)](https://hachyderm.io/@joshbuchea)

## Tabla de Contenidos

- [Mínimo Recomendado](#mínimo-recomendado)
- [Elementos](#elementos)
- [Meta](#meta)
- [Enlaces](#enlaces)
- [Iconos](#iconos)
- [Social](#social)
  - [Facebook Open Graph](#facebook-open-graph)
  - [X Card](#x-card)
  - [Privacidad de X](#privacidad-de-x)
  - [Schema.org](#schemaorg)
  - [Pinterest](#pinterest)
  - [Facebook Instant Articles](#facebook-instant-articles)
  - [OEmbed](#oembed)
  - [QQ/Wechat](#qqwechat)
- [Navegadores / Plataformas](#navegadores--plataformas)
  - [Apple iOS](#apple-ios)
  - [Google Android](#google-android)
  - [Google Chrome](#google-chrome)
  - [Microsoft Internet Explorer](#microsoft-internet-explorer)
- [Navegadores (Chinos)](#navegadores-chinos)
  - [Navegador 360](#navegador-360)
  - [Navegador Móvil QQ](#navegador-móvil-qq)
  - [Navegador Móvil UC](#navegador-móvil-uc)
- [Enlaces de Aplicaciones](#enlaces-de-aplicaciones)
- [Otros Recursos](#otros-recursos)
- [Proyectos Relacionados](#proyectos-relacionados)
- [Otros Formatos](#otros-formatos)
- [Traducciones](#-traducciones)
- [Contribuir](#-contribuir)
- [Autor](#-autor-del-proyecto)
- [Autor de la traducción](#-autor-de-la-traduccion)
- [Licencia](#licencia)

## Mínimo Recomendado

A continuación se muestran los elementos esenciales para cualquier documento web (sitios web/aplicaciones):

```html
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<!--
  Las 2 etiquetas meta anteriores *deben* aparecer primero en el <head>
  para garantizar consistentemente el renderizado correcto del documento.
  Cualquier otro elemento head debe venir *después* de estas etiquetas.
 -->
<title>Título de la Página</title>
```

`meta charset` - define la codificación del sitio web, `utf-8` es el estándar

`meta name="viewport"` - configuración de la ventana gráfica relacionada con la capacidad de respuesta móvil

`width=device-width` - usar el ancho físico del dispositivo (¡excelente para móviles!)

`initial-scale=1` - el zoom inicial, 1 significa sin zoom

**[⬆ volver arriba](#tabla-de-contenidos)**

## Elementos

Los elementos válidos para `<head>` incluyen `meta`, `link`, `title`, `style`, `script`, `noscript`, y `base`.

Estos elementos proporcionan información sobre cómo debe ser percibido y renderizado un documento por las tecnologías web. Por ejemplo: navegadores, motores de búsqueda, bots, etc.

```html
<!--
  Establece la codificación de caracteres para este documento, para que
  todos los caracteres dentro del espacio UTF-8 (como los emojis)
  se rendericen correctamente.
-->
<meta charset="utf-8">

<!-- Establece el título del documento -->
<title>Título de la Página</title>

<!-- Establece la URL base para todas las URLs relativas dentro del documento -->
<base href="https://ejemplo.com/pagina.html">

<!-- Enlace a un archivo CSS externo -->
<link rel="stylesheet" href="estilos.css">

<!-- Usado para agregar CSS dentro del documento -->
<style>
  /* ... */
</style>

<!-- JavaScript y etiquetas No-JavaScript -->
<script src="script.js"></script>
<script>
  // función(es) aquí
</script>
<noscript>
  <!-- Alternativa sin JS -->
</noscript>
```

**[⬆ volver arriba](#tabla-de-contenidos)**

## Meta

```html
<!--
  Las siguientes 2 etiquetas meta *deben* aparecer primero en el <head>
  para garantizar consistentemente el renderizado correcto del documento.
  Cualquier otro elemento head debe venir *después* de estas etiquetas.
-->
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">

<!--
  Permite controlar desde dónde se cargan los recursos.
  Colocar lo más temprano posible en el <head>, ya que la etiqueta
  solo se aplica a los recursos que se declaran después de ella.
-->
<meta http-equiv="Content-Security-Policy" content="default-src 'self'">

<!-- Nombre de la aplicación web (solo debe usarse si el sitio web se usa como una aplicación) -->
<meta name="application-name" content="Nombre de la Aplicación">

<!-- Color del tema para Chrome, Firefox OS y Opera -->
<meta name="theme-color" content="#4285f4">

<!-- Descripción corta del documento (límite de 150 caracteres) -->
<!-- Este contenido *puede* ser usado como parte de los resultados del motor de búsqueda. -->
<meta name="description" content="Una descripción de la página">

<!-- Control del comportamiento de rastreo e indexación del motor de búsqueda -->
<meta name="robots" content="index,follow"><!-- Todos los Motores de Búsqueda -->
<meta name="googlebot" content="index,follow"><!-- Específico de Google -->

<!-- Le dice a Google que no muestre el cuadro de búsqueda de enlaces del sitio -->
<meta name="google" content="nositelinkssearchbox">

<!-- Le dice a Google que no proporcione una traducción para este documento -->
<meta name="google" content="notranslate">

<!-- Verificar la propiedad del sitio web -->
<meta name="google-site-verification" content="token_de_verificacion"><!-- Google Search Console -->
<meta name="yandex-verification" content="token_de_verificacion"><!-- Yandex Webmasters -->
<meta name="msvalidate.01" content="token_de_verificacion"><!-- Bing Webmaster Center -->
<meta name="alexaVerifyID" content="token_de_verificacion"><!-- Alexa Console -->
<meta name="p:domain_verify" content="codigo_de_pinterest"><!-- Pinterest Console-->
<meta name="norton-safeweb-site-verification" content="codigo_norton"><!-- Norton Safe Web -->

<!-- Identifica el software usado para construir el documento (ej. - WordPress, Dreamweaver) -->
<meta name="generator" content="programa">

<!-- Breve descripción del tema de tu documento -->
<meta name="subject" content="tema de tu documento">

<!-- Proporciona una calificación de edad general basada en el contenido del documento -->
<meta name="rating" content="General">

<!-- Permite controlar cómo se pasa la información del referente -->
<meta name="referrer" content="no-referrer">

<!-- Desactiva la detección y el formateo automático de posibles números de teléfono -->
<meta name="format-detection" content="telephone=no">

<!-- Desactiva completamente la búsqueda previa de DNS configurándola en "off" -->
<meta http-equiv="x-dns-prefetch-control" content="off">

<!-- Especifica que el documento aparezca en un marco específico -->
<meta http-equiv="Window-Target" content="_value">

<!-- Etiquetas Geo -->
<meta name="ICBM" content="latitud, longitud">
<meta name="geo.position" content="latitud;longitud">
<meta name="geo.region" content="pais[-estado]"><!-- Código de país (ISO 3166-1): obligatorio, código de estado (ISO 3166-2): opcional; ej. content="US" / content="US-NY" -->
<meta name="geo.placename" content="ciudad/pueblo"><!-- ej. content="Nueva York" -->

<!-- Monetización Web https://webmonetization.org/docs/getting-started -->
<meta name="monetization" content="$indicador_de_pago.ejemplo">
```

- 📖 [Meta tags que Google entiende](https://support.google.com/webmasters/answer/79812?hl=es)
- 📖 [WHATWG Wiki: MetaExtensions](https://wiki.whatwg.org/wiki/MetaExtensions)
- 📖 [ICBM en Wikipedia](https://en.wikipedia.org/wiki/ICBM_address#Modern_use)
- 📖 [Geoetiquetado en Wikipedia](https://en.wikipedia.org/wiki/Geotagging#HTML_pages)

**[⬆ volver arriba](#tabla-de-contenidos)**

## Enlaces

```html
<!-- Apunta a una hoja de estilo externa -->
<link rel="stylesheet" href="https://ejemplo.com/estilos.css">

<!-- Ayuda a prevenir problemas de contenido duplicado -->
<link rel="canonical" href="https://ejemplo.com/articulo/?pagina=2">

<!-- Enlaza a una versión AMP HTML del documento actual -->
<link rel="amphtml" href="https://ejemplo.com/ruta/a/version-amp.html">

<!-- Enlaces a un archivo JSON que especifica credenciales de "instalación" para las aplicaciones web -->
<link rel="manifest" href="manifest.json">

<!-- Enlaces a información sobre el/los autor(es) del documento -->
<link rel="author" href="humans.txt">

<!-- Se refiere a una declaración de derechos de autor que se aplica al contexto del enlace -->
<link rel="license" href="copyright.html">

<!-- Da una referencia a una ubicación en tu documento que puede estar en otro idioma -->
<link rel="alternate" href="https://es.ejemplo.com/" hreflang="es">

<!-- Proporciona información sobre un autor u otra persona -->
<link rel="me" href="https://google.com/profiles/thenextweb" type="text/html">
<link rel="me" href="mailto:nombre@ejemplo.com">
<link rel="me" href="sms:+15035550125">

<!-- Enlaces a un documento que describe una colección de registros, documentos u otros materiales de interés histórico -->
<link rel="archives" href="https://ejemplo.com/archivos/">

<!-- Enlaces al recurso de nivel superior en una estructura jerárquica -->
<link rel="index" href="https://ejemplo.com/articulo/">

<!-- Proporciona una auto-referencia - útil cuando el documento tiene múltiples referencias posibles -->
<link rel="self" type="application/atom+xml" href="https://ejemplo.com/atom.xml">

<!-- Los documentos primero, último, anterior y siguiente en una serie de documentos, respectivamente -->
<link rel="first" href="https://ejemplo.com/articulo/">
<link rel="last" href="https://ejemplo.com/articulo/?pagina=42">
<link rel="prev" href="https://ejemplo.com/articulo/?pagina=1">
<link rel="next" href="https://ejemplo.com/articulo/?pagina=3">

<!-- Usado cuando se utiliza un servicio de terceros para mantener un blog -->
<link rel="EditURI" href="https://ejemplo.com/xmlrpc.php?rsd" type="application/rsd+xml" title="RSD">

<!-- Forma un comentario automatizado cuando otro blog WordPress enlaza a tu blog o entrada de WordPress -->
<link rel="pingback" href="https://ejemplo.com/xmlrpc.php">

<!-- Notifica a una URL cuando enlazas a ella en tu documento -->
<link rel="webmention" href="https://ejemplo.com/webmention">

<!-- Permite publicar en tu propio dominio usando un cliente Micropub -->
<link rel="micropub" href="https://ejemplo.com/micropub">

<!-- Búsqueda Abierta -->
<link rel="search" href="/open-search.xml" type="application/opensearchdescription+xml" title="Título de Búsqueda">

<!-- Feeds -->
<link rel="alternate" href="https://feeds.feedburner.com/ejemplo" type="application/rss+xml" title="RSS">
<link rel="alternate" href="https://ejemplo.com/feed.atom" type="application/atom+xml" title="Atom 0.3">

<!-- Prebúsqueda, precarga, pre-navegación -->
<!-- Más información: https://css-tricks.com/prefetching-preloading-prebrowsing/ -->
<link rel="dns-prefetch" href="//ejemplo.com/">
<link rel="preconnect" href="https://www.ejemplo.com/">
<link rel="prefetch" href="https://www.ejemplo.com/">
<link rel="prerender" href="https://ejemplo.com/">
<link rel="preload" href="imagen.png" as="image">
```

- 📖 [Relaciones de Enlaces](https://www.iana.org/assignments/link-relations/link-relations.xhtml)

**[⬆ volver arriba](#tabla-de-contenidos)**

## Iconos

```html
<!-- Para IE 10 y anteriores -->
<!-- Colocar favicon.ico en el directorio raíz - no se necesita etiqueta -->

<!-- Icono en la resolución más alta que necesitamos -->
<link rel="icon" sizes="192x192" href="/ruta/al/icono.png">

<!-- Icono de Apple Touch (reutilizar icono.png de 192px) -->
<link rel="apple-touch-icon" href="/ruta/al/apple-touch-icon.png">

<!-- Icono de Pestaña Fijada de Safari -->
<link rel="mask-icon" href="/ruta/al/icono.svg" color="blue">
```

- 📖 [Todo sobre Favicons (Y los Iconos Touch)](https://bitsofco.de/all-about-favicons-and-touch-icons/)
- 📖 [Crear Iconos de Pestañas Fijadas](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/pinnedTabs/pinnedTabs.html)
- 📖 [Hoja de Trucos de Favicon](https://github.com/audreyr/favicon-cheat-sheet)
- 📖 [Iconos y Colores del Navegador](https://developers.google.com/web/fundamentals/design-and-ux/browser-customization/)

**[⬆ volver arriba](#tabla-de-contenidos)**

## Social

### Facebook Open Graph
> La mayoría del contenido se comparte en Facebook como una URL, por lo que es importante que marques tu sitio web con etiquetas Open Graph para controlar cómo aparece tu contenido en Facebook. [Más sobre el Marcado Facebook Open Graph](https://developers.facebook.com/docs/sharing/webmasters#markup)

```html
<meta property="fb:app_id" content="123456789">
<meta property="og:url" content="https://ejemplo.com/pagina.html">
<meta property="og:type" content="website">
<meta property="og:title" content="Título del Contenido">
<meta property="og:image" content="https://ejemplo.com/imagen.jpg">
<meta property="og:image:alt" content="Una descripción de lo que hay en la imagen (no un pie de foto)">
<meta property="og:description" content="Descripción Aquí">
<meta property="og:site_name" content="Nombre del Sitio">
<meta property="og:locale" content="es_ES">
<meta property="article:author" content="">
```

- 📖 [Protocolo Open Graph](http://ogp.me/)
- 🛠 Prueba tu página con el [Depurador de Compartidos de Facebook](https://developers.facebook.com/tools/debug/)

### X Card
> Con las Tarjetas de X, puedes adjuntar fotos, videos y experiencias multimedia enriquecidas a los Tweets, ayudando a dirigir tráfico a tu sitio web. [Más sobre las Tarjetas de X](https://developer.x.com/en/docs/tweets/optimize-with-cards/overview/abouts-cards)

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@cuenta_del_sitio">
<meta name="twitter:creator" content="@cuenta_individual">
<meta name="twitter:url" content="https://ejemplo.com/pagina.html">
<meta name="twitter:title" content="Título del Contenido">
<meta name="twitter:description" content="Descripción del contenido menor a 200 caracteres">
<meta name="twitter:image" content="https://ejemplo.com/imagen.jpg">
<meta name="twitter:image:alt" content="Una descripción textual de la imagen que transmite la naturaleza esencial de una imagen a usuarios con discapacidad visual. Máximo 420 caracteres.">
```

- 📖 [Comenzando con las tarjetas — Desarrolladores de X](https://dev.x.com/cards/getting-started)
- 🛠 Prueba tu página con el [Validador de Tarjetas de X](https://cards-dev.x.com/validator)

### Privacidad de X
Si incrustas tweets en tu sitio web, X puede usar información de tu sitio para personalizar contenido y sugerencias para usuarios de X. [Más sobre las opciones de privacidad de X](https://dev.x.com/web/overview/privacy#what-privacy-options-do-website-publishers-have).

```html
<!-- no permitir que X use la información de tu sitio para propósitos de personalización -->
<meta name="twitter:dnt" content="on">
```

### Schema.org

```html
<html lang="" itemscope itemtype="https://schema.org/Article">
    <head>
      <link rel="author" href="">
      <link rel="publisher" href="">
      <meta itemprop="name" content="Título del Contenido">
      <meta itemprop="description" content="Descripción del contenido menor a 200 caracteres">
      <meta itemprop="image" content="https://ejemplo.com/imagen.jpg">
```

**Nota:** Estas etiquetas meta requieren que los atributos `itemscope` y `itemtype` se añadan a la etiqueta `<html>`.

- 📖 [Comenzando - schema.org](https://schema.org/docs/gs.html)
- 🛠 Prueba tu página con la [Prueba de Resultados Enriquecidos](https://search.google.com/test/rich-results)

### Pinterest

Pinterest te permite evitar que las personas guarden cosas de tu sitio web, según [su centro de ayuda](https://help.pinterest.com/en/business/article/prevent-saves-to-pinterest-from-your-site). La `descripción` es opcional.

```html
<meta name="pinterest" content="nopin" description="¡Lo siento, no puedes guardar desde mi sitio web!">
```

### Facebook Instant Articles

```html
<meta charset="utf-8">
<meta property="op:markup_version" content="v1.0">

<!-- La URL de la versión web de tu artículo -->
<link rel="canonical" href="https://ejemplo.com/articulo.html">

<!-- El estilo a usar para este artículo -->
<meta property="fb:article_style" content="miestilodearticulo">
```

- 📖 [Creando Artículos - Instant Articles](https://developers.facebook.com/docs/instant-articles/guides/articlecreate)
- 📖 [Ejemplos de Código - Instant Articles](https://developers.facebook.com/docs/instant-articles/reference)

### OEmbed

```html
<link rel="alternate" type="application/json+oembed"
  href="https://ejemplo.com/servicios/oembed?url=http%3A%2F%2Fejemplo.com%2Ffoo%2F&amp;format=json"
  title="Perfil oEmbed: JSON">
<link rel="alternate" type="text/xml+oembed"
  href="https://ejemplo.com/servicios/oembed?url=http%3A%2F%2Fejemplo.com%2Ffoo%2F&amp;format=xml"
  title="Perfil oEmbed: XML">
```

- 📖 [Formato oEmbed](https://oembed.com/)

### QQ/Wechat

Los usuarios que comparten páginas web en qq wechat tendrán un mensaje formateado

```html
<meta itemprop="name" content="título compartido">
<meta itemprop="image" content="http://imgcache.qq.com/qqshow/ac/v4/global/logo.png">
<meta name="description" itemprop="description" content="contenido compartido">
```
- 📖 [Documentación del Formato de Código](http://open.mobile.qq.com/api/mqq/index#api:setShareInfo)

**[⬆ volver arriba](#tabla-de-contenidos)**

## Navegadores (Chinos)

### Navegador 360

```html
<!-- Seleccionar orden del motor de renderizado -->
<meta name="renderer" content="webkit|ie-comp|ie-stand">
```

### Navegador Móvil QQ

```html
<!-- Bloquea la pantalla en la orientación especificada -->
<meta name="x5-orientation" content="landscape/portrait">

<!-- Mostrar este documento en pantalla completa -->
<meta name="x5-fullscreen" content="true">

<!-- El documento se mostrará en "modo aplicación" (pantalla completa, etc.) -->
<meta name="x5-page-mode" content="app">
```

### Navegador Móvil UC

```html
<!-- Bloquea la pantalla en la orientación especificada -->
<meta name="screen-orientation" content="landscape/portrait">

<!-- Mostrar este documento en pantalla completa -->
<meta name="full-screen" content="yes">

<!-- El navegador UC mostrará imágenes incluso en "modo texto" -->
<meta name="imagemode" content="force">

<!-- El documento se mostrará en "modo aplicación" (pantalla completa, prohibiendo gestos, etc.) -->
<meta name="browsermode" content="application">

<!-- Deshabilitado el "modo nocturno" del navegador UC para este documento -->
<meta name="nightmode" content="disable">

<!-- Simplificar el documento para reducir la transferencia de datos -->
<meta name="layoutmode" content="fitscreen">

<!-- Deshabilitar la función del navegador UC de "escalar fuente cuando hay muchas palabras en este documento" -->
<meta name="wap-font-scale" content="no">
```

- 📖 [Documentación del Navegador UC](https://www.uc.cn/download/UCBrowser_U3_API.doc)

**[⬆ volver arriba](#tabla-de-contenidos)**

## Enlaces de Aplicaciones

```html
<!-- iOS -->
<meta property="al:ios:url" content="applinks://docs">
<meta property="al:ios:app_store_id" content="12345">
<meta property="al:ios:app_name" content="Enlaces de App">

<!-- Android -->
<meta property="al:android:url" content="applinks://docs">
<meta property="al:android:app_name" content="Enlaces de App">
<meta property="al:android:package" content="org.applinks">

<!-- Respaldo Web -->
<meta property="al:web:url" content="https://applinks.org/documentation">
```

- 📖 [Enlaces de App](https://developers.facebook.com/docs/applinks)

**[⬆ volver arriba](#tabla-de-contenidos)**

## Otros Recursos

- 📖 [Documentación de HTML5 Boilerplate: El HTML](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/html.md)
- 📖 [Documentación de HTML5 Boilerplate: Extender y personalizar](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/extend.md)

**[⬆ volver arriba](#tabla-de-contenidos)**

## Proyectos Relacionados

- [Fragmentos de HEAD para Atom](https://github.com/joshbuchea/atom-html-head-snippets) - Paquete de Atom para fragmentos de `HEAD`
- [Fragmentos de HEAD para Sublime Text](https://github.com/marcobiedermann/sublime-head-snippets) - Paquete de Sublime Text para fragmentos de `HEAD`
- [head-it](https://github.com/hemanth/head-it) - Interfaz CLI para fragmentos de `HEAD`
- [vue-head](https://github.com/ktquez/vue-head) - Manipulación de la información meta de la etiqueta `HEAD` para Vue.js

**[⬆ volver arriba](#tabla-de-contenidos)**

## Otros Formatos

- 📄 [PDF](https://gitprint.com/joshbuchea/HEAD/blob/master/README.md)

**[⬆ volver arriba](#tabla-de-contenidos)**

## 🌐 Traducciones

- 🇮🇩 [Bahasa](https://github.com/rijdz/HEAD)
- 🇧🇷 [Portugués Brasileño](https://github.com/Webschool-io/HEAD)
- 🇨🇳 [Chino (Simplificado)](https://github.com/Amery2010/HEAD)
- 🇩🇪 [Alemán](https://github.com/Shidigital/HEAD)
- 🇮🇹 [Italiano](https://github.com/Fakkio/HEAD)
- 🇯🇵 [Japonés](https://coliss.com/articles/build-websites/operation/work/collection-of-html-head-elements.html)
- 🇰🇷 [Coreano](https://github.com/Lutece/HEAD)
- 🇷🇺 [Ruso/Русский](https://github.com/Konfuze/HEAD)
- 🇪🇸 [Español](https://github.com/alvaroadlf/HEAD)
- 🇹🇷 [Turco/Türkçe](https://github.com/mkg0/HEAD)

**[⬆ volver arriba](#tabla-de-contenidos)**

## 🤝 Contribuir

**Abre un issue o una solicitud de extracción para sugerir cambios o adiciones.**

### Guía

El repositorio **HEAD** consiste en dos ramas:

#### 1. `master`

Esta rama consiste en el archivo `README.md` que se refleja en el sitio web [htmlhead.dev](https://htmlhead.dev/). Todos los cambios al contenido de la guía deben hacerse en este archivo.

Por favor, sigue estos pasos para las solicitudes de extracción:

{:.list-style-default}
- Modifica solo una etiqueta, o un conjunto relacionado de etiquetas a la vez
- Usa comillas dobles en los atributos
- No incluyas una barra diagonal al final en elementos de cierre automático — la especificación HTML5 dice que son opcionales
- Considera incluir un enlace a la documentación que respalde tu cambio

#### 2. `gh-pages`

Esta rama es responsable del sitio web [htmlhead.dev](https://htmlhead.dev/). Usamos [Jekyll](https://jekyllrb.com/) para desplegar el archivo `README.md` markdown a [GitHub Pages](https://pages.github.com/). Todas las modificaciones relacionadas con el sitio web deben hacerse en esta rama.

Puede ser útil revisar la [Documentación de Jekyll](https://jekyllrb.com/docs/home/) y entender cómo funciona Jekyll antes de trabajar en esta rama.

## 🌟 Contribuidores

Revisa todos los increíbles [contribuidores](https://github.com/joshbuchea/HEAD/graphs/contributors) 🤩

## 👤 Autor del proyecto

**Josh Buchea**

- GitHub: [@joshbuchea](https://github.com/joshbuchea)
- Mastodon: [@joshbuchea@hachyderm.io](https://hachyderm.io/@joshbuchea)

## 👤 Autor de la traducción

**Alvaro Araoz**

- GitHub: [@alvaroadlf](https://github.com/alvaroadlf)

## 💛 Apoyo por la traducción

Si este proyecto fue útil para ti o tu organización, considera apoyar mi trabajo directamente:

- ☕️ [Buy me a Ko-Fi](https://ko-fi.com/alvaro)

¡Toda ayuda cuenta, gracias! 🙏

— Josh

## 📝 Licencia

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ volver arriba](#tabla-de-contenidos)**