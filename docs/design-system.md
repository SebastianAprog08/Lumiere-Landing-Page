<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sofía Lumière — Design System</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --color-primary:#1C3D5A;
    --color-primary-dark:#132C42;
    --color-primary-light:#2E5578;
    --color-secondary:#FFFFFF;
    --color-support:#F4F6F8;
    --color-support-line:#E4E8EC;
    --color-accent:#C9A66B;
    --color-accent-dark:#AD8A50;
    --color-text:#23262B;
    --color-text-secondary:#5B6470;
    --font-display:'Poppins', sans-serif;
    --font-body:'Inter', sans-serif;
    --font-mono:'JetBrains Mono', monospace;
    --radius-sm:6px;
    --radius-md:10px;
    --radius-lg:16px;
    --space-1:4px;
    --space-2:8px;
    --space-3:16px;
    --space-4:24px;
    --space-5:32px;
    --space-6:48px;
    --space-7:64px;
    --space-8:96px;
  }

  *{box-sizing:border-box; margin:0; padding:0;}

  body{
    font-family:var(--font-body);
    color:var(--color-text);
    background:var(--color-secondary);
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }

  ::selection{ background:var(--color-accent); color:var(--color-primary-dark); }

  .wrap{ max-width:1080px; margin:0 auto; padding:0 var(--space-5); }

  /* ---------- top bar ---------- */
  .topbar{
    position:sticky; top:0; z-index:50;
    background:rgba(255,255,255,0.92);
    backdrop-filter:blur(8px);
    border-bottom:1px solid var(--color-support-line);
  }
  .topbar .wrap{ display:flex; align-items:center; justify-content:space-between; padding-top:var(--space-3); padding-bottom:var(--space-3); }
  .topbar-mark{ font-family:var(--font-display); font-weight:600; font-size:16px; color:var(--color-primary); letter-spacing:0.02em; display:flex; align-items:center; gap:8px;}
  .topbar-mark .dot{ width:8px; height:8px; border-radius:50%; background:var(--color-accent); display:inline-block;}
  .topbar-nav{ display:flex; gap:var(--space-4); flex-wrap:wrap; }
  .topbar-nav a{ font-size:13px; color:var(--color-text-secondary); text-decoration:none; font-weight:500; }
  .topbar-nav a:hover{ color:var(--color-primary); }

  /* ---------- hero ---------- */
  .hero{
    background:linear-gradient(180deg, #F8F9FA 0%, #FFFFFF 100%);
    padding:var(--space-8) 0 var(--space-7);
    border-bottom:1px solid var(--color-support-line);
  }
  .eyebrow{
    display:inline-flex; align-items:center; gap:8px;
    font-family:var(--font-mono); font-size:11px; letter-spacing:0.12em; text-transform:uppercase;
    color:var(--color-accent-dark); background:#FBF6EC; border:1px solid #EEDFC1;
    padding:6px 12px; border-radius:100px; margin-bottom:var(--space-4);
  }
  .hero h1{
    font-family:var(--font-display); font-weight:600;
    font-size:clamp(32px,5vw,52px); color:var(--color-primary); letter-spacing:-0.02em;
    max-width:820px; margin-bottom:var(--space-3);
  }
  .hero .concept{
    font-family:var(--font-display); font-weight:400; font-style:italic;
    font-size:clamp(18px,2.4vw,24px); color:var(--color-text); max-width:700px;
    border-left:3px solid var(--color-accent); padding-left:var(--space-4); margin-top:var(--space-4);
  }
  .hero .sub{ color:var(--color-text-secondary); font-size:15px; margin-top:var(--space-4); max-width:640px; }

  /* ---------- section shell ---------- */
  section{ padding:var(--space-7) 0; border-bottom:1px solid var(--color-support-line); }
  .section-head{ display:flex; align-items:baseline; gap:var(--space-3); margin-bottom:var(--space-5); }
  .section-num{ font-family:var(--font-mono); font-size:13px; color:var(--color-accent-dark); }
  .section-head h2{ font-family:var(--font-display); font-weight:600; font-size:26px; color:var(--color-primary); }
  .section-desc{ color:var(--color-text-secondary); font-size:14.5px; max-width:640px; margin-bottom:var(--space-5); }

  /* ---------- color swatches ---------- */
  .swatch-grid{ display:grid; grid-template-columns:repeat(auto-fit,minmax(220px,1fr)); gap:var(--space-4); }
  .swatch{ border:1px solid var(--color-support-line); border-radius:var(--radius-lg); overflow:hidden; background:#fff; }
  .swatch-color{ height:110px; position:relative; }
  .swatch-body{ padding:var(--space-3) var(--space-4) var(--space-4); }
  .swatch-name{ font-weight:600; font-size:14px; margin-bottom:2px; }
  .swatch-role{ font-size:12.5px; color:var(--color-text-secondary); margin-bottom:var(--space-2); }
  .swatch-codes{ display:flex; flex-direction:column; gap:2px; font-family:var(--font-mono); font-size:11.5px; color:var(--color-text-secondary); }
  .swatch-codes button{
    all:unset; cursor:pointer; display:flex; justify-content:space-between; align-items:center;
    padding:3px 6px; border-radius:4px; font-family:var(--font-mono); font-size:11.5px; color:var(--color-text-secondary);
  }
  .swatch-codes button:hover{ background:var(--color-support); color:var(--color-text); }
  .copy-hint{ opacity:0; font-size:10px; color:var(--color-accent-dark); transition:opacity .15s; }
  .swatch-codes button:hover .copy-hint{ opacity:1; }

  /* ---------- typography ---------- */
  .type-sample{ border:1px solid var(--color-support-line); border-radius:var(--radius-lg); padding:var(--space-5); margin-bottom:var(--space-4); background:#fff; }
  .type-meta{ display:flex; justify-content:space-between; align-items:center; margin-bottom:var(--space-3); flex-wrap:wrap; gap:8px;}
  .type-tag{ font-family:var(--font-mono); font-size:11.5px; color:var(--color-text-secondary); background:var(--color-support); padding:4px 10px; border-radius:100px; }
  .display-xl{ font-family:var(--font-display); font-weight:600; font-size:44px; color:var(--color-primary); letter-spacing:-0.02em; line-height:1.1;}
  .display-lg{ font-family:var(--font-display); font-weight:600; font-size:32px; color:var(--color-primary); letter-spacing:-0.01em;}
  .display-md{ font-family:var(--font-display); font-weight:500; font-size:22px; color:var(--color-primary);}
  .body-lg{ font-family:var(--font-body); font-weight:400; font-size:18px; color:var(--color-text); max-width:560px;}
  .body-md{ font-family:var(--font-body); font-weight:400; font-size:15px; color:var(--color-text); max-width:560px;}
  .body-caption{ font-family:var(--font-body); font-weight:500; font-size:12.5px; color:var(--color-text-secondary); text-transform:uppercase; letter-spacing:0.06em;}
  .weight-row{ display:flex; gap:var(--space-5); flex-wrap:wrap; margin-top:var(--space-3);}
  .weight-item span{ display:block; }
  .weight-item .w-label{ font-family:var(--font-mono); font-size:11px; color:var(--color-text-secondary); margin-top:4px;}

  /* ---------- buttons ---------- */
  .btn-row{ display:flex; gap:var(--space-4); flex-wrap:wrap; align-items:center; margin-bottom:var(--space-4); }
  .btn{
    font-family:var(--font-body); font-weight:600; font-size:14.5px;
    padding:13px 26px; border-radius:10px; border:none; cursor:pointer;
    display:inline-flex; align-items:center; gap:8px; transition:transform .15s, box-shadow .15s, background .15s;
  }
  .btn-primary{ background:var(--color-accent); color:var(--color-primary-dark); box-shadow:0 1px 2px rgba(0,0,0,0.06);}
  .btn-primary:hover{ background:var(--color-accent-dark); transform:translateY(-1px); }
  .btn-secondary{ background:var(--color-primary); color:#fff; }
  .btn-secondary:hover{ background:var(--color-primary-dark); transform:translateY(-1px); }
  .btn-ghost{ background:transparent; color:var(--color-primary); border:1.5px solid var(--color-support-line); }
  .btn-ghost:hover{ border-color:var(--color-primary); }
  .btn-sm{ padding:9px 18px; font-size:13px; border-radius:8px;}
  .do-dont{ display:grid; grid-template-columns:1fr 1fr; gap:var(--space-4); margin-top:var(--space-4);}
  .dd-card{ border-radius:var(--radius-md); padding:var(--space-4); font-size:13.5px; }
  .dd-yes{ background:#F2F8F4; border:1px solid #D3E9DA; color:#2C5C3D; }
  .dd-no{ background:#FBF1F1; border:1px solid #F0D6D6; color:#8A3B3B; }
  .dd-card strong{ display:block; margin-bottom:6px; font-family:var(--font-display); }

  /* ---------- spacing ---------- */
  .space-row{ display:flex; align-items:flex-end; gap:var(--space-3); flex-wrap:wrap; }
  .space-item{ text-align:center; }
  .space-bar{ background:var(--color-accent); border-radius:4px; width:32px; }
  .space-label{ font-family:var(--font-mono); font-size:11px; color:var(--color-text-secondary); margin-top:6px; }

  /* ---------- photography ---------- */
  .photo-grid{ display:grid; grid-template-columns:repeat(auto-fit,minmax(200px,1fr)); gap:var(--space-4); }
  .photo-slot{
    aspect-ratio:4/3; border-radius:var(--radius-lg); border:1.5px dashed var(--color-support-line);
    display:flex; align-items:center; justify-content:center; flex-direction:column; gap:8px;
    background:var(--color-support); color:var(--color-text-secondary);
  }
  .photo-slot svg{ opacity:0.35; }
  .photo-slot span{ font-size:12px; font-weight:500; }
  .rules-grid{ display:grid; grid-template-columns:1fr 1fr; gap:var(--space-5); margin-top:var(--space-5);}
  .rules-list{ list-style:none; display:flex; flex-direction:column; gap:10px; }
  .rules-list li{ display:flex; gap:10px; font-size:14px; align-items:flex-start; }
  .rules-list.yes li::before{ content:"✓"; color:#2C5C3D; font-weight:700; }
  .rules-list.no li::before{ content:"✕"; color:#8A3B3B; font-weight:700; }

  /* ---------- icons ---------- */
  .icon-row{ display:flex; gap:var(--space-5); align-items:center; flex-wrap:wrap; }
  .icon-chip{ display:flex; flex-direction:column; align-items:center; gap:8px; color:var(--color-primary); }
  .icon-chip .box{ width:52px; height:52px; border-radius:var(--radius-md); background:var(--color-support); display:flex; align-items:center; justify-content:center; border:1px solid var(--color-support-line);}
  .icon-chip span{ font-size:11.5px; color:var(--color-text-secondary); font-family:var(--font-mono); }

  /* ---------- voice ---------- */
  .voice-grid{ display:grid; grid-template-columns:1fr 1fr; gap:var(--space-4); }
  .voice-card{ border:1px solid var(--color-support-line); border-radius:var(--radius-lg); padding:var(--space-4); background:#fff;}
  .voice-card .from{ font-size:13px; text-decoration:line-through; color:#B04848; margin-bottom:6px;}
  .voice-card .to{ font-family:var(--font-display); font-weight:500; font-size:15px; color:var(--color-primary); }

  /* ---------- footer ---------- */
  footer{ padding:var(--space-6) 0; text-align:center; color:var(--color-text-secondary); font-size:12.5px; }

  @media (max-width:680px){
    .do-dont, .rules-grid, .voice-grid{ grid-template-columns:1fr; }
    .wrap{ padding:0 var(--space-3); }
    section{ padding:var(--space-6) 0; }
  }

  @media print{
    .topbar{ position:static; }
    section{ break-inside:avoid; }
  }
</style>
</head>
<body>

<div class="topbar">
  <div class="wrap">
    <div class="topbar-mark"><span class="dot"></span>Sofía Lumière — Design System</div>
    <nav class="topbar-nav">
      <a href="#concepto">Concepto</a>
      <a href="#color">Color</a>
      <a href="#tipografia">Tipografía</a>
      <a href="#botones">Botones</a>
      <a href="#espaciado">Espaciado</a>
      <a href="#fotografia">Fotografía</a>
      <a href="#iconos">Iconos</a>
      <a href="#voz">Voz</a>
    </nav>
  </div>
</div>

<div class="hero">
  <div class="wrap">
    <div class="eyebrow">Referencia visual · v1.0</div>
    <h1>El sistema de diseño de Sofía Lumière</h1>
    <p class="concept" id="concepto">"La claridad de la luz, la confianza de un profesional y la calidez de una atención humana."</p>
    <p class="sub">Este documento reúne cada decisión visual —color, tipografía, botones, fotografía e iconografía— para que sirva como referencia constante durante el desarrollo de la landing page. Cada elemento debe reforzar la idea central de arriba.</p>
  </div>
</div>

<!-- 1. DIRECCIÓN ARTÍSTICA -->
<section id="direccion">
  <div class="wrap">
    <div class="section-head"><span class="section-num">01</span><h2>Dirección artística</h2></div>
    <p class="section-desc">Lumière es una marca de salud moderna, no una clínica fría. El nivel de referencia: la limpieza visual de Apple combinada con la cercanía de una buena clínica privada — no para copiar, sino como calibre de simplicidad y cuidado.</p>
    <div class="do-dont">
      <div class="dd-card dd-no">
        <strong>Evitar</strong>
        Gafas por todas partes · ojos enormes en pantalla · azules saturados · estética de hospital · fotos de stock genéricas.
      </div>
      <div class="dd-card dd-yes">
        <strong>Buscar</strong>
        Espacio en blanco generoso · un solo azul profundo con propósito · acentos dorados discretos · fotografía real y luz natural.
      </div>
    </div>
  </div>
</section>

<!-- 2. COLOR -->
<section id="color">
  <div class="wrap">
    <div class="section-head"><span class="section-num">02</span><h2>Paleta de colores</h2></div>
    <p class="section-desc">Clic en cualquier código para copiarlo. El azul profundo es el color dominante; el dorado se reserva para acentos y llamados a la acción — nunca para grandes superficies.</p>

    <div class="swatch-grid">
      <div class="swatch">
        <div class="swatch-color" style="background:#1C3D5A"></div>
        <div class="swatch-body">
          <div class="swatch-name">Azul profundo</div>
          <div class="swatch-role">Primario — confianza, profesionalismo</div>
          <div class="swatch-codes">
            <button onclick="copyHex('#1C3D5A', this)">#1C3D5A <span class="copy-hint">copiar</span></button>
          </div>
        </div>
      </div>
      <div class="swatch">
        <div class="swatch-color" style="background:#132C42"></div>
        <div class="swatch-body">
          <div class="swatch-name">Azul profundo (hover)</div>
          <div class="swatch-role">Estados hover / activo del primario</div>
          <div class="swatch-codes">
            <button onclick="copyHex('#132C42', this)">#132C42 <span class="copy-hint">copiar</span></button>
          </div>
        </div>
      </div>
      <div class="swatch">
        <div class="swatch-color" style="background:#FFFFFF; border-bottom:1px solid var(--color-support-line)"></div>
        <div class="swatch-body">
          <div class="swatch-name">Blanco</div>
          <div class="swatch-role">Secundario — limpieza, claridad, luz</div>
          <div class="swatch-codes">
            <button onclick="copyHex('#FFFFFF', this)">#FFFFFF <span class="copy-hint">copiar</span></button>
          </div>
        </div>
      </div>
      <div class="swatch">
        <div class="swatch-color" style="background:#F4F6F8"></div>
        <div class="swatch-body">
          <div class="swatch-name">Gris muy claro</div>
          <div class="swatch-role">Apoyo — fondos, respiración</div>
          <div class="swatch-codes">
            <button onclick="copyHex('#F4F6F8', this)">#F4F6F8 <span class="copy-hint">copiar</span></button>
          </div>
        </div>
      </div>
      <div class="swatch">
        <div class="swatch-color" style="background:#C9A66B"></div>
        <div class="swatch-body">
          <div class="swatch-name">Dorado suave</div>
          <div class="swatch-role">Acento — botones y detalles clave</div>
          <div class="swatch-codes">
            <button onclick="copyHex('#C9A66B', this)">#C9A66B <span class="copy-hint">copiar</span></button>
          </div>
        </div>
      </div>
      <div class="swatch">
        <div class="swatch-color" style="background:#AD8A50"></div>
        <div class="swatch-body">
          <div class="swatch-name">Dorado (hover)</div>
          <div class="swatch-role">Estados hover del acento</div>
          <div class="swatch-codes">
            <button onclick="copyHex('#AD8A50', this)">#AD8A50 <span class="copy-hint">copiar</span></button>
          </div>
        </div>
      </div>
      <div class="swatch">
        <div class="swatch-color" style="background:#23262B"></div>
        <div class="swatch-body">
          <div class="swatch-name">Negro suave</div>
          <div class="swatch-role">Texto principal</div>
          <div class="swatch-codes">
            <button onclick="copyHex('#23262B', this)">#23262B <span class="copy-hint">copiar</span></button>
          </div>
        </div>
      </div>
      <div class="swatch">
        <div class="swatch-color" style="background:#5B6470"></div>
        <div class="swatch-body">
          <div class="swatch-name">Gris oscuro</div>
          <div class="swatch-role">Texto secundario</div>
          <div class="swatch-codes">
            <button onclick="copyHex('#5B6470', this)">#5B6470 <span class="copy-hint">copiar</span></button>
          </div>
        </div>
      </div>
      <div class="swatch">
        <div class="swatch-color" style="background:#E4E8EC"></div>
        <div class="swatch-body">
          <div class="swatch-name">Línea / borde</div>
          <div class="swatch-role">Divisores, bordes de tarjetas</div>
          <div class="swatch-codes">
            <button onclick="copyHex('#E4E8EC', this)">#E4E8EC <span class="copy-hint">copiar</span></button>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- 3. TIPOGRAFÍA -->
<section id="tipografia">
  <div class="wrap">
    <div class="section-head"><span class="section-num">03</span><h2>Tipografía</h2></div>
    <p class="section-desc">Poppins para títulos —personalidad en encabezados— e Inter para texto —excelente en lectura prolongada—. Si más adelante se busca simplificar, Inter solo también funciona.</p>

    <div class="type-sample">
      <div class="type-meta"><span class="type-tag">Poppins · Display / Títulos</span></div>
      <div class="display-xl">Ve el mundo con claridad</div>
      <div class="weight-row">
        <div class="weight-item"><span style="font-family:var(--font-display); font-weight:300; font-size:20px;">Light 300</span><span class="w-label">Aa Bb Cc</span></div>
        <div class="weight-item"><span style="font-family:var(--font-display); font-weight:400; font-size:20px;">Regular 400</span><span class="w-label">Aa Bb Cc</span></div>
        <div class="weight-item"><span style="font-family:var(--font-display); font-weight:500; font-size:20px;">Medium 500</span><span class="w-label">Aa Bb Cc</span></div>
        <div class="weight-item"><span style="font-family:var(--font-display); font-weight:600; font-size:20px;">SemiBold 600</span><span class="w-label">Aa Bb Cc</span></div>
      </div>
    </div>

    <div class="type-sample">
      <div class="type-meta"><span class="type-tag">Inter · Texto / Cuerpo</span></div>
      <p class="body-lg">Cuidamos tu visión con la misma elegancia con la que ves el mundo.</p>
      <p class="body-md" style="margin-top:10px;">Texto de párrafo estándar para descripciones de servicios, testimonios y contenido de apoyo en toda la landing page.</p>
      <div class="weight-row">
        <div class="weight-item"><span style="font-family:var(--font-body); font-weight:400; font-size:16px;">Regular 400</span><span class="w-label">Aa Bb Cc</span></div>
        <div class="weight-item"><span style="font-family:var(--font-body); font-weight:500; font-size:16px;">Medium 500</span><span class="w-label">Aa Bb Cc</span></div>
        <div class="weight-item"><span style="font-family:var(--font-body); font-weight:600; font-size:16px;">SemiBold 600</span><span class="w-label">Aa Bb Cc</span></div>
        <div class="weight-item"><span style="font-family:var(--font-body); font-weight:700; font-size:16px;">Bold 700</span><span class="w-label">Aa Bb Cc</span></div>
      </div>
    </div>

    <div class="type-sample">
      <div class="type-meta"><span class="type-tag">Escala tipográfica sugerida</span></div>
      <div style="display:flex; flex-direction:column; gap:14px;">
        <div class="display-xl">H1 — 44px / Poppins 600</div>
        <div class="display-lg">H2 — 32px / Poppins 600</div>
        <div class="display-md">H3 — 22px / Poppins 500</div>
        <p class="body-lg" style="font-size:18px;">Body large — 18px / Inter 400</p>
        <p class="body-md" style="font-size:15px;">Body — 15px / Inter 400</p>
        <p class="body-caption">Caption / eyebrow — 12.5px / Inter 500, mayúsculas</p>
      </div>
    </div>
  </div>
</section>

<!-- 4. BOTONES -->
<section id="botones">
  <div class="wrap">
    <div class="section-head"><span class="section-num">04</span><h2>Botones</h2></div>
    <p class="section-desc">Bordes ligeramente redondeados, buen espacio interno, texto directo. Las acciones nombran lo que ocurre, nunca "haz clic aquí".</p>

    <div class="btn-row">
      <button class="btn btn-primary">Agenda tu valoración</button>
      <button class="btn btn-secondary">Conoce nuestros servicios</button>
      <button class="btn btn-ghost">Solicita asesoría</button>
    </div>
    <div class="btn-row">
      <button class="btn btn-primary btn-sm">Agendar</button>
      <button class="btn btn-secondary btn-sm">Ver servicios</button>
      <button class="btn btn-ghost btn-sm">Asesoría</button>
    </div>

    <div class="do-dont">
      <div class="dd-card dd-yes">
        <strong>Usar</strong>
        Agenda tu valoración · Conoce nuestros servicios · Solicita asesoría · Escríbenos por WhatsApp
      </div>
      <div class="dd-card dd-no">
        <strong>Evitar</strong>
        Haz clic aquí · Enviar · Más info · botones con sombras pesadas o degradados llamativos
      </div>
    </div>
  </div>
</section>

<!-- 5. ESPACIADO -->
<section id="espaciado">
  <div class="wrap">
    <div class="section-head"><span class="section-num">05</span><h2>Espaciado</h2></div>
    <p class="section-desc">Escala base de 8px. Usar generosamente entre secciones para que la página "respire" — es parte del concepto de claridad.</p>
    <div class="space-row">
      <div class="space-item"><div class="space-bar" style="height:4px;"></div><div class="space-label">4 · xs</div></div>
      <div class="space-item"><div class="space-bar" style="height:8px;"></div><div class="space-label">8 · sm</div></div>
      <div class="space-item"><div class="space-bar" style="height:16px;"></div><div class="space-label">16 · md</div></div>
      <div class="space-item"><div class="space-bar" style="height:24px;"></div><div class="space-label">24 · lg</div></div>
      <div class="space-item"><div class="space-bar" style="height:32px;"></div><div class="space-label">32 · xl</div></div>
      <div class="space-item"><div class="space-bar" style="height:48px;"></div><div class="space-label">48 · 2xl</div></div>
      <div class="space-item"><div class="space-bar" style="height:64px;"></div><div class="space-label">64 · 3xl</div></div>
      <div class="space-item"><div class="space-bar" style="height:96px;"></div><div class="space-label">96 · 4xl</div></div>
    </div>
  </div>
</section>

<!-- 6. FOTOGRAFÍA -->
<section id="fotografia">
  <div class="wrap">
    <div class="section-head"><span class="section-num">06</span><h2>Estilo fotográfico</h2></div>
    <p class="section-desc">Aún no hay banco de imágenes definitivo — los siguientes espacios marcan dónde y con qué proporción irán las fotos reales.</p>

    <div class="photo-grid">
      <div class="photo-slot" style="aspect-ratio:16/9;">
        <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="5" width="18" height="14" rx="2"/><circle cx="8.5" cy="10" r="1.5"/><path d="M21 15l-5-5-4 4-3-3-6 6"/></svg>
        <span>Imagen aquí — Hero (16:9)</span>
      </div>
      <div class="photo-slot">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="5" width="18" height="14" rx="2"/><circle cx="8.5" cy="10" r="1.5"/><path d="M21 15l-5-5-4 4-3-3-6 6"/></svg>
        <span>Imagen aquí — Familia</span>
      </div>
      <div class="photo-slot">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="5" width="18" height="14" rx="2"/><circle cx="8.5" cy="10" r="1.5"/><path d="M21 15l-5-5-4 4-3-3-6 6"/></svg>
        <span>Imagen aquí — Atención profesional</span>
      </div>
      <div class="photo-slot">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="5" width="18" height="14" rx="2"/><circle cx="8.5" cy="10" r="1.5"/><path d="M21 15l-5-5-4 4-3-3-6 6"/></svg>
        <span>Imagen aquí — Adulto mayor</span>
      </div>
    </div>

    <div class="rules-grid">
      <div>
        <p class="body-caption" style="margin-bottom:10px;">Sí usar</p>
        <ul class="rules-list yes">
          <li>Personas reales, no modelos de stock evidentes</li>
          <li>Familias, niños con sus padres, adultos mayores</li>
          <li>Profesionales atendiendo pacientes en contexto</li>
          <li>Ambientes con luz natural</li>
        </ul>
      </div>
      <div>
        <p class="body-caption" style="margin-bottom:10px;">No usar</p>
        <ul class="rules-list no">
          <li>Miradas forzadas directo a cámara con sonrisa artificial</li>
          <li>Fotos de stock que se notan falsas</li>
          <li>Imágenes sobresaturadas de color</li>
          <li>Ojos gigantes ocupando media pantalla</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- 7. ICONOGRAFÍA -->
<section id="iconos">
  <div class="wrap">
    <div class="section-head"><span class="section-num">07</span><h2>Iconografía</h2></div>
    <p class="section-desc">Una sola familia de iconos, sin mezclar estilos. Trazo fino y consistente, sin relleno — se alinea con la ligereza del resto del sistema. Recomendadas: <strong>Lucide</strong> o <strong>Heroicons</strong> (outline).</p>
    <div class="icon-row">
      <div class="icon-chip">
        <div class="box"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#1C3D5A" stroke-width="1.6"><circle cx="12" cy="12" r="3"/><path d="M2 12s3.5-7 10-7 10 7 10 7-3.5 7-10 7-10-7-10-7z"/></svg></div>
        <span>eye</span>
      </div>
      <div class="icon-chip">
        <div class="box"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#1C3D5A" stroke-width="1.6"><circle cx="12" cy="12" r="5"/><line x1="12" y1="1" x2="12" y2="3"/><line x1="12" y1="21" x2="12" y2="23"/><line x1="4.2" y1="4.2" x2="5.6" y2="5.6"/><line x1="18.4" y1="18.4" x2="19.8" y2="19.8"/></svg></div>
        <span>light</span>
      </div>
      <div class="icon-chip">
        <div class="box"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#1C3D5A" stroke-width="1.6"><path d="M12 2l8 4v6c0 5-3.5 8-8 10-4.5-2-8-5-8-10V6l8-4z"/></svg></div>
        <span>trust</span>
      </div>
      <div class="icon-chip">
        <div class="box"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#1C3D5A" stroke-width="1.6"><path d="M20.8 4.6a5.5 5.5 0 0 0-7.8 0L12 5.6l-1-1a5.5 5.5 0 0 0-7.8 7.8l1 1L12 21l7.8-7.6 1-1a5.5 5.5 0 0 0 0-7.8z"/></svg></div>
        <span>care</span>
      </div>
      <div class="icon-chip">
        <div class="box"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#1C3D5A" stroke-width="1.6"><rect x="3" y="4" width="18" height="18" rx="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg></div>
        <span>calendar</span>
      </div>
    </div>
  </div>
</section>

<!-- 8. VOZ -->
<section id="voz" style="border-bottom:none;">
  <div class="wrap">
    <div class="section-head"><span class="section-num">08</span><h2>Voz y microcopy</h2></div>
    <p class="section-desc">El texto de la interfaz habla en acciones concretas, cálidas pero seguras — nunca genérico ni frío.</p>
    <div class="voice-grid">
      <div class="voice-card"><div class="from">Haz clic aquí</div><div class="to">Agenda tu valoración</div></div>
      <div class="voice-card"><div class="from">Enviar</div><div class="to">Solicita asesoría</div></div>
      <div class="voice-card"><div class="from">Más info</div><div class="to">Conoce nuestros servicios</div></div>
      <div class="voice-card"><div class="from">Bienvenido a nuestra óptica</div><div class="to">Donde la luz encuentra tu mirada</div></div>
    </div>
  </div>
</section>

<footer>
  Sofía Lumière — Design System v1.0 · Documento de referencia para desarrollo
</footer>

<script>
function copyHex(hex, el){
  navigator.clipboard.writeText(hex).then(()=>{
    const hint = el.querySelector('.copy-hint');
    const original = hint.textContent;
    hint.textContent = '¡copiado!';
    hint.style.opacity = '1';
    setTimeout(()=>{ hint.textContent = original; }, 1200);
  });
}
</script>

</body>
</html>