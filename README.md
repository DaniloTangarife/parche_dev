# Parche Dev 2026

Sitio oficial del encuentro Parche Dev 2026, construido solo con HTML semántico.
Reto individual del Módulo 1 · HTML y CSS, RIWI.

Sitio publicado: https://danilotangarife.github.io/parche_dev/

## Páginas

- Inicio
- Agenda
- Ponentes
- Inscripción y confirmación
- Código de conducta

## Cómo verlo en tu computador

1. Clona el repositorio.
2. Ábrelo en VS Code.
3. Abre `index.html` con Live Preview.

## Decisiones que tomé

- **`<dl>` para los datos del evento:** fecha, hora, lugar y entrada son pares término–definición, no una lista de ítems sueltos, por eso usé una lista de descripción.
- **`<ol>` en «Lo que vas a encontrar»:** el orden importa porque va de lo general (charlas) a lo específico (café y networking). Si el orden no importara, habría usado `<ul>`.
- **`<table>` con `colspan` y `rowspan` en la agenda:** es la forma natural de representar dos salas paralelas y un taller que ocupa dos bloques.
- **`<section>` con `<h2>` en el inicio:** agrupa cada bloque temático («¿Qué es Parche Dev?», «Lo que vas a encontrar», «Para quién es») bajo su propio encabezado.
- **`<article>` por ponente:** cada perfil es contenido autónomo e independiente, con su propio `<h2>`, imagen y sesiones.
- **`<fieldset>` y `<legend>` en el formulario:** agrupan campos relacionados y dan contexto al lector de pantalla sin necesidad de CSS.

## Investiga (Ticket 5)

- **Espacios, tildes y arroba:** la URL codifica los caracteres especiales. Los espacios se vuelven `+` o `%20`, las tildes se convierten en secuencias como `%C3%A1`, y la arroba en `%40`.
- **Campos vacíos:** si el campo tiene `name`, aparece en la URL con valor vacío (`&campo=`); si no tiene `name`, el navegador lo ignora.
- **Por qué no usar `method="get"` con contraseñas:** los datos quedan visibles en la URL, guardados en el historial del navegador y registrados en los logs del servidor. Para datos sensibles se usa `method="post"`, que envía la información en el cuerpo de la petición.

## Lo que aprendí

- Un `id` debe ser único en toda la página; repetirlo rompe los `label` y el validador lo marca como error.
- El validador del W3C detecta errores de anidación (como `<br>` dentro de `<ol>` o `<p>` dentro de `<table>`) que a simple vista no se notan.
- La accesibilidad empieza en el HTML: `alt` descriptivo, `label` conectados con `for` e `id`, `aria-current` en el menú y enlaces «Saltar al contenido» hacen el sitio usable con teclado y lector de pantalla.

## Hecho por

Danilo Tangarife Bustamante · [GitHub](https://github.com/danilotangarife)