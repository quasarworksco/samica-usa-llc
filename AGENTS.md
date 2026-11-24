# Samica USA LLC · sitio web de DGP Global Group

Este repositorio es el sitio web de **Samica USA LLC** (cliente: Carlos Carreño). Lo publica GitHub Pages desde la rama `main`.

Estas instrucciones valen para Codex, Claude o cualquier asistente. Lee también `CONTEXTO-DGP.md`: explica quién es DGP Global Group, sus servicios y cómo prefiere trabajar el dueño. Respóndele en español sencillo.

## Cómo empezar: decide tú, pregunta lo mínimo
Cuando te digan "empecemos", **empieza a construir** con los datos de abajo, el logo y el rubro. No le des al dueño menús de opciones.
- **Estilo visual, estructura, colores, fuentes y textos:** si no están definidos, decídelos tú a partir del logo y del rubro (usa ui-ux-pro-max para elegir). Di en una línea qué elegiste.
- **Página de ejemplo:** si hay enlaces, revísalos y toma ideas de estructura, sin copiar diseño ni textos. Si no hay, sigue sin ella.
- **Idiomas:** si no se indicó, usa el idioma del rubro y del cliente (español por defecto) y deja el sitio listo para agregar inglés.
- **Lo único que no puedes inventar:** contacto (correo, teléfono, WhatsApp, dirección, horario), redes sociales, y servicios con precios reales. Si falta, pídelo en **un solo mensaje corto**, o termina el sitio con lo que haya (sin datos falsos, ocultando lo que no exista) y al final haz la lista de lo que falta.
- Para pedidos típicos (panel `/admin`, formulario, bilingüe, `/entrega`) sigue las recetas de `CONTEXTO-DGP.md` sin preguntar.

## Datos que ya tenemos
- **Empresa:** Samica USA LLC
- **Rubro / qué hace:** Telehealth
- **Estilo visual:** Glassmorphism
- **Página de ejemplo:** _sin definir_
- **Correo:** _sin definir_
- **Teléfono / WhatsApp:** +13522330463
- **Redes sociales:** _sin definir_
- **Idiomas:** Bilingüe ES/EN con botón
- **Notas:** _sin definir_
- **Logo:** _no se subió: usa el nombre como logotipo tipográfico y pídelo en la lista de lo que falta_

## Skills de diseño instaladas (úsalas)
Este repositorio trae el kit de diseño de DGP en `.agents/skills/` (Codex) y en `.claude/skills/` (Claude Code); es el mismo contenido. Si tu herramienta no muestra una skill, abre su `SKILL.md` y sigue sus instrucciones. Úsalo en este orden:
1. **impeccable** → empieza con su comando `init` (`./.agents/skills/impeccable/scripts/impeccable context` muestra el contexto) para guardar PRODUCT.md. Las respuestas a su entrevista (para quién es, qué necesita lograr) sácalas de este archivo, de `CONTEXTO-DGP.md` y del rubro; no hagas una ronda de preguntas aparte.
   Para consultar estilos, paletas y fuentes: `python3 .agents/skills/ui-ux-pro-max/scripts/search.py "<tipo de negocio>"`.
2. **ui-ux-pro-max** → busca el estilo, la paleta, las fuentes y los íconos recomendados para este tipo de negocio antes de decidir el diseño.
3. **frontend-design** y **taste-skill** → dirección visual distintiva, sin plantillas genéricas ni "AI slop".
4. **animate / improve-animations / choreograph** (Emil Kowalski) → animaciones con propósito, suaves y rápidas.
5. Antes de entregar: los comandos `critique` y `audit` de impeccable y **review-animations**; corrige lo que salga P0/P1. Revisa el sitio en el navegador a 390 px y a escritorio.

## Reglas de diseño (obligatorias)
- **Todo el sitio con un solo sistema visual:** las páginas nuevas (`/admin`, `/entrega` u otras) reutilizan los colores, fuentes, componentes, animaciones y transiciones de la página principal (ver "Coherencia visual" en `CONTEXTO-DGP.md`). Documenta ese sistema en `DESIGN.md` en cuanto la página principal esté lista.
- **Diseño premium basado en el logo:** saca la paleta de colores, el estilo y la personalidad del logo (`assets/logo`). El sitio debe sentirse hecho a la medida de esa marca.
- **Sin emojis.** Solo **iconos SVG** (inline o de una librería de iconos), consistentes en estilo y grosor.
- Tipografías de Google Fonts que combinen con la marca; jerarquía clara y mucho aire.
- **Mobile first:** perfecto en celular (botones grandes, nada se sale de la pantalla) y en escritorio.
- Animaciones suaves y discretas (aparecer al hacer scroll, hover); respeta `prefers-reduced-motion`.
- Botón flotante de **WhatsApp** y llamadas a la acción claras (cotizar, llamar, escribir) si hay contacto.
- **SEO básico:** `<title>`, meta description, Open Graph con imagen, favicon a partir del logo, `lang` correcto, textos alternativos en las imágenes, datos estructurados LocalBusiness si hay dirección o teléfono.
- Rendimiento: imágenes optimizadas (webp), carga diferida, sin librerías pesadas innecesarias.
- Nunca pidas ni muestres datos sensibles (SSN, ITIN, documentos de identidad) en formularios.
- Pie de página: © año, nombre de la empresa y "Diseñado por DGP Global Group" con enlace a https://dgpglobalgroup.com
- **Deja el CSS listo para la barra de prueba de DGP:** suma `var(--dgp-trial-h,0px)` al `top` del header fijo, a `scroll-padding-top`, al `padding-top` del hero, a la barra de progreso de scroll y al enlace "saltar al contenido". El panel pone y quita esa barra (`assets/dgp-trial.js`); no la agregues a mano.

## Cómo trabajar
- Todo el sitio vive en `index.html` (CSS y JS dentro) salvo imágenes en `assets/`, a menos que el proyecto pida varias páginas.
- Cuando termines, haz commit y push a `main`: GitHub Pages publica solo.

## Página de entrega (/entrega) — cuando el sitio esté listo
Cuando el cliente apruebe el sitio (o te digan "ya está listo"), crea `entrega/index.html` (se ve en `/entrega`). Es la página que DGP le muestra al cliente para entregarle su web:
- Mismo diseño premium y colores de la marca del sitio, sin emojis (solo iconos SVG), perfecta en celular. En el idioma del sitio (si es bilingüe, con botón ES/EN).
- `<meta name="robots" content="noindex">` y que **no** aparezca en el menú ni en el sitemap del sitio.
- Contenido:
  1. Título tipo "Tu sitio web está listo" con el logo y un botón grande para abrir el sitio.
  2. Qué se entregó: las páginas y secciones del sitio, y las funciones (botón de WhatsApp, formulario, idiomas, galería, etc.).
  3. Lo que ya queda listo: candado de seguridad (https), adaptado a celular, SEO básico para Google (título, descripción, sitemap), favicon y vista previa al compartir en WhatsApp/redes.
  4. Un **código QR** que lleve al sitio (generado en la página, para imprimir o compartir) y un botón "Copiar enlace".
  5. Próximos pasos recomendados: compartir el enlace en sus redes y en la bio de Instagram, agregarlo a su perfil de Google Business, y pedir reseñas a sus clientes.
  6. Soporte: "¿Cambios o dudas? Escríbenos" con WhatsApp +1 (239) 823-1738 (https://wa.me/12398231738) y info@dgpglobalgroup.com.
  7. Un botón "Déjanos tu reseña en Google" → https://g.page/r/CbcyuFX7hqvuEAI/review
  8. Pie: "Diseñado por DGP Global Group" con enlace a https://dgpglobalgroup.com
- Haz commit y push a `main`, y responde con el enlace final de `/entrega`.
