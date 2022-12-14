---
layout: correo
title: Web vitales
description: Métricas esenciales para un sitio saludable
hero: imagen/admin/BHaoqqR73jDWe6FL2kfw.png
authors:
  - felipewalton
date: '2020-04-30'
updated: '2020-07-21'
tags:
  - métrica
  - actuación
  - web-vitales
---

La optimización de la calidad de la experiencia del usuario es clave para el éxito a largo plazo de cualquier sitio en la web. Ya sea propietario de un negocio, comercializador o desarrollador, Web Vitals puede ayudarlo a cuantificar la experiencia de su sitio e identificar oportunidades para mejorar.

## Visión general

Web Vitals es una iniciativa de Google para proporcionar orientación unificada para señales de calidad que son esenciales para brindar una excelente experiencia de usuario en la web.

Google ha proporcionado una serie de herramientas a lo largo de los años para medir e informar sobre el rendimiento. Algunos desarrolladores son expertos en el uso de estas herramientas, mientras que a otros les resulta difícil mantenerse al día con la abundancia de herramientas y métricas.

Los propietarios de sitios no deberían tener que ser gurús del rendimiento para comprender la calidad de la experiencia que ofrecen a sus usuarios. La iniciativa Web Vitals tiene como objetivo simplificar el panorama y ayudar a los sitios a centrarse en las métricas más importantes, **Core Web Vitals** .

## Vitales principales de la web

Core Web Vitals es el subconjunto de Web Vitals que se aplica a todas las páginas web, debe ser medido por todos los propietarios de sitios y aparecerá en todas las herramientas de Google. Cada uno de los Core Web Vitals representa una faceta distinta de la experiencia del usuario, es medible [en el campo](/user-centric-performance-metrics/#how-metrics-are-measured) y refleja la experiencia del mundo real de un resultado crítico [centrado en el usuario](/user-centric-performance-metrics/#how-metrics-are-measured) .

Las métricas que componen Core Web Vitals [evolucionarán](#evolving-web-vitals) con el tiempo. El conjunto actual para 2020 se centra en tres aspectos de la experiencia del usuario: *carga* , *interactividad* y *estabilidad visual* , e incluye las siguientes métricas (y sus respectivos umbrales):

<div class="w-stack w-stack--center w-stack--md">
<img src="lcp_ux.svg" width="400px" height="350px" alt="Recomendaciones de umbral de pintura con contenido más grande"><img src="fid_ux.svg" width="400px" height="350px" alt="Recomendaciones de umbral de retardo de primera entrada"><img src="cls_ux.svg" width="400px" height="350px" alt="Recomendaciones de umbral de cambio de diseño acumulativo">
</div>

- **[Pintura con contenido más grande (LCP)](/lcp/)** : mide el rendimiento *de carga* . Para proporcionar una buena experiencia de usuario, LCP debe ocurrir dentro de los **2,5 segundos** desde que la página comienza a cargarse por primera vez.
- **[First Input Delay (FID)](/fid/)** : mide *la interactividad* . Para proporcionar una buena experiencia de usuario, las páginas deben tener un FID de menos de **100 milisegundos** .
- **[Cambio de diseño acumulativo (CLS)](/cls/)** : mide *la estabilidad visual* . Para proporcionar una buena experiencia de usuario, las páginas deben mantener un CLS inferior a **0,1.**

Para cada una de las métricas anteriores, para asegurarse de alcanzar el objetivo recomendado para la mayoría de sus usuarios, un buen umbral para medir es el **percentil 75** de cargas de página, segmentado en dispositivos móviles y de escritorio.

Las herramientas que evalúan el cumplimiento de Core Web Vitals deben considerar la aprobación de una página si cumple con los objetivos recomendados en el percentil 75 para las tres métricas anteriores.

{% Aside %} Para obtener más información sobre la investigación y la metodología detrás de estas recomendaciones, consulte: [Definición de los umbrales de métricas de Core Web Vitals](/defining-core-web-vitals-thresholds/) {% endAside %}

### Herramientas para medir e informar Core Web Vitals

Google cree que Core Web Vitals es fundamental para todas las experiencias web. Como resultado, se compromete a mostrar estas métricas [en todas sus herramientas populares](/vitals-tools/) . Las siguientes secciones detallan qué herramientas son compatibles con Core Web Vitals.

#### Herramientas de campo para medir Core Web Vitals

El[Informe de experiencia del usuario de Chrome](https://developers.google.com/web/tools/chrome-user-experience-report) recopila datos de medición de usuarios reales y anónimos para cada Core Web Vital. Estos datos permiten a los propietarios de sitios evaluar rápidamente su rendimiento sin necesidad de instrumentar análisis manualmente en sus páginas, y potencian herramientas como [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) y el [informe Core Web Vitals](https://support.google.com/webmasters/answer/9205520) de Search Console.

<div class="w-table-wrapper">
  <table>
    <tr>
      <td> </td>
      <td>LCP</td>
      <td>DEFENSOR</td>
      <td>CLS</td>
    </tr>
    <tr>
      <td><a href="https://developers.google.com/web/tools/chrome-user-experience-report">Informe de experiencia de usuario de Chrome</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr>
      <td><a href="https://developers.google.com/speed/pagespeed/insights/">Perspectivas de PageSpeed</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr>
      <td><a href="https://support.google.com/webmasters/answer/9205520">Consola de búsqueda (informe Core Web Vitals)</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
  </table>
</div>

{% Aside %} Para obtener orientación sobre cómo usar estas herramientas y qué herramienta es adecuada para su caso de uso, consulte: [Introducción a la medición de Web Vitals](/vitals-measurement-getting-started/) {% endAside %}

Los datos proporcionados por Chrome User Experience Report ofrecen una forma rápida de evaluar el rendimiento de los sitios, pero no proporcionan la telemetría detallada por página vista que a menudo es necesaria para diagnosticar, monitorear y reaccionar rápidamente a las regresiones con precisión. Como resultado, recomendamos enfáticamente que los sitios configuren su propio monitoreo de usuarios reales.

#### Medir Core Web Vitals en JavaScript

Cada uno de los Core Web Vitals se puede medir en JavaScript utilizando API web estándar.

La forma más fácil de medir todos los Core Web Vitals es usar la biblioteca de JavaScript [de web-vitals](https://github.com/GoogleChrome/web-vitals) , un contenedor pequeño, listo para producción, alrededor de las API web subyacentes que mide cada métrica de una manera que coincide con precisión con la forma en que todos los informan. Herramientas de Google enumeradas anteriormente.

Con la biblioteca [web-vitals](https://github.com/GoogleChrome/web-vitals) , medir cada métrica es tan simple como llamar a una sola función (consulte la documentación para conocer el [uso](https://github.com/GoogleChrome/web-vitals#usage) completo y los detalles de la [API](https://github.com/GoogleChrome/web-vitals#api) ):

```js
import {getCLS, getFID, getLCP} from 'web-vitals';

function sendToAnalytics(metric) {
  const body = JSON.stringify(metric);
  // Use `navigator.sendBeacon()` if available, falling back to `fetch()`.
  (navigator.sendBeacon && navigator.sendBeacon('/analytics', body)) ||
      fetch('/analytics', {body, method: 'POST', keepalive: true});
}

getCLS(sendToAnalytics);
getFID(sendToAnalytics);
getLCP(sendToAnalytics);
```

Una vez que haya configurado su sitio para usar la biblioteca [web-vitals](https://github.com/GoogleChrome/web-vitals) para medir y enviar sus datos Core Web Vitals a un punto final de análisis, el siguiente paso es agregar e informar sobre esos datos para ver si sus páginas cumplen con los umbrales recomendados para al menos el 75% de las visitas a la página.

Si bien algunos proveedores de análisis tienen compatibilidad integrada con las métricas de Core Web Vitals, incluso aquellos que no la tienen deben incluir características básicas de métricas personalizadas que le permitan medir Core Web Vitals en su herramienta.

Un ejemplo de esto es el [Informe Web Vitals](https://github.com/GoogleChromeLabs/web-vitals-report) , que permite a los propietarios de sitios medir sus Core Web Vitals utilizando Google Analytics. Para obtener orientación sobre cómo medir Core Web Vitals con otras herramientas de análisis, consulte [Mejores prácticas para medir Web Vitals en el campo](/vitals-field-measurement-best-practices/) .

También puede generar informes sobre cada uno de los Core Web Vitals sin escribir ningún código utilizando la [extensión de Chrome de Web Vitals](https://github.com/GoogleChrome/web-vitals-extension) . Esta extensión utiliza la biblioteca [web-vitals](https://github.com/GoogleChrome/web-vitals) para medir cada una de estas métricas y mostrárselas a los usuarios mientras navegan por la web.

Esta extensión puede ser útil para comprender el rendimiento de sus propios sitios, los sitios de sus competidores y la web en general.

<div class="w-table-wrapper">
  <table>
    <thead>
      <tr>
        <th> </th>
        <th>LCP</th>
        <th>DEFENSOR</th>
        <th>CLS</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><a href="https://github.com/GoogleChrome/web-vitals">web-vitales</a></td>
        <td>✔</td>
        <td>✔</td>
        <td>✔</td>
      </tr>
      <tr>
        <td><a href="https://github.com/GoogleChrome/web-vitals-extension">Extensión Web Vitals</a></td>
        <td>✔</td>
        <td>✔</td>
        <td>✔</td>
      </tr>
    </tbody>
  </table>
</div>

Alternativamente, los desarrolladores que prefieren medir estas métricas directamente a través de las API web subyacentes pueden consultar estas guías de métricas para obtener detalles de implementación:

- [Medir LCP en JavaScript](/lcp/#measure-lcp-in-javascript)
- [Medir FID en JavaScript](/fid/#measure-fid-in-javascript)
- [Medir CLS en JavaScript](/cls/#measure-cls-in-javascript)

{% Aside %} Para obtener orientación adicional sobre cómo medir estas métricas utilizando servicios de análisis populares (o sus propias herramientas de análisis internas), consulte: [Prácticas recomendadas para medir Web Vitals en el campo](/vitals-field-measurement-best-practices/) {% endAside %}

#### Herramientas de laboratorio para medir Core Web Vitals

Si bien todos los Core Web Vitals son, ante todo, métricas de campo, muchas de ellas también se pueden medir en el laboratorio.

La medición de laboratorio es la mejor manera de probar el rendimiento de las funciones durante el desarrollo, antes de que se lancen a los usuarios. También es la mejor manera de detectar regresiones de rendimiento antes de que sucedan.

Las siguientes herramientas se pueden utilizar para medir Core Web Vitals en un entorno de laboratorio:

<div class="w-table-wrapper">
  <table>
    <thead>
      <tr>
        <th> </th>
        <th>LCP</th>
        <th>DEFENSOR</th>
        <th>CLS</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><a href="https://developers.google.com/web/tools/chrome-devtools">Herramientas para desarrolladores de Chrome</a></td>
        <td>✔</td>
        <td>✘ (use <a href="/tbt/">TBT</a> en su lugar)</td>
        <td>✔</td>
      </tr>
      <tr>
        <td><a href="https://developers.google.com/web/tools/lighthouse">Faro</a></td>
        <td>✔</td>
        <td>✘ (use <a href="/tbt/">TBT</a> en su lugar)</td>
        <td>✔</td>
      </tr>
    </tbody>
  </table>
</div>

{% Aside %} Herramientas como Lighthouse que cargan páginas en un entorno simulado sin un usuario no pueden medir FID (no hay entrada de usuario). Sin embargo, la métrica del tiempo total de bloqueo (TBT) es medible en laboratorio y es un excelente proxy para FID. Las optimizaciones de rendimiento que mejoran TBT en el laboratorio deberían mejorar FID en el campo (consulte las recomendaciones de rendimiento a continuación). {% endAside%}

Si bien la medición de laboratorio es una parte esencial para brindar excelentes experiencias, no es un sustituto de la medición de campo.

El rendimiento de un sitio puede variar drásticamente según las capacidades del dispositivo del usuario, las condiciones de su red, qué otros procesos pueden estar ejecutándose en el dispositivo y cómo interactúan con la página. De hecho, la puntuación de cada una de las métricas de Core Web Vitals puede verse afectada por la interacción del usuario. Solo la medición de campo puede capturar con precisión la imagen completa.

### Recomendaciones para mejorar tus puntuaciones

Una vez que haya medido Core Web Vitals e identificado áreas de mejora, el siguiente paso es optimizar. Las siguientes guías ofrecen recomendaciones específicas sobre cómo optimizar sus páginas para cada uno de los Core Web Vitals:

- [Optimizar LCP](/optimize-lcp/)
- [Optimizar FID](/optimize-fid/)
- [Optimizar CLS](/optimize-cls/)

## Otros vitales web

Si bien Core Web Vitals son las métricas críticas para comprender y brindar una excelente experiencia de usuario, también existen otras métricas vitales.

Estos otros Web Vitals a menudo sirven como métricas proxy o complementarias para Core Web Vitals, para ayudar a capturar una parte más grande de la experiencia o para ayudar a diagnosticar un problema específico.

Por ejemplo, las métricas [Time to First Byte (TTFB)](/time-to-first-byte/) y [First Contentful Paint (FCP)](/fcp/) son aspectos vitales de la experiencia de *carga* y son útiles para diagnosticar problemas con LCP (tiempos de [respuesta del servidor](/overloaded-server/) lentos o [recursos que bloquean el renderizado](/render-blocking-resources/) , respectivamente) .

Del mismo modo, métricas como el [tiempo total de bloqueo (TBT)](/tbt/) y [el tiempo de interacción (TTI)](/tti/) son métricas de laboratorio que son vitales para detectar y diagnosticar posibles problemas de *interactividad* que afectarán a FID. Sin embargo, no forman parte del conjunto Core Web Vitals porque no se pueden medir en el campo ni reflejan un resultado [centrado en el usuario](/user-centric-performance-metrics/#how-metrics-are-measured) .

## Vitales web en evolución

Web Vitals y Core Web Vitals representan las mejores señales disponibles que los desarrolladores tienen hoy para medir la calidad de la experiencia en la web, pero estas señales no son perfectas y se deben esperar futuras mejoras o adiciones.

Los **Core Web Vitals** son relevantes para todas las páginas web y aparecen en todas las herramientas relevantes de Google. Los cambios en estas métricas tendrán un impacto de gran alcance; como tal, los desarrolladores deben esperar que las definiciones y los umbrales de Core Web Vitals sean estables y que las actualizaciones tengan un aviso previo y una cadencia anual predecible.

Los otros Web Vitals a menudo son específicos del contexto o de la herramienta, y pueden ser más experimentales que los Core Web Vitals. Como tal, sus definiciones y umbrales pueden cambiar con mayor frecuencia.

Para todos los Web Vitals, los cambios se documentarán claramente en este [REGISTRO DE CAMBIOS](http://bit.ly/chrome-speed-metrics-changelog) público.
