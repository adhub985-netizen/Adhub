<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Adhub Firm — Digital Marketing Agency</title>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Outfit:wght@300;400;500;600;700&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --black: #0a0a0a;
      --white: #f5f0e8;
      --gold: #c9a84c;
      --gold-light: #e8c96a;
      --dark: #111111;
      --muted: #888;
      --accent: #ff4d1c;
    }

    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      background: var(--black);
      color: var(--white);
      font-family: 'Outfit', sans-serif;
      overflow-x: hidden;
      cursor: none;
    }

    /* Custom Cursor */
    .cursor {
      width: 12px; height: 12px;
      background: var(--gold);
      border-radius: 50%;
      position: fixed; top: 0; left: 0;
      pointer-events: none; z-index: 9999;
      transition: transform 0.15s ease;
      mix-blend-mode: difference;
    }
    .cursor-follower {
      width: 40px; height: 40px;
      border: 1px solid var(--gold);
      border-radius: 50%;
      position: fixed; top: 0; left: 0;
      pointer-events: none; z-index: 9998;
      transition: transform 0.4s ease, width 0.3s, height 0.3s;
      mix-blend-mode: difference;
    }

    /* NAV */
    nav {
      position: fixed; top: 0; width: 100%;
      z-index: 100;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 28px 60px;
      background: linear-gradient(to bottom, rgba(10,10,10,0.95), transparent);
      backdrop-filter: blur(2px);
    }
    .logo {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 2.2rem;
      letter-spacing: 0.15em;
      color: var(--white);
    }
    .logo span { color: var(--gold); }
    .nav-links { display: flex; gap: 40px; list-style: none; }
    .nav-links a {
      color: var(--white);
      text-decoration: none;
      font-size: 0.85rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      font-weight: 500;
      opacity: 0.75;
      transition: opacity 0.3s, color 0.3s;
      position: relative;
    }
    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -4px; left: 0;
      width: 0; height: 1px;
      background: var(--gold);
      transition: width 0.3s;
    }
    .nav-links a:hover { opacity: 1; color: var(--gold); }
    .nav-links a:hover::after { width: 100%; }
    .nav-cta {
      background: var(--gold);
      color: var(--black) !important;
      padding: 10px 24px;
      font-weight: 700 !important;
      opacity: 1 !important;
      letter-spacing: 0.1em;
    }
    .nav-cta:hover { background: var(--gold-light); }
    .nav-cta::after { display: none !important; }

    /* HERO */
    .hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 120px 60px 80px;
      position: relative;
      overflow: hidden;
    }
    .hero-bg {
      position: absolute; inset: 0;
      background:
        radial-gradient(ellipse 60% 60% at 70% 50%, rgba(201,168,76,0.08) 0%, transparent 70%),
        radial-gradient(ellipse 40% 40% at 20% 80%, rgba(255,77,28,0.05) 0%, transparent 60%);
    }
    .hero-grid {
      position: absolute; inset: 0;
      background-image:
        linear-gradient(rgba(201,168,76,0.04) 1px, transparent 1px),
        linear-gradient(90deg, rgba(201,168,76,0.04) 1px, transparent 1px);
      background-size: 80px 80px;
    }
    .hero-content { position: relative; z-index: 2; max-width: 900px; }
    .hero-tag {
      display: inline-block;
      border: 1px solid var(--gold);
      color: var(--gold);
      font-size: 0.75rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      padding: 8px 20px;
      margin-bottom: 40px;
      animation: fadeUp 0.8s ease both;
    }
    .hero h1 {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(5rem, 12vw, 11rem);
      line-height: 0.9;
      letter-spacing: 0.02em;
      margin-bottom: 40px;
      animation: fadeUp 0.8s ease 0.15s both;
    }
    .hero h1 .accent { color: var(--gold); }
    .hero h1 .outline {
      -webkit-text-stroke: 1px var(--white);
      color: transparent;
    }
    .hero-sub {
      font-size: 1.15rem;
      line-height: 1.7;
      opacity: 0.65;
      max-width: 520px;
      margin-bottom: 56px;
      font-weight: 300;
      animation: fadeUp 0.8s ease 0.3s both;
    }
    .hero-btns {
      display: flex; gap: 20px; flex-wrap: wrap;
      animation: fadeUp 0.8s ease 0.45s both;
    }
    .btn-primary {
      background: var(--gold);
      color: var(--black);
      padding: 18px 44px;
      font-size: 0.9rem;
      font-weight: 700;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      text-decoration: none;
      display: inline-block;
      transition: background 0.3s, transform 0.2s;
    }
    .btn-primary:hover { background: var(--gold-light); transform: translateY(-2px); }
    .btn-outline {
      border: 1px solid rgba(245,240,232,0.3);
      color: var(--white);
      padding: 18px 44px;
      font-size: 0.9rem;
      font-weight: 500;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      text-decoration: none;
      display: inline-block;
      transition: border-color 0.3s, transform 0.2s;
    }
    .btn-outline:hover { border-color: var(--gold); color: var(--gold); transform: translateY(-2px); }

    .hero-stats {
      display: flex; gap: 60px; flex-wrap: wrap;
      margin-top: 56px;
      animation: fadeUp 0.8s ease 0.6s both;
    }
    .stat-item { text-align: left; }
    .stat-num {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 3.5rem;
      color: var(--gold);
      line-height: 1;
      letter-spacing: 0.05em;
    }
    .stat-label {
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.15em;
      opacity: 0.5;
      margin-top: 4px;
    }

    /* MARQUEE */
    .marquee-wrap {
      border-top: 1px solid rgba(201,168,76,0.2);
      border-bottom: 1px solid rgba(201,168,76,0.2);
      padding: 18px 0;
      overflow: hidden;
      background: rgba(201,168,76,0.03);
    }
    .marquee-inner {
      display: flex; gap: 0;
      animation: marquee 20s linear infinite;
      white-space: nowrap;
    }
    .marquee-item {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.2rem;
      letter-spacing: 0.2em;
      color: var(--gold);
      opacity: 0.6;
      padding: 0 40px;
      flex-shrink: 0;
    }
    .marquee-dot { color: var(--accent); opacity: 1; }

    /* SECTIONS */
    section { padding: 120px 60px; }
    .section-label {
      font-size: 0.75rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 16px;
    }
    .section-title {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(3rem, 6vw, 5.5rem);
      line-height: 0.95;
      letter-spacing: 0.03em;
      margin-bottom: 60px;
    }

    /* SERVICES */
    .services-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 2px;
      background: rgba(201,168,76,0.1);
    }
    .service-card {
      background: var(--black);
      padding: 50px 40px;
      transition: background 0.3s;
      position: relative;
      overflow: hidden;
    }
    .service-card::before {
      content: '';
      position: absolute;
      bottom: 0; left: 0;
      height: 2px; width: 0;
      background: var(--gold);
      transition: width 0.4s ease;
    }
    .service-card:hover { background: #111; }
    .service-card:hover::before { width: 100%; }
    .service-num {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 4rem;
      color: rgba(201,168,76,0.15);
      line-height: 1;
      margin-bottom: 24px;
      transition: color 0.3s;
    }
    .service-card:hover .service-num { color: rgba(201,168,76,0.35); }
    .service-icon { font-size: 2rem; margin-bottom: 20px; }
    .service-name {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.8rem;
      letter-spacing: 0.05em;
      margin-bottom: 14px;
      color: var(--white);
    }
    .service-desc { font-size: 0.9rem; line-height: 1.7; opacity: 0.55; font-weight: 300; }

    /* ABOUT */
    .about-section {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 100px;
      align-items: center;
    }
    .about-visual { position: relative; aspect-ratio: 4/5; }
    .about-box { position: absolute; inset: 0; border: 1px solid rgba(201,168,76,0.3); }
    .about-box-inner {
      position: absolute;
      top: 24px; left: 24px; right: -24px; bottom: -24px;
      background: linear-gradient(135deg, rgba(201,168,76,0.08), rgba(201,168,76,0.02));
      border: 1px solid rgba(201,168,76,0.15);
      display: flex; align-items: center; justify-content: center;
      font-family: 'Bebas Neue', sans-serif;
      font-size: 5rem;
      color: rgba(201,168,76,0.1);
      letter-spacing: 0.05em;
      text-align: center;
      line-height: 1.1;
    }
    .about-badge {
      position: absolute;
      bottom: -30px; right: -30px;
      width: 130px; height: 130px;
      background: var(--gold);
      color: var(--black);
      border-radius: 50%;
      display: flex; flex-direction: column;
      align-items: center; justify-content: center;
      font-family: 'Bebas Neue', sans-serif;
    }
    .about-badge .big { font-size: 2.5rem; line-height: 1; }
    .about-badge .small { font-size: 0.7rem; letter-spacing: 0.1em; }
    .about-text p { font-size: 1rem; line-height: 1.8; opacity: 0.6; font-weight: 300; margin-bottom: 20px; }
    .about-features { margin-top: 40px; display: flex; flex-direction: column; gap: 16px; }
    .feature-item { display: flex; align-items: center; gap: 14px; font-size: 0.9rem; font-weight: 500; }
    .feature-dot { width: 8px; height: 8px; background: var(--gold); flex-shrink: 0; }

    /* PORTFOLIO */
    .works-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 2px;
      background: rgba(201,168,76,0.1);
    }
    .work-item {
      background: var(--black);
      aspect-ratio: 16/9;
      position: relative; overflow: hidden; cursor: none;
    }
    .work-bg { position: absolute; inset: 0; transition: transform 0.6s ease; }
    .work-item:hover .work-bg { transform: scale(1.05); }
    .work-overlay {
      position: absolute; inset: 0;
      background: linear-gradient(to top, rgba(10,10,10,0.9) 0%, transparent 60%);
      opacity: 0; transition: opacity 0.4s;
      display: flex; align-items: flex-end; padding: 40px;
    }
    .work-item:hover .work-overlay { opacity: 1; }
    .work-cat { font-size: 0.7rem; letter-spacing: 0.2em; text-transform: uppercase; color: var(--gold); margin-bottom: 8px; }
    .work-title { font-family: 'Bebas Neue', sans-serif; font-size: 2rem; letter-spacing: 0.05em; }
    .work-grad-1 { background: linear-gradient(135deg, #1a1a2e, #16213e); }
    .work-grad-2 { background: linear-gradient(135deg, #0d1b2a, #1b2838); }
    .work-grad-3 { background: linear-gradient(135deg, #1a0a00, #2d1500); }
    .work-grad-4 { background: linear-gradient(135deg, #0a1628, #12243d); }
    .work-pattern { position: absolute; inset: 0; display: flex; align-items: center; justify-content: center; font-size: 7rem; opacity: 0.15; }

    /* PROCESS */
    .process-steps {
      display: grid; grid-template-columns: repeat(4, 1fr); gap: 0;
      position: relative;
    }
    .process-steps::before {
      content: '';
      position: absolute;
      top: 28px; left: 5%; right: 5%; height: 1px;
      background: linear-gradient(to right, transparent, rgba(201,168,76,0.4), transparent);
    }
    .process-step { padding: 0 30px 0 0; position: relative; }
    .step-circle {
      width: 56px; height: 56px;
      border: 1px solid var(--gold); border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      font-family: 'Bebas Neue', sans-serif; font-size: 1.4rem;
      color: var(--gold); background: var(--black);
      margin-bottom: 30px; position: relative; z-index: 1;
    }
    .step-title { font-family: 'Bebas Neue', sans-serif; font-size: 1.5rem; letter-spacing: 0.05em; margin-bottom: 12px; }
    .step-desc { font-size: 0.875rem; line-height: 1.7; opacity: 0.5; font-weight: 300; }

    /* TESTIMONIALS */
    .testimonials-section { background: #0d0d0d; }
    .testimonials-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px; margin-top: 60px; }
    .testimonial-card {
      border: 1px solid rgba(201,168,76,0.15);
      padding: 40px;
      position: relative;
      transition: border-color 0.3s;
    }
    .testimonial-card:hover { border-color: rgba(201,168,76,0.4); }
    .quote-mark { font-family: 'Bebas Neue', sans-serif; font-size: 5rem; color: var(--gold); opacity: 0.3; line-height: 0.7; margin-bottom: 20px; }
    .testimonial-text { font-size: 0.95rem; line-height: 1.8; opacity: 0.7; font-weight: 300; margin-bottom: 30px; font-style: italic; }
    .testimonial-author { display: flex; align-items: center; gap: 14px; }
    .author-avatar {
      width: 46px; height: 46px; border-radius: 50%;
      background: linear-gradient(135deg, var(--gold), var(--accent));
      display: flex; align-items: center; justify-content: center;
      font-family: 'Bebas Neue', sans-serif; font-size: 1.1rem;
      color: var(--black); flex-shrink: 0;
    }
    .author-name { font-weight: 600; font-size: 0.9rem; }
    .author-role { font-size: 0.78rem; opacity: 0.45; margin-top: 2px; }

    /* CTA */
    .cta-section {
      text-align: center;
      padding: 160px 60px;
      position: relative; overflow: hidden;
    }
    .cta-bg { position: absolute; inset: 0; background: radial-gradient(ellipse 70% 70% at 50% 50%, rgba(201,168,76,0.07), transparent); }
    .cta-section h2 {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(4rem, 9vw, 8rem);
      letter-spacing: 0.03em;
      margin-bottom: 20px;
      position: relative;
    }
    .cta-section p { font-size: 1.1rem; opacity: 0.55; margin-bottom: 50px; font-weight: 300; position: relative; }

    /* FOOTER */
    footer {
      border-top: 1px solid rgba(201,168,76,0.15);
      padding: 60px;
      display: grid;
      grid-template-columns: 2fr 1fr 1fr 1fr;
      gap: 60px;
    }
    .footer-brand .logo { font-size: 2rem; margin-bottom: 16px; display: block; }
    .footer-desc { font-size: 0.875rem; opacity: 0.45; line-height: 1.7; font-weight: 300; }
    .footer-col h4 { font-size: 0.75rem; letter-spacing: 0.2em; text-transform: uppercase; color: var(--gold); margin-bottom: 24px; }
    .footer-links { list-style: none; display: flex; flex-direction: column; gap: 12px; }
    .footer-links a { color: var(--white); text-decoration: none; font-size: 0.875rem; opacity: 0.5; transition: opacity 0.3s; }
    .footer-links a:hover { opacity: 1; }
    .footer-bottom {
      border-top: 1px solid rgba(255,255,255,0.06);
      padding: 24px 60px;
      display: flex; justify-content: space-between; align-items: center;
      font-size: 0.78rem; opacity: 0.35;
    }

    /* ANIMATIONS */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes marquee {
      from { transform: translateX(0); }
      to { transform: translateX(-50%); }
    }
    .reveal {
      opacity: 0; transform: translateY(40px);
      transition: opacity 0.8s ease, transform 0.8s ease;
    }
    .reveal.visible { opacity: 1; transform: translateY(0); }

    @media (max-width: 900px) {
      nav { padding: 20px 24px; }
      .nav-links { display: none; }
      section { padding: 80px 24px; }
      .hero { padding: 100px 24px 80px; }
      .hero-stats { position: static; flex-direction: row; flex-wrap: wrap; gap: 30px; margin-top: 40px; }
      .stat-item { text-align: left; }
      .services-grid { grid-template-columns: 1fr; }
      .about-section { grid-template-columns: 1fr; gap: 60px; }
      .about-visual { display: none; }
      .works-grid { grid-template-columns: 1fr; }
      .process-steps { grid-template-columns: 1fr 1fr; gap: 40px; }
      .process-steps::before { display: none; }
      .testimonials-grid { grid-template-columns: 1fr; }
      footer { grid-template-columns: 1fr; gap: 40px; padding: 40px 24px; }
      .footer-bottom { padding: 20px 24px; flex-direction: column; gap: 10px; text-align: center; }
    }
  </style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-follower" id="follower"></div>

<!-- NAV -->
<nav>
  <div class="logo">Adhub<span> Firm</span></div>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#works">Work</a></li>
    <li><a href="#process">Process</a></li>
    <li><a href="#contact" class="nav-cta">Get In Touch</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-content">
    <div class="hero-tag">✦ Digital Marketing Agency ✦</div>
    <h1>
      We Make<br>
      <span class="outline">Brands</span><br>
      <span class="accent">Unforgettable</span>
    </h1>
    <p class="hero-sub">
      Adhub Firm crafts bold marketing strategies that drive real growth.
      We combine creativity, data, and relentless execution to put your brand
      exactly where it needs to be.
    </p>
    <div class="hero-btns">
      <a href="#contact" class="btn-primary">Start a Project</a>
      <a href="#works" class="btn-outline">View Our Work</a>
    <div class="hero-stats">
      <div class="stat-item">
        <div class="stat-num">15</div>
        <div class="stat-label">Projects Done</div>
      </div>
      <div class="stat-item">
        <div class="stat-num">98%</div>
        <div class="stat-label">Client Satisfaction</div>
      </div>
      <div class="stat-item">
        <div class="stat-num">8+</div>
        <div class="stat-label">Years Experience</div>
      </div>
    </div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-wrap">
  <div class="marquee-inner">
    <span class="marquee-item">Brand Strategy</span>
    <span class="marquee-item marquee-dot">✦</span>
    <span class="marquee-item">Social Media</span>
    <span class="marquee-item marquee-dot">✦</span>
    <span class="marquee-item">SEO Optimization</span>
    <span class="marquee-item marquee-dot">✦</span>
    <span class="marquee-item">Content Marketing</span>
    <span class="marquee-item marquee-dot">✦</span>
    <span class="marquee-item">Web Design</span>
    <span class="marquee-item marquee-dot">✦</span>
    <span class="marquee-item">Digital Advertising</span>
    <span class="marquee-item marquee-dot">✦</span>
    <span class="marquee-item">Brand Strategy</span>
    <span class="marquee-item marquee-dot">✦</span>
    <span class="marquee-item">Social Media</span>
    <span class="marquee-item marquee-dot">✦</span>
    <span class="marquee-item">SEO Optimization</span>
    <span class="marquee-item marquee-dot">✦</span>
    <span class="marquee-item">Content Marketing</span>
    <span class="marquee-item marquee-dot">✦</span>
    <span class="marquee-item">Web Design</span>
    <span class="marquee-item marquee-dot">✦</span>
    <span class="marquee-item">Digital Advertising</span>
    <span class="marquee-item marquee-dot">✦</span>
  </div>
</div>

<!-- SERVICES -->
<section id="services">
  <div class="section-label reveal">What We Offer</div>
  <div class="section-title reveal">Our Core<br>Services</div>
  <div class="services-grid">
    <div class="service-card reveal">
      <div class="service-num">01</div>
      <div class="service-icon">🎯</div>
      <div class="service-name">Brand Strategy</div>
      <div class="service-desc">We define your brand's identity, values, and market positioning through deep research and strategic planning that sets you apart from competitors.</div>
    </div>
    <div class="service-card reveal">
      <div class="service-num">02</div>
      <div class="service-icon">📱</div>
      <div class="service-name">Social Media</div>
      <div class="service-desc">Build a powerful presence across Facebook, Instagram, TikTok, and LinkedIn. We create content that engages, converts, and grows your audience.</div>
    </div>
    <div class="service-card reveal">
      <div class="service-num">03</div>
      <div class="service-icon">🔍</div>
      <div class="service-name">SEO & SEM</div>
      <div class="service-desc">Dominate search rankings with technical SEO, content optimization, and targeted paid campaigns that bring qualified traffic to your business.</div>
    </div>
    <div class="service-card reveal">
      <div class="service-num">04</div>
      <div class="service-icon">✍️</div>
      <div class="service-name">Content Marketing</div>
      <div class="service-desc">We produce and distribute high-quality content that builds deep connections with your target audience and drives long-term organic growth.</div>
    </div>
    <div class="service-card reveal">
      <div class="service-num">05</div>
      <div class="service-icon">💻</div>
      <div class="service-name">Web Design</div>
      <div class="service-desc">Stunning, conversion-focused websites that reflect your brand's personality and deliver seamless user experiences across all devices.</div>
    </div>
    <div class="service-card reveal">
      <div class="service-num">06</div>
      <div class="service-icon">📊</div>
      <div class="service-name">Data Analytics</div>
      <div class="service-desc">Track every campaign's performance with precision. We turn raw data into clear insights that inform smarter marketing decisions.</div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about" style="background: #080808;">
  <div class="about-section">
    <div class="about-visual reveal">
      <div class="about-box"></div>
      <div class="about-box-inner">ADHUB<br>FIRM</div>
      <div class="about-badge">
        <span class="big">8+</span>
        <span class="small">YEARS</span>
      </div>
    </div>
    <div class="about-text">
      <div class="section-label reveal">About Us</div>
      <div class="section-title reveal">Why We're<br>Different</div>
      <p class="reveal">Since 2016, Adhub Firm has been helping brands achieve real, measurable results in the digital world. Our experienced team blends creative thinking with data-driven strategy to deliver campaigns that actually perform.</p>
      <p class="reveal">We believe every brand has a unique story worth telling. Our job is to make sure that story reaches the right people, at the right time, in the most compelling way possible.</p>
      <div class="about-features">
        <div class="feature-item reveal"><div class="feature-dot"></div>Experienced & dedicated team of specialists</div>
        <div class="feature-item reveal"><div class="feature-dot"></div>Data-driven strategies with real ROI focus</div>
        <div class="feature-item reveal"><div class="feature-dot"></div>Transparent reporting & constant communication</div>
        <div class="feature-item reveal"><div class="feature-dot"></div>Committed to measurable, lasting results</div>
      </div>
    </div>
  </div>
</section>

<!-- PORTFOLIO -->
<section id="works">
  <div class="section-label reveal">Portfolio</div>
  <div class="section-title reveal">Our Best<br>Work</div>
  <div class="works-grid">
    <div class="work-item">
      <div class="work-bg work-grad-1">
        <div class="work-pattern">🏢</div>
      </div>
      <div class="work-overlay">
        <div class="work-info">
          <div class="work-cat">Brand Identity</div>
          <div class="work-title">TechVision Bangladesh</div>
        </div>
      </div>
    </div>
    <div class="work-item">
      <div class="work-bg work-grad-2">
        <div class="work-pattern">🛍️</div>
      </div>
      <div class="work-overlay">
        <div class="work-info">
          <div class="work-cat">E-Commerce Marketing</div>
          <div class="work-title">FashionHub BD</div>
        </div>
      </div>
    </div>
    <div class="work-item">
      <div class="work-bg work-grad-3">
        <div class="work-pattern">🍽️</div>
      </div>
      <div class="work-overlay">
        <div class="work-info">
          <div class="work-cat">Social Media Campaign</div>
          <div class="work-title">Spice Garden Restaurant</div>
        </div>
      </div>
    </div>
    <div class="work-item">
      <div class="work-bg work-grad-4">
        <div class="work-pattern">🏦</div>
      </div>
      <div class="work-overlay">
        <div class="work-info">
          <div class="work-cat">Digital Transformation</div>
          <div class="work-title">NovaPay Fintech</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROCESS -->
<section id="process" style="background: #0d0d0d;">
  <div class="section-label reveal">Our Approach</div>
  <div class="section-title reveal">How We<br>Work</div>
  <div class="process-steps">
    <div class="process-step reveal">
      <div class="step-circle">01</div>
      <div class="step-title">Discovery</div>
      <div class="step-desc">We dig deep into your business, goals, and competitive landscape to build a complete picture before we plan anything.</div>
    </div>
    <div class="process-step reveal">
      <div class="step-circle">02</div>
      <div class="step-title">Strategy</div>
      <div class="step-desc">Using data and research, we craft a custom marketing roadmap tailored to your specific audience and objectives.</div>
    </div>
    <div class="process-step reveal">
      <div class="step-circle">03</div>
      <div class="step-title">Execution</div>
      <div class="step-desc">Our skilled team brings the strategy to life with precision, creativity, and an obsessive attention to quality.</div>
    </div>
    <div class="process-step reveal">
      <div class="step-circle">04</div>
      <div class="step-title">Optimization</div>
      <div class="step-desc">We continuously analyze performance and refine every element to maximize results and drive ongoing growth.</div>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section class="testimonials-section">
  <div class="section-label reveal">Client Reviews</div>
  <div class="section-title reveal">What They're<br>Saying</div>
  <div class="testimonials-grid">
    <div class="testimonial-card reveal">
      <div class="quote-mark">"</div>
      <p class="testimonial-text">Working with Adhub Firm has been a game-changer. Their strategic approach tripled our online sales in less than six months. Absolutely incredible team.</p>
      <div class="testimonial-author">
        <div class="author-avatar">RH</div>
        <div>
          <div class="author-name">Rahela Hossain</div>
          <div class="author-role">CEO, StyleCraft BD</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card reveal">
      <div class="quote-mark">"</div>
      <p class="testimonial-text">Professional team, on-time delivery, and unbelievable results. Adhub Firm elevated our brand to a completely new level. Highly recommend.</p>
      <div class="testimonial-author">
        <div class="author-avatar">KA</div>
        <div>
          <div class="author-name">Karim Ahmed</div>
          <div class="author-role">Founder, TechNova</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card reveal">
      <div class="quote-mark">"</div>
      <p class="testimonial-text">Adhub Firm's content marketing strategy increased our website's organic traffic by 5x. The ROI has been extraordinary. A true partner in growth.</p>
      <div class="testimonial-author">
        <div class="author-avatar">SN</div>
        <div>
          <div class="author-name">Sumaiya Nasrin</div>
          <div class="author-role">Marketing Director, FoodieHub</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CTA -->
<section class="cta-section" id="contact">
  <div class="cta-bg"></div>
  <p class="section-label" style="justify-content: center; display: flex;">Ready to grow?</p>
  <h2 class="reveal">Take Your Brand<br><span style="color: var(--gold);">To The Next</span><br>Level</h2>
  <p class="reveal">Get in touch today and receive a free strategy consultation — no strings attached.</p>
  <div style="display: flex; gap: 20px; justify-content: center; flex-wrap: wrap; position: relative;">
    <a href="/cdn-cgi/l/email-protection#a2c3c6cad7c09b9a97e2c5cfc3cbce8cc1cdcf" class="btn-primary reveal">Book a Free Consultation</a>
    <a href="tel:+8801700958614" class="btn-outline reveal">01700958614</a>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-brand">
    <span class="logo">Adhub<span style="color:var(--gold)"> Firm</span></span>
    <p class="footer-desc">A results-driven digital marketing agency helping brands grow, connect, and lead in the digital age.</p>
  </div>
  <div class="footer-col">
    <h4>Services</h4>
    <ul class="footer-links">
      <li><a href="#">Brand Strategy</a></li>
      <li><a href="#">Social Media</a></li>
      <li><a href="#">SEO / SEM</a></li>
      <li><a href="#">Content Marketing</a></li>
      <li><a href="#">Web Design</a></li>
    </ul>
  </div>
  <div class="footer-col">
    <h4>Company</h4>
    <ul class="footer-links">
      <li><a href="#">About Us</a></li>
      <li><a href="#">Portfolio</a></li>
      <li><a href="#">Blog</a></li>
      <li><a href="#">Careers</a></li>
    </ul>
  </div>
  <div class="footer-col">
    <h4>Contact</h4>
    <ul class="footer-links">
      <li><a href="#"><span class="__cf_email__" data-cfemail="58393c302d3a61606d183f35393134763b3735">[email&#160;protected]</span></a></li>
      <li><a href="#">01700958614</a></li>
      <li><a href="#">Dhaka, Bangladesh</a></li>
      <li><a href="#">Facebook</a></li>
      <li><a href="#">LinkedIn</a></li>
    </ul>
  </div>
</footer>
<div class="footer-bottom">
  <span>© 2026 Adhub Firm. All rights reserved.</span>
  <span>Privacy Policy · Terms of Service</span>
</div>

<script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
  // Custom cursor
  const cursor = document.getElementById('cursor');
  const follower = document.getElementById('follower');
  let mx = 0, my = 0, fx = 0, fy = 0;
  document.addEventListener('mousemove', e => {
    mx = e.clientX; my = e.clientY;
    cursor.style.transform = `translate(${mx - 6}px, ${my - 6}px)`;
  });
  function animateFollower() {
    fx += (mx - fx - 20) * 0.12;
    fy += (my - fy - 20) * 0.12;
    follower.style.transform = `translate(${fx}px, ${fy}px)`;
    requestAnimationFrame(animateFollower);
  }
  animateFollower();
  document.querySelectorAll('a, button').forEach(el => {
    el.addEventListener('mouseenter', () => {
      follower.style.width = '60px'; follower.style.height = '60px';
      follower.style.marginTop = '-10px'; follower.style.marginLeft = '-10px';
    });
    el.addEventListener('mouseleave', () => {
      follower.style.width = '40px'; follower.style.height = '40px';
      follower.st
