# Web_documentado
<!DOCTYPE html>
<!--
  ╔══════════════════════════════════════════════════════════════════════════════╗
  ║                    SERVITIC · Web Empresarial Comentada                     ║
  ║                  Versión didáctica para estudiantes de HTML/CSS             ║
  ╠══════════════════════════════════════════════════════════════════════════════╣
  ║  AUTOR:        SERVITIC                                                     ║
  ║  VERSIÓN:      2.0 Didáctica                                                ║
  ║  DESCRIPCIÓN:  Página web completa con HTML5 semántico + CSS embebido       ║
  ║  TECNOLOGÍAS:  HTML5 · CSS3 · Google Fonts                                  ║
  ╠══════════════════════════════════════════════════════════════════════════════╣
  ║  ÍNDICE DE SECCIONES:                                                       ║
  ║  1. <head>      → Metadatos, fuentes y estilos CSS                          ║
  ║  2. <header>    → Cabecera fija con logo y navegación                       ║
  ║  3. <section#inicio>  → Hero / portada principal                            ║
  ║  4. <section#servicios> → Tarjetas de servicios                             ║
  ║  5. <section#nosotros> → Quiénes somos / About                              ║
  ║  6. <section.cta-band> → Banda de llamada a la acción                       ║
  ║  7. <section#contacto> → Formulario de contacto                             ║
  ║  8. <footer>    → Pie de página con info y LOPD                             ║
  ╠══════════════════════════════════════════════════════════════════════════════╣
  ║  CONCEPTOS CLAVE QUE APRENDERÁS:                                            ║
  ║  ✓ Estructura semántica HTML5                                               ║
  ║  ✓ Variables CSS (custom properties)                                        ║
  ║  ✓ Flexbox y CSS Grid para maquetación                                      ║
  ║  ✓ Diseño responsive con Media Queries                                      ║
  ║  ✓ Pseudo-elementos ::before y ::after                                      ║
  ║  ✓ Transiciones y animaciones CSS                                           ║
  ║  ✓ Formularios accesibles HTML                                              ║
  ║  ✓ SVG inline para iconos escalables                                        ║
  ╚══════════════════════════════════════════════════════════════════════════════╝
-->

<!--
  ════════════════════════════════════════════════════════
  DOCTYPE: Declaración de tipo de documento
  ════════════════════════════════════════════════════════
  "<!DOCTYPE html>" le dice al navegador que use HTML5.
  SIEMPRE debe ir en la primera línea, antes de cualquier
  otra cosa. Sin esto, el navegador entra en "modo quirks"
  y puede interpretar el código de forma incorrecta.

  💡 ALTERNATIVA HISTÓRICA (ya NO se usa):
     <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" ...>

  🎯 EJERCICIO: Borra esta línea, recarga y observa
     si el diseño cambia. Luego ponla de nuevo.
-->
<html lang="es">
<!--
  <html lang="es">
  ─────────────────
  Etiqueta raíz que envuelve TODO el contenido de la página.
  El atributo "lang" es muy importante porque:
    → Los lectores de pantalla (para personas con discapacidad visual)
      saben en qué idioma pronunciar el texto.
    → Google y otros buscadores indexan mejor el contenido.
    → El navegador puede ofrecer traducción automática correcta.

  VALORES COMUNES:
    lang="es"    → Español
    lang="en"    → Inglés
    lang="fr"    → Francés
    lang="es-419"→ Español latinoamericano

  🎯 EJERCICIO: Cambia lang="es" por lang="en" y observa
     qué pasa cuando el navegador ofrece traducir la página.
-->

<!-- ════════════════════════════════════════════════════════
     SECCIÓN 1: HEAD — La "cabeza" invisible de la página
     ════════════════════════════════════════════════════════
     Todo lo que está dentro de <head> NO se muestra en pantalla.
     Contiene información SOBRE la página (metadatos) que el
     navegador, Google y otros servicios necesitan para funcionar.
     Es como el "pasaporte" de tu página web.
-->
<head>

  <!-- CHARSET: Codificación de caracteres
       ─────────────────────────────────────
       Le dice al navegador qué "idioma" usa el archivo para
       guardar los caracteres. UTF-8 soporta prácticamente
       todos los idiomas y símbolos del mundo (ñ, á, é, €, 中, etc.)

       SIN ESTO: verías ????? o caracteres raros en vez de tildes.

       💡 ALTERNATIVA (antigua, evitar):
          <meta charset="ISO-8859-1">  → Solo español/europeo occidental

       🎯 EJERCICIO: Cambia UTF-8 por ISO-8859-1 y observa qué
          pasa con la "ñ" de "Quiénes" en el menú. -->
  <meta charset="UTF-8" />

  <!-- VIEWPORT: Control del tamaño en dispositivos móviles
       ──────────────────────────────────────────────────────
       Sin este meta, los móviles muestran la web como si fuera
       un escritorio pequeñísimo y el usuario tendría que hacer zoom.

       DESGLOSE del contenido:
         width=device-width → El ancho de la página = ancho real del dispositivo
         initial-scale=1.0  → Nivel de zoom inicial = 1 (sin zoom)

       💡 VARIANTE con zoom deshabilitado (NO recomendado por accesibilidad):
          <meta name="viewport" content="width=device-width,
                initial-scale=1.0, user-scalable=no">

       🎯 EJERCICIO: Comenta esta línea con <!-- --> y abre la web
          en un móvil real o con F12 > modo responsive. ¡Verás la diferencia! -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <!-- TITLE: Título de la pestaña del navegador
       ──────────────────────────────────────────
       Aparece en:
         → La pestaña del navegador
         → Los resultados de Google (máx. 60 caracteres recomendados)
         → Cuando guardas la página en favoritos
         → Cuando compartes el enlace en redes sociales

       BUENA PRÁCTICA: "Nombre de página · Nombre empresa"

       🎯 EJERCICIO: Crea diferentes títulos para cada sección
          y cámbialos dinámicamente con JavaScript:
          document.title = "Servicios · SERVITIC"; -->
  <title>SERVITIC · Servicios Tecnológicos</title>

  <!-- GOOGLE FONTS: Carga de fuentes tipográficas externas
       ──────────────────────────────────────────────────────
       Las fuentes del sistema (Arial, Times New Roman...) son
       limitadas y aburridas. Google Fonts ofrece cientos gratis.

       Se necesitan TRES etiquetas para cargar Google Fonts de forma
       eficiente usando "preconnect" (conexión anticipada):

       1. preconnect a googleapis.com → Donde están los metadatos
       2. preconnect a gstatic.com    → Donde están los archivos de fuente
       3. link rel="stylesheet"       → Carga la hoja de estilos con la fuente

       "crossorigin" en el 2º preconnect indica que se hace una
       petición a un dominio diferente al de nuestra web.

       FUENTE ELEGIDA: Poppins (pesos 300, 400, 500, 600, 700, 800)
         → Moderna, geométrica, muy legible. Ideal para tecnología.

       💡 ALTERNATIVA SIN INTERNET (fuentes locales):
          @font-face {
            font-family: 'MiFuente';
            src: url('fonts/mifuente.woff2') format('woff2');
          }

       🎯 EJERCICIO: Prueba otras fuentes de Google Fonts:
          - Cambiar "Poppins" por "Nunito" para un look más redondeado
          - Cambiar "Poppins" por "Roboto" para un look más técnico
          - Combinar dos fuentes: una para títulos y otra para cuerpo -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet" />

  <!-- ══════════════════════════════════════════════════════════
       ESTILOS CSS — Toda la apariencia visual de la página
       ══════════════════════════════════════════════════════════
       El CSS está escrito DENTRO del HTML usando <style></style>.
       Esto se llama CSS "embebido" o "interno".

       VENTAJA: Un solo archivo .html es más fácil de distribuir.
       DESVENTAJA: Si tienes varias páginas, tienes que repetir el CSS.

       💡 LA MEJOR PRÁCTICA para proyectos reales es usar un archivo
          externo separado: <link rel="stylesheet" href="styles.css">
          Así todas las páginas comparten el mismo CSS.

       🎯 EJERCICIO AVANZADO: Mueve todo el contenido del <style>
          a un archivo llamado "styles.css" en la misma carpeta y
          enlázalo con: <link rel="stylesheet" href="styles.css">
  -->
  <style>

  /*
  ┌─────────────────────────────────────────────────────────────────────────┐
  │  VARIABLES CSS (Custom Properties)                                      │
  │  Definidas en :root para usarlas en todo el documento                   │
  └─────────────────────────────────────────────────────────────────────────┘

  :root es el selector que representa el elemento <html>.
  Al definir variables aquí, están disponibles en TODA la página.

  Las variables CSS se declaran con dos guiones: --nombre-variable
  Y se usan con la función: var(--nombre-variable)

  VENTAJA ENORME: Si quieres cambiar el color naranja de toda la web,
  solo cambias UN valor aquí en lugar de buscar y reemplazar en 100 sitios.

  💡 ALTERNATIVA: También puedes definir variables en elementos concretos:
     .mi-componente { --color-local: red; }
     → Solo disponible dentro de .mi-componente

  🎯 EJERCICIO: Cambia --orange: #FF6B1A por --orange: #e91e63 (rosa)
     y observa cómo TODA la web cambia de color de acento instantáneamente.
  */
  :root {

    /* ── PALETA DE GRISES ──────────────────────────────────────
       Usamos una escala de grises del más oscuro al más claro.
       El número indica la "oscuridad": 950=casi negro, 100=casi blanco.
       Esta convención viene del sistema de colores de Tailwind CSS. */

    --gray-950: #111111;  /* Fondo principal de la página — casi negro */
    --gray-900: #1a1a1a;  /* Fondo de header, hero y secciones alternativas */
    --gray-800: #242424;  /* Fondo de inputs de formulario y barra de stats */
    --gray-700: #2e2e2e;  /* Bordes de cards y separadores */
    --gray-600: #3a3a3a;  /* Bordes sutiles y placeholders */
    --gray-400: #888888;  /* Texto secundario / descripciones */
    --gray-300: #aaaaaa;  /* Texto de navegación y etiquetas */
    --gray-100: #f5f5f5;  /* Casi blanco — hover del botón blanco */
    --white:    #ffffff;  /* Blanco puro — títulos y texto principal */

    /* ── PALETA NARANJA (color de acento principal) ─────────────
       El naranja es el color identitario de SERVITIC.
       Usamos variantes para distintos estados (hover, fondos, bordes). */

    --orange:        #FF6B1A;              /* Naranja principal — botones, iconos */
    --orange-light:  #FF8C47;              /* Naranja más claro — hover de botones */
    --orange-dark:   #E05500;              /* Naranja más oscuro — gradiente CTA */
    --orange-soft:   rgba(255,107,26,0.12);/* Naranja muy transparente — fondos suaves */
    --orange-border: rgba(255,107,26,0.3); /* Naranja semi-transparente — bordes */

    /*
    SOBRE rgba(): Es una función de color con 4 parámetros:
      rgba(rojo, verde, azul, opacidad)
      → Rojo: 0-255 (255,107,26 es el naranja #FF6B1A en decimal)
      → Opacidad: 0=invisible, 1=sólido, 0.12=12% visible

    🎯 EJERCICIO: Cambia el color de acento a azul:
       --orange:        #1A6BFF;
       --orange-light:  #478CFF;
       --orange-dark:   #0047E0;
       --orange-soft:   rgba(26,107,255,0.12);
       --orange-border: rgba(26,107,255,0.3);
    */

    /* ── SOMBRAS ────────────────────────────────────────────────
       Las sombras dan profundidad y sensación 3D a los elementos.
       box-shadow: desplazamiento-X desplazamiento-Y difuminado color */

    --shadow-sm: 0 2px 8px  rgba(0,0,0,0.25); /* Sombra pequeña — header */
    --shadow-md: 0 4px 20px rgba(0,0,0,0.35); /* Sombra media — cards hover */
    --shadow-lg: 0 8px 40px rgba(0,0,0,0.45); /* Sombra grande — modales */

    /* ── LAYOUT Y ESTRUCTURA ────────────────────────────────────*/
    --header-h: 70px;   /* Altura del header fijo — importante para el padding del hero */
    --max-w:    1160px; /* Ancho máximo del contenido — evita líneas de texto muy largas */
    --radius:   10px;   /* Radio de esquinas — para botones e inputs */
    --radius-lg:16px;   /* Radio mayor — para tarjetas y secciones */

    /* ── TIPOGRAFÍA ─────────────────────────────────────────────
       Definimos la fuente en una variable para cambiarla fácilmente. */
    --font: 'Poppins', sans-serif;
    /*
    'Poppins' = fuente de Google que cargamos arriba
    sans-serif = fuente de respaldo si Poppins no carga
    (Arial, Helvetica, etc. según el sistema del usuario)
    */
  }

  /*
  ┌─────────────────────────────────────────────────────────────────────────┐
  │  RESET CSS — Eliminar estilos por defecto del navegador                 │
  └─────────────────────────────────────────────────────────────────────────┘

  Cada navegador (Chrome, Firefox, Safari...) tiene sus propios estilos
  por defecto para los elementos HTML. Para que nuestra web se vea IGUAL
  en todos, primero "reseteamos" estos estilos.

  El selector * selecciona TODOS los elementos de la página.
  El selector *::before y *::after selecciona los pseudo-elementos
  (contenido generado por CSS que veremos más adelante).

  box-sizing: border-box es MUY IMPORTANTE:
    - Por defecto (content-box): width=200px significa 200px de CONTENIDO,
      y el padding y border se suman por fuera → el elemento ocupa MÁS de 200px
    - Con border-box: width=200px incluye padding y border → siempre 200px exactos
    → Esto hace los cálculos de tamaño MUCHO más predecibles.

  🎯 EJERCICIO: Prueba a quitar "box-sizing: border-box" de un input
     y añade padding: 20px. Verás cómo se "sale" de su contenedor.
  */
  *, *::before, *::after {
    box-sizing: border-box; /* Incluir padding y border dentro del ancho declarado */
    margin: 0;              /* Eliminar márgenes por defecto (ej: <h1> tiene margin arriba) */
    padding: 0;             /* Eliminar rellenos por defecto (ej: <ul> tiene padding izquierdo) */
  }

  /* scroll-behavior: smooth → En lugar de saltar bruscamente al hacer clic
     en un enlace de anclaje (#servicios), hace un desplazamiento suave.
     Solo afecta a los saltos internos de la página (#id). */
  html { scroll-behavior: smooth; }

  /*
  Estilos base del <body>: afectan a TODO el contenido visible.
  Si cambias aquí la fuente, cambias TODA la web.
  */
  body {
    font-family: var(--font);       /* Fuente Poppins (definida en :root) */
    background: var(--gray-950);    /* Fondo casi negro de toda la página */
    color: var(--gray-300);         /* Color de texto por defecto (gris claro) */
    font-size: 1rem;                /* 1rem = 16px (tamaño base del navegador) */
    line-height: 1.7;               /* Interlineado: 1.7 × 16px = 27.2px entre líneas */
    overflow-x: hidden;             /* Ocultar scrollbar horizontal si algo se sale */
  }
  /*
  💡 SOBRE REM vs PX:
     px = píxeles absolutos. 16px siempre son 16px.
     rem = relativo al tamaño base del navegador.
           Si el usuario aumenta el texto del navegador, los rem escalan.
           MEJOR para accesibilidad. Úsalo para fuentes y espaciados.
     em = relativo al tamaño del elemento padre. Más complejo de gestionar.

  🎯 EJERCICIO: Cambia font-size a 1.2rem y observa cómo escala todo.
  */

  /* Resetear los enlaces: por defecto son azules y subrayados.
     transition: color .2s → el cambio de color al hacer hover tarda 0.2 segundos */
  a {
    color: inherit;          /* Heredar el color del elemento padre */
    text-decoration: none;   /* Quitar el subrayado */
    transition: color .2s;   /* Animación suave al cambiar de color */
  }

  ul { list-style: none; }   /* Quitar los puntos/números de las listas */
  img, svg { display: block; } /* Eliminar el espacio en blanco extra debajo de imágenes */

  /* ── CLASE UTILITARIA: .accent ─────────────────────────────
     Una clase de "utilidad" es reutilizable en cualquier elemento.
     Simplemente colorea el texto de naranja.
     Uso: <span class="accent">texto naranja</span> */
  .accent { color: var(--orange); }

  /*
  ┌─────────────────────────────────────────────────────────────────────────┐
  │  .container — Contenedor centrado con ancho máximo                      │
  └─────────────────────────────────────────────────────────────────────────┘

  Este patrón es uno de los más usados en diseño web.
  Centra el contenido y evita que en pantallas muy anchas el texto
  se extienda de borde a borde (difícil de leer).

  margin: 0 auto → 0px arriba/abajo, auto izquierda/derecha.
  "auto" en los márgenes horizontales centra el elemento si tiene un ancho definido.

  padding: 0 1.5rem → 0 arriba/abajo, 1.5rem (24px) a los lados.
  Esto deja un "respiro" en móviles cuando el contenido llega al borde.

  🎯 EJERCICIO: Cambia --max-w a 800px y observa cómo se estrecha el contenido.
     Luego prueba con 100% para ver por qué usamos un máximo.
  */
  .container {
    max-width: var(--max-w); /* Ancho máximo: 1160px */
    margin: 0 auto;          /* Centrar horizontalmente */
    padding: 0 1.5rem;       /* Margen lateral de 24px para no pegarse a los bordes */
  }

  /*
  ┌─────────────────────────────────────────────────────────────────────────┐
  │  .pill — Etiqueta/badge decorativa pequeña                              │
  └─────────────────────────────────────────────────────────────────────────┘
  Usada para títulos de sección tipo "Qué ofrecemos" o "Sobre nosotros".
  Le da un look moderno y categoriza visualmente el contenido.
  */
  .pill {
    display: inline-block;             /* Para poder darle padding, pero sin ocupar toda la línea */
    background: var(--orange-soft);    /* Fondo naranja muy transparente (12%) */
    color: var(--orange);              /* Texto naranja sólido */
    border: 1px solid var(--orange-border); /* Borde naranja semi-transparente */
    border-radius: 999px;              /* Radio muy grande → siempre ovalado (pastilla) */
    padding: .28rem .9rem;             /* Relleno vertical pequeño, horizontal mayor */
    font-size: .72rem;                 /* Texto pequeño: 0.72 × 16px ≈ 11.5px */
    font-weight: 600;                  /* Semi-negrita */
    letter-spacing: .08em;            /* Espaciado entre letras → se lee mejor en mayúsculas */
    text-transform: uppercase;         /* Todo en MAYÚSCULAS */
    margin-bottom: .85rem;             /* Separación con el título de abajo */
  }

  /*
  ┌─────────────────────────────────────────────────────────────────────────┐
  │  .section-header — Encabezado centrado de cada sección                  │
  └─────────────────────────────────────────────────────────────────────────┘
  Patrón repetido en varias secciones: pill + título + descripción, centrados.
  max-width: 580px con margin: 0 auto lo centra y limita el ancho del texto.
  */
  .section-header {
    text-align: center;       /* Centrar texto horizontalmente */
    max-width: 580px;         /* Limitar ancho para mejor legibilidad */
    margin: 0 auto 3.5rem;   /* Centrar + 3.5rem de separación con el contenido de abajo */
  }

  .section-header h2 {
    /* clamp(min, preferido, max): función CSS para tamaños fluidos
       → En pantallas pequeñas: mínimo 1.8rem
       → En pantallas medianas: 3.5vw (3.5% del ancho de pantalla)
       → En pantallas grandes: máximo 2.6rem
       🎯 EJERCICIO: Cambia los valores y observa cómo escala el título */
    font-size: clamp(1.8rem, 3.5vw, 2.6rem);
    font-weight: 700;
    color: var(--white);
    line-height: 1.2;    /* Interlineado compacto para títulos grandes */
    margin-bottom: .6rem;
  }

  .section-header p {
    font-size: .95rem;
    color: var(--gray-400); /* Texto gris más tenue para subtítulos */
  }

  /*
  ┌─────────────────────────────────────────────────────────────────────────┐
  │  BOTONES — Sistema de variantes                                         │
  └─────────────────────────────────────────────────────────────────────────┘

  Usamos una clase base (.btn) + clases modificadoras (.btn-primary, etc.)
  Esto es el patrón BEM (Block Element Modifier) simplificado.

  display: inline-flex → Flex pero sin ocupar toda la línea.
  Permite centrar el contenido del botón (ícono + texto) verticalmente.
  */
  .btn {
    display: inline-flex;   /* Flex "en línea" para no romper el flujo del texto */
    align-items: center;    /* Centrar contenido verticalmente */
    gap: .4rem;             /* Espacio entre ícono y texto si los hay */
    padding: .72rem 1.8rem; /* Relleno vertical y horizontal del botón */
    border-radius: var(--radius); /* Esquinas redondeadas */
    font-family: var(--font);     /* Asegurar que el botón use nuestra fuente */
    font-size: .9rem;
    font-weight: 600;
    cursor: pointer;        /* Mano al pasar el ratón (es un botón, no texto) */
    border: none;           /* Quitar el borde nativo de <button> */
    transition: all .22s;   /* Animar TODOS los cambios en 0.22 segundos */
    text-decoration: none;  /* Por si el botón es un <a>, quitar subrayado */
  }

  /* VARIANTE PRIMARIA: naranja sólido — acción principal */
  .btn-primary {
    background: var(--orange);
    color: var(--white);
    /* box-shadow con color naranja semi-transparente simula un "glow" */
    box-shadow: 0 4px 18px rgba(255,107,26,.35);
  }
  /* Estado hover: más claro + se mueve hacia arriba + sombra más intensa */
  .btn-primary:hover {
    background: var(--orange-light);
    transform: translateY(-2px);              /* Subir 2px = efecto de "levantación" */
    box-shadow: 0 6px 24px rgba(255,107,26,.45);
  }

  /* VARIANTE OUTLINE: transparente con borde — acción secundaria */
  .btn-outline {
    background: transparent;
    color: var(--white);
    border: 1.5px solid rgba(255,255,255,.25); /* Borde blanco semi-transparente */
  }
  .btn-outline:hover {
    border-color: var(--orange);
    color: var(--orange);
    transform: translateY(-2px);
  }

  /* VARIANTE BLANCO: para fondos de color (la banda naranja CTA) */
  .btn-white {
    background: var(--white);
    color: var(--orange-dark);
    font-weight: 700;
  }
  .btn-white:hover { background: var(--gray-100); transform: translateY(-2px); }

  /*
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 2: HEADER — Cabecera fija de la página                         ║
  ╚══════════════════════════════════════════════════════════════════════════╝

  position: fixed → El header "flota" y no se mueve al hacer scroll.
  Permanece siempre visible en la parte superior.

  Importante: cuando un elemento es "fixed", sale del flujo normal
  del documento. Por eso el hero tiene padding-top: calc(var(--header-h) + 5rem)
  para que el contenido de abajo no quede DEBAJO del header.

  z-index: 200 → El header está "encima" de todos los demás elementos.
  Los elementos sin z-index tienen z-index: auto (≈0).
  Cuanto mayor el número, más "arriba" visualmente.

  🎯 EJERCICIO: Cambia position: fixed por position: sticky.
     ¿Qué diferencia notas? (sticky sigue el scroll hasta su posición).
  */
  .site-header {
    position: fixed;
    top: 0; left: 0; right: 0; /* Pegado a los 3 lados superiores */
    z-index: 200;               /* Encima de todo */
    height: var(--header-h);    /* Altura fija de 70px */
    background: var(--gray-900);
    border-bottom: 1px solid var(--gray-800); /* Línea separadora sutil */
    box-shadow: var(--shadow-sm);             /* Sombra sutil debajo */
  }

  /*
  .header-inner usa Flexbox para colocar logo y nav en la misma línea.

  Flexbox es ideal para layouts de UNA dimensión (fila o columna).
  CSS Grid es mejor para layouts de DOS dimensiones (filas Y columnas).

  align-items: center → Alinear verticalmente al centro de los 70px de altura.
  */
  .header-inner {
    display: flex;
    align-items: center;
    height: 100%;
    max-width: var(--max-w);
    margin: 0 auto;
    padding: 0 1.5rem;
  }

  /* Logo: ocupa el 20% del ancho del header
     flex: 0 0 20% = no crece (0), no encoge (0), base 20%
     El 0 0 evita que el logo se estire o comprima. */
  .logo-wrap { flex: 0 0 20%; }

  .logo {
    display: inline-flex;
    align-items: center;
    gap: .55rem; /* Espacio entre el ícono SVG y el texto "SERVITIC" */
  }

  .logo-icon { flex-shrink: 0; } /* Evitar que el ícono SVG se comprima */

  .logo-text {
    font-size: 1.35rem;
    font-weight: 800;  /* Extra-negrita */
    color: var(--white);
    letter-spacing: -.02em; /* Letras ligeramente más juntas — look moderno */
  }

  /* Navegación: ocupa el 80% restante
     margin-left: auto empuja la nav hacia la derecha (lo que quede libre).
     Combinado con flex del contenedor, esto centra el logo a la izquierda
     y la navegación a la derecha. */
  .main-nav {
    flex: 0 0 80%;
    margin-left: auto;
  }

  /* Los elementos del menú en fila, alineados a la derecha */
  .main-nav ul {
    display: flex;
    align-items: center;
    justify-content: flex-end; /* Alinear a la derecha */
    gap: .1rem; /* Pequeño espacio entre ítems */
  }

  /* Cada enlace del menú */
  .main-nav a {
    padding: .48rem .9rem;
    border-radius: var(--radius);
    font-size: .88rem;
    font-weight: 500;
    color: var(--gray-300);
    transition: all .2s;
  }

  /* Hover del menú: fondo gris y texto blanco */
  .main-nav a:hover {
    color: var(--white);
    background: var(--gray-800);
  }

  /* Botón CTA del menú: el único naranja, destaca entre los grises
     !important fuerza estos estilos sobre los de .main-nav a */
  .nav-cta {
    background: var(--orange) !important;
    color: var(--white) !important;
    font-weight: 600 !important;
    margin-left: .6rem;
    box-shadow: 0 2px 12px rgba(255,107,26,.3);
  }
  .nav-cta:hover {
    background: var(--orange-light) !important;
    transform: translateY(-1px);
  }

  /*
  ┌─────────────────────────────────────────────────────────────────────────┐
  │  MENÚ HAMBURGUESA — Para móviles (CSS puro, sin JavaScript)             │
  └─────────────────────────────────────────────────────────────────────────┘

  TÉCNICA AVANZADA: Usar un <input type="checkbox"> invisible como "interruptor".
  Cuando el usuario hace clic en el ícono hamburguesa (que es un <label>),
  activa/desactiva el checkbox. Con CSS podemos detectar si está marcado
  y mostrar/ocultar el menú.

  ¿Por qué esta técnica? → Funciona sin JavaScript.
  ¿Cuándo usar JavaScript? → Si necesitas comportamiento más complejo
  (cerrar al hacer clic fuera, animaciones avanzadas, etc.)

  display: none oculta el checkbox pero sigue siendo funcional.
  */
  .menu-toggle { display: none; } /* Checkbox invisible (solo el estado importa) */

  .hamburger {
    display: none;         /* Oculto en escritorio, visible en móvil (ver media queries) */
    flex-direction: column;
    gap: 5px;              /* Espacio entre las 3 rayas del ícono hamburguesa */
    cursor: pointer;
    padding: .4rem;
    margin-left: auto;     /* Empuja el botón hamburguesa a la derecha */
  }

  /* Cada raya del ícono hamburguesa ═══ */
  .hamburger span {
    display: block;
    width: 22px; height: 2px;    /* Rayita horizontal */
    background: var(--white);
    border-radius: 2px;
    transition: all .25s;         /* Animará el giro en X al abrir el menú */
  }

  /*
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 3: HERO — La primera pantalla que ve el usuario                 ║
  ╚══════════════════════════════════════════════════════════════════════════╝

  El "hero" es la sección más importante: el usuario decide si se queda
  en los primeros 5 segundos. Debe ser impactante y claro.

  position: relative → Necesario para que los ::before y ::after (decoraciones)
  se posicionen relativas a esta sección y no a la pantalla.

  overflow: hidden → Las decoraciones que sobresalen del borde se recortan.
  */
  .hero {
    position: relative;
    background: var(--gray-900);
    padding-top: calc(var(--header-h) + 5rem); /* Compensar los 70px del header fijo */
    padding-bottom: 0;
    overflow: hidden;
  }

  /*
  ┌─────────────────────────────────────────────────────────────────────────┐
  │  PSEUDO-ELEMENTOS ::before y ::after                                    │
  └─────────────────────────────────────────────────────────────────────────┘

  ::before y ::after son "elementos virtuales" que CSS crea antes y después
  del contenido de un elemento. Son PERFECTOS para decoraciones que no
  deberían estar en el HTML (el HTML es para contenido, no decoración).

  SIEMPRE necesitan content: '' para existir (aunque esté vacío).

  position: absolute → Se posicionan relativas al .hero (que es position:relative).
  pointer-events: none → El ratón "atraviesa" estas decoraciones.

  radial-gradient(circle, ...) → Gradiente circular:
    - Del color naranja semi-transparente en el centro
    - Hacia completamente transparente al borde
  Crea un "glow" o resplandor ambiental.

  🎯 EJERCICIO: Prueba a cambiar los valores de top/right/bottom/left
     y los tamaños (width/height) para mover los círculos decorativos.
  */
  .hero::before {
    content: '';
    position: absolute;
    top: -120px; right: -120px; /* Parcialmente fuera del hero (arriba-derecha) */
    width: 520px; height: 520px;
    background: radial-gradient(circle, rgba(255,107,26,.14) 0%, transparent 70%);
    border-radius: 50%;
    pointer-events: none;
  }

  .hero::after {
    content: '';
    position: absolute;
    bottom: 60px; left: -80px; /* Parte inferior izquierda */
    width: 340px; height: 340px;
    background: radial-gradient(circle, rgba(255,107,26,.07) 0%, transparent 70%);
    border-radius: 50%;
    pointer-events: none;
  }

  /* El contenido del hero: centrado con max-width para confort de lectura */
  .hero-content {
    position: relative;
    z-index: 1;          /* Encima de los ::before y ::after decorativos */
    text-align: center;
    max-width: 780px;
    margin: 0 auto;
    padding-bottom: 4rem;
    padding-left: 1.5rem;
    padding-right: 1.5rem;
  }

  /* Pequeña pastilla naranja sobre el título principal */
  .hero-eyebrow {
    display: inline-block;
    background: var(--orange-soft);
    color: var(--orange);
    border: 1px solid var(--orange-border);
    border-radius: 999px;
    padding: .3rem 1rem;
    font-size: .78rem;
    font-weight: 600;
    letter-spacing: .07em;
    text-transform: uppercase;
    margin-bottom: 1.4rem;
  }

  /* Título principal: el más grande de la página
     clamp() para que sea fluido entre pantallas */
  .hero-content h1 {
    font-size: clamp(2.4rem, 5vw, 4rem);
    font-weight: 800;
    color: var(--white);
    line-height: 1.1;
    letter-spacing: -.025em; /* Compactar letras en títulos grandes */
    margin-bottom: 1.2rem;
  }

  /* Subtítulo descriptivo */
  .hero-sub {
    font-size: 1.05rem;
    color: var(--gray-400);
    max-width: 560px;
    margin: 0 auto 2.2rem; /* Centrado + separación de los botones */
  }

  /* Botones del hero: flex para colocarlos en fila y centrarlos */
  .hero-btns {
    display: flex;
    gap: 1rem;
    justify-content: center;
    flex-wrap: wrap; /* Si no caben en una fila, bajan a la siguiente */
  }

  /*
  ┌─────────────────────────────────────────────────────────────────────────┐
  │  BARRA DE ESTADÍSTICAS — Debajo del hero                                │
  └─────────────────────────────────────────────────────────────────────────┘
  Los números grandes (+500 clientes, 24/7...) generan confianza rápidamente.
  */
  .hero-stats-bar {
    background: var(--gray-800);
    border-top: 1px solid var(--gray-700);
  }

  /* Usamos Flexbox para poner las stats en fila y centrarlas */
  .stats-row {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 1.5rem 1.5rem;
    max-width: var(--max-w);
    margin: 0 auto;
  }

  .stat-item {
    display: flex;
    flex-direction: column;   /* Número arriba, texto abajo */
    align-items: center;
    padding: 0 2.5rem;        /* Espacio horizontal entre stats */
    text-align: center;
    flex: 1;                  /* Distribuir el espacio igualmente */
  }

  /* El número grande en naranja */
  .stat-item strong {
    font-size: 1.8rem;
    font-weight: 800;
    color: var(--orange);
    line-height: 1;
  }

  .stat-item span { font-size: .78rem; color: var(--gray-400); margin-top: .2rem; }

  /* Línea vertical separadora entre stats */
  .stat-sep { width: 1px; height: 36px; background: var(--gray-700); flex-shrink: 0; }

  /*
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIONES GENÉRICAS                                                    ║
  ╚══════════════════════════════════════════════════════════════════════════╝
  Padding uniforme para todas las secciones de contenido.
  .section-alt tiene fondo ligeramente diferente para "separar" visualmente
  las secciones sin usar líneas — alternancia de tonos de gris.
  */
  .section { padding: 5.5rem 0; }
  .section-alt { background: var(--gray-900); }

  /*
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 4: SERVICIOS — Grid de tarjetas                                ║
  ╚══════════════════════════════════════════════════════════════════════════╝

  CSS Grid: perfecto para layouts de 2 dimensiones (filas y columnas).
  repeat(3, 1fr) = 3 columnas que se reparten el espacio igualmente.
  1fr = "1 fracción" del espacio disponible.

  💡 ALTERNATIVA más flexible:
     grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
     → Las columnas se adaptan solas, sin media queries.

  🎯 EJERCICIO: Cambia a 2 columnas (repeat(2, 1fr)) y observa el resultado.
  */
  .services-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* 3 columnas iguales */
    gap: 1.25rem;                           /* Espacio entre tarjetas */
  }

  /*
  ┌─────────────────────────────────────────────────────────────────────────┐
  │  .service-card — Tarjeta individual de servicio                         │
  └─────────────────────────────────────────────────────────────────────────┘

  position: relative es necesario para el pseudo-elemento ::after
  (la línea naranja que aparece en la parte inferior al hacer hover).

  overflow: hidden → La línea naranja ::after no se verá cuando
  está escalada a 0 (fuera del borde visible de la tarjeta).
  */
  .service-card {
    background: var(--gray-900);
    border: 1px solid var(--gray-700);
    border-radius: var(--radius-lg);
    padding: 2rem 1.75rem;
    transition: all .25s;    /* Animar todo al hacer hover */
    position: relative;
    overflow: hidden;
  }

  /*
  La línea naranja de la parte inferior de la tarjeta.
  Está inicialmente "invisible" (scaleX: 0 = escala horizontal 0 = desaparecida).
  Al hacer hover en la tarjeta, se expande (scaleX: 1 = tamaño completo).
  transform-origin: left → La expansión empieza desde la izquierda.

  Este es un truco muy común para crear efectos de "underline" o bordes animados.
  */
  .service-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0; /* Pegado al borde inferior de la tarjeta */
    height: 3px;
    background: var(--orange);
    transform: scaleX(0);          /* Invisible al inicio */
    transform-origin: left;        /* La animación empieza desde la izquierda */
    transition: transform .3s;     /* Animar solo la transformación */
  }

  /* Al hacer hover en la tarjeta:
     - Borde naranja visible
     - Subir 5px (efecto flotante)
     - Sombra más intensa */
  .service-card:hover {
    border-color: var(--orange-border);
    transform: translateY(-5px);
    box-shadow: var(--shadow-md), 0 0 0 1px var(--orange-border);
  }

  /* La línea naranja inferior se expande al hacer hover en la tarjeta */
  .service-card:hover::after { transform: scaleX(1); }

  /* Tarjeta especial "highlight": la de Cloud & Servidores
     Tiene borde y fondo ligeramente diferentes para destacar */
  .service-card.highlight {
    border-color: var(--orange-border);
    background: linear-gradient(145deg, rgba(255,107,26,.07), var(--gray-900));
  }

  /* Contenedor del ícono SVG */
  .svc-icon {
    width: 54px; height: 54px;
    background: var(--orange-soft);
    border: 1px solid var(--orange-border);
    border-radius: var(--radius);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--orange);    /* Los SVGs usan currentColor → heredan este color */
    margin-bottom: 1.2rem;
    transition: all .25s;
  }

  .svc-icon svg { width: 26px; height: 26px; }

  /* Al hacer hover en la tarjeta, el ícono se rellena de naranja sólido */
  .service-card:hover .svc-icon {
    background: var(--orange);
    color: var(--white); /* Las líneas del SVG cambian a blanco */
    border-color: var(--orange);
  }

  .service-card h3 { font-size: 1.05rem; font-weight: 700; color: var(--white); margin-bottom: .6rem; }
  .service-card p  { font-size: .88rem; color: var(--gray-400); line-height: 1.65; margin-bottom: 1rem; }

  /* Enlace "Más información →" de cada tarjeta */
  .card-link { font-size: .83rem; font-weight: 600; color: var(--orange); display: inline-block; transition: color .2s; }
  .card-link:hover { color: var(--orange-light); }

  /*
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 5: QUIÉNES SOMOS                                              ║
  ╚══════════════════════════════════════════════════════════════════════════╝

  CSS Grid de 2 columnas: imagen a la izquierda, texto a la derecha.
  La primera columna tiene un ancho fijo (420px) para la imagen.
  La segunda columna usa "1fr" para ocupar el resto.

  🎯 EJERCICIO: Cambia el orden visual de columnas con:
     direction: rtl; (en .about-layout) → texto a la izquierda, imagen a la derecha.
  */
  .about-layout {
    display: grid;
    grid-template-columns: 420px 1fr; /* Imagen fija + texto flexible */
    gap: 5rem;
    align-items: center; /* Alinear verticalmente al centro */
  }

  /* Contenedor de la imagen con posición relativa para el badge flotante */
  .about-img-wrap {
    position: relative;
    border-radius: var(--radius-lg);
    overflow: visible; /* Permitir que el badge .img-badge sobresalga */
  }

  /* Marco de la imagen placeholder */
  .img-placeholder {
    border-radius: var(--radius-lg);
    overflow: hidden;
    aspect-ratio: 4/3; /* Mantiene proporción 4:3 sin importar el ancho */
    border: 1px solid var(--gray-700);
    background: var(--gray-800);
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .img-placeholder svg { width: 100%; height: 100%; }

  /* Badge "15+ Años de experiencia" que flota sobre la imagen
     position: absolute relativa a .about-img-wrap (position: relative) */
  .img-badge {
    position: absolute;
    bottom: -1rem; right: -1rem; /* Esquina inferior derecha, ligeramente fuera */
    background: var(--orange);
    color: var(--white);
    border-radius: var(--radius-lg);
    padding: 1rem 1.4rem;
    text-align: center;
    box-shadow: var(--shadow-md);
  }

  .img-badge strong { display: block; font-size: 2rem; font-weight: 800; line-height: 1; }
  .img-badge span   { font-size: .72rem; font-weight: 500; opacity: .9; }

  /* Columna de texto del about */
  .about-text-col .pill { display: inline-block; }

  .about-text-col h2 {
    font-size: clamp(1.8rem, 3vw, 2.5rem);
    font-weight: 700;
    color: var(--white);
    margin-bottom: .8rem;
    line-height: 1.2;
  }

  .about-text-col > p { font-size: .93rem; color: var(--gray-400); margin-bottom: 1rem; }

  /* Lista de valores con punto naranja decorativo */
  .values-list { display: flex; flex-direction: column; gap: 1rem; margin: 1.5rem 0; }

  .value-item { display: flex; align-items: flex-start; gap: .9rem; }

  /* El puntito naranja — decoración pura, debería estar en CSS y no en HTML */
  .value-dot {
    flex-shrink: 0;          /* No se comprime nunca */
    width: 10px; height: 10px;
    background: var(--orange);
    border-radius: 50%;      /* Círculo perfecto */
    margin-top: .55rem;      /* Alinear con la primera línea de texto */
  }

  .value-item strong { display: block; font-size: .93rem; color: var(--white); margin-bottom: .15rem; }
  .value-item p { font-size: .85rem; color: var(--gray-400); margin: 0; }

  /* Badges de certificaciones: Microsoft Partner, ISO 27001, etc. */
  .partner-badges { display: flex; flex-wrap: wrap; gap: .6rem; margin-top: 1.5rem; }

  .badge {
    background: var(--gray-800);
    border: 1px solid var(--gray-700);
    border-radius: var(--radius);
    padding: .35rem .85rem;
    font-size: .75rem;
    font-weight: 500;
    color: var(--gray-300);
    transition: all .2s;
  }

  .badge:hover { border-color: var(--orange-border); color: var(--orange); }

  /*
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 6: CTA BAND — Llamada a la acción                              ║
  ╚══════════════════════════════════════════════════════════════════════════╝

  CTA = Call To Action. Una sección de contraste alto para motivar al usuario
  a hacer algo concreto (solicitar presupuesto).

  linear-gradient(135deg, ...) → Gradiente lineal en diagonal (135 grados):
    - 0° sería de abajo a arriba
    - 90° de izquierda a derecha
    - 135° diagonal de arriba-izquierda a abajo-derecha
  */
  .cta-band {
    background: linear-gradient(135deg, var(--orange-dark), var(--orange), var(--orange-light));
    padding: 3.5rem 0;
  }

  /* Flexbox para colocar texto a la izquierda y botón a la derecha */
  .cta-inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 2rem;
    flex-wrap: wrap; /* Si no caben, el botón baja */
    max-width: var(--max-w);
    margin: 0 auto;
    padding: 0 1.5rem;
  }

  .cta-band h2 { font-size: clamp(1.4rem, 3vw, 2rem); font-weight: 700; color: var(--white); margin-bottom: .35rem; }
  .cta-band p  { color: rgba(255,255,255,.8); font-size: .95rem; }

  /*
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 7: CONTACTO — Formulario                                       ║
  ╚══════════════════════════════════════════════════════════════════════════╝
  */
  .contact-layout {
    display: grid;
    grid-template-columns: 300px 1fr; /* Sidebar fija + formulario flexible */
    gap: 3rem;
    align-items: start; /* Alinear al tope (no estirar verticalmente) */
  }

  .contact-sidebar h3 { font-size: 1.1rem; font-weight: 700; color: var(--white); margin-bottom: 1.5rem; }
  .contact-list { display: flex; flex-direction: column; gap: 1.25rem; margin-bottom: 1.75rem; }
  .contact-list li { display: flex; align-items: flex-start; gap: .85rem; }

  /* Cuadrado con ícono de contacto */
  .c-icon {
    flex-shrink: 0;
    width: 40px; height: 40px;
    background: var(--orange-soft);
    border: 1px solid var(--orange-border);
    border-radius: var(--radius);
    display: flex; align-items: center; justify-content: center;
    color: var(--orange);
    margin-top: .1rem;
  }
  .c-icon svg { width: 18px; height: 18px; }

  .contact-list strong { display: block; font-size: .82rem; font-weight: 600; color: var(--gray-300); margin-bottom: .15rem; }
  .contact-list a, .contact-list span { font-size: .9rem; color: var(--white); font-weight: 500; }
  .contact-list a:hover { color: var(--orange); }

  /* Nota informativa con borde naranja */
  .sidebar-note {
    display: flex;
    align-items: flex-start;
    gap: .6rem;
    background: var(--orange-soft);
    border: 1px solid var(--orange-border);
    border-radius: var(--radius);
    padding: .85rem 1rem;
    font-size: .82rem;
    color: var(--gray-300);
    line-height: 1.5;
  }
  .sidebar-note svg { flex-shrink: 0; width: 18px; height: 18px; color: var(--orange); margin-top: .1rem; }

  /* Caja del formulario */
  .contact-form {
    background: var(--gray-900);
    border: 1px solid var(--gray-700);
    border-radius: var(--radius-lg);
    padding: 2rem;
    display: flex;
    flex-direction: column; /* Los campos apilados verticalmente */
    gap: 1.1rem;            /* Separación entre grupos de campo */
  }

  /* Fila con dos campos lado a lado */
  .form-row { display: flex; gap: 1rem; }
  .form-row.two-col .form-group { flex: 1; } /* Cada campo ocupa la mitad */

  /* Grupo label + input */
  .form-group {
    display: flex;
    flex-direction: column; /* Label arriba, input abajo */
    gap: .35rem;
    flex: 1;
  }

  /* Etiquetas de los campos */
  .form-group label {
    font-size: .78rem;
    font-weight: 600;
    color: var(--gray-300);
    letter-spacing: .03em;
    text-transform: uppercase;
  }

  /* Asterisco rojo que indica campo obligatorio */
  .req { color: var(--orange); }

  /*
  Estilos compartidos para input, select y textarea.
  Usamos el mismo estilo en los tres para consistencia visual.
  -webkit-appearance: none → Quitar el estilo nativo del sistema operativo.
  */
  .form-group input,
  .form-group select,
  .form-group textarea {
    background: var(--gray-800);
    border: 1px solid var(--gray-700);
    border-radius: var(--radius);
    padding: .72rem 1rem;
    color: var(--white);
    font-family: var(--font); /* Sin esto, los inputs usan su fuente por defecto */
    font-size: .92rem;
    outline: none;            /* Quitar el contorno azul nativo del navegador */
    transition: border-color .2s, box-shadow .2s;
    -webkit-appearance: none; /* Compatibilidad con Safari/iOS */
  }

  /* Estado de foco (cuando el usuario está escribiendo en el campo)
     Resaltar con borde naranja + sombra interior suave = accesibilidad visual */
  .form-group input:focus,
  .form-group select:focus,
  .form-group textarea:focus {
    border-color: var(--orange);
    box-shadow: 0 0 0 3px rgba(255,107,26,.12); /* "Ring" de foco */
  }

  /* Texto de placeholder (indicación dentro del campo vacío) */
  .form-group input::placeholder,
  .form-group textarea::placeholder { color: var(--gray-600); }

  /* El textarea puede redimensionarse verticalmente (no horizontalmente) */
  .form-group textarea { resize: vertical; min-height: 130px; }

  /* Select personalizado: inyectar flecha custom con SVG en base64
     como imagen de fondo. Así podemos controlar su apariencia. */
  .form-group select {
    cursor: pointer;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='14' height='14' viewBox='0 0 24 24' fill='none' stroke='%23888' stroke-width='2'%3E%3Cpolyline points='6,9 12,15 18,9'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right .85rem center;
    padding-right: 2.5rem; /* Espacio para la flecha */
  }

  .form-group select option { background: var(--gray-800); }

  /* Checkbox de privacidad */
  .form-check { display: flex; align-items: center; gap: .6rem; }

  /* accent-color → Colorea el checkbox con el color de la marca (naranja) */
  .form-check input[type="checkbox"] {
    width: 16px; height: 16px;
    accent-color: var(--orange);
    cursor: pointer;
    flex-shrink: 0; /* El checkbox no se comprime */
  }

  .form-check label { font-size: .83rem; color: var(--gray-400); }
  .form-check a { color: var(--orange); }
  .form-check a:hover { text-decoration: underline; }

  /* Botón de envío a ancho completo */
  .btn-submit { width: 100%; justify-content: center; padding: .85rem 2rem; font-size: .95rem; }

  /*
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 8: FOOTER — Pie de página                                      ║
  ╚══════════════════════════════════════════════════════════════════════════╝
  */
  .site-footer { background: var(--gray-950); border-top: 1px solid var(--gray-800); }
  .footer-main { padding: 4rem 0 3rem; }

  /* Grid de 3 columnas para el footer:
     1.5fr = más ancho (datos de empresa) + 1fr + 1fr (menús) */
  .footer-grid { display: grid; grid-template-columns: 1.5fr 1fr 1fr; gap: 3rem; }

  .footer-brand .logo { margin-bottom: 1rem; }
  .footer-brand p { font-size: .88rem; color: var(--gray-400); margin-bottom: 1.5rem; max-width: 300px; line-height: 1.65; }

  /* Links de contacto con ícono a la izquierda */
  .footer-contact-links { display: flex; flex-direction: column; gap: .65rem; }
  .footer-contact-links a { display: flex; align-items: center; gap: .55rem; font-size: .88rem; color: var(--gray-300); font-weight: 500; transition: color .2s; }
  .footer-contact-links a svg { width: 16px; height: 16px; color: var(--orange); flex-shrink: 0; }
  .footer-contact-links a:hover { color: var(--orange); }

  /* Títulos de columna del footer */
  .footer-col h4 { font-size: .72rem; font-weight: 700; letter-spacing: .12em; text-transform: uppercase; color: var(--gray-300); margin-bottom: 1rem; }
  .footer-col h4.mt { margin-top: 2rem; } /* Margen superior para el 2º título */

  .footer-col ul { display: flex; flex-direction: column; gap: .55rem; }
  .footer-col ul li a { font-size: .88rem; color: var(--gray-400); transition: color .2s; display: inline-block; }
  .footer-col ul li a:hover { color: var(--orange); }

  /* Franja inferior del footer: copyright + menú LOPD */
  .footer-bottom { border-top: 1px solid var(--gray-800); padding: 1.2rem 0; }
  .footer-bottom-row { display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: .75rem; }
  .footer-bottom-row p { font-size: .8rem; color: var(--gray-600); }

  /* Menú LOPD (Ley Orgánica de Protección de Datos) */
  .lopd-bar { display: flex; align-items: center; gap: .75rem; font-size: .8rem; }
  .lopd-bar a { color: var(--gray-600); transition: color .2s; }
  .lopd-bar a:hover { color: var(--orange); }
  .lopd-bar span { color: var(--gray-700); } /* El punto separador · */

  /*
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  MEDIA QUERIES — DISEÑO RESPONSIVE                                      ║
  ╚══════════════════════════════════════════════════════════════════════════╝

  Media Queries: reglas CSS que solo se aplican cuando se cumple una condición.
  En este caso, la condición es el ANCHO DE PANTALLA del dispositivo.

  Filosofía "Desktop First": empezamos con el diseño de escritorio (arriba)
  y usamos media queries para ADAPTAR a pantallas más pequeñas.

  Alternativa "Mobile First": empezar por el móvil y usar min-width.
  → RECOMENDADO para proyectos nuevos. Ejemplo:
    @media (min-width: 768px) { ... } → Estilos para tablet y escritorio

  BREAKPOINTS (puntos de ruptura) usados en este proyecto:
    1024px → Tablets en horizontal, laptops pequeñas
    768px  → Tablets en vertical, móviles grandes
    480px  → Móviles pequeños

  🎯 EJERCICIO: Abre DevTools (F12) > ícono de móvil/tablet
     y redimensiona la ventana para ver los cambios en cada breakpoint.
  */

  /* ── TABLET (max-width: 1024px) ──────────────────────── */
  @media (max-width: 1024px) {

    /* Servicios: de 3 columnas a 2 */
    .services-grid  { grid-template-columns: repeat(2, 1fr); }

    /* About: de 2 columnas a 1 (imagen arriba, texto abajo) */
    .about-layout   { grid-template-columns: 1fr; gap: 2.5rem; }
    .about-img-col  { max-width: 400px; margin: 0 auto; } /* Centrar imagen */

    /* Contacto: de 2 columnas a 1 (sidebar arriba, form abajo) */
    .contact-layout { grid-template-columns: 1fr; }

    /* Footer: de 3 columnas a 2 (empresa ocupa toda la fila) */
    .footer-grid    { grid-template-columns: 1fr 1fr; }
    .footer-brand   { grid-column: 1 / -1; } /* Ocupa de columna 1 al final */

    /* CTA: de fila a columna (texto arriba, botón abajo, centrado) */
    .cta-inner      { flex-direction: column; text-align: center; }
  }

  /* ── MÓVIL (max-width: 768px) ────────────────────────── */
  @media (max-width: 768px) {

    /* Mostrar el ícono hamburguesa */
    .hamburger { display: flex; }

    /*
    MENÚ MÓVIL: Se oculta encima del viewport y aparece al activar el checkbox.

    transform: translateY(-110%) → Mueve el menú hacia arriba (fuera de vista).
    opacity: 0 → Invisible.
    pointer-events: none → No se puede hacer clic cuando está oculto.

    Al marcar el checkbox (.menu-toggle:checked):
    → translateY(0) → Vuelve a su posición normal
    → opacity: 1 → Visible
    → pointer-events: all → Se puede clicar de nuevo

    La transición (transition: all .28s) anima el cambio suavemente.
    */
    .main-nav {
      position: absolute;
      top: var(--header-h); left: 0; right: 0;
      background: var(--gray-900);
      border-bottom: 1px solid var(--gray-800);
      padding: 1.25rem 1.5rem;
      transform: translateY(-110%); /* Oculto hacia arriba */
      opacity: 0;
      pointer-events: none;
      transition: all .28s cubic-bezier(.4,0,.2,1); /* Easing natural */
      z-index: 100;
    }

    /* Cuando el checkbox está marcado → mostrar el menú */
    .menu-toggle:checked ~ .main-nav {
      transform: translateY(0); /* Volver a posición normal */
      opacity: 1;
      pointer-events: all;
    }

    /*
    El selector ~ es el "selector de hermano general".
    Significa: "el elemento .main-nav que viene DESPUÉS de .menu-toggle:checked".
    Esto solo funciona si los elementos son hermanos en el HTML.

    También animamos las rayas del hamburguesa para que formen una X:
    - Raya 1: gira 45° y se desplaza
    - Raya 2: se hace invisible
    - Raya 3: gira -45° y se desplaza
    */
    .menu-toggle:checked ~ .hamburger span:nth-child(1) { transform: rotate(45deg) translate(5px,5px); }
    .menu-toggle:checked ~ .hamburger span:nth-child(2) { opacity: 0; }
    .menu-toggle:checked ~ .hamburger span:nth-child(3) { transform: rotate(-45deg) translate(5px,-5px); }

    /* Los ítems del menú en columna vertical */
    .main-nav ul { flex-direction: column; align-items: stretch; gap: .2rem; }
    .main-nav a  { display: block; padding: .7rem 1rem; }
    .nav-cta     { margin-left: 0 !important; text-align: center; margin-top: .5rem; }

    /* Servicios: de 2 columnas a 1 */
    .services-grid   { grid-template-columns: 1fr; }

    /* Formulario: las filas de 2 campos pasan a 1 campo por fila */
    .form-row.two-col{ flex-direction: column; }

    /* Footer: todo en 1 columna */
    .footer-grid     { grid-template-columns: 1fr; }
    .footer-bottom-row{ flex-direction: column; text-align: center; }

    /* Stats: en cuadrícula si no caben en fila */
    .stats-row       { flex-wrap: wrap; gap: 1rem; }
    .stat-sep        { display: none; } /* Ocultar separadores verticales */

    /* Reducir padding de secciones en móvil */
    .section         { padding: 3.5rem 0; }
  }

  /* ── MÓVIL PEQUEÑO (max-width: 480px) ───────────────── */
  @media (max-width: 480px) {
    .logo-wrap       { flex: none; }         /* El logo no ocupa % fijo */
    .hero-content h1 { font-size: 2rem; }    /* Título más pequeño */
    .contact-form    { padding: 1.25rem; }   /* Menos padding en el form */
    .img-badge       { right: .5rem; bottom: -1.5rem; } /* Reposicionar badge */
  }

  </style>
  <!--
  FIN DE LOS ESTILOS CSS
  ════════════════════════════════════════════════════════
  Si añades más secciones, agrega sus estilos ANTES del cierre </style>.
  Mantén el orden: variables → reset → componentes → secciones → responsive.
  -->

</head>

<!--
  ════════════════════════════════════════════════════════
  <body> — Todo lo que SE VE en la página
  ════════════════════════════════════════════════════════
  Aquí empieza el contenido real. El <body> contiene:
  - <header>  → Cabecera de navegación
  - <section> → Cada bloque de contenido
  - <footer>  → Pie de página

  HTML5 introdujo etiquetas SEMÁNTICAS que describen el PROPÓSITO
  del contenido, no solo su apariencia:
    <header>  → Cabecera del sitio o sección
    <nav>     → Bloque de navegación
    <main>    → Contenido principal único de la página
    <section> → Sección temática del documento
    <article> → Contenido independiente y reutilizable
    <aside>   → Contenido lateral o complementario
    <footer>  → Pie del sitio o sección

  Antes de HTML5 todo era <div>. Ahora usamos <div> solo
  cuando NO hay una etiqueta semántica apropiada.

  BENEFICIOS de HTML semántico:
    ✓ Google entiende mejor el contenido (SEO)
    ✓ Los lectores de pantalla navegan mejor (accesibilidad)
    ✓ El código es más fácil de leer y mantener
-->
<body>

<!--
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 2 HTML: <header> — Cabecera fija de navegación                 ║
  ╚══════════════════════════════════════════════════════════════════════════╝

  <header> = etiqueta semántica para la cabecera principal del sitio.
  La clase "site-header" distingue esta cabecera de otras posibles
  sub-cabeceras dentro de secciones o artículos.

  Por qué usar <header> en vez de <div>:
    → Semántica: describe su propósito
    → Accesibilidad: los lectores de pantalla lo identifican como cabecera
    → SEO: Google lo reconoce como área de navegación principal
-->
<header class="site-header">

  <!-- .header-inner: div contenedor que limita el ancho y centra el contenido.
       Usa Flexbox para colocar logo y nav en la misma línea horizontal.
       Es una práctica común separar el elemento semántico (<header>)
       de su contenedor de layout (.header-inner) para más flexibilidad CSS. -->
  <div class="header-inner">

    <!-- LOGO: Envuelto en un <div class="logo-wrap"> que ocupa el 20% del header.
         El <a href="#inicio"> convierte el logo en un enlace a la sección inicio.
         "#inicio" es un "enlace de anclaje" → salta al elemento con id="inicio". -->
    <div class="logo-wrap">
      <a href="#inicio" class="logo">

        <!-- SVG INLINE: El logo es un SVG directamente en el HTML.
             VENTAJAS del SVG inline:
               ✓ Escala sin perder calidad (vectorial)
               ✓ Sin petición HTTP adicional (ya está en el HTML)
               ✓ Se puede animar y colorear con CSS
               ✓ No depende de un archivo externo que podría fallar

             ALTERNATIVA con imagen:
               <img src="logo.png" alt="SERVITIC" width="38" height="38">
               → Más fácil de cambiar, pero no escalable ni animable.

             DESGLOSE DEL SVG:
               viewBox="0 0 38 38" → Área de dibujo: ancho=38, alto=38
               fill="none" → Por defecto, las formas no tienen relleno

             🎯 EJERCICIO: Cambia fill="#FF6B1A" en el <rect> por otro color.
                Prueba "#28a745" (verde) o "#007bff" (azul).
        -->
        <svg class="logo-icon" width="38" height="38" viewBox="0 0 38 38" fill="none">
          <!-- <rect>: Rectángulo con esquinas redondeadas (rx="8")
               Actúa como "fondo" del logo con gradiente naranja -->
          <rect width="38" height="38" rx="8" fill="#FF6B1A"/>
          <!-- Dos rombos blancos (diamantes) que forman el símbolo de SERVITIC
               opacity="0.95" y "0.55" crean la sensación de profundidad -->
          <path d="M10 19 L16 12 L22 19 L16 26 Z" fill="white" opacity="0.95"/>
          <path d="M18 19 L24 12 L30 19 L24 26 Z" fill="white" opacity="0.55"/>
        </svg>

        <!-- Texto del logo: "SERVI" en blanco + "TIC" en naranja (clase .accent) -->
        <span class="logo-text">SERVI<span class="accent">TIC</span></span>

      </a>
    </div>
    <!-- FIN logo-wrap -->

    <!--
      MENÚ HAMBURGUESA: Técnica CSS pura (sin JavaScript)
      ─────────────────────────────────────────────────────
      Esta técnica usa el truco del checkbox:

      1. <input type="checkbox" id="menu-toggle"> → El "interruptor" invisible
      2. <label for="menu-toggle"> → Al hacer clic aquí, el checkbox se marca/desmarca
         (el "for" vincula el label con el input por el id)
      3. En el CSS: .menu-toggle:checked ~ .main-nav → Cuando el checkbox está marcado,
         el menú aparece (usando el selector de hermanos ~)

      ¿Por qué el label y el input deben estar ANTES del nav en el HTML?
      → Porque el selector CSS "~" solo funciona con hermanos POSTERIORES.
         El nav viene después del checkbox en el HTML.

      IMPORTANTE: display: none oculta el checkbox visualmente
      pero mantiene su funcionalidad de estado (marcado/desmarcado).
    -->
    <input type="checkbox" id="menu-toggle" class="menu-toggle" />

    <!-- <label for="menu-toggle">: Al hacer clic en este label,
         se activa el checkbox invisible. Muestra el ícono hamburguesa ≡
         aria-label="Abrir menú" → Descripción para lectores de pantalla
         (el ícono visual no tiene texto, pero necesitamos describirlo) -->
    <label for="menu-toggle" class="hamburger" aria-label="Abrir menú">
      <!-- Tres <span> vacíos que CSS convierte en las 3 rayas del ícono hamburguesa -->
      <span></span>
      <span></span>
      <span></span>
    </label>

    <!--
      <nav>: Etiqueta semántica para bloques de NAVEGACIÓN principal.
      aria-label="Navegación principal" → Identifica esta nav para lectores
      de pantalla (puede haber varias <nav> en la página, como en el footer).

      Contiene una <ul> (lista no ordenada) con <li> (ítems) y <a> (enlaces).
      Esta estructura es semánticamente correcta para menús de navegación.
    -->
    <nav class="main-nav" aria-label="Navegación principal">
      <ul>
        <!-- Cada <li> es un ítem del menú. El <a> es el enlace.
             href="#servicios" salta a la sección con id="servicios" -->
        <li><a href="#inicio">Inicio</a></li>
        <li><a href="#servicios">Servicios</a></li>
        <li><a href="#nosotros">Quiénes Somos</a></li>
        <li><a href="#contacto">Contacto</a></li>
        <!-- Este último enlace tiene la clase nav-cta → botón naranja destacado -->
        <li><a href="#contacto" class="nav-cta">Solicitar presupuesto</a></li>
      </ul>
    </nav>

  </div>
  <!-- FIN header-inner -->

</header>
<!-- FIN site-header -->

<!--
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 3 HTML: HERO — Portada principal                               ║
  ╚══════════════════════════════════════════════════════════════════════════╝

  <section>: Etiqueta semántica para una sección temática del documento.
  Cada sección debería poder identificarse con un título (<h1>-<h6>).

  id="inicio" → Permite enlazar a esta sección desde el menú (#inicio).
  IMPORTANTE: Los id deben ser ÚNICOS en toda la página.

  🎯 EJERCICIO: Añade una imagen de fondo al hero con CSS:
     background-image: url('tu-imagen.jpg');
     background-size: cover;
     background-position: center;
-->
<section class="hero" id="inicio">

  <!-- .hero-content: div que limita el ancho del contenido del hero.
       El CSS posiciona este div con z-index:1 para que esté encima
       de las decoraciones ::before y ::after del .hero -->
  <div class="hero-content">

    <!-- Pastilla de texto descriptivo sobre el título principal.
         ✦ es un símbolo Unicode (estrella especial). Alternativas: ★ ● → -->
    <p class="hero-eyebrow">✦ Tecnología al servicio de tu empresa</p>

    <!-- <h1>: El título más importante de la página.
         REGLA DE ORO: Solo debe haber UN <h1> por página.
         Los buscadores le dan mucho peso → incluir la palabra clave principal.
         El <br/> fuerza un salto de línea dentro del título. -->
    <h1>Soluciones Tecnológicas<br/><span class="accent">Profesionales</span></h1>

    <!-- Descripción breve: el usuario lee esto en 2-3 segundos.
         Debe responder: ¿Qué haces? ¿Para quién? -->
    <p class="hero-sub">Expertos en servicios informáticos y mantenimiento tecnológico para empresas y particulares.</p>

    <!-- Los dos botones de llamada a la acción -->
    <div class="hero-btns">
      <!-- Botón primario: acción más importante → ver servicios -->
      <a href="#servicios" class="btn btn-primary">Ver servicios</a>
      <!-- Botón secundario: alternativa → contactar directamente -->
      <a href="#contacto" class="btn btn-outline">Contactar</a>
    </div>

  </div>
  <!-- FIN hero-content -->

  <!-- BARRA DE ESTADÍSTICAS: prueba social = genera confianza -->
  <div class="hero-stats-bar">
    <div class="stats-row">

      <!-- Cada stat: número grande + descripción pequeña -->
      <div class="stat-item">
        <!-- <strong>: negrita semántica. Indica que este texto es importante.
             Usar <b> si solo quieres negrita visual sin significado semántico. -->
        <strong>+500</strong>
        <span>Clientes satisfechos</span>
      </div>

      <!-- .stat-sep: línea vertical decorativa entre estadísticas -->
      <div class="stat-sep"></div>

      <div class="stat-item">
        <strong>24/7</strong>
        <span>Soporte técnico</span>
      </div>

      <div class="stat-sep"></div>

      <div class="stat-item">
        <strong>15+</strong>
        <span>Años de experiencia</span>
      </div>

      <div class="stat-sep"></div>

      <div class="stat-item">
        <strong>98%</strong>
        <span>Satisfacción cliente</span>
      </div>

    </div>
  </div>
  <!-- FIN hero-stats-bar -->

</section>
<!-- FIN hero -->

<!--
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 4 HTML: SERVICIOS — Grid de tarjetas                           ║
  ╚══════════════════════════════════════════════════════════════════════════╝

  Sin clase .section-alt → fondo oscuro por defecto (--gray-950).
  El siguiente "Quiénes Somos" tiene .section-alt → fondo ligeramente diferente.
  Esta alternancia visual separa secciones sin bordes ni líneas.
-->
<section class="section" id="servicios">
  <div class="container">

    <!-- Encabezado de la sección: pill + título + descripción -->
    <div class="section-header">
      <span class="pill">Qué ofrecemos</span>
      <h2>Nuestros <span class="accent">Servicios</span></h2>
      <p>Soluciones completas de tecnología e informática para que tu empresa nunca se detenga.</p>
    </div>
    <!-- FIN section-header -->

    <!-- Grid de 6 tarjetas de servicios -->
    <div class="services-grid">

      <!--
        <article>: Etiqueta semántica para contenido INDEPENDIENTE y reutilizable.
        Una tarjeta de servicio puede "sacarse" de la web y seguir teniendo sentido.
        Alternativa: <div class="service-card"> funciona pero es menos semántico.

        🎯 EJERCICIO: Añade un 7º servicio copiando uno de estos <article>
           y cambiando el ícono SVG, título y descripción.
      -->
      <article class="service-card">

        <!-- Contenedor del ícono SVG -->
        <div class="svc-icon">
          <!--
            SVG INLINE: Ícono de monitor/pantalla para "Mantenimiento".

            ATRIBUTOS CLAVE:
              viewBox="0 0 48 48" → Área de dibujo de 48×48 unidades
              fill="none" → No rellenar las formas por defecto
              stroke="currentColor" → El color del trazo = color CSS del padre
              (si el CSS dice color: orange, el SVG se pone naranja)
              stroke-width="2.5" → Grosor del trazo
              stroke-linecap="round" → Extremos de línea redondeados (más suave)

            FORMAS SVG BÁSICAS:
              <rect> → Rectángulo
              <circle> → Círculo
              <path d="..."> → Forma libre con comandos:
                M x,y → Mover a (sin trazar)
                L x,y → Línea hasta
                Z → Cerrar la forma (volver al inicio)
                C → Curva Bezier

            🎯 EJERCICIO: Prueba a cambiar stroke-width="2.5" por "5"
               en una tarjeta y observa el ícono más grueso.
          -->
          <svg viewBox="0 0 48 48" fill="none">
            <rect x="4" y="8" width="40" height="26" rx="3" stroke="currentColor" stroke-width="2.5"/>
            <path d="M15 42h18M24 34v8" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"/>
          </svg>
        </div>
        <!-- FIN svc-icon -->

        <!-- <h3>: Tercer nivel jerárquico. <h1>=página, <h2>=sección, <h3>=subsección -->
        <h3>Mantenimiento Informático</h3>

        <!-- Descripción del servicio -->
        <p>Mantenimiento preventivo y correctivo de equipos, diagnóstico de fallos y reparación rápida para mantener tu flota operativa.</p>

        <!-- Enlace "más info": lleva al formulario de contacto para solicitar info -->
        <a href="#contacto" class="card-link">Más información →</a>

      </article>
      <!-- FIN service-card: Mantenimiento -->

      <!-- ── TARJETA 2: Redes ─────────────────────────── -->
      <article class="service-card">
        <div class="svc-icon">
          <!-- Ícono de globo terráqueo con meridianos → representa redes/internet -->
          <svg viewBox="0 0 48 48" fill="none">
            <circle cx="24" cy="24" r="18" stroke="currentColor" stroke-width="2.5"/>
            <path d="M24 6v36M6 24h36M9.5 13.5C14 16.5 19 18 24 18s10-1.5 14.5-4.5M9.5 34.5C14 31.5 19 30 24 30s10 1.5 14.5 4.5" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
          </svg>
        </div>
        <h3>Redes e Infraestructura</h3>
        <p>Diseño, instalación y administración de redes LAN/WAN, WiFi corporativo, VPN y securización perimetral.</p>
        <a href="#contacto" class="card-link">Más información →</a>
      </article>

      <!-- ── TARJETA 3: Cloud (DESTACADA) ───────────────
           La clase "highlight" le da un fondo y borde ligeramente diferentes
           para que visualmente destaque entre las demás. -->
      <article class="service-card highlight">
        <div class="svc-icon">
          <!-- Ícono de servidor/nube -->
          <svg viewBox="0 0 48 48" fill="none">
            <path d="M8 30V20a4 4 0 014-4h24a4 4 0 014 4v10" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"/>
            <path d="M4 30h40v2a4 4 0 01-4 4H8a4 4 0 01-4-4v-2z" stroke="currentColor" stroke-width="2.5"/>
            <path d="M24 16V9M20 9h8" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"/>
          </svg>
        </div>
        <!-- &amp; es la entidad HTML para el símbolo & (evita errores de parsing) -->
        <h3>Cloud &amp; Servidores</h3>
        <p>Migración a la nube, gestión de servidores virtuales, backups automáticos y alta disponibilidad para tu negocio.</p>
        <a href="#contacto" class="card-link">Más información →</a>
      </article>

      <!-- ── TARJETA 4: Ciberseguridad ──────────────── -->
      <article class="service-card">
        <div class="svc-icon">
          <!-- Ícono de escudo/poliedro → ciberseguridad -->
          <svg viewBox="0 0 48 48" fill="none">
            <path d="M24 4L4 16v16l20 12 20-12V16L24 4z" stroke="currentColor" stroke-width="2.5" stroke-linejoin="round"/>
            <path d="M4 16l20 12 20-12M24 28v16" stroke="currentColor" stroke-width="2.5"/>
          </svg>
        </div>
        <h3>Ciberseguridad</h3>
        <p>Auditorías de seguridad, protección frente a ransomware, gestión de antivirus corporativo y formación a empleados.</p>
        <a href="#contacto" class="card-link">Más información →</a>
      </article>

      <!-- ── TARJETA 5: Software ──────────────────── -->
      <article class="service-card">
        <div class="svc-icon">
          <!-- Ícono de 4 cuadrados (Windows-like) → software -->
          <svg viewBox="0 0 48 48" fill="none">
            <rect x="6" y="6" width="15" height="15" rx="2" stroke="currentColor" stroke-width="2.5"/>
            <rect x="27" y="6" width="15" height="15" rx="2" stroke="currentColor" stroke-width="2.5"/>
            <rect x="6" y="27" width="15" height="15" rx="2" stroke="currentColor" stroke-width="2.5"/>
            <!-- El 4º cuadrado tiene un "+" en vez de relleno → indica "añadir" -->
            <path d="M27 34.5h7m3.5 0h1.5M34.5 27v7m0 3.5v1.5" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"/>
          </svg>
        </div>
        <h3>Software &amp; Licencias</h3>
        <p>Gestión de licencias Microsoft 365, configuración de ERP, CRM y software de gestión empresarial.</p>
        <a href="#contacto" class="card-link">Más información →</a>
      </article>

      <!-- ── TARJETA 6: Soporte 24/7 ─────────────── -->
      <article class="service-card">
        <div class="svc-icon">
          <!-- Ícono de reloj → soporte 24/7 -->
          <svg viewBox="0 0 48 48" fill="none">
            <path d="M24 4C13 4 4 13 4 24s9 20 20 20 20-9 20-20S35 4 24 4z" stroke="currentColor" stroke-width="2.5"/>
            <path d="M24 16v8l6 4" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
        <h3>Soporte Técnico 24/7</h3>
        <p>Helpdesk permanente con tiempos de respuesta garantizados, resolución remota y SLA adaptados a cada empresa.</p>
        <a href="#contacto" class="card-link">Más información →</a>
      </article>

    </div>
    <!-- FIN services-grid -->

  </div>
  <!-- FIN container -->
</section>
<!-- FIN section#servicios -->

<!--
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 5 HTML: QUIÉNES SOMOS — About                                  ║
  ╚══════════════════════════════════════════════════════════════════════════╝

  .section-alt → fondo ligeramente diferente (--gray-900 en vez de --gray-950)
  para separar visualmente esta sección de la anterior.
-->
<section class="section section-alt" id="nosotros">
  <div class="container">

    <!-- .about-layout: Grid de 2 columnas (imagen | texto) definido en CSS -->
    <div class="about-layout">

      <!-- ── COLUMNA IZQUIERDA: Imagen placeholder ── -->
      <div class="about-img-col">
        <div class="about-img-wrap">
          <!-- .img-placeholder: En producción real, sustituirías esto por:
               <img src="equipo.jpg" alt="El equipo de SERVITIC trabajando" />

               El alt="" de las imágenes es MUY IMPORTANTE:
               → Lectores de pantalla lo leen en voz alta
               → Se muestra si la imagen no carga
               → Google lo usa para indexar imágenes

               🎯 EJERCICIO: Crea una carpeta "img/" en el mismo directorio,
                  pon una foto allí y reemplaza el SVG por:
                  <img src="img/equipo.jpg" alt="Equipo SERVITIC" style="width:100%;border-radius:16px;">
          -->
          <div class="img-placeholder">
            <!-- SVG ilustrativo de una persona trabajando en ordenador
                 En un proyecto real, sería una foto de verdad del equipo -->
            <svg viewBox="0 0 400 300" fill="none" xmlns="http://www.w3.org/2000/svg">
              <rect width="400" height="300" fill="#242424"/>
              <rect x="80" y="180" width="240" height="12" rx="4" fill="#2e2e2e"/><!-- Mesa -->
              <rect x="100" y="100" width="200" height="130" rx="6" fill="#2e2e2e"/><!-- Monitor exterior -->
              <rect x="115" y="112" width="170" height="105" rx="4" fill="#1a1a1a"/><!-- Pantalla -->
              <rect x="125" y="122" width="150" height="8" rx="2" fill="#FF6B1A" opacity=".7"/><!-- Barra naranja -->
              <rect x="125" y="136" width="110" height="5" rx="2" fill="#3a3a3a"/><!-- Líneas de "código" -->
              <rect x="125" y="147" width="130" height="5" rx="2" fill="#3a3a3a"/>
              <rect x="125" y="158" width="90"  height="5" rx="2" fill="#3a3a3a"/>
              <rect x="125" y="172" width="50"  height="18" rx="4" fill="#FF6B1A" opacity=".8"/><!-- Botón -->
              <rect x="120" y="195" width="160" height="10" rx="3" fill="#2e2e2e"/><!-- Teclado -->
              <circle cx="50"  cy="60"  r="30" fill="#FF6B1A" opacity=".08"/><!-- Círculo decorativo -->
              <circle cx="350" cy="240" r="45" fill="#FF6B1A" opacity=".06"/>
              <circle cx="340" cy="50"  r="20" fill="#FF6B1A" opacity=".1"/>
            </svg>
          </div>
          <!-- FIN img-placeholder -->

          <!-- Badge flotante en la esquina inferior derecha de la imagen
               position: absolute lo posiciona relativo a .about-img-wrap (position: relative) -->
          <div class="img-badge">
            <strong>15+</strong>
            <span>Años de experiencia</span>
          </div>

        </div>
        <!-- FIN about-img-wrap -->
      </div>
      <!-- FIN about-img-col -->

      <!-- ── COLUMNA DERECHA: Texto about ── -->
      <div class="about-text-col">

        <!-- Pill de identificación de sección -->
        <span class="pill">Sobre nosotros</span>

        <!-- <h2>: Título de segundo nivel. La sección principal tiene un h2. -->
        <h2>Tecnología con <span class="accent">personas detrás</span></h2>

        <!-- Párrafos de texto explicativo.
             <strong>SERVITIC</strong>: negrita semántica = contenido importante -->
        <p>En <strong>SERVITIC</strong> somos un equipo de ingenieros y técnicos especializados con más de 15 años resolviendo los retos tecnológicos de empresas de todos los tamaños.</p>
        <p>Nacimos con la convicción de que la tecnología debe ser una herramienta que facilite el trabajo, no un obstáculo. Por eso apostamos por soluciones claras, soporte humano y tiempos de respuesta que marcan la diferencia.</p>

        <!-- Lista de valores/ventajas con punto naranja decorativo -->
        <div class="values-list">

          <!-- Cada value-item: punto naranja + título + descripción -->
          <div class="value-item">
            <!-- .value-dot: div vacío → solo decoración visual (punto naranja) -->
            <span class="value-dot"></span>
            <div>
              <strong>Compromiso total</strong>
              <p>Respondemos en menos de 2 horas. Siempre.</p>
            </div>
          </div>

          <div class="value-item">
            <span class="value-dot"></span>
            <div>
              <strong>Soluciones a medida</strong>
              <p>Adaptamos cada servicio a las necesidades reales de tu empresa.</p>
            </div>
          </div>

          <div class="value-item">
            <span class="value-dot"></span>
            <div>
              <strong>Certificados y actualizados</strong>
              <p>Microsoft Partner, ISO 27001, AWS y Google Workspace Certified.</p>
            </div>
          </div>

        </div>
        <!-- FIN values-list -->

        <!-- Badges de certificaciones y partnerships -->
        <div class="partner-badges">
          <!-- Cada .badge es un span con texto.
               🎯 EJERCICIO: Añade más certificaciones relevantes al negocio -->
          <span class="badge">Microsoft Partner</span>
          <span class="badge">ISO 27001</span>
          <span class="badge">AWS Certified</span>
          <span class="badge">Google Workspace</span>
        </div>

      </div>
      <!-- FIN about-text-col -->

    </div>
    <!-- FIN about-layout -->

  </div>
</section>
<!-- FIN section#nosotros -->

<!--
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 6 HTML: CTA BAND — Llamada a la acción                         ║
  ╚══════════════════════════════════════════════════════════════════════════╝

  Esta sección NO usa <section> semántica ya que es más bien decorativa/funcional.
  Se puede usar <div> cuando no hay un significado semántico claro,
  aunque técnicamente también sería válido usar <section>.

  El fondo naranja contrastan fuertemente con las secciones grises → atrae la mirada.
  Es una técnica clásica de diseño: "interrupción de patrón" para captar atención.
-->
<section class="cta-band">
  <div class="cta-inner">

    <!-- Texto de la CTA -->
    <div>
      <h2>¿Listo para mejorar tu tecnología?</h2>
      <p>Cuéntanos tu proyecto y te preparamos una propuesta sin compromiso.</p>
    </div>

    <!-- Botón blanco sobre fondo naranja → máximo contraste -->
    <a href="#contacto" class="btn btn-white">Solicitar presupuesto gratuito</a>

  </div>
</section>
<!-- FIN cta-band -->

<!--
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 7 HTML: CONTACTO — Formulario                                  ║
  ╚══════════════════════════════════════════════════════════════════════════╝
-->
<section class="section" id="contacto">
  <div class="container">

    <div class="section-header">
      <span class="pill">Hablemos</span>
      <h2>¿Tienes un <span class="accent">proyecto</span>?</h2>
      <p>Rellena el formulario y te respondemos en menos de 24 horas.</p>
    </div>

    <!-- Grid de 2 columnas: sidebar de datos | formulario -->
    <div class="contact-layout">

      <!-- ── SIDEBAR: Información de contacto ── -->
      <div class="contact-sidebar">
        <h3>Datos de contacto</h3>

        <!-- Lista de métodos de contacto (teléfono, email, horario) -->
        <ul class="contact-list">

          <!-- ÍTEM DE CONTACTO: Teléfono -->
          <li>
            <!-- Ícono de teléfono -->
            <div class="c-icon">
              <svg viewBox="0 0 24 24" fill="none">
                <path d="M22 16.92v3a2 2 0 01-2.18 2 19.8 19.8 0 01-8.63-3.07 19.5 19.5 0 01-6-6 19.8 19.8 0 01-3.07-8.67A2 2 0 014.11 2h3a2 2 0 012 1.72c.13.96.36 1.9.7 2.81a2 2 0 01-.45 2.11L8.09 9.91a16 16 0 006 6l1.27-1.27a2 2 0 012.11-.45c.91.34 1.85.57 2.81.7A2 2 0 0122 16.92z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>
            <div>
              <strong>Teléfono</strong>
              <!-- href="tel:" permite llamar directamente al hacer clic en móvil -->
              <a href="tel:+34900123456">+34 900 123 456</a>
            </div>
          </li>

          <!-- ÍTEM DE CONTACTO: Email -->
          <li>
            <div class="c-icon">
              <svg viewBox="0 0 24 24" fill="none">
                <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <polyline points="22,6 12,13 2,6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>
            <div>
              <strong>Email</strong>
              <!-- href="mailto:" abre el cliente de correo del usuario -->
              <a href="mailto:info@servitic.es">info@servitic.es</a>
            </div>
          </li>

          <!-- ÍTEM DE CONTACTO: Horario -->
          <li>
            <div class="c-icon">
              <svg viewBox="0 0 24 24" fill="none">
                <circle cx="12" cy="12" r="10" stroke="currentColor" stroke-width="2"/>
                <polyline points="12,6 12,12 16,14" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>
            <div>
              <strong>Horario</strong>
              <!-- <span> para texto que no es un enlace -->
              <span>Lun–Vie 8:00–20:00<br/>Soporte 24/7</span>
            </div>
          </li>

        </ul>
        <!-- FIN contact-list -->

        <!-- Nota informativa con ícono de información -->
        <div class="sidebar-note">
          <svg viewBox="0 0 20 20" fill="none">
            <path d="M10 18a8 8 0 100-16 8 8 0 000 16zm0-11v4m0 2v.5" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>
          </svg>
          Respuesta garantizada en menos de 24 horas laborables.
        </div>

      </div>
      <!-- FIN contact-sidebar -->

      <!--
        <form>: Elemento semántico para formularios.
        ATRIBUTOS IMPORTANTES:
          novalidate → Desactiva la validación nativa del navegador.
          Así podemos controlar la validación con CSS o JS personalizado.
          (Sin novalidate, el navegador muestra sus propios errores en inglés)

        EN PRODUCCIÓN necesitarías:
          action="enviar.php" → URL donde se envían los datos
          method="POST" → Método HTTP (POST para datos sensibles, GET para búsquedas)

        O con JavaScript moderno (sin recargar la página):
          event.preventDefault() + fetch('/api/contacto', { method: 'POST', body: datos })

        🎯 EJERCICIO AVANZADO: Añade este script al final del <body> para
           mostrar un mensaje al enviar el formulario:
           <script>
             document.querySelector('form').addEventListener('submit', function(e) {
               e.preventDefault();
               alert('¡Mensaje enviado! Te contactaremos pronto.');
             });
           </script>
      -->
      <form class="contact-form" novalidate>

        <!-- FILA 1: Nombre y Empresa en dos columnas -->
        <div class="form-row two-col">

          <!-- GRUPO: Nombre (obligatorio) -->
          <div class="form-group">
            <!-- <label for="nombre"> vincula la etiqueta al input por el id.
                 Al hacer clic en la etiqueta, el foco va al input.
                 IMPORTANTE para accesibilidad: cada input debe tener su label. -->
            <label for="nombre">Nombre <span class="req">*</span></label>
            <!-- <input type="text">: campo de texto de una línea
                 id="nombre" → vinculado con el label
                 name="nombre" → nombre del campo al enviar el formulario
                 placeholder → texto de ayuda que desaparece al escribir
                 required → campo obligatorio (validación HTML nativa) -->
            <input type="text" id="nombre" name="nombre" placeholder="Tu nombre completo" required />
          </div>

          <!-- GRUPO: Empresa (opcional, sin asterisco) -->
          <div class="form-group">
            <label for="empresa">Empresa</label>
            <input type="text" id="empresa" name="empresa" placeholder="Nombre de tu empresa" />
          </div>

        </div>
        <!-- FIN form-row 1 -->

        <!-- FILA 2: Email y Teléfono -->
        <div class="form-row two-col">

          <!-- GRUPO: Email (type="email" valida el formato automáticamente) -->
          <div class="form-group">
            <label for="email">Email <span class="req">*</span></label>
            <!-- type="email" → El teclado móvil muestra @ automáticamente
                               → El navegador valida el formato si no hay "novalidate" -->
            <input type="email" id="email" name="email" placeholder="tu@email.com" required />
          </div>

          <!-- GRUPO: Teléfono (type="tel" muestra teclado numérico en móvil) -->
          <div class="form-group">
            <label for="telefono">Teléfono</label>
            <!-- type="tel" → teclado numérico en móviles -->
            <input type="tel" id="telefono" name="telefono" placeholder="+34 000 000 000" />
          </div>

        </div>
        <!-- FIN form-row 2 -->

        <!-- GRUPO: Selector de servicio -->
        <div class="form-group">
          <label for="servicio">Servicio de interés</label>
          <!--
            <select>: Lista desplegable.
            La primera <option> con value="" actúa como placeholder.
            &amp; = entidad HTML para el símbolo &

            🎯 EJERCICIO: Añade más opciones con <option> o
               agrupa servicios con <optgroup label="Soporte">:
               <optgroup label="Mantenimiento">
                 <option>Preventivo</option>
                 <option>Correctivo</option>
               </optgroup>
          -->
          <select id="servicio" name="servicio">
            <option value="">Selecciona un servicio...</option>
            <option>Mantenimiento Informático</option>
            <option>Redes e Infraestructura</option>
            <option>Cloud &amp; Servidores</option>
            <option>Ciberseguridad</option>
            <option>Software &amp; Licencias</option>
            <option>Soporte Técnico 24/7</option>
            <option>Otro</option>
          </select>
        </div>

        <!-- GRUPO: Mensaje / Textarea -->
        <div class="form-group">
          <label for="mensaje">Mensaje <span class="req">*</span></label>
          <!--
            <textarea>: Campo de texto de múltiples líneas.
            rows="5" → Altura inicial en líneas (el usuario puede redimensionar).
            El contenido va ENTRE las etiquetas (no en value="" como los input).
            Para placeholder: igual que en input, con el atributo placeholder.
          -->
          <textarea id="mensaje" name="mensaje" rows="5" placeholder="Cuéntanos qué necesitas..." required></textarea>
        </div>

        <!-- Checkbox de aceptación de privacidad (OBLIGATORIO por LOPD) -->
        <div class="form-check">
          <!--
            type="checkbox": Casilla de verificación que el usuario marca/desmarca.
            id vinculado con el <label for="privacidad"> de abajo.
            required → No se puede enviar el formulario sin marcar esta casilla.

            LOPD: La Ley Orgánica de Protección de Datos española OBLIGA a
            obtener consentimiento explícito antes de tratar datos personales.
            Este checkbox cumple con esa obligación legal.
          -->
          <input type="checkbox" id="privacidad" name="privacidad" required />
          <label for="privacidad">
            He leído y acepto la
            <!-- Enlace a la política de privacidad (ancla dentro de la página)
                 En un sitio real, esto enlazaría a una página completa de privacidad -->
            <a href="#privacidad-politica">Política de Privacidad</a>
          </label>
        </div>

        <!--
          <button type="submit">: Envía el formulario.
          Alternativa: <input type="submit" value="Enviar">
          DIFERENCIA: <button> puede contener HTML (iconos, spans, etc.)
                      <input type="submit"> solo acepta texto plano.

          Las clases le dan el estilo naranja a ancho completo.
        -->
        <button type="submit" class="btn btn-primary btn-submit">Enviar mensaje</button>

      </form>
      <!-- FIN contact-form -->

    </div>
    <!-- FIN contact-layout -->

  </div>
</section>
<!-- FIN section#contacto -->

<!--
  ╔══════════════════════════════════════════════════════════════════════════╗
  ║  SECCIÓN 8 HTML: <footer> — Pie de página                               ║
  ╚══════════════════════════════════════════════════════════════════════════╝

  <footer>: Etiqueta semántica para el pie del documento.
  Típicamente contiene: info de contacto, mapa del sitio, avisos legales,
  derechos de autor y menú LOPD.

  LOPD (Ley Orgánica de Protección de Datos): Ley española que obliga a
  los sitios web a informar sobre:
    - Política de Privacidad: cómo se usan los datos personales
    - Política de Cookies: qué cookies se instalan y para qué
    - Aviso Legal: información de la empresa, responsabilidades

  🎯 EJERCICIO: Crea páginas separadas para cada uno de estos documentos
     y enlázalos aquí correctamente:
     <a href="privacidad.html">Política de Privacidad</a>
-->
<footer class="site-footer">

  <!-- Parte superior del footer: logo + columnas de información -->
  <div class="footer-main">
    <div class="container footer-grid">

      <!-- ── COLUMNA 1: Brand / Empresa ── -->
      <div class="footer-brand">

        <!-- Logo clickable que lleva al inicio de la página -->
        <a href="#inicio" class="logo">
          <svg class="logo-icon" width="34" height="34" viewBox="0 0 38 38" fill="none">
            <rect width="38" height="38" rx="8" fill="#FF6B1A"/>
            <path d="M10 19 L16 12 L22 19 L16 26 Z" fill="white" opacity="0.95"/>
            <path d="M18 19 L24 12 L30 19 L24 26 Z" fill="white" opacity="0.55"/>
          </svg>
          <span class="logo-text">SERVI<span class="accent">TIC</span></span>
        </a>

        <!-- Tagline / descripción breve de la empresa -->
        <p>Soluciones tecnológicas para empresas que quieren seguir creciendo sin preocupaciones.</p>

        <!-- Links de contacto con iconos.
             Los iconos SVG son más fiables que caracteres Unicode (📞✉)
             ya que se renderizan igual en todos los sistemas. -->
        <div class="footer-contact-links">

          <!-- tel: activa la llamada en móviles -->
          <a href="tel:+34900123456">
            <svg viewBox="0 0 20 20" fill="none">
              <path d="M2 3a1 1 0 011-1h2.153a1 1 0 01.986.836l.74 4.435a1 1 0 01-.54 1.06l-1.548.773a11.037 11.037 0 006.105 6.105l.774-1.548a1 1 0 011.059-.54l4.435.74a1 1 0 01.836.986V17a1 1 0 01-1 1h-2C7.82 18 2 12.18 2 5V3z" stroke="currentColor" stroke-width="1.5"/>
            </svg>
            +34 900 123 456
          </a>

          <!-- mailto: abre el cliente de correo -->
          <a href="mailto:info@servitic.es">
            <!-- fill="currentColor" → El SVG hereda el color del texto del enlace -->
            <svg viewBox="0 0 20 20" fill="currentColor">
              <path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"/>
              <path d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"/>
            </svg>
            info@servitic.es
          </a>

        </div>
        <!-- FIN footer-contact-links -->

      </div>
      <!-- FIN footer-brand -->

      <!-- ── COLUMNA 2: Menú de servicios ── -->
      <div class="footer-col">
        <h4>Servicios</h4>
        <!-- Lista de enlaces a las tarjetas de servicios (van a la sección) -->
        <ul>
          <li><a href="#servicios">Mantenimiento Informático</a></li>
          <li><a href="#servicios">Redes e Infraestructura</a></li>
          <li><a href="#servicios">Cloud &amp; Servidores</a></li>
          <li><a href="#servicios">Ciberseguridad</a></li>
          <li><a href="#servicios">Software &amp; Licencias</a></li>
          <li><a href="#servicios">Soporte 24/7</a></li>
        </ul>
      </div>

      <!-- ── COLUMNA 3: Empresa + Legal LOPD ── -->
      <div class="footer-col">

        <h4>Empresa</h4>
        <ul>
          <li><a href="#nosotros">Quiénes somos</a></li>
          <li><a href="#contacto">Contacto</a></li>
          <li><a href="#contacto">Solicitar presupuesto</a></li>
        </ul>

        <!-- Menú LOPD: requerido por ley en España para webs con usuarios europeos
             En un sitio real estos enlaces van a páginas HTML independientes -->
        <h4 class="mt">Legal – LOPD</h4>
        <ul>
          <!--
            id="privacidad-politica": Este elemento ES el destino del anclaje.
            Cuando se hace clic en <a href="#privacidad-politica">, el navegador
            salta a este <li> con ese id.

            En producción: <a href="privacidad.html">Política de Privacidad</a>
          -->
          <li><a href="#privacidad-politica" id="privacidad-politica">Política de Privacidad</a></li>
          <li><a href="#cookies"      id="cookies">Política de Cookies</a></li>
          <li><a href="#aviso-legal"  id="aviso-legal">Aviso Legal</a></li>
        </ul>

      </div>
      <!-- FIN footer-col -->

    </div>
    <!-- FIN footer-grid -->
  </div>
  <!-- FIN footer-main -->

  <!-- Barra inferior: copyright + menú LOPD compacto -->
  <div class="footer-bottom">
    <div class="container footer-bottom-row">

      <!-- Copyright: el símbolo © se puede escribir como &copy; en HTML -->
      <p>© 2025 SERVITIC · Todos los derechos reservados</p>

      <!--
        <nav>: Segundo bloque de navegación de la página (legal).
        aria-label="Legal" diferencia esta nav de la principal del header.
        Los lectores de pantalla leerán "Navegación: Legal" cuando lleguen aquí.
      -->
      <nav class="lopd-bar" aria-label="Legal">
        <a href="#privacidad-politica">Política de Privacidad</a>
        <!-- aria-hidden="true": El punto separador · es puramente decorativo.
             Los lectores de pantalla lo ignorarán. -->
        <span aria-hidden="true">·</span>
        <a href="#cookies">Cookies</a>
        <span aria-hidden="true">·</span>
        <a href="#aviso-legal">Aviso Legal</a>
      </nav>

    </div>
  </div>
  <!-- FIN footer-bottom -->

</footer>
<!-- FIN site-footer -->

<!--
  ════════════════════════════════════════════════════════════════════
  SECCIÓN DE JAVASCRIPT (si lo necesitaras)
  ════════════════════════════════════════════════════════════════════
  Los scripts se colocan al FINAL del <body> (antes del </body>).
  ¿Por qué? Porque el HTML se carga de arriba a abajo.
  Si el script está en el <head>, el JavaScript se ejecuta ANTES
  de que exista el HTML → no puede manipular elementos que aún no existen.

  Este proyecto funciona SIN JavaScript (el menú hamburguesa usa el
  truco del checkbox en CSS puro).

  🎯 EJERCICIO 1: Añade un aviso de cookies con JavaScript:
  <script>
    // Si el usuario no ha aceptado cookies, mostrar el aviso
    if (!localStorage.getItem('cookiesAceptadas')) {
      document.body.insertAdjacentHTML('beforeend', `
        <div id="cookie-banner" style="
          position:fixed; bottom:0; left:0; right:0;
          background:#1a1a1a; color:#aaa; padding:1rem 1.5rem;
          display:flex; align-items:center; justify-content:space-between;
          border-top:1px solid #2e2e2e; z-index:999;">
          <p>Usamos cookies para mejorar tu experiencia. 
             <a href="#cookies" style="color:#FF6B1A">Más info</a></p>
          <button onclick="
            localStorage.setItem('cookiesAceptadas','true');
            document.getElementById('cookie-banner').remove();"
            style="background:#FF6B1A; color:white; border:none;
                   padding:.5rem 1rem; border-radius:8px; cursor:pointer;">
            Aceptar
          </button>
        </div>
      `);
    }
  </script>

  🎯 EJERCICIO 2: Añadir scroll suave + highlight del menú activo:
  <script>
    // Marcar el ítem de menú de la sección visible actualmente
    const sections = document.querySelectorAll('section[id]');
    const navLinks = document.querySelectorAll('.main-nav a');

    window.addEventListener('scroll', () => {
      let current = '';
      sections.forEach(section => {
        if (window.scrollY >= section.offsetTop - 100) {
          current = section.getAttribute('id');
        }
      });
      navLinks.forEach(link => {
        link.style.color = '';
        if (link.getAttribute('href') === '#' + current) {
          link.style.color = '#FF6B1A'; // naranja en el ítem activo
        }
      });
    });
  </script>

  🎯 EJERCICIO 3: Validación del formulario con feedback visual:
  <script>
    document.querySelector('form').addEventListener('submit', function(e) {
      e.preventDefault(); // Prevenir recarga de página
      const nombre  = document.getElementById('nombre').value;
      const email   = document.getElementById('email').value;
      const mensaje = document.getElementById('mensaje').value;
      const privacy = document.getElementById('privacidad').checked;

      if (!nombre || !email || !mensaje || !privacy) {
        alert('Por favor, completa todos los campos obligatorios (*)');
        return;
      }

      // Aquí enviarías los datos a un servidor con fetch()
      console.log('Formulario enviado:', { nombre, email, mensaje });
      alert('¡Mensaje enviado correctamente! Te contactaremos pronto.');
      this.reset(); // Limpiar el formulario
    });
  </script>
-->

</body>
<!--
  FIN DEL <body> y del documento HTML.
  Todo el contenido visible debe estar DENTRO del body.
  Nada debe ir después del </html>.
-->
</html>
<!--
  ════════════════════════════════════════════════════════════════════
  RESUMEN FINAL — Conceptos clave aprendidos
  ════════════════════════════════════════════════════════════════════

  ✅ HTML5 SEMÁNTICO:
     header, nav, section, article, footer → Dan significado al código

  ✅ CSS VARIABLES:
     :root { --nombre: valor; } → Cambiar el diseño en un solo punto

  ✅ FLEXBOX (1D):
     display: flex → Filas o columnas
     justify-content, align-items → Alineación principal y secundaria

  ✅ CSS GRID (2D):
     display: grid → Filas Y columnas simultáneamente
     grid-template-columns: repeat(3, 1fr) → 3 columnas iguales

  ✅ PSEUDO-ELEMENTOS:
     ::before, ::after → Decoraciones sin añadir HTML

  ✅ PSEUDO-CLASES:
     :hover, :focus, :checked → Estilos según estado del elemento

  ✅ RESPONSIVE DESIGN:
     @media (max-width: Xpx) → Estilos que solo aplican en ciertas pantallas

  ✅ TRANSICIONES CSS:
     transition: all .25s → Animar cambios de estilo suavemente

  ✅ ACCESIBILIDAD:
     aria-label, for/id en labels, alt en imágenes, roles semánticos

  ════════════════════════════════════════════════════════════════════
  PRÓXIMOS PASOS PARA AMPLIAR ESTE PROYECTO
  ════════════════════════════════════════════════════════════════════

  📚 NIVEL PRINCIPIANTE:
     → Añade más servicios copiando un <article class="service-card">
     → Cambia los colores de acento modificando las variables CSS en :root
     → Añade tu foto real en la sección "Quiénes somos"
     → Crea páginas HTML separadas para Privacidad, Cookies y Aviso Legal

  🛠 NIVEL INTERMEDIO:
     → Añade animaciones de entrada con @keyframes cuando el usuario hace scroll
     → Implementa un banner de cookies con JavaScript y localStorage
     → Conecta el formulario a un servicio como Formspree, EmailJS o un backend PHP
     → Añade un favicon.ico (ícono de la pestaña del navegador)

  🚀 NIVEL AVANZADO:
     → Migra a un framework: React, Vue o Svelte para componentes reutilizables
     → Implementa internacionalización (i18n) para múltiples idiomas
     → Añade un blog con un CMS headless (Contentful, Sanity, Strapi)
     → Optimiza la Performance: lazy loading de imágenes, minificación de CSS/JS
     → Configura SEO avanzado: meta OG (Open Graph), Twitter Cards, Schema.org
     → Despliega en Netlify, Vercel o GitHub Pages (hosting gratuito)

  ════════════════════════════════════════════════════════════════════
  RECURSOS PARA APRENDER MÁS
  ════════════════════════════════════════════════════════════════════
  → MDN Web Docs (developer.mozilla.org) → La referencia más completa
  → CSS Tricks (css-tricks.com) → Artículos prácticos de CSS
  → Flexbox Froggy (flexboxfroggy.com) → Juego para aprender Flexbox
  → Grid Garden (cssgridgarden.com) → Juego para aprender CSS Grid
  → Can I Use (caniuse.com) → Compatibilidad de CSS en navegadores
  ════════════════════════════════════════════════════════════════════
-->

