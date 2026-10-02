<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SC&amp;E Newsletter — Septiembre 2026</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Syne:wght@700;800&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --dark: #0e0e18;
    --dark2: #181828;
    --dark3: #22223a;
    --purple: #6c5ce7;
    --purple-light: #a29bfe;
    --teal: #00cec9;
    --teal-light: #81ecec;
    --coral: #e17055;
    --gold: #fdcb6e;
    --white: #ffffff;
    --off-white: #f8f7ff;
    --muted: #9a97b8;
    --card-bg: #1c1c30;
    --card-border: rgba(255,255,255,0.07);
    --radius: 14px;
    --radius-sm: 8px;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Inter', sans-serif;
    background: var(--dark);
    color: var(--white);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── LAYOUT ── */
  .shell {
    display: grid;
    grid-template-columns: 220px 1fr;
    min-height: 100vh;
  }

  /* ── SIDEBAR ── */
  .sidebar {
    background: var(--dark2);
    border-right: 1px solid var(--card-border);
    display: flex;
    flex-direction: column;
    padding: 2rem 0;
    position: sticky;
    top: 0;
    height: 100vh;
    overflow-y: auto;
  }

  .sidebar-brand {
    padding: 0 1.5rem 2rem;
    border-bottom: 1px solid var(--card-border);
  }
  .sidebar-brand .label {
    font-size: 10px;
    letter-spacing: 3px;
    color: var(--purple-light);
    font-weight: 500;
    margin-bottom: 4px;
    text-transform: uppercase;
  }
  .sidebar-brand .title {
    font-family: 'Syne', sans-serif;
    font-size: 22px;
    font-weight: 800;
    line-height: 1.1;
    color: var(--white);
  }
  .sidebar-brand .month {
    font-size: 12px;
    color: var(--muted);
    margin-top: 4px;
  }

  .nav-list {
    list-style: none;
    padding: 1.5rem 0.75rem;
    display: flex;
    flex-direction: column;
    gap: 2px;
    flex: 1;
  }
  .nav-list li a {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 10px 12px;
    border-radius: var(--radius-sm);
    text-decoration: none;
    color: var(--muted);
    font-size: 13px;
    font-weight: 400;
    transition: background 0.15s, color 0.15s;
    cursor: pointer;
  }
  .nav-list li a:hover, .nav-list li a.active {
    background: rgba(108,92,231,0.15);
    color: var(--purple-light);
  }
  .nav-list li a .nav-icon {
    width: 28px;
    height: 28px;
    border-radius: 6px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 14px;
    flex-shrink: 0;
  }
  .nav-list li a.active .nav-icon { background: rgba(108,92,231,0.25); }
  .nav-count {
    margin-left: auto;
    font-size: 10px;
    background: rgba(108,92,231,0.25);
    color: var(--purple-light);
    padding: 2px 7px;
    border-radius: 20px;
    font-weight: 500;
  }

  .sidebar-footer {
    padding: 1rem 1.5rem;
    border-top: 1px solid var(--card-border);
    font-size: 11px;
    color: var(--muted);
    line-height: 1.5;
  }
  .sidebar-footer a { color: var(--purple-light); text-decoration: none; }

  /* ── MAIN ── */
  main {
    padding: 2.5rem 3rem;
    max-width: 860px;
  }

  .section { display: none; }
  .section.visible { display: block; }

  .section-head {
    margin-bottom: 2rem;
  }
  .section-eyebrow {
    font-size: 11px;
    font-weight: 500;
    color: var(--purple-light);
    margin-bottom: 6px;
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .section-eyebrow::after {
    content: '';
    flex: 1;
    max-width: 40px;
    height: 1px;
    background: var(--purple);
    opacity: 0.4;
  }
  .section-h1 {
    font-family: 'Syne', sans-serif;
    font-size: 32px;
    font-weight: 800;
    line-height: 1.15;
    color: var(--white);
  }
  .section-sub {
    font-size: 14px;
    color: var(--muted);
    margin-top: 6px;
    line-height: 1.6;
  }

  /* ── CARDS ── */
  .card {
    background: var(--card-bg);
    border: 1px solid var(--card-border);
    border-radius: var(--radius);
    padding: 1.5rem;
  }

  /* ── RECORDATORIO ── */
  .reminder-hero {
    background: linear-gradient(135deg, #6c5ce7 0%, #a29bfe 50%, #00cec9 100%);
    border-radius: var(--radius);
    padding: 2.5rem 2rem;
    position: relative;
    overflow: hidden;
    margin-bottom: 1rem;
  }
  .reminder-hero::before {
    content: '🤖';
    position: absolute;
    right: 2rem;
    top: 50%;
    transform: translateY(-50%);
    font-size: 80px;
    opacity: 0.2;
  }
  .reminder-hero .tag {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    background: rgba(255,255,255,0.2);
    color: #fff;
    font-size: 11px;
    font-weight: 500;
    padding: 4px 12px;
    border-radius: 20px;
    margin-bottom: 1rem;
    backdrop-filter: blur(8px);
  }
  .reminder-hero h2 {
    font-family: 'Syne', sans-serif;
    font-size: 24px;
    font-weight: 800;
    color: #fff;
    margin-bottom: 0.75rem;
    max-width: 400px;
    line-height: 1.2;
  }
  .reminder-hero p {
    font-size: 14px;
    color: rgba(255,255,255,0.85);
    line-height: 1.65;
    max-width: 440px;
  }
  .reminder-pills {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    margin-top: 1.5rem;
  }
  .reminder-pill {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: rgba(255,255,255,0.18);
    color: #fff;
    font-size: 12px;
    padding: 6px 14px;
    border-radius: 20px;
    font-weight: 500;
    backdrop-filter: blur(8px);
  }

  .reminder-details {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin-top: 1rem;
  }
  .reminder-detail-card {
    background: var(--card-bg);
    border: 1px solid var(--card-border);
    border-radius: var(--radius-sm);
    padding: 1rem 1.25rem;
  }
  .rdc-label { font-size: 11px; color: var(--muted); margin-bottom: 4px; }
  .rdc-value { font-size: 14px; color: var(--white); font-weight: 500; line-height: 1.4; }

  /* ── INGRESOS ── */
  .month-tab-bar {
    display: flex;
    gap: 6px;
    margin-bottom: 1.5rem;
  }
  .month-tab {
    font-size: 12px;
    padding: 6px 16px;
    border-radius: 20px;
    border: 1px solid var(--card-border);
    background: transparent;
    color: var(--muted);
    cursor: pointer;
    font-family: 'Inter', sans-serif;
    transition: all 0.15s;
  }
  .month-tab.active, .month-tab:hover {
    background: var(--purple);
    color: #fff;
    border-color: var(--purple);
  }

  .area-block { margin-bottom: 2rem; }
  .area-block:last-child { margin-bottom: 0; }
  .area-title {
    font-size: 11px;
    font-weight: 500;
    color: var(--muted);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 0.75rem;
    padding-left: 4px;
  }
  .people-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 8px;
  }
  .person-card {
    background: var(--card-bg);
    border: 1px solid var(--card-border);
    border-radius: var(--radius-sm);
    padding: 12px 14px;
    display: flex;
    align-items: center;
    gap: 10px;
    transition: border-color 0.15s;
  }
  .person-card:hover { border-color: rgba(108,92,231,0.4); }
  .avatar {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 12px;
    font-weight: 600;
    flex-shrink: 0;
  }
  .person-name { font-size: 13px; color: var(--white); line-height: 1.3; }
  .person-meta { font-size: 11px; color: var(--muted); margin-top: 2px; }

  .av-sp   { background: rgba(0,206,201,0.15); color: var(--teal-light); }
  .av-ff   { background: rgba(162,155,254,0.15); color: var(--purple-light); }
  .av-icp  { background: rgba(253,203,110,0.15); color: var(--gold); }
  .av-plan { background: rgba(225,112,85,0.15); color: var(--coral); }

  /* ── CERTIFICACIONES ── */
  .cert-toolbar {
    display: flex;
    gap: 8px;
    margin-bottom: 1.25rem;
    flex-wrap: wrap;
    align-items: center;
  }
  .cert-filter-btn {
    font-size: 11px;
    padding: 5px 14px;
    border-radius: 20px;
    border: 1px solid var(--card-border);
    background: transparent;
    color: var(--muted);
    cursor: pointer;
    font-family: 'Inter', sans-serif;
    transition: all 0.15s;
  }
  .cert-filter-btn:hover { border-color: var(--purple); color: var(--purple-light); }
  .cert-filter-btn.active { background: var(--purple); color: #fff; border-color: var(--purple); }
  .cert-search {
    margin-left: auto;
    background: var(--card-bg);
    border: 1px solid var(--card-border);
    color: var(--white);
    font-size: 12px;
    padding: 6px 12px;
    border-radius: var(--radius-sm);
    font-family: 'Inter', sans-serif;
    outline: none;
    width: 180px;
    transition: border-color 0.15s;
  }
  .cert-search:focus { border-color: var(--purple); }
  .cert-search::placeholder { color: var(--muted); }

  .cert-stats {
    display: flex;
    gap: 12px;
    margin-bottom: 1.5rem;
    flex-wrap: wrap;
  }
  .cert-stat {
    background: var(--card-bg);
    border: 1px solid var(--card-border);
    border-radius: var(--radius-sm);
    padding: 12px 18px;
    display: flex;
    flex-direction: column;
    gap: 2px;
  }
  .cert-stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 26px;
    font-weight: 800;
    color: var(--white);
    line-height: 1;
  }
  .cert-stat-label { font-size: 11px; color: var(--muted); }

  .cert-list { display: flex; flex-direction: column; gap: 6px; }
  .cert-item {
    background: var(--card-bg);
    border: 1px solid var(--card-border);
    border-radius: var(--radius-sm);
    padding: 12px 16px;
    display: flex;
    align-items: center;
    gap: 12px;
    transition: border-color 0.15s;
  }
  .cert-item:hover { border-color: rgba(108,92,231,0.35); }
  .cert-item-avatar {
    width: 34px;
    height: 34px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 11px;
    font-weight: 600;
    flex-shrink: 0;
  }
  .cert-info { flex: 1; min-width: 0; }
  .cert-person { font-size: 13px; font-weight: 500; color: var(--white); }
  .cert-name { font-size: 12px; color: var(--muted); margin-top: 2px; line-height: 1.35; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
  .cert-badge {
    font-size: 10px;
    font-weight: 600;
    padding: 3px 10px;
    border-radius: 20px;
    flex-shrink: 0;
  }
  .badge-ff  { background: rgba(162,155,254,0.15); color: var(--purple-light); }
  .badge-sp  { background: rgba(0,206,201,0.15); color: var(--teal-light); }
  .badge-vct { background: rgba(253,203,110,0.15); color: var(--gold); }

  .cert-empty {
    text-align: center;
    padding: 3rem;
    color: var(--muted);
    font-size: 14px;
  }

  /* ── D&I ── */
  .di-hero {
    background: var(--card-bg);
    border: 1px solid var(--card-border);
    border-radius: var(--radius);
    overflow: hidden;
    margin-bottom: 1rem;
  }
  .di-banner {
    background: linear-gradient(135deg, #fd79a8 0%, #e84393 50%, #6c5ce7 100%);
    padding: 2rem;
    position: relative;
    overflow: hidden;
  }
  .di-banner::after {
    content: '🤟';
    position: absolute;
    right: 2rem;
    top: 50%;
    transform: translateY(-50%);
    font-size: 70px;
    opacity: 0.25;
  }
  .di-banner .date-pill {
    display: inline-block;
    background: rgba(255,255,255,0.2);
    color: #fff;
    font-size: 11px;
    font-weight: 600;
    padding: 4px 12px;
    border-radius: 20px;
    margin-bottom: 0.75rem;
  }
  .di-banner h2 {
    font-family: 'Syne', sans-serif;
    font-size: 22px;
    font-weight: 800;
    color: #fff;
    max-width: 380px;
    line-height: 1.2;
    margin-bottom: 0.5rem;
  }
  .di-banner p {
    font-size: 13px;
    color: rgba(255,255,255,0.8);
    max-width: 420px;
    line-height: 1.6;
  }
  .di-facts {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 0;
  }
  .di-fact {
    padding: 1rem 1.25rem;
    border-right: 1px solid var(--card-border);
    border-top: 1px solid var(--card-border);
    cursor: pointer;
    transition: background 0.15s;
  }
  .di-fact:nth-child(3n) { border-right: none; }
  .di-fact:hover { background: rgba(255,255,255,0.03); }
  .di-fact-emoji { font-size: 20px; margin-bottom: 6px; }
  .di-fact-text { font-size: 12px; color: var(--muted); line-height: 1.55; }

  /* ── SQUAD ── */
  .squad-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(170px, 1fr));
    gap: 12px;
  }
  .squad-card {
    background: var(--card-bg);
    border: 1px solid var(--card-border);
    border-radius: var(--radius);
    padding: 1.5rem 1rem;
    text-align: center;
    transition: border-color 0.15s, transform 0.15s;
    cursor: pointer;
  }
  .squad-card:hover {
    border-color: rgba(108,92,231,0.45);
    transform: translateY(-2px);
  }
  .squad-avatar {
    width: 54px;
    height: 54px;
    border-radius: 50%;
    margin: 0 auto 0.75rem;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 16px;
    font-weight: 700;
  }
  .squad-name {
    font-size: 13px;
    font-weight: 500;
    color: var(--white);
    margin-bottom: 4px;
    line-height: 1.3;
  }
  .squad-role {
    font-size: 11px;
    color: var(--muted);
    line-height: 1.4;
    margin-bottom: 8px;
  }
  .squad-chip {
    display: inline-block;
    font-size: 10px;
    font-weight: 600;
    padding: 3px 10px;
    border-radius: 20px;
    letter-spacing: 0.5px;
  }

  /* ── PROMOCIONES ── */
  .promo-empty-state {
    border: 2px dashed var(--card-border);
    border-radius: var(--radius);
    padding: 3rem;
    text-align: center;
    color: var(--muted);
  }
  .promo-empty-state .big { font-size: 40px; margin-bottom: 0.75rem; }
  .promo-empty-state p { font-size: 14px; line-height: 1.6; }
  .promo-empty-state strong { color: var(--white); }

  /* ── HISTORIA ── */
  .historia-empty {
    border: 2px dashed var(--card-border);
    border-radius: var(--radius);
    padding: 3rem;
    text-align: center;
    color: var(--muted);
  }
  .historia-empty .big { font-size: 40px; margin-bottom: 0.75rem; }
  .historia-empty p { font-size: 14px; line-height: 1.6; }

  /* ── MISC ── */
  .tag-pill {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    font-size: 10px;
    font-weight: 600;
    padding: 3px 10px;
    border-radius: 20px;
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 700px) {
    .shell { grid-template-columns: 1fr; }
    .sidebar { position: static; height: auto; flex-direction: row; flex-wrap: wrap; padding: 1rem; }
    .sidebar-brand { border-bottom: none; border-right: 1px solid var(--card-border); padding-right: 1.5rem; }
    .nav-list { flex-direction: row; padding: 0; }
    main { padding: 1.5rem 1.25rem; }
    .di-facts { grid-template-columns: 1fr 1fr; }
    .reminder-details { grid-template-columns: 1fr; }
    .cert-search { width: 120px; }
  }
</style>
</head>
<body>

<div class="shell">

  <!-- SIDEBAR -->
  <aside class="sidebar">
    <div class="sidebar-brand">
      <div class="label">SC &amp; E</div>
      <div class="title">Newsletter</div>
      <div class="month">Septiembre 2026</div>
    </div>
    <ul class="nav-list">
      <li><a href="#" class="active" data-section="recordatorio" onclick="nav(this)">
        <span class="nav-icon">🔔</span> Recordatorio
      </a></li>
      <li><a href="#" data-section="ingresos" onclick="nav(this)">
        <span class="nav-icon">🚀</span> Ingresos
        <span class="nav-count">10</span>
      </a></li>
      <li><a href="#" data-section="certs" onclick="nav(this)">
        <span class="nav-icon">🏅</span> Certificaciones
        <span class="nav-count">39</span>
      </a></li>
      <li><a href="#" data-section="di" onclick="nav(this)">
        <span class="nav-icon">🤟</span> Inclusión &amp; Diversidad
      </a></li>
      <li><a href="#" data-section="promo" onclick="nav(this)">
        <span class="nav-icon">🏆</span> Promociones
      </a></li>
      <li><a href="#" data-section="historia" onclick="nav(this)">
        <span class="nav-icon">📖</span> Historia del mes
      </a></li>
      <li><a href="#" data-section="squad" onclick="nav(this)">
        <span class="nav-icon">👥</span> Newsletter Squad
      </a></li>
    </ul>
    <div class="sidebar-footer">
      <div style="margin-bottom:6px">
        <a href="#">SC&amp;E Newsletter Community</a>
      </div>
      <div>¿Feedback? <a href="#">Escribinos</a></div>
    </div>
  </aside>

  <!-- MAIN -->
  <main>

    <!-- ── RECORDATORIO ── -->
    <section id="sec-recordatorio" class="section visible">
      <div class="section-head">
        <div class="section-eyebrow">Comunicado importante</div>
        <h1 class="section-h1">Recordatorio del mes</h1>
      </div>

      <div class="reminder-hero">
        <div class="tag">⚡ Acción requerida</div>
        <h2>SC&amp;E · AI Fluency Self-Assessment</h2>
        <p>Queremos escuchar tu opinión. Una breve encuesta para entender cómo estamos utilizando la IA hoy y cómo podemos crecer juntos como equipo.</p>
        <p style="margin-top:0.75rem">Estaremos enviando por correo, mediante un link de forms, una Autoevaluación de Fluidez en IA abierta a todos los miembros del equipo. No se requiere preparación previa y no hay respuestas correctas o incorrectas.</p>
        <div class="reminder-pills">
          <span class="reminder-pill">📅 21 sep → 2 oct</span>
          <span class="reminder-pill">⏱ ~5 minutos</span>
          <span class="reminder-pill">👥 Todo el equipo</span>
          <span class="reminder-pill">🚫 No es evaluación de desempeño</span>
        </div>
      </div>

      <div class="reminder-details">
        <div class="reminder-detail-card">
          <div class="rdc-label">¿Por qué participar?</div>
          <div class="rdc-value">La IA está transformando la forma en que trabajamos. Tus respuestas ayudarán a definir las herramientas, capacitaciones y guías en las que invertiremos como equipo.</div>
        </div>
        <div class="reminder-detail-card">
          <div class="rdc-label">¿Qué es?</div>
          <div class="rdc-value">Un diagnóstico para comprender la situación actual del equipo. Ni preparación previa ni respuestas correctas o incorrectas — solo tu visión honesta.</div>
        </div>
        <div class="reminder-detail-card">
          <div class="rdc-label">Disponibilidad</div>
          <div class="rdc-value">Lunes 21 de septiembre al viernes 2 de octubre de 2026.</div>
        </div>
        <div class="reminder-detail-card">
          <div class="rdc-label">Tiempo estimado</div>
          <div class="rdc-value">Aproximadamente 5 minutos para completar. Se envía el link por correo.</div>
        </div>
      </div>
    </section>

    <!-- ── INGRESOS ── -->
    <section id="sec-ingresos" class="section">
      <div class="section-head">
        <div class="section-eyebrow">Bienvenidos al equipo</div>
        <h1 class="section-h1">Ingresos &amp; nuevos talentos</h1>
        <p class="section-sub">10 nuevas personas se sumaron al equipo en agosto y septiembre 2026.</p>
      </div>

      <div class="month-tab-bar">
        <button class="month-tab active" onclick="filterMes('todos', this)">Todos</button>
        <button class="month-tab" onclick="filterMes('Agosto', this)">Agosto</button>
        <button class="month-tab" onclick="filterMes('Septiembre', this)">Septiembre</button>
      </div>

      <div id="ingresos-content"></div>
    </section>

    <!-- ── CERTIFICACIONES ── -->
    <section id="sec-certs" class="section">
      <div class="section-head">
        <div class="section-eyebrow">El equipo sigue creciendo</div>
        <h1 class="section-h1">Certificaciones &amp; cursos</h1>
        <p class="section-sub">Agosto 2026</p>
      </div>

      <div class="cert-stats">
        <div class="cert-stat">
          <div class="cert-stat-num" id="stat-total">39</div>
          <div class="cert-stat-label">Certificaciones totales</div>
        </div>
        <div class="cert-stat">
          <div class="cert-stat-num" id="stat-ff">10</div>
          <div class="cert-stat-label">Fulfillment</div>
        </div>
        <div class="cert-stat">
          <div class="cert-stat-num" id="stat-sp">8</div>
          <div class="cert-stat-label">S&amp;P</div>
        </div>
        <div class="cert-stat">
          <div class="cert-stat-num" id="stat-vct">21</div>
          <div class="cert-stat-label">VCT</div>
        </div>
      </div>

      <div class="cert-toolbar">
        <button class="cert-filter-btn active" onclick="filterCert('all', this)">Todos</button>
        <button class="cert-filter-btn" onclick="filterCert('FF', this)">Fulfillment</button>
        <button class="cert-filter-btn" onclick="filterCert('S&P', this)">S&amp;P</button>
        <button class="cert-filter-btn" onclick="filterCert('VCT', this)">VCT</button>
        <input class="cert-search" type="text" placeholder="Buscar persona..." id="cert-search-input" oninput="searchCerts(this.value)">
      </div>

      <div class="cert-list" id="cert-list"></div>
    </section>

    <!-- ── D&I ── -->
    <section id="sec-di" class="section">
      <div class="section-head">
        <div class="section-eyebrow">Calendario inclusión &amp; diversidad</div>
        <h1 class="section-h1">Inclusión &amp; Diversidad</h1>
      </div>

      <div class="di-hero">
        <div class="di-banner">
          <div class="date-pill">23 de Septiembre</div>
          <h2>Día Internacional de las Lenguas de Señas</h2>
          <p>Para comenzar, es importante reconocer que las lenguas de señas facilitan la comunicación y participación de millones de personas sordas en todo el mundo.</p>
        </div>
        <div class="di-facts">
          <div class="di-fact">
            <div class="di-fact-emoji">📚</div>
            <div class="di-fact-text">Las lenguas de señas son idiomas completos, con gramática y estructura propias.</div>
          </div>
          <div class="di-fact">
            <div class="di-fact-emoji">🌍</div>
            <div class="di-fact-text">No existe una lengua de señas universal. Cada país, e incluso algunas regiones, tiene la suya propia.</div>
          </div>
          <div class="di-fact">
            <div class="di-fact-emoji">😊</div>
            <div class="di-fact-text">Las expresiones faciales son parte de la gramática — no solo las manos comunican.</div>
          </div>
          <div class="di-fact">
            <div class="di-fact-emoji">🤝</div>
            <div class="di-fact-text">La accesibilidad en la comunicación beneficia a toda la sociedad y promueve la igualdad de oportunidades.</div>
          </div>
          <div class="di-fact">
            <div class="di-fact-emoji">🌱</div>
            <div class="di-fact-text">Aprender algunas señas básicas ayuda a construir entornos más inclusivos y acogedores.</div>
          </div>
          <div class="di-fact">
            <div class="di-fact-emoji">🏠</div>
            <div class="di-fact-text">Crear espacios accesibles es una responsabilidad compartida. La inclusión empieza cuando todos pueden comunicarse.</div>
          </div>
        </div>
      </div>

      <div class="card" style="margin-top:1rem">
        <div style="font-size:13px;color:var(--muted);line-height:1.65">
          💡 <strong style="color:var(--white)">¿Sabías que…?</strong> El respeto por las diferentes formas de comunicación fortalece el sentido de pertenencia. La diversidad lingüística también incluye las lenguas de señas. La inclusión comienza cuando todos pueden comunicarse y ser escuchados.
        </div>
      </div>
    </section>

    <!-- ── PROMOCIONES ── -->
    <section id="sec-promo" class="section">
      <div class="section-head">
        <div class="section-eyebrow">Reconocimientos del mes</div>
        <h1 class="section-h1">Promociones</h1>
      </div>
      <div class="promo-empty-state">
        <div class="big">🏆</div>
        <p><strong>Sin datos cargados este mes</strong><br>Completá la pestaña "Promociones" en el Excel de carga antes del día 25 para que aparezcan acá.</p>
      </div>
    </section>

    <!-- ── HISTORIA DEL MES ── -->
    <section id="sec-historia" class="section">
      <div class="section-head">
        <div class="section-eyebrow">Caso destacado</div>
        <h1 class="section-h1">Historia del mes</h1>
      </div>
      <div class="historia-empty">
        <div class="big">📖</div>
        <p>La historia del mes aún no fue cargada.<br>Completá la pestaña "Historia del Mes" en el Excel para que aparezca acá.</p>
      </div>
    </section>

    <!-- ── SQUAD ── -->
    <section id="sec-squad" class="section">
      <div class="section-head">
        <div class="section-eyebrow">El equipo editorial</div>
        <h1 class="section-h1">Newsletter Squad</h1>
        <p class="section-sub">Las personas detrás de cada edición mensual.</p>
      </div>
      <div class="squad-grid" id="squad-grid"></div>
    </section>

  </main>
</div>

<script>
/* ── DATA ── */
const ingresos = [
  {nombre:"Jannet Rodríguez Dávila, Erika", area:"S&P", mes:"Agosto"},
  {nombre:"Cortes, Christian Alexandre", area:"S&P", mes:"Agosto"},
  {nombre:"Ibañez, Federico S.", area:"S&P", mes:"Agosto"},
  {nombre:"Lenis, Facundo", area:"S&P", mes:"Agosto"},
  {nombre:"Sorrentino, Jonás", area:"S&P", mes:"Agosto"},
  {nombre:"Degano, Mariano", area:"S&P", mes:"Septiembre"},
  {nombre:"Lenis, Facundo H.", area:"S&P", mes:"Septiembre"},
  {nombre:"Bermudez, Candela", area:"Fulfillment", mes:"Agosto"},
  {nombre:"Madero, Delfina", area:"Fulfillment", mes:"Agosto"},
  {nombre:"López Morel, Bernardo", area:"I&CP", mes:"Agosto"},
];

const certs = [
  {nombre:"Nestor Romera", cert:"SAP Certified - Positioning SAP Business AI Solutions as part of SAP Business Suite", area:"FF"},
  {nombre:"Lifranny Alvarado", cert:"SAP Certified - Positioning the Autonomous Enterprise", area:"FF"},
  {nombre:"Valentino Taborda", cert:"Integration Developer", area:"FF"},
  {nombre:"Luciana Tavella", cert:"SAP Certified - SAP S/4HANA Cloud Private Edition, Extended Warehouse Management", area:"FF"},
  {nombre:"Luciana Tavella", cert:"SAP Certified - Positioning the Autonomous Enterprise", area:"FF"},
  {nombre:"Edgardo Ayala", cert:"SAP Manufacturing", area:"FF"},
  {nombre:"Edgardo Ayala", cert:"SAP Certified - Positioning the Autonomous Enterprise", area:"FF"},
  {nombre:"Luciano Rivadera", cert:"SAP Certified - Positioning the Autonomous Enterprise", area:"FF"},
  {nombre:"Natalia Merlo", cert:"SAP Certified - Positioning the Autonomous Enterprise", area:"FF"},
  {nombre:"Natalia Merlo", cert:"SAP Certified - Project Manager - SAP Activate for Agile Implementation Management", area:"FF"},
  {nombre:"Andres Buzzurro", cert:"Coupa", area:"S&P"},
  {nombre:"Francisco Allende", cert:"SAP Certified - Implementing SAP S/4HANA Cloud Public Edition, Sourcing and Procurement", area:"S&P"},
  {nombre:"Agustin Ayala", cert:"SAP Certified - Positioning the Autonomous Enterprise", area:"S&P"},
  {nombre:"Jesus Martinez", cert:"SAP Certified - Positioning the Autonomous Enterprise", area:"S&P"},
  {nombre:"Romina Braun", cert:"SAP Certified - Positioning the Autonomous Enterprise", area:"S&P"},
  {nombre:"Flor Heredia", cert:"SAP Certified Associate - Implementation Consultant - SAP Business Network for Supply Chain", area:"S&P"},
  {nombre:"Flavio Peralta", cert:"SAP Certified Ariba Buying and Invoicing", area:"S&P"},
  {nombre:"Meiby Uribe", cert:"SAP Certified - Positioning the Autonomous Enterprise", area:"S&P"},
  {nombre:"Santiago Luna", cert:"SAP Certified Associate - Process Data Analyst - SAP Signavio (C_SIGDA)", area:"VCT"},
  {nombre:"Josefina Buteler", cert:"SAP Certified Associate - Process Data Analyst - SAP Signavio (C_SIGDA)", area:"VCT"},
  {nombre:"Alfredo Herrera", cert:"SAP Certified Associate - Process Data Analyst - SAP Signavio (C_SIGDA)", area:"VCT"},
  {nombre:"Julia Angelani", cert:"SAP Certified Associate - Business Transformation Consultant (C_SIGBT)", area:"VCT"},
  {nombre:"D.K. Rodriguez", cert:"Drive SAP S/4Hana Transformations with SAP Signavio Solutions", area:"VCT"},
  {nombre:"Marcelo D. Amarilla", cert:"SAP Signavio Manager - Customer Journey", area:"VCT"},
  {nombre:"Maria Jose Aguilar", cert:"SAP Certified Associate - Process Management Consultant (C_SIGPM)", area:"VCT"},
  {nombre:"Narella E. Caceres", cert:"SAP Certified Associate - Process Management Consultant (C_SIGPM)", area:"VCT"},
  {nombre:"Maria Del R. Cicconi", cert:"SAP Certified Associate - Process Management Consultant (C_SIGPM)", area:"VCT"},
  {nombre:"Juan B. Colombatti", cert:"SAP Certified Associate - Process Management Consultant (C_SIGPM)", area:"VCT"},
  {nombre:"Iara Diaz", cert:"SAP Certified Associate - Process Management Consultant (C_SIGPM)", area:"VCT"},
  {nombre:"Julian B. Fernandez", cert:"SAP Certified Associate - Process Data Analyst - SAP Signavio (C_SIGDA)", area:"VCT"},
  {nombre:"Julieta Montes", cert:"SAP Certified Associate - Process Management Consultant (C_SIGPM)", area:"VCT"},
  {nombre:"Julian Osuna", cert:"SAP Certified Associate - Process Data Analyst - SAP Signavio (C_SIGDA)", area:"VCT"},
  {nombre:"Julian Osuna", cert:"SAP Certified Associate - Process Management Consultant (C_SIGPM)", area:"VCT"},
  {nombre:"Leonel D. Pascansky", cert:"SAP Certified Associate - Process Data Analyst - SAP Signavio (C_SIGDA)", area:"VCT"},
  {nombre:"I.M. Perez Donadio", cert:"SAP Certified Associate - Process Management Consultant (C_SIGPM)", area:"VCT"},
  {nombre:"Celina A. Perino", cert:"SAP Certified Associate - Process Management Consultant (C_SIGPM)", area:"VCT"},
  {nombre:"Emilia Romero", cert:"SAP Certified Associate - Process Management Consultant (C_SIGPM)", area:"VCT"},
  {nombre:"Heraly Torrelles", cert:"SAP Certified Associate - Process Management Consultant (C_SIGPM)", area:"VCT"},
  {nombre:"Emilia Toyos", cert:"SAP Certified Associate - Process Management Consultant (C_SIGPM)", area:"VCT"},
];

const squad = [
  {nombre:"Sabaté, Carolina", rol:"Management Consulting Manager", offering:"S&P"},
  {nombre:"Rivadera, Luciano", rol:"Management Consulting Manager", offering:"FF"},
  {nombre:"Sanchez, Camila", rol:"Management Consultant", offering:"FF"},
  {nombre:"Giovannetti, Ayelén", rol:"Management Consultant", offering:"S&P"},
  {nombre:"Guarducci, Constanza", rol:"Management Consultant", offering:"Planning"},
  {nombre:"Casalla, Jazmín", rol:"Management Consulting Analyst", offering:"S&P"},
  {nombre:"Barboza, Lucas", rol:"MC Senior Analyst", offering:"FF"},
  {nombre:"Zarraga, Jessica", rol:"Management Consulting", offering:"E&RD"},
  {nombre:"Tavella, Luciana", rol:"Management Consulting", offering:"FF"},
  {nombre:"López Morel, Bernardo", rol:"Management Consulting", offering:"I&CP"},
];

/* ── HELPERS ── */
function initials(name) {
  return name.split(/[\s,]+/).filter(Boolean).slice(0,2).map(p => p[0].toUpperCase()).join('');
}

const areaColors = {
  "S&P":    {bg:"rgba(0,206,201,0.15)", color:"#81ecec"},
  "Fulfillment": {bg:"rgba(162,155,254,0.15)", color:"#a29bfe"},
  "FF":     {bg:"rgba(162,155,254,0.15)", color:"#a29bfe"},
  "I&CP":   {bg:"rgba(253,203,110,0.15)", color:"#fdcb6e"},
  "VCT":    {bg:"rgba(253,203,110,0.15)", color:"#fdcb6e"},
  "Planning":{bg:"rgba(225,112,85,0.15)", color:"#e17055"},
  "E&RD":   {bg:"rgba(253,121,108,0.15)", color:"#ff7675"},
};

function acColor(area) {
  return areaColors[area] || {bg:"rgba(255,255,255,0.1)", color:"#dfe6e9"};
}

/* ── NAV ── */
function nav(el) {
  event.preventDefault();
  document.querySelectorAll('.nav-list a').forEach(a => a.classList.remove('active'));
  el.classList.add('active');
  const id = el.dataset.section;
  document.querySelectorAll('.section').forEach(s => s.classList.remove('visible'));
  document.getElementById('sec-' + id).classList.add('visible');
}

/* ── INGRESOS ── */
let mesFiltro = 'todos';

function filterMes(mes, btn) {
  mesFiltro = mes;
  document.querySelectorAll('.month-tab').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  renderIngresos();
}

function renderIngresos() {
  const filtered = mesFiltro === 'todos' ? ingresos : ingresos.filter(i => i.mes === mesFiltro);
  const areas = {};
  filtered.forEach(p => {
    if (!areas[p.area]) areas[p.area] = [];
    areas[p.area].push(p);
  });

  const avClass = {"S&P":"av-sp","Fulfillment":"av-ff","I&CP":"av-icp"};

  let html = '';
  Object.entries(areas).forEach(([area, people]) => {
    const col = acColor(area);
    html += `<div class="area-block">
      <div class="area-title">${area} <span style="font-size:10px;background:${col.bg};color:${col.color};padding:2px 8px;border-radius:10px;margin-left:4px;font-weight:600">${people.length}</span></div>
      <div class="people-grid">`;
    people.forEach(p => {
      const initls = initials(p.nombre);
      html += `<div class="person-card">
        <div class="avatar" style="background:${col.bg};color:${col.color}">${initls}</div>
        <div>
          <div class="person-name">${p.nombre}</div>
          <div class="person-meta">${p.mes}</div>
        </div>
      </div>`;
    });
    html += `</div></div>`;
  });

  if (!html) html = '<div style="padding:2rem;color:var(--muted);text-align:center;font-size:14px">No hay ingresos en este período.</div>';
  document.getElementById('ingresos-content').innerHTML = html;
}

/* ── CERTIFICACIONES ── */
let certFiltro = 'all';
let certSearch = '';

function filterCert(area, btn) {
  certFiltro = area;
  document.querySelectorAll('.cert-filter-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  renderCerts();
}

function searchCerts(val) {
  certSearch = val.toLowerCase();
  renderCerts();
}

function renderCerts() {
  let filtered = certs;
  if (certFiltro !== 'all') filtered = filtered.filter(c => c.area === certFiltro);
  if (certSearch) filtered = filtered.filter(c =>
    c.nombre.toLowerCase().includes(certSearch) || c.cert.toLowerCase().includes(certSearch)
  );

  document.getElementById('stat-total').textContent = filtered.length;

  const badgeClass = {FF:'badge-ff','S&P':'badge-sp',VCT:'badge-vct'};
  const badgeLabel = {FF:'Fulfillment','S&P':'S&P',VCT:'VCT'};

  let html = '';
  if (!filtered.length) {
    html = `<div class="cert-empty">Sin resultados para la búsqueda.</div>`;
  } else {
    filtered.forEach(c => {
      const col = acColor(c.area === 'FF' ? 'FF' : c.area === 'VCT' ? 'VCT' : 'S&P');
      const initls = initials(c.nombre);
      html += `<div class="cert-item">
        <div class="cert-item-avatar" style="background:${col.bg};color:${col.color}">${initls}</div>
        <div class="cert-info">
          <div class="cert-person">${c.nombre}</div>
          <div class="cert-name" title="${c.cert}">${c.cert}</div>
        </div>
        <span class="cert-badge ${badgeClass[c.area] || ''}">${badgeLabel[c.area] || c.area}</span>
      </div>`;
    });
  }
  document.getElementById('cert-list').innerHTML = html;
}

/* ── SQUAD ── */
function renderSquad() {
  const colors = [
    {bg:"rgba(162,155,254,0.2)",color:"#a29bfe"},
    {bg:"rgba(0,206,201,0.15)",color:"#81ecec"},
    {bg:"rgba(253,203,110,0.15)",color:"#fdcb6e"},
    {bg:"rgba(225,112,85,0.15)",color:"#fab1a0"},
    {bg:"rgba(253,121,108,0.15)",color:"#ff7675"},
    {bg:"rgba(108,92,231,0.2)",color:"#a29bfe"},
  ];
  const offeringChip = {
    "S&P":    {bg:"rgba(0,206,201,0.15)",color:"#81ecec"},
    "FF":     {bg:"rgba(162,155,254,0.15)",color:"#a29bfe"},
    "Planning":{bg:"rgba(225,112,85,0.15)",color:"#e17055"},
    "E&RD":   {bg:"rgba(253,121,108,0.15)",color:"#ff7675"},
    "I&CP":   {bg:"rgba(253,203,110,0.15)",color:"#fdcb6e"},
  };

  const html = squad.map((m, i) => {
    const col = colors[i % colors.length];
    const chip = offeringChip[m.offering] || {bg:"rgba(255,255,255,0.1)",color:"#dfe6e9"};
    const initls = initials(m.nombre);
    return `<div class="squad-card">
      <div class="squad-avatar" style="background:${col.bg};color:${col.color}">${initls}</div>
      <div class="squad-name">${m.nombre}</div>
      <div class="squad-role">${m.rol}</div>
      <span class="squad-chip" style="background:${chip.bg};color:${chip.color}">${m.offering}</span>
    </div>`;
  }).join('');

  document.getElementById('squad-grid').innerHTML = html;
}

/* ── INIT ── */
renderIngresos();
renderCerts();
renderSquad();
</script>
</body>
</html>
[Uploading index.html…]()
