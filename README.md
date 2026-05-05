<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Taha Mert Dülger — Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300&family=DM+Mono:wght@300;400&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --bg: #0a0907;
    --bg2: #111009;
    --gold: #c9a84c;
    --gold-dim: #7a6230;
    --cream: #e8e0d0;
    --muted: #6b6456;
    --line: rgba(201,168,76,0.15);
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--cream);
    font-family: 'DM Mono', monospace;
    font-size: 13px;
    letter-spacing: 0.02em;
    overflow-x: hidden;
    cursor: none;
  }

  /* Custom cursor */
  .cursor {
    position: fixed;
    width: 6px;
    height: 6px;
    background: var(--gold);
    border-radius: 50%;
    pointer-events: none;
    z-index: 9999;
    transform: translate(-50%, -50%);
    transition: transform 0.1s;
  }
  .cursor-ring {
    position: fixed;
    width: 32px;
    height: 32px;
    border: 1px solid var(--gold-dim);
    border-radius: 50%;
    pointer-events: none;
    z-index: 9998;
    transform: translate(-50%, -50%);
    transition: all 0.18s ease;
  }

  /* Noise overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 9997;
    opacity: 0.4;
  }

  /* Nav */
  nav {
    position: fixed;
    top: 0;
    width: 100%;
    padding: 1.6rem 3rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 100;
    background: linear-gradient(var(--bg), transparent);
  }
  .nav-logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.1rem;
    font-weight: 300;
    color: var(--gold);
    letter-spacing: 0.1em;
    text-decoration: none;
  }
  nav ul {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }
  nav a {
    color: var(--muted);
    text-decoration: none;
    font-size: 11px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    transition: color 0.3s;
  }
  nav a:hover { color: var(--gold); }

  /* Hero */
  #hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 0 3rem 5rem;
    position: relative;
    border-bottom: 1px solid var(--line);
  }

  .hero-label {
    font-size: 10px;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1.5rem;
    opacity: 0;
    animation: fadeUp 1s 0.3s ease forwards;
  }

  h1 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(4.5rem, 12vw, 11rem);
    font-weight: 300;
    line-height: 0.88;
    color: var(--cream);
    letter-spacing: -0.02em;
    opacity: 0;
    animation: fadeUp 1.2s 0.5s ease forwards;
  }
  h1 em {
    font-style: italic;
    color: var(--gold);
  }

  .hero-sub {
    margin-top: 2.5rem;
    max-width: 420px;
    color: var(--muted);
    line-height: 1.8;
    opacity: 0;
    animation: fadeUp 1s 0.9s ease forwards;
  }

  .hero-scroll {
    position: absolute;
    bottom: 2rem;
    right: 3rem;
    display: flex;
    align-items: center;
    gap: 1rem;
    color: var(--muted);
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    opacity: 0;
    animation: fadeUp 1s 1.3s ease forwards;
  }
  .hero-scroll::before {
    content: '';
    width: 40px;
    height: 1px;
    background: var(--gold-dim);
  }

  .hero-year {
    position: absolute;
    top: 50%;
    right: 3rem;
    transform: translateY(-50%);
    font-family: 'Cormorant Garamond', serif;
    font-size: 14rem;
    font-weight: 300;
    color: rgba(201,168,76,0.04);
    letter-spacing: -0.05em;
    pointer-events: none;
    user-select: none;
  }

  /* Sections */
  section { padding: 6rem 3rem; border-bottom: 1px solid var(--line); }

  .section-header {
    display: flex;
    align-items: center;
    gap: 1.5rem;
    margin-bottom: 4rem;
  }
  .section-num {
    font-size: 10px;
    color: var(--gold);
    letter-spacing: 0.2em;
    min-width: 2rem;
  }
  .section-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 2.8rem;
    font-weight: 300;
    color: var(--cream);
    letter-spacing: -0.01em;
  }
  .section-line {
    flex: 1;
    height: 1px;
    background: var(--line);
  }

  /* About */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: start;
  }
  .about-text {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.45rem;
    font-weight: 300;
    line-height: 1.65;
    color: var(--cream);
  }
  .about-text em { font-style: italic; color: var(--gold); }
  .about-meta { display: flex; flex-direction: column; gap: 1.5rem; }
  .meta-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0.8rem 0;
    border-bottom: 1px solid var(--line);
  }
  .meta-label { color: var(--muted); font-size: 10px; letter-spacing: 0.15em; text-transform: uppercase; }
  .meta-val { color: var(--cream); }

  /* Timeline */
  .timeline { position: relative; padding-left: 2rem; }
  .timeline::before {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    bottom: 0;
    width: 1px;
    background: var(--line);
  }
  .tl-item {
    position: relative;
    padding: 0 0 3.5rem 2.5rem;
    opacity: 0;
    transform: translateY(20px);
    transition: all 0.7s ease;
  }
  .tl-item.visible { opacity: 1; transform: translateY(0); }
  .tl-dot {
    position: absolute;
    left: -4px;
    top: 6px;
    width: 7px;
    height: 7px;
    background: var(--gold);
    border-radius: 50%;
  }
  .tl-date {
    font-size: 10px;
    color: var(--gold);
    letter-spacing: 0.18em;
    text-transform: uppercase;
    margin-bottom: 0.4rem;
  }
  .tl-company {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.4rem;
    font-weight: 300;
    color: var(--cream);
    margin-bottom: 0.2rem;
  }
  .tl-role {
    color: var(--muted);
    font-size: 11px;
    margin-bottom: 0.6rem;
  }
  .tl-desc { color: var(--muted); line-height: 1.7; max-width: 480px; }

  /* Skills */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
    gap: 1px;
    border: 1px solid var(--line);
  }
  .skill-card {
    padding: 2rem 1.5rem;
    border-right: 1px solid var(--line);
    border-bottom: 1px solid var(--line);
    transition: background 0.3s;
    opacity: 0;
    transform: scale(0.97);
    transition: opacity 0.5s ease, transform 0.5s ease, background 0.3s;
  }
  .skill-card.visible { opacity: 1; transform: scale(1); }
  .skill-card:hover { background: rgba(201,168,76,0.04); }
  .skill-icon {
    font-family: 'Cormorant Garamond', serif;
    font-size: 2rem;
    font-weight: 300;
    color: var(--gold);
    line-height: 1;
    margin-bottom: 0.8rem;
  }
  .skill-name { color: var(--cream); font-size: 12px; letter-spacing: 0.05em; }
  .skill-type { color: var(--muted); font-size: 10px; margin-top: 0.3rem; }

  /* Projects */
  .projects-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1px; border: 1px solid var(--line); }
  .proj-card {
    padding: 3rem 2.5rem;
    border-right: 1px solid var(--line);
    position: relative;
    overflow: hidden;
    transition: background 0.4s;
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.6s ease, transform 0.6s ease, background 0.4s;
  }
  .proj-card.visible { opacity: 1; transform: translateY(0); }
  .proj-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 1px;
    background: var(--line);
  }
  .proj-card:hover { background: rgba(201,168,76,0.03); }
  .proj-year { font-size: 10px; color: var(--gold); letter-spacing: 0.2em; margin-bottom: 1rem; }
  .proj-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 2rem;
    font-weight: 300;
    color: var(--cream);
    line-height: 1.1;
    margin-bottom: 1rem;
  }
  .proj-desc { color: var(--muted); line-height: 1.7; }
  .proj-tag {
    display: inline-block;
    margin-top: 1.2rem;
    padding: 0.3rem 0.9rem;
    border: 1px solid var(--gold-dim);
    color: var(--gold);
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  /* Languages */
  .lang-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1px; border: 1px solid var(--line); }
  .lang-card {
    padding: 2.5rem;
    text-align: center;
    border-right: 1px solid var(--line);
    opacity: 0;
    transition: opacity 0.6s ease;
  }
  .lang-card.visible { opacity: 1; }
  .lang-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.8rem;
    font-weight: 300;
    color: var(--cream);
    margin-bottom: 0.4rem;
  }
  .lang-level { color: var(--gold); font-size: 10px; letter-spacing: 0.2em; text-transform: uppercase; }

  /* Contact */
  #contact {
    padding: 6rem 3rem;
    text-align: center;
    border-bottom: none;
  }
  .contact-big {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(3rem, 8vw, 7rem);
    font-weight: 300;
    color: var(--cream);
    line-height: 1;
    margin-bottom: 2rem;
  }
  .contact-big em { color: var(--gold); font-style: italic; }
  .contact-links { display: flex; justify-content: center; gap: 3rem; margin-top: 3rem; }
  .contact-link {
    color: var(--muted);
    text-decoration: none;
    font-size: 11px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    transition: color 0.3s;
    padding-bottom: 0.3rem;
    border-bottom: 1px solid transparent;
    transition: all 0.3s;
  }
  .contact-link:hover { color: var(--gold); border-bottom-color: var(--gold-dim); }

  /* Footer */
  footer {
    padding: 1.5rem 3rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: var(--muted);
    font-size: 10px;
    letter-spacing: 0.12em;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* Interests */
  .interests { display: flex; gap: 0; flex-wrap: wrap; }
  .interest-item {
    padding: 1.8rem 2.5rem;
    border-right: 1px solid var(--line);
    border-bottom: 1px solid var(--line);
    flex: 1;
    min-width: 200px;
  }
  .interest-num { font-size: 2rem; font-family: 'Cormorant Garamond', serif; color: var(--gold); font-weight: 300; margin-bottom: 0.6rem; }
  .interest-text { color: var(--cream); line-height: 1.6; }

  @media (max-width: 768px) {
    nav ul { display: none; }
    h1 { font-size: 4rem; }
    .about-grid, .projects-grid, .lang-grid { grid-template-columns: 1fr; }
    section { padding: 4rem 1.5rem; }
    nav { padding: 1.2rem 1.5rem; }
    #hero { padding: 0 1.5rem 4rem; }
    .hero-year { display: none; }
  }
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<nav>
  <a href="#hero" class="nav-logo">T.M.D</a>
  <ul>
    <li><a href="#about">Hakkımda</a></li>
    <li><a href="#experience">Deneyim</a></li>
    <li><a href="#skills">Yetenekler</a></li>
    <li><a href="#projects">Projeler</a></li>
    <li><a href="#contact">İletişim</a></li>
  </ul>
</nav>

<section id="hero">
  <div class="hero-year">22</div>
  <p class="hero-label">// Portfolio — İstanbul, Kağıthane</p>
  <h1>Taha<br><em>Mert</em><br>Dülger</h1>
  <p class="hero-sub">Video editörü, e-ticaret uzmanı ve yapay zeka meraklısı. Yaratıcılık ile teknolojiyi birleştiren çok yönlü bir profesyonel.</p>
  <div class="hero-scroll">Scroll to explore</div>
</section>

<section id="about">
  <div class="section-header">
    <span class="section-num">01</span>
    <h2 class="section-title">Hakkımda</h2>
    <div class="section-line"></div>
  </div>
  <div class="about-grid">
    <p class="about-text">
      Bilgisayar Teknolojisi eğitimimin verdiği <em>teknik temel</em> üzerine, video prodüksiyon ve dijital ticaret dünyasında geniş bir deneyim inşa ettim. Şu an yapay zeka araçlarıyla projeler geliştiriyor, yabancı dilde içerikler takip ederek kendimi sürekli güncelliyorum.
    </p>
    <div class="about-meta">
      <div class="meta-row">
        <span class="meta-label">Konum</span>
        <span class="meta-val">İstanbul, Kağıthane</span>
      </div>
      <div class="meta-row">
        <span class="meta-label">Doğum Yılı</span>
        <span class="meta-val">2003</span>
      </div>
      <div class="meta-row">
        <span class="meta-label">Eğitim</span>
        <span class="meta-val">İstinye Üni. — Bilgisayar Tek.</span>
      </div>
      <div class="meta-row">
        <span class="meta-label">Askerlik</span>
        <span class="meta-val">Muaf</span>
      </div>
      <div class="meta-row">
        <span class="meta-label">E-posta</span>
        <span class="meta-val">t.mert.d1@gmail.com</span>
      </div>
    </div>
  </div>
</section>

<section id="experience">
  <div class="section-header">
    <span class="section-num">02</span>
    <h2 class="section-title">Deneyim</h2>
    <div class="section-line"></div>
  </div>
  <div class="timeline">

    <div class="tl-item">
      <div class="tl-dot"></div>
      <p class="tl-date">Mar 2025 — Eyl 2025</p>
      <p class="tl-company">Kaset Medya</p>
      <p class="tl-role">Video Editörü</p>
      <p class="tl-desc">Reklam ve röportaj projeleri için çekim ve kurgu süreçlerini yönettim. Adobe Premiere ve After Effects ile profesyonel post-prodüksiyon çalışmaları gerçekleştirdim.</p>
    </div>

    <div class="tl-item">
      <div class="tl-dot"></div>
      <p class="tl-date">Mar 2025 — Haz 2025</p>
      <p class="tl-company">Snowy Ulu Kardeşler</p>
      <p class="tl-role">E-Ticaret Yetkilisi</p>
      <p class="tl-desc">Online satış operasyonlarını yönetim altına aldım. Platform yönetimi ve stok takibi konularında aktif rol üstlendim.</p>
    </div>

    <div class="tl-item">
      <div class="tl-dot"></div>
      <p class="tl-date">Eki 2024 — Mar 2025</p>
      <p class="tl-company">Tunay.co</p>
      <p class="tl-role">Online Satış Müdürü</p>
      <p class="tl-desc">Online satış kanallarını yönettim, ürün durumlarını takip ettim ve müşteri memnuniyetini en üst düzeyde tutmak için süreçler geliştirdim.</p>
    </div>

    <div class="tl-item">
      <div class="tl-dot"></div>
      <p class="tl-date">Ağu 2024 — Eyl 2024</p>
      <p class="tl-company">Qapera</p>
      <p class="tl-role">Stajyer</p>
      <p class="tl-desc">Sektör dinamiklerini yakından gözlemleyerek pratik iş deneyimi edindim.</p>
    </div>

    <div class="tl-item">
      <div class="tl-dot"></div>
      <p class="tl-date">Ağu 2021 — Eyl 2021</p>
      <p class="tl-company">LG Elektronik Yetkili Servisi</p>
      <p class="tl-role">Teknik Servis Teknikeri</p>
      <p class="tl-desc">Bakım ve onarım gerektiren ürünlerin teknik servis işlemlerini gerçekleştirdim.</p>
    </div>

    <div class="tl-item">
      <div class="tl-dot"></div>
      <p class="tl-date">Haz 2014 — Eyl 2020</p>
      <p class="tl-company">Telkom Teknik</p>
      <p class="tl-role">Teknik Servis Teknikeri</p>
      <p class="tl-desc">Uzun soluklu bir süreçte teknik servis alanında deneyim kazandım. Müşteri odaklı servis anlayışı geliştirdim.</p>
    </div>

  </div>
</section>

<section id="skills">
  <div class="section-header">
    <span class="section-num">03</span>
    <h2 class="section-title">Yetenekler</h2>
    <div class="section-line"></div>
  </div>
  <div class="skills-grid">
    <div class="skill-card">
      <div class="skill-icon">Pr</div>
      <div class="skill-name">Adobe Premiere</div>
      <div class="skill-type">Video Editing</div>
    </div>
    <div class="skill-card">
      <div class="skill-icon">Ae</div>
      <div class="skill-name">After Effects</div>
      <div class="skill-type">Motion Design</div>
    </div>
    <div class="skill-card">
      <div class="skill-icon">Bl</div>
      <div class="skill-name">Blender</div>
      <div class="skill-type">3D Modelling</div>
    </div>
    <div class="skill-card">
      <div class="skill-icon">C4</div>
      <div class="skill-name">Cinema 4D</div>
      <div class="skill-type">3D & Motion</div>
    </div>
    <div class="skill-card">
      <div class="skill-icon">Wp</div>
      <div class="skill-name">WordPress</div>
      <div class="skill-type">Web & CMS</div>
    </div>
    <div class="skill-card">
      <div class="skill-icon">C#</div>
      <div class="skill-name">Visual C#</div>
      <div class="skill-type">Programming</div>
    </div>
  </div>
</section>

<section id="projects">
  <div class="section-header">
    <span class="section-num">04</span>
    <h2 class="section-title">Projeler</h2>
    <div class="section-line"></div>
  </div>
  <div class="projects-grid">
    <div class="proj-card">
      <p class="proj-year">2024</p>
      <h3 class="proj-name">E-Ticaret<br>Sitesi</h3>
      <p class="proj-desc">Web tabanlı bir satış platformu geliştirdim. Ürün yönetimi, sipariş takibi ve müşteri arayüzü içeren kapsamlı bir e-ticaret altyapısı kurdum.</p>
      <span class="proj-tag">Web · E-Commerce</span>
    </div>
    <div class="proj-card">
      <p class="proj-year">2025</p>
      <h3 class="proj-name">AI<br>Development</h3>
      <p class="proj-desc">Yapay zeka araçları ve API'leri kullanarak çeşitli otomasyon ve üretkenlik projeleri geliştiriyorum. LLM entegrasyonları üzerine aktif çalışmalar sürdürüyorum.</p>
      <span class="proj-tag">AI · Automation</span>
    </div>
  </div>
</section>

<section id="languages" style="border-bottom: 1px solid var(--line);">
  <div class="section-header">
    <span class="section-num">05</span>
    <h2 class="section-title">Diller</h2>
    <div class="section-line"></div>
  </div>
  <div class="lang-grid">
    <div class="lang-card">
      <p class="lang-name">Türkçe</p>
      <p class="lang-level">Anadil</p>
    </div>
    <div class="lang-card">
      <p class="lang-name">İngilizce</p>
      <p class="lang-level">İyi seviye</p>
    </div>
    <div class="lang-card">
      <p class="lang-name">日本語</p>
      <p class="lang-level">Temel seviye</p>
    </div>
  </div>

  <div style="margin-top: 4rem;">
    <div class="section-header" style="margin-bottom: 0;">
      <span class="section-num" style="font-size:10px; color:var(--muted); letter-spacing:0.2em; text-transform:uppercase;">İlgi Alanları</span>
      <div class="section-line"></div>
    </div>
    <div class="interests" style="margin-top: 1px; border: 1px solid var(--line);">
      <div class="interest-item">
        <div class="interest-num">01</div>
        <div class="interest-text">Yabancı dilde kitap okumak</div>
      </div>
      <div class="interest-item">
        <div class="interest-num">02</div>
        <div class="interest-text">Ufak animasyonlar hazırlamak</div>
      </div>
      <div class="interest-item">
        <div class="interest-num">03</div>
        <div class="interest-text">Yapay zeka ile projeler geliştirmek</div>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <p class="contact-big">Birlikte bir<br><em>şeyler</em> yapalım.</p>
  <p style="color: var(--muted); max-width: 400px; margin: 0 auto; line-height: 1.8;">
    Yeni projeler, iş birlikleri ya da sadece tanışmak için — her zaman ulaşabilirsiniz.
  </p>
  <div class="contact-links">
    <a href="mailto:t.mert.d1@gmail.com" class="contact-link">t.mert.d1@gmail.com</a>
    <a href="tel:+905434124078" class="contact-link">+90 543 412 40 78</a>
  </div>
</section>

<footer>
  <span>© 2025 Taha Mert Dülger</span>
  <span>İstanbul, Kağıthane</span>
</footer>

<script>
  const cursor = document.getElementById('cursor');
  const ring = document.getElementById('cursorRing');
  let mx = 0, my = 0, rx = 0, ry = 0;

  document.addEventListener('mousemove', e => {
    mx = e.clientX; my = e.clientY;
    cursor.style.left = mx + 'px';
    cursor.style.top = my + 'px';
  });

  function animRing() {
    rx += (mx - rx) * 0.12;
    ry += (my - ry) * 0.12;
    ring.style.left = rx + 'px';
    ring.style.top = ry + 'px';
    requestAnimationFrame(animRing);
  }
  animRing();

  document.querySelectorAll('a, button').forEach(el => {
    el.addEventListener('mouseenter', () => {
      ring.style.width = '50px';
      ring.style.height = '50px';
      ring.style.borderColor = 'var(--gold)';
    });
    el.addEventListener('mouseleave', () => {
      ring.style.width = '32px';
      ring.style.height = '32px';
      ring.style.borderColor = 'var(--gold-dim)';
    });
  });

  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.tl-item, .skill-card, .proj-card, .lang-card').forEach(el => {
    observer.observe(el);
  });
</script>
</body>
</html>
