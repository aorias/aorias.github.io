<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Diseñador de Interfaces UI/UX: diseño digital, UX, HTML, CSS, responsive, JavaScript y WordPress. Diseña, crea y emprende.">
  <title>Diseñador de Interfaces UI/UX</title>

  <!-- Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css">

  <style>
    :root {
      --ink: #242738;
      --yellow: #f2b530;
      --teal: #40b0ac;
      --cream: #f7f8f6;
      --white: #ffffff;
      --muted: #697080;
      --border: rgba(36, 39, 56, .10);
      --shadow: 0 18px 50px rgba(36, 39, 56, .12);
      --radius: 22px;
      --max: 1120px;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      color: var(--ink);
      background: var(--white);
      line-height: 1.6;
    }

    a { color: inherit; text-decoration: none; }

    .container {
      width: min(var(--max), calc(100% - 40px));
      margin-inline: auto;
    }

    /* NAV */
    nav {
      position: sticky;
      top: 0;
      z-index: 1000;
      background: rgba(255,255,255,.92);
      backdrop-filter: blur(14px);
      border-bottom: 1px solid var(--border);
    }

    .nav-inner {
      min-height: 72px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 24px;
    }

    .brand {
      font-weight: 900;
      letter-spacing: -.04em;
      font-size: 1.05rem;
    }

    .brand span { color: var(--teal); }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 24px;
      font-size: .92rem;
      font-weight: 700;
    }

    .nav-links a:hover { color: var(--teal); }

    .nav-cta {
      background: var(--ink);
      color: var(--white) !important;
      padding: 10px 17px;
      border-radius: 999px;
    }

    .nav-cta:hover { background: var(--teal); }

    /* HERO */
    .hero {
      position: relative;
      overflow: hidden;
      background:
        radial-gradient(circle at 86% 18%, rgba(64,176,172,.22), transparent 28%),
        radial-gradient(circle at 10% 90%, rgba(242,181,48,.18), transparent 30%),
        var(--cream);
      padding: 96px 0 92px;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.1fr .9fr;
      align-items: center;
      gap: 60px;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 9px;
      font-size: .78rem;
      font-weight: 900;
      text-transform: uppercase;
      letter-spacing: .13em;
      color: var(--teal);
      margin-bottom: 18px;
    }

    .eyebrow i { font-size: .9rem; }

    h1 {
      font-size: clamp(3rem, 7vw, 5.9rem);
      line-height: .94;
      letter-spacing: -.065em;
      max-width: 760px;
    }

    h1 .accent { color: var(--teal); }
    h1 .highlight {
      display: inline-block;
      color: var(--ink);
      background: var(--yellow);
      padding: 0 .12em .04em;
      transform: rotate(-1.5deg);
    }

    .hero-copy {
      max-width: 650px;
      font-size: 1.14rem;
      color: var(--muted);
      margin: 25px 0 31px;
    }

    .buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 13px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 14px 21px;
      border-radius: 999px;
      font-weight: 850;
      border: 2px solid transparent;
      transition: .2s ease;
    }

    .btn-primary {
      background: var(--ink);
      color: var(--white);
    }

    .btn-primary:hover {
      transform: translateY(-2px);
      background: var(--teal);
    }

    .btn-secondary {
      border-color: var(--ink);
      color: var(--ink);
      background: transparent;
    }

    .btn-secondary:hover {
      background: var(--ink);
      color: var(--white);
    }

    .hero-card {
      position: relative;
      min-height: 420px;
      display: grid;
      place-items: center;
    }

    .orbit {
      width: min(390px, 80vw);
      aspect-ratio: 1;
      border: 2px dashed rgba(36,39,56,.20);
      border-radius: 50%;
      position: relative;
      animation: spin 22s linear infinite;
    }

    .orbit::before {
      content: "";
      position: absolute;
      inset: 16%;
      border: 2px solid rgba(64,176,172,.25);
      border-radius: 50%;
    }

    .center-ui {
      position: absolute;
      inset: 50% auto auto 50%;
      transform: translate(-50%,-50%);
      width: 145px;
      height: 145px;
      border-radius: 30px;
      background: var(--ink);
      color: white;
      display: grid;
      place-items: center;
      text-align: center;
      box-shadow: var(--shadow);
      z-index: 2;
    }

    .center-ui i { font-size: 2.3rem; color: var(--yellow); }
    .center-ui strong { display: block; font-size: 1rem; line-height: 1.1; }

    .floating-icon {
      position: absolute;
      width: 68px;
      height: 68px;
      display: grid;
      place-items: center;
      border-radius: 20px;
      box-shadow: 0 12px 30px rgba(36,39,56,.13);
      font-size: 1.5rem;
      animation: counterSpin 22s linear infinite;
    }

    .f1 { top: 4%; left: 42%; background: var(--yellow); }
    .f2 { right: 2%; top: 38%; background: var(--teal); color: white; }
    .f3 { bottom: 5%; left: 14%; background: var(--white); }
    .f4 { left: 0; top: 39%; background: var(--white); color: var(--teal); }

    @keyframes spin { to { transform: rotate(360deg); } }
    @keyframes counterSpin { to { transform: rotate(-360deg); } }

    /* SECTIONS */
    section { padding: 90px 0; }

    .section-head {
      max-width: 720px;
      margin-bottom: 42px;
    }

    .section-label {
      color: var(--teal);
      font-weight: 900;
      text-transform: uppercase;
      letter-spacing: .12em;
      font-size: .78rem;
      margin-bottom: 10px;
    }

    h2 {
      font-size: clamp(2.2rem, 5vw, 3.8rem);
      line-height: 1;
      letter-spacing: -.05em;
    }

    .section-intro {
      color: var(--muted);
      margin-top: 14px;
      font-size: 1.05rem;
    }

    /* MODULES */
    .modules {
      background: var(--white);
    }

    .module-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 18px;
    }

    .module {
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 27px;
      background: var(--white);
      box-shadow: 0 8px 28px rgba(36,39,56,.05);
      transition: .22s ease;
    }

    .module:hover {
      transform: translateY(-6px);
      box-shadow: var(--shadow);
    }

    .module-number {
      color: var(--teal);
      font-size: .76rem;
      font-weight: 900;
      letter-spacing: .1em;
    }

    .module-icon {
      width: 55px;
      height: 55px;
      display: grid;
      place-items: center;
      border-radius: 16px;
      margin: 17px 0;
      background: rgba(64,176,172,.13);
      color: var(--teal);
      font-size: 1.35rem;
    }

    .module:nth-child(even) .module-icon {
      background: rgba(242,181,48,.20);
      color: var(--ink);
    }

    .module h3 { font-size: 1.2rem; margin-bottom: 7px; }
    .module p { color: var(--muted); font-size: .94rem; }

    /* SKILLS */
    .skills {
      background: var(--ink);
      color: var(--white);
    }

    .skills .section-label { color: var(--yellow); }
    .skills .section-intro { color: rgba(255,255,255,.72); }

    .skill-pills {
      display: flex;
      flex-wrap: wrap;
      gap: 11px;
      margin-top: 30px;
    }

    .skill-pill {
      padding: 11px 16px;
      border: 1px solid rgba(255,255,255,.17);
      border-radius: 999px;
      background: rgba(255,255,255,.06);
      font-weight: 750;
    }

    .skill-pill i { color: var(--yellow); margin-right: 7px; }

    /* CAREERS */
    .career-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 22px;
    }

    .career-card {
      border-radius: var(--radius);
      padding: 35px;
      border: 1px solid var(--border);
      background: var(--cream);
    }

    .career-card.featured {
      background: var(--teal);
      color: white;
      border: none;
      position: relative;
      overflow: hidden;
    }

    .career-card.featured::after {
      content: "↗";
      position: absolute;
      right: 25px;
      bottom: -12px;
      font-size: 8rem;
      line-height: 1;
      opacity: .12;
      font-weight: 900;
    }

    .career-card i {
      font-size: 2rem;
      color: var(--teal);
      margin-bottom: 18px;
    }

    .career-card.featured i { color: var(--yellow); }

    .career-card h3 {
      font-size: 1.65rem;
      margin-bottom: 10px;
    }

    .career-card p { color: var(--muted); }
    .career-card.featured p { color: rgba(255,255,255,.85); }

    .career-list {
      list-style: none;
      display: grid;
      gap: 10px;
      margin-top: 20px;
    }

    .career-list li {
      display: flex;
      gap: 10px;
      align-items: flex-start;
      font-weight: 700;
    }

    .career-list i {
      font-size: .9rem;
      margin-top: 5px;
      color: var(--teal);
    }

    .featured .career-list i { color: var(--yellow); }

    /* CTA */
    .cta {
      padding: 0 0 90px;
    }

    .cta-box {
      background: var(--yellow);
      border-radius: 30px;
      padding: 60px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 30px;
      overflow: hidden;
      position: relative;
    }

    .cta-box h2 { max-width: 700px; }
    .cta-box p { margin-top: 12px; max-width: 620px; }

    .cta-box .btn {
      flex-shrink: 0;
      background: var(--ink);
      color: white;
    }

    /* FOOTER */
    footer {
      background: var(--ink);
      color: rgba(255,255,255,.72);
      padding: 30px 0;
      font-size: .88rem;
    }

    .footer-inner {
      display: flex;
      justify-content: space-between;
      gap: 20px;
      align-items: center;
    }

    .footer-brand { color: white; font-weight: 900; }

    /* REVEAL */
    .reveal {
      opacity: 0;
      transform: translateY(18px);
      transition: .65s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* MOBILE */
    @media (max-width: 850px) {
      .nav-links a:not(.nav-cta) { display: none; }
      .hero { padding: 70px 0 55px; }
      .hero-grid { grid-template-columns: 1fr; gap: 35px; }
      .hero-card { min-height: 340px; }
      .module-grid { grid-template-columns: repeat(2, 1fr); }
      .career-grid { grid-template-columns: 1fr; }
      .cta-box { padding: 42px 30px; flex-direction: column; align-items: flex-start; }
    }

    @media (max-width: 560px) {
      .container { width: min(var(--max), calc(100% - 28px)); }
      section { padding: 65px 0; }
      .module-grid { grid-template-columns: 1fr; }
      .hero-card { transform: scale(.88); margin: -15px 0; }
      .cta { padding-bottom: 65px; }
      .footer-inner { flex-direction: column; align-items: flex-start; }
    }

    @media (prefers-reduced-motion: reduce) {
      html { scroll-behavior: auto; }
      *, *::before, *::after {
        animation-duration: .01ms !important;
        transition-duration: .01ms !important;
      }
    }
  </style>
</head>

<body>

  <nav>
    <div class="container nav-inner">
      <a class="brand" href="#inicio">UI<span>/</span>UX</a>
      <div class="nav-links">
        <a href="#programa">Programa</a>
        <a href="#salidas">Salidas laborales</a>
        <a href="#emprende">Emprende</a>
        <a class="nav-cta" href="#contacto">Quiero saber más <i class="fa-solid fa-arrow-right"></i></a>
      </div>
    </div>
  </nav>

  <main>

    <section class="hero" id="inicio">
      <div class="container hero-grid">
        <div>
          <div class="eyebrow"><i class="fa-solid fa-wand-magic-sparkles"></i> Diseñador de Interfaces UI/UX</div>
          <h1>Diseña.<br><span class="accent">Crea.</span><br><span class="highlight">Emprende.</span></h1>
          <p class="hero-copy">
            Convierte tus ideas en experiencias digitales. Aprende diseño, UX, desarrollo web e interacción para crear sitios modernos, funcionales y pensados para las personas.
          </p>
          <div class="buttons">
            <a class="btn btn-primary" href="#programa">Conoce el programa <i class="fa-solid fa-arrow-down"></i></a>
            <a class="btn btn-secondary" href="#emprende">Descubre cómo emprender</a>
          </div>
        </div>

        <div class="hero-card" aria-hidden="true">
          <div class="orbit">
            <div class="center-ui">
              <div>
                <i class="fa-solid fa-display"></i>
                <strong>Experiencias<br>digitales</strong>
              </div>
            </div>
            <div class="floating-icon f1"><i class="fa-solid fa-pen-nib"></i></div>
            <div class="floating-icon f2"><i class="fa-solid fa-code"></i></div>
            <div class="floating-icon f3"><i class="fa-solid fa-mobile-screen-button"></i></div>
            <div class="floating-icon f4"><i class="fa-solid fa-lightbulb"></i></div>
          </div>
        </div>
      </div>
    </section>

    <section id="programa" class="modules">
      <div class="container">
        <div class="section-head reveal">
          <div class="section-label">El programa</div>
          <h2>6 módulos para llevar una idea de la pantalla al navegador.</h2>
          <p class="section-intro">Aprende paso a paso las herramientas y conocimientos que necesitas para diseñar y construir experiencias web.</p>
        </div>

        <div class="module-grid">

          <article class="module reveal">
            <div class="module-number">M1</div>
            <div class="module-icon"><i class="fa-solid fa-pen-ruler"></i></div>
            <h3>Diseño Digital</h3>
            <p>Illustrator, Photoshop y Adobe XD para crear piezas, interfaces y prototipos digitales.</p>
          </article>

          <article class="module reveal">
            <div class="module-number">M2</div>
            <div class="module-icon"><i class="fa-solid fa-users-viewfinder"></i></div>
            <h3>Diseño UX</h3>
            <p>Design Thinking, investigación y diseño centrado en las necesidades de las personas.</p>
          </article>

          <article class="module reveal">
            <div class="module-number">M3</div>
            <div class="module-icon"><i class="fa-brands fa-html5"></i></div>
            <h3>Diseño HTML</h3>
            <p>HTML y CSS para convertir tus diseños en páginas web reales.</p>
          </article>

          <article class="module reveal">
            <div class="module-number">M4</div>
            <div class="module-icon"><i class="fa-solid fa-mobile-screen"></i></div>
            <h3>Web Responsive</h3>
            <p>Diseña sitios que se adapten a computadoras, tablets y celulares.</p>
          </article>

          <article class="module reveal">
            <div class="module-number">M5</div>
            <div class="module-icon"><i class="fa-brands fa-js"></i></div>
            <h3>Interacción con JavaScript</h3>
            <p>Agrega interacción, movimiento y funcionalidades a tus proyectos web.</p>
          </article>

          <article class="module reveal">
            <div class="module-number">M6</div>
            <div class="module-icon"><i class="fa-brands fa-wordpress"></i></div>
            <h3>Diseño con CMS</h3>
            <p>Crea y administra sitios profesionales utilizando WordPress.</p>
          </article>

        </div>
      </div>
    </section>

    <section class="skills">
      <div class="container">
        <div class="section-head reveal">
          <div class="section-label">Tu caja de herramientas</div>
          <h2>Diseño + tecnología + creatividad.</h2>
          <p class="section-intro">Una combinación de habilidades para entender el proceso completo: desde la idea y el diseño hasta una experiencia web funcional.</p>
        </div>

        <div class="skill-pills reveal">
          <span class="skill-pill"><i class="fa-solid fa-pen-nib"></i> Diseño UI</span>
          <span class="skill-pill"><i class="fa-solid fa-users"></i> UX</span>
          <span class="skill-pill"><i class="fa-solid fa-code"></i> HTML & CSS</span>
          <span class="skill-pill"><i class="fa-solid fa-mobile-screen"></i> Responsive</span>
          <span class="skill-pill"><i class="fa-brands fa-js"></i> JavaScript</span>
          <span class="skill-pill"><i class="fa-brands fa-wordpress"></i> WordPress</span>
          <span class="skill-pill"><i class="fa-solid fa-lightbulb"></i> Design Thinking</span>
          <span class="skill-pill"><i class="fa-solid fa-wand-magic-sparkles"></i> Prototipado</span>
        </div>
      </div>
    </section>

    <section id="salidas">
      <div class="container">
        <div class="section-head reveal">
          <div class="section-label">Después de estudiar</div>
          <h2>¿Dónde puedes llevar tus conocimientos?</h2>
          <p class="section-intro">Tu perfil puede abrirte puertas en empresas, agencias, proyectos digitales… o ayudarte a crear tus propias oportunidades.</p>
        </div>

        <div class="career-grid">

          <article class="career-card reveal">
            <i class="fa-solid fa-briefcase"></i>
            <h3>Trabaja en el mundo digital</h3>
            <p>Aplica tus conocimientos en diferentes roles y proyectos relacionados con diseño y desarrollo web.</p>
            <ul class="career-list">
              <li><i class="fa-solid fa-check"></i> Diseñador UI/UX</li>
              <li><i class="fa-solid fa-check"></i> Diseñador web</li>
              <li><i class="fa-solid fa-check"></i> Desarrollador web front-end</li>
              <li><i class="fa-solid fa-check"></i> Creador de sitios WordPress</li>
              <li><i class="fa-solid fa-check"></i> Freelancer</li>
            </ul>
          </article>

          <article class="career-card featured reveal" id="emprende">
            <i class="fa-solid fa-rocket"></i>
            <h3>O crea tu propio camino</h3>
            <p>No tienes que esperar a que una empresa te contrate. Tus conocimientos también pueden convertirse en un emprendimiento.</p>
            <ul class="career-list">
              <li><i class="fa-solid fa-check"></i> Crea páginas web para clientes</li>
              <li><i class="fa-solid fa-check"></i> Diseña landing pages y tiendas online</li>
              <li><i class="fa-solid fa-check"></i> Construye tu propia marca</li>
              <li><i class="fa-solid fa-check"></i> Ofrece servicios como freelancer</li>
            </ul>
          </article>

        </div>
      </div>
    </section>

    <section class="cta" id="contacto">
      <div class="container">
        <div class="cta-box reveal">
          <div>
            <h2>Tu próxima idea podría convertirse en una experiencia digital.</h2>
            <p>Aprende a diseñarla, construirla y hacerla realidad.</p>
          </div>
          <!-- Reemplaza # por el enlace real de inscripción o información -->
          <a class="btn" href="#" onclick="return false;">Quiero conocer más <i class="fa-solid fa-arrow-right"></i></a>
        </div>
      </div>
    </section>

  </main>

  <footer>
    <div class="container footer-inner">
      <div class="footer-brand">DISEÑADOR DE INTERFACES UI/UX</div>
      <div>Diseña · Crea · Emprende</div>
    </div>
  </footer>

  <script>
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.12 });

    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
  </script>

</body>
</html>

