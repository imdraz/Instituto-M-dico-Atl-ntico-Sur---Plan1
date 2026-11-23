# Instituto Médico Atlántico Sur · Espacio Terapéutico del Sur

Sitio web institucional de un instituto médico con dos sedes: especialidades, equipo de especialistas, solicitud de turnos online, pagos y contacto por WhatsApp.

Sitio estático, hecho con HTML, CSS y JavaScript puro, sin frameworks ni dependencias. Está pensado para publicarse en GitHub Pages.

## Secciones

- **Inicio:** presentación del instituto y botón para solicitar turno.
- **Especialidades y Sedes:** 15 especialidades con filtro por sede, y mapas con cómo llegar a cada sede (las dos sedes comparten contenido).
- **Especialistas:** carrusel con hasta 15 especialistas. Todos son **provisorios** (ver abajo).
- **Solicitar Turno:** formulario encadenado (sede, especialidad, profesional, fecha y franja) con validación y consentimiento de datos.
- **Pagos:** botón de pago con Mercado Pago (enlace de ejemplo).
- **Aviso de privacidad:** texto basado en la Ley 25.326 de Argentina, con los servicios de terceros (Google Apps Script, WhatsApp, Google Calendar y Mercado Pago).
- **Contacto:** datos de cada sede, horarios y enlaces rápidos.
- **WhatsApp:** botón flotante y enlace de contacto para el asistente de WhatsApp.

## Estructura

```
index.html      Estructura y contenido de la página
styles.css      Estilos (colores y tipografía en las variables de :root)
script.js       Filtros, carrusel, turnos, validación y envío del formulario
apps-script/Code.gs   Backend de turnos (Google Apps Script)
img/            Fotos de especialidades y especialistas, logos y fondo
img/especialistas/provisorio.svg   Foto de reemplazo para especialistas provisorios
```

## Configuración

- **Backend de turnos:** `CONFIG.formEndpoint` en `script.js` apunta a la aplicación web de Google Apps Script (cuenta ojoahi065@gmail.com). El código está en `apps-script/Code.gs`.
- **WhatsApp:** número `5491177430739` en los enlaces `wa.me` de `index.html`. El asistente y los recordatorios (hasta 200 mensajes por mes) se implementan del lado del backend.
- **Google Calendar:** los turnos se registran en un calendario por especialidad mediante Apps Script. El cliente necesita una cuenta de Google.
- **Mercado Pago:** el botón de pago de la sección "Pagos" apunta a un enlace de ejemplo. Reemplazarlo por el enlace de pago real del cliente.
- **Especialistas (hasta 15):** objeto `PROFESIONALES` en `script.js` (uno por especialidad) y bloque de diapositivas en el carrusel de `index.html`. Todos están marcados como **provisorios**: confirmar nombre, especialidad, foto y sede con el cliente.
- **Profesionales y agenda:** objeto `PROFESIONALES` y rotación `PATRONES` en `script.js`.
- **Feriados:** lista `FERIADOS` en `script.js`. Hay que actualizarla cada año.
- **Textos y datos de contacto:** directamente en `index.html`, incluido el aviso de privacidad.
- **Colores:** variables `--color-*` al inicio de `styles.css`.

## Nota

Es una propuesta de demostración. Antes de usarla con datos reales, revisá los datos de contacto, los nombres y las fotos de los profesionales, los enlaces de WhatsApp y Mercado Pago, y el aviso de privacidad.
