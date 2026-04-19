<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>K20 — Portfolio / v2</title>
  <meta name="description" content="Editorial dark developer portfolio for K20, built for GitHub Pages." />
  <link href="https://api.fontshare.com/v2/css?f[]=general-sans@400,500,600,700&f[]=clash-display@500,600,700&display=swap" rel="stylesheet">
  <style>
    :root, [data-theme="dark"] {
      --text-xs: clamp(0.75rem, 0.72rem + 0.2vw, 0.875rem);
      --text-sm: clamp(0.9rem, 0.82rem + 0.28vw, 1rem);
      --text-base: clamp(1rem, 0.96rem + 0.22vw, 1.12rem);
      --text-lg: clamp(1.2rem, 1rem + 0.8vw, 1.55rem);
      --text-xl: clamp(1.6rem, 1.2rem + 1.6vw, 2.5rem);
      --text-2xl: clamp(2.8rem, 1.6rem + 4vw, 5.6rem);
      --text-hero: clamp(4rem, 1rem + 10vw, 9rem);
      --space-1: 0.25rem; --space-2: 0.5rem; --space-3: 0.75rem; --space-4: 1rem; --space-5: 1.25rem;
      --space-6: 1.5rem; --space-8: 2rem; --space-10: 2.5rem; --space-12: 3rem; --space-16: 4rem; --space-20: 5rem; --space-24: 6rem;
      --color-bg: #0b0d0e;
      --color-surface: #101416;
      --color-surface-2: #151a1d;
      --color-surface-offset: #1c2327;
      --color-border: rgba(228, 236, 240, 0.10);
      --color-divider: rgba(228, 236, 240, 0.08);
      --color-text: #eef2f3;
      --color-text-muted: #a4afb5;
      --color-text-faint: #6f7a80;
      --color-text-inverse: #0b0d0e;
      --color-primary: #a78bfa;
      --color-primary-2: #70d6ff;
      --color-purple: #a78bfa;
      --color-purple-strong: #8b5cf6;
      --color-purple-dim: rgba(167, 139, 250, 0.12);
      --color-primary-dim: rgba(139, 243, 200, 0.12);
      --radius-sm: 0.45rem; --radius-md: 0.8rem; --radius-lg: 1.25rem; --radius-xl: 1.8rem; --radius-full: 9999px;
      --shadow-sm: 0 1px 2px rgba(0,0,0,0.25);
      --shadow-md: 0 16px 40px rgba(0,0,0,0.35);
      --shadow-lg: 0 30px 80px rgba(0,0,0,0.45);
      --transition: 220ms cubic-bezier(0.16, 1, 0.3, 1);
      --font-body: 'General Sans', 'Inter', sans-serif;
      --font-display: 'Clash Display', 'Inter', sans-serif;
      --content: 1180px;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; -webkit-font-smoothing: antialiased; }
    body {
      min-height: 100dvh;
      font-family: var(--font-body);
      font-size: var(--text-base);
      line-height: 1.6;
      color: var(--color-text);
      background:
        radial-gradient(circle at 10% 10%, rgba(112, 214, 255, 0.08), transparent 24%),
        radial-gradient(circle at 78% 18%, rgba(167, 139, 250, 0.05), transparent 20%),
        radial-gradient(circle at 90% 12%, rgba(139, 243, 200, 0.08), transparent 22%),
        linear-gradient(180deg, #0b0d0e 0%, #0d1011 50%, #0b0d0e 100%);
    }
    img, svg { display: block; max-width: 100%; height: auto; }
    a { color: inherit; text-decoration: none; }
    button { font: inherit; border: 0; background: none; color: inherit; cursor: pointer; }
    :focus-visible { outline: 2px solid var(--color-primary); outline-offset: 3px; border-radius: var(--radius-sm); }

    .skip-link {
      position: absolute; left: var(--space-4); top: -3rem; z-index: 50;
      background: var(--color-text); color: var(--color-text-inverse); padding: var(--space-2) var(--space-3); border-radius: var(--radius-sm);
    }
    .skip-link:focus { top: var(--space-4); }

    .container { width: min(calc(100% - 2rem), var(--content)); margin-inline: auto; }
    .grid { display: grid; gap: var(--space-5); }
    .eyebrow {
      display: inline-flex; align-items: center; gap: var(--space-2); width: fit-content;
      min-height: 2rem; padding: 0.35rem 0.8rem; border-radius: var(--radius-full);
      font-size: var(--text-xs); letter-spacing: 0.14em; text-transform: uppercase;
      color: var(--color-text-muted); border: 1px solid var(--color-border); background: rgba(255,255,255,0.02);
    }
    .section { padding-block: clamp(var(--space-16), 11vw, var(--space-24)); }
    .section-head { margin-bottom: var(--space-8); display: grid; gap: var(--space-3); }
    .section-title {
      font-family: var(--font-display); font-size: var(--text-2xl); line-height: 0.96; letter-spacing: -0.03em; max-width: 11ch;
    }
    .section-copy { color: var(--color-text-muted); max-width: 62ch; }

    .site-header {
      position: sticky; top: 0; z-index: 30; backdrop-filter: blur(18px);
      background: rgba(11, 13, 14, 0.72); border-bottom: 1px solid color-mix(in srgb, var(--color-divider) 55%, rgba(167,139,250,0.40) 45%); box-shadow: 0 8px 30px rgba(0,0,0,0.18), inset 0 -1px 0 rgba(167,139,250,0.18);
    }
    .header-inner {
      display: flex; align-items: center; justify-content: space-between; gap: var(--space-4); min-height: 4.8rem;
    }
    .brand {
      display: inline-flex; align-items: center; gap: var(--space-3); font-size: var(--text-sm); font-weight: 600; letter-spacing: 0.02em;
    }
    .brand-mark {
      width: 2.7rem; height: 2.7rem; padding: 0.4rem; border-radius: 0.9rem; color: #091010;
      background: linear-gradient(135deg, var(--color-primary), var(--color-purple));
      box-shadow: 0 0 0 1px rgba(255,255,255,0.05), 0 10px 30px rgba(167, 139, 250, 0.14);
    }
    .nav { display: flex; align-items: center; gap: var(--space-4); flex-wrap: wrap; }
    .nav a { font-size: var(--text-sm); color: var(--color-text-muted); transition: color var(--transition); }
    .nav a:hover, .nav a.active { color: var(--color-text); }
    .header-cta {
      display: inline-flex; align-items: center; gap: var(--space-3);
    }
    .icon-btn, .pill-btn {
      min-height: 2.8rem; display: inline-flex; align-items: center; justify-content: center; border-radius: var(--radius-full);
      border: 1px solid var(--color-border); transition: transform var(--transition), border-color var(--transition), background var(--transition), color var(--transition);
    }
    .icon-btn { width: 2.8rem; background: rgba(255,255,255,0.02); box-shadow: inset 0 0 0 1px rgba(167,139,250,0.06); }
    .pill-btn { padding: 0.8rem 1.1rem; background: var(--color-text); color: var(--color-text-inverse); font-size: var(--text-sm); font-weight: 700; }
    .pill-btn:hover, .icon-btn:hover { transform: translateY(-1px); border-color: rgba(167,139,250,0.35); }
    .pill-btn:hover { background: var(--color-primary); }

    .hero {
      padding-top: clamp(var(--space-16), 10vw, 8rem);
      padding-bottom: clamp(var(--space-16), 8vw, 7rem);
      position: relative;
      overflow: clip;
    }
    .hero-layout {
      display: grid; gap: var(--space-8);
    }
    .hero-copy { display: grid; gap: var(--space-5); }
    .hero-title {
      font-family: var(--font-display);
      font-size: var(--text-hero);
      line-height: 0.88;
      letter-spacing: -0.045em;
      max-width: 8ch;
    }
    .hero-title .dim { color: var(--color-text-faint); display: block; }
    .hero-desc { max-width: 58ch; color: var(--color-text-muted); }
    .hero-actions { display: flex; flex-wrap: wrap; gap: var(--space-3); }
    .hero-notes {
      display: grid; gap: var(--space-4); align-content: start;
    }
    .panel {
      background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(167,139,250,0.05));
      border: 1px solid color-mix(in srgb, var(--color-border) 55%, rgba(167,139,250,0.35) 45%);
      border-radius: var(--radius-xl);
      box-shadow: var(--shadow-md);
      overflow: hidden;
    }
    .hero-terminal {
      min-height: 22rem; padding: var(--space-5);
      background:
        linear-gradient(180deg, rgba(9, 13, 14, 0.7), rgba(16,20,22,0.96)),
        linear-gradient(120deg, rgba(112,214,255,0.05), transparent 40%);
    }
    .terminal-top {
      display: flex; align-items: center; justify-content: space-between; gap: var(--space-4); padding-bottom: var(--space-4); border-bottom: 1px solid var(--color-divider); margin-bottom: var(--space-5);
    }
    .terminal-dots { display: inline-flex; gap: 0.45rem; }
    .terminal-dots span { width: 0.7rem; height: 0.7rem; border-radius: 50%; background: rgba(255,255,255,0.18); }
    .terminal-dots span:nth-child(1) { background: #ff7b72; }
    .terminal-dots span:nth-child(2) { background: #f2cc60; }
    .terminal-dots span:nth-child(3) { background: #7ee787; }
    .mono { font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace; font-size: 0.95rem; }
    .command-list { display: grid; gap: var(--space-4); color: var(--color-text-muted); }
    .command-line { display: grid; gap: var(--space-2); }
    .prompt { color: var(--color-primary); }
    .output { color: var(--color-text); }

    .quick-grid, .skills-grid, .projects-grid, .story-grid, .contact-grid {
      display: grid; gap: var(--space-5);
    }
    .quick-card, .skill-card, .project-card, .story-card, .contact-card {
      padding: var(--space-5);
      background: rgba(255,255,255,0.02);
      border: 1px solid color-mix(in srgb, var(--color-border) 72%, rgba(167,139,250,0.22) 28%);
      border-radius: var(--radius-lg);
      transition: transform var(--transition), border-color var(--transition), background var(--transition);
    }
    .quick-card:hover, .skill-card:hover, .project-card:hover, .story-card:hover, .contact-card:hover {
      transform: translateY(-2px);
      border-color: rgba(167,139,250,0.3);
      background: rgba(255,255,255,0.03);
    }
    .quick-card strong, .skill-card h3, .project-card h3, .story-card h3, .contact-card h3 {
      display: block; font-family: var(--font-display); font-size: var(--text-lg); line-height: 1.05; letter-spacing: -0.015em; margin-bottom: var(--space-3);
    }
    .muted { color: var(--color-text-muted); }
    .stat-line {
      display: flex; justify-content: space-between; gap: var(--space-4); padding-top: var(--space-3); margin-top: var(--space-4);
      border-top: 1px solid color-mix(in srgb, var(--color-divider) 72%, rgba(167,139,250,0.18) 28%); font-size: var(--text-xs); text-transform: uppercase; letter-spacing: 0.12em; color: var(--color-text-faint);
    }
    .tags { display: flex; flex-wrap: wrap; gap: var(--space-2); margin-top: var(--space-4); }
    .tag {
      display: inline-flex; align-items: center; min-height: 2rem; padding: 0.35rem 0.75rem; border-radius: var(--radius-full);
      font-size: var(--text-xs); letter-spacing: 0.04em; background: color-mix(in srgb, var(--color-primary-dim) 70%, var(--color-purple-dim) 30%); color: var(--color-text);
      border: 1px solid rgba(167,139,250,0.2);
    }

    .about-wrap {
      display: grid; gap: var(--space-5);
    }
    .about-main {
      padding: clamp(var(--space-6), 4vw, var(--space-8));
      background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(167,139,250,0.05));
      border: 1px solid color-mix(in srgb, var(--color-border) 55%, rgba(167,139,250,0.35) 45%); border-radius: var(--radius-xl);
    }
    .about-main p + p { margin-top: var(--space-4); }
    .quote-bar {
      margin-top: var(--space-6); padding-top: var(--space-4); border-top: 1px solid var(--color-divider); color: var(--color-text); font-size: var(--text-lg); max-width: 28ch;
    }

    .project-card {
      display: grid; gap: var(--space-4);
      min-height: 100%;
    }
    .project-top {
      display: flex; justify-content: space-between; gap: var(--space-4); align-items: start;
    }
    .project-index {
      font-size: var(--text-xs); color: var(--color-text-faint); text-transform: uppercase; letter-spacing: 0.14em;
    }
    .project-links { display: flex; gap: var(--space-3); flex-wrap: wrap; }
    .project-links a { color: var(--color-purple); font-size: var(--text-sm); font-weight: 700; text-shadow: 0 0 20px rgba(167,139,250,0.25); }

    .story-card {
      position: relative; overflow: hidden;
    }
    .story-card::before {
      content: ""; position: absolute; left: 0; top: 0; bottom: 0; width: 2px;
      background: linear-gradient(180deg, var(--color-purple), transparent);
    }

    .contact-panel {
      display: grid; gap: var(--space-5);
      padding: clamp(var(--space-6), 4vw, var(--space-8));
      border-radius: var(--radius-xl);
      border: 1px solid rgba(167,139,250,0.18);
      background: linear-gradient(180deg, rgba(167,139,250,0.04), rgba(167,139,250,0.07));
      box-shadow: var(--shadow-lg);
    }
    .contact-links { display: grid; gap: var(--space-3); }
    .contact-links a {
      display: flex; align-items: center; justify-content: space-between; gap: var(--space-4);
      padding: 0.95rem 1rem; border-radius: var(--radius-md); border: 1px solid color-mix(in srgb, var(--color-border) 45%, rgba(167,139,250,0.38) 55%); background: linear-gradient(180deg, rgba(0,0,0,0.12), rgba(167,139,250,0.08)); box-shadow: 0 0 0 1px rgba(167,139,250,0.05);
    }
    .contact-links a span:last-child { color: var(--color-primary); font-weight: 700; }

    .footer {
      padding: var(--space-8) 0 var(--space-12);
      border-top: 1px solid var(--color-divider);
      color: var(--color-text-muted);
    }
    .footer-inner {
      display: flex; justify-content: space-between; gap: var(--space-4); flex-wrap: wrap;
    }


    .pill-btn-secondary { background: transparent; color: var(--color-text); border: 1px solid rgba(167,139,250,0.35); }
    .pill-btn-secondary:hover { background: rgba(167,139,250,0.10); }
    .hero-layout { position: relative; }
    .hero-layout::before {
      content: ""; position: absolute; inset: 8% auto auto 52%; width: 24rem; height: 24rem; border-radius: 50%;
      background: radial-gradient(circle, rgba(167,139,250,0.16), transparent 62%); filter: blur(10px); pointer-events: none; animation: pulseGlow 8s ease-in-out infinite;
    }
    .hero-title { display: flex; flex-wrap: wrap; gap: 0.04em 0.12em; }
    .char { display: inline-block; opacity: 0; transform: translateY(16px) scale(0.98); animation: popIn 0.7s var(--delay) cubic-bezier(0.16,1,0.3,1) forwards; }
    .hero-visual { position: relative; min-height: 24rem; border-radius: var(--radius-xl); border: 1px solid rgba(167,139,250,0.22); overflow: hidden; background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(167,139,250,0.04)); }
    .hero-visual::after { content: ""; position: absolute; inset: 0; background: linear-gradient(120deg, transparent, rgba(167,139,250,0.10), transparent); transform: translateX(-60%); animation: sweep 7s linear infinite; }
    .floating-card { position: absolute; left: var(--float-x); top: var(--float-y); padding: 0.85rem 1rem; border-radius: 9999px; background: rgba(11,13,14,0.72); border: 1px solid rgba(167,139,250,0.22); color: #ebe4ff; box-shadow: 0 10px 30px rgba(0,0,0,0.25); backdrop-filter: blur(12px); animation: floatUp 6s ease-in-out infinite; }
    .floating-card:nth-child(2) { animation-delay: 0.8s; }
    .floating-card:nth-child(3) { animation-delay: 1.6s; }
    .floating-card:nth-child(4) { animation-delay: 2.4s; }
    @keyframes popIn { to { opacity: 1; transform: translateY(0) scale(1); } }
    @keyframes floatUp { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }
    @keyframes pulseGlow { 0%,100% { opacity: 0.55; transform: scale(1); } 50% { opacity: 0.95; transform: scale(1.04); } }
    @keyframes sweep { 0% { transform: translateX(-70%); } 100% { transform: translateX(70%); } }
    .reveal { opacity: 0; transform: translateY(20px); transition: opacity 0.8s ease, transform 0.8s ease; }
    .reveal.visible { opacity: 1; transform: translateY(0); }

    @media (min-width: 860px) {
      .hero-layout { grid-template-columns: 1.05fr 0.95fr; align-items: end; }
      .quick-grid { grid-template-columns: repeat(4, minmax(0, 1fr)); }
      .skills-grid { grid-template-columns: repeat(3, minmax(0, 1fr)); }
      .projects-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); }
      .story-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); }
      .contact-grid { grid-template-columns: 1fr 1fr; align-items: start; }
      .about-wrap { grid-template-columns: 1.15fr 0.85fr; }
    }

    @media (max-width: 760px) {
      .nav { display: none; }
      .header-cta .pill-btn { display: none; }
      .hero-title { max-width: 9ch; }
      .section-title { max-width: 12ch; }
    }

    @media (prefers-reduced-motion: reduce) {
      html { scroll-behavior: auto; }
      *, *::before, *::after { animation-duration: 0.01ms !important; transition-duration: 0.01ms !important; }
      .reveal { opacity: 1; transform: none; }
    }
  
/* Modern hero animations */
.hero-part { 
  opacity: 0; transform: translateY(1.8rem); display: inline-block;
  animation: heroPartIn 0.7s cubic-bezier(0.23, 1, 0.32, 1) forwards;
}
.hero-part { animation-delay: var(--delay); }
@keyframes heroPartIn { 
  to { opacity: 1; transform: translateY(0); } 
}
.modern-terminal { 
  animation: terminalShine 3s ease-in-out infinite; 
  position: relative; overflow: hidden;
}
.modern-terminal::before {
  content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px;
  background: linear-gradient(90deg, transparent, var(--color-purple), transparent);
  animation: shine 2s linear infinite;
}
@keyframes shine { 0% { transform: translateX(-100%); } 100% { transform: translateX(100%); } }
@keyframes terminalShine { 
  0% { box-shadow: 0 0 25px rgba(167,139,250,0.3); }
  100% { box-shadow: 0 0 45px rgba(167,139,250,0.6); } 
}
.pill-btn.secondary { background: transparent; color: var(--color-text); border: 1px solid var(--color-border); }
.pill-btn.secondary:hover { background: var(--color-purple); color: var(--color-text-inverse); }
</style>
</head>
<body>
  <a href="#main" class="skip-link">Skip to content</a>

  <header class="site-header">
    <div class="container header-inner">
      <a href="#top" class="brand" aria-label="K20 home">
        <svg class="brand-mark" viewBox="0 0 64 64" fill="none" aria-hidden="true">
          <path d="M14 14V50" stroke="currentColor" stroke-width="6" stroke-linecap="round"/>
          <path d="M44 15L23 32L44 49" stroke="currentColor" stroke-width="6" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M50 20C54.4183 20 58 23.5817 58 28V36C58 40.4183 54.4183 44 50 44C45.5817 44 42 40.4183 42 36V28C42 23.5817 45.5817 20 50 20Z" stroke="currentColor" stroke-width="4"/>
        </svg>
        <span>K20 / portfolio</span>
      </a>

      <nav class="nav" aria-label="Primary navigation">
        <a href="#about">About</a>
        <a href="#skills">Stack</a>
        <a href="#projects">Projects</a>
        <a href="#story">Journey</a>
        <a href="#contact">Contact</a>
      </nav>

      <div class="header-cta">
        <button type="button" class="icon-btn" data-theme-toggle aria-label="Switch theme">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path></svg>
        </button>
        <a class="pill-btn" href="#contact">Work with me</a>
      </div>
    </div>
  </header>

  <main id="main">
    
<section class="hero" id="top">
  <div class="container hero-layout">
    <div class="hero-copy reveal">
      <span class="eyebrow">GitHub Pages · Static · Modern</span>
      <h1 class="hero-title">
        <span class="hero-part" style="--delay: 0.1s">K20</span>
        <span class="hero-part" style="--delay: 0.3s">/</span>
        <span class="hero-part" style="--delay: 0.5s">Dev Portfolio</span>
      </h1>
      <p class="hero-desc">
        Frontend specialist with backend, Linux, and cybersecurity interests. 
        I build clean interfaces, practical tools, and systems that scale.
      </p>
      <div class="hero-actions">
        <a href="#projects" class="pill-btn">View projects</a>
        <a href="#contact" class="pill-btn secondary">Contact</a>
      </div>
    </div>
    <aside class="hero-notes reveal">
      <div class="panel hero-terminal modern-terminal">
        <div class="terminal-top mono">
          <div class="terminal-dots" aria-hidden="true">
            <span></span><span></span><span></span>
          </div>
          <span>k20@portfolio:~$</span>
        </div>
        <div class="command-list mono">
          <div class="command-line">
            <span class="prompt">skills</span>
            <span class="output">Frontend, Python, Linux, Security</span>
          </div>
          <div class="command-line">
            <span class="prompt">status</span>
            <span class="output">Available for collaboration</span>
          </div>
          <div class="command-line">
            <span class="prompt">deploy</span>
            <span class="output">Live on GitHub Pages</span>
          </div>
        </div>
      </div>
    </aside>
  </div>
</section>
>

    <section class="section">
      <div class="container quick-grid">
        <article class="quick-card reveal">
          <strong>Frontend</strong>
          <p class="muted">Responsive layouts, strong typography, refined components, and clean page structure.</p>
          <div class="stat-line"><span>focus</span><span>UI / UX / CSS</span></div>
        </article>
        <article class="quick-card reveal">
          <strong>Backend</strong>
          <p class="muted">Practical scripting, forms, data flows, and automation that supports real workflows.</p>
          <div class="stat-line"><span>tools</span><span>PHP / Python / SQL</span></div>
        </article>
        <article class="quick-card reveal">
          <strong>Systems</strong>
          <p class="muted">Linux-first habits, troubleshooting mindset, and comfort working close to the terminal.</p>
          <div class="stat-line"><span>env</span><span>Linux / Bash</span></div>
        </article>
        <article class="quick-card reveal">
          <strong>Security</strong>
          <p class="muted">Research-driven learning around WordPress, web surfaces, and testing-oriented thinking.</p>
          <div class="stat-line"><span>lens</span><span>audit / hardening</span></div>
        </article>
      </div>
    </section>

    <section class="section" id="about">
      <div class="container about-wrap">
        <div class="section-head reveal">
          <span class="eyebrow">About</span>
          <h2 class="section-title">A cleaner, darker direction with more character.</h2>
          <p class="section-copy">This version leans into a bold editorial layout, sharper display typography, and a terminal-inspired visual language while keeping the site static and easy to host on GitHub Pages.</p>
        </div>
        <article class="about-main reveal">
          <p>
            I work best on projects that mix clarity with technical depth. That can mean building a responsive interface, improving an internal workflow, understanding a broken setup, or documenting a system so it becomes easier to use and maintain.
          </p>
          <p>
            My interests sit across frontend development, Linux administration, WordPress internals, automation, data handling, and cybersecurity learning. I care about practical output, not just theory.
          </p>
          <p class="quote-bar">
            The goal is simple: make complex things feel structured, useful, and well built.
          </p>
        </article>
      </div>
    </section>

    <section class="section" id="skills">
      <div class="container">
        <div class="section-head reveal">
          <span class="eyebrow" style="border-color: rgba(167,139,250,0.22);">Stack</span>
          <h2 class="section-title">Skills grouped by how I actually work.</h2>
          <p class="section-copy">You prefer straightforward skill presentation rather than certificate-heavy sections, so this design keeps the stack grouped and direct. [cite:1][cite:21]</p>
        </div>
        <div class="skills-grid">
          <article class="skill-card reveal">
            <h3>Interface building</h3>
            <p class="muted">HTML, CSS, Bootstrap, responsive design systems, visual hierarchy, layout cleanup, and practical JavaScript interactions.</p>
            <div class="tags">
              <span class="tag">HTML</span><span class="tag">CSS</span><span class="tag">Bootstrap</span><span class="tag">JavaScript</span><span class="tag">Accessibility</span>
            </div>
          </article>
          <article class="skill-card reveal">
            <h3>Scripting and workflows</h3>
            <p class="muted">PHP scripts, Python utilities, request logic, automation ideas, and data-driven thinking for repetitive tasks.</p>
            <div class="tags">
              <span class="tag">PHP</span><span class="tag">Python</span><span class="tag">SQL</span><span class="tag">APIs</span><span class="tag">Automation</span>
            </div>
          </article>
          <article class="skill-card reveal">
            <h3>Security-minded systems</h3>
            <p class="muted">Linux habits, terminal workflows, WordPress checks, troubleshooting, and research-oriented technical exploration.</p>
            <div class="tags">
              <span class="tag">Linux</span><span class="tag">Bash</span><span class="tag">WordPress</span><span class="tag">Testing</span><span class="tag">Hardening</span>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section class="section" id="projects">
      <div class="container">
        <div class="section-head reveal">
          <span class="eyebrow" style="border-color: rgba(167,139,250,0.28); color: #c7b8ff;">Projects</span>
          <h2 class="section-title">Real projects from my work and experiments.</h2>
          <p class="section-copy">These entries are based on the project details from your attached file, then adapted into tighter portfolio-style summaries so they read more professionally on a public portfolio. [file:39]</p>
        </div>
        <div class="projects-grid">
          <article class="project-card reveal">
            <div class="project-top">
              <div>
                <div class="project-index">01 · web scraping</div>
                <h3>Contact extraction crawler</h3>
              </div>
              <div class="project-links"></div>
            </div>
            <p class="muted">Built a tool that scans one or more websites, extracts email addresses with pattern matching, removes duplicates, and can optionally follow internal links to widen coverage. The result is a clean contact list that can be exported or reviewed directly. [file:39]</p>
            <div class="tags"><span class="tag">Python</span><span class="tag">Regex</span><span class="tag">Web scraping</span></div>
          </article>

          <article class="project-card reveal">
            <div class="project-top">
              <div>
                <div class="project-index">02 · business platform</div>
                <h3>Atlas Online Morocco flight management system</h3>
              </div>
              <div class="project-links"></div>
            </div>
            <p class="muted">Designed a custom web platform for managing flight schedules, reservations, passenger records, and real-time operational updates. The system centralizes travel administration, improves booking accuracy, and gives staff faster search, filtering, and reporting tools. [file:39]</p>
            <div class="tags"><span class="tag">Web app</span><span class="tag">Operations</span><span class="tag">Reporting</span></div>
          </article>

          <article class="project-card reveal">
            <div class="project-top">
              <div>
                <div class="project-index">03 · retail software</div>
                <h3>Store management system</h3>
              </div>
              <div class="project-links"></div>
            </div>
            <p class="muted">Created a business management website that handles inventory, purchases, sales, customers, suppliers, invoices, expenses, and profit analysis in one place. It supports role-based access, stock alerts, payment tracking, returns, and dashboard views for day-to-day store control. [file:39]</p>
            <div class="tags"><span class="tag">Dashboard</span><span class="tag">Inventory</span><span class="tag">Role-based access</span></div>
          </article>

          <article class="project-card reveal">
            <div class="project-top">
              <div>
                <div class="project-index">04 · data synchronization</div>
                <h3>Multi-store database synchronization program</h3>
              </div>
              <div class="project-links"></div>
            </div>
            <p class="muted">Built a synchronization layer that pulls inventory, sales, customers, and order data from multiple independent store databases into one unified real-time view. The system handles transformation, conflict resolution, and live aggregation across different database engines. [file:39]</p>
            <div class="tags"><span class="tag">Databases</span><span class="tag">Real-time sync</span><span class="tag">Data integration</span></div>
          </article>

          <article class="project-card reveal">
            <div class="project-top">
              <div>
                <div class="project-index">05 · data security</div>
                <h3>Secure data erasure program</h3>
              </div>
              <div class="project-links"></div>
            </div>
            <p class="muted">Developed a secure deletion utility for files, folders, and drives using multi-pass overwrite workflows aligned with recognized sanitization standards. The program is aimed at privacy-focused environments and can generate audit logs and erasure certificates for compliance reporting. [file:39]</p>
            <div class="tags"><span class="tag">Security</span><span class="tag">Data sanitization</span><span class="tag">Compliance</span></div>
          </article>

          <article class="project-card reveal">
            <div class="project-top">
              <div>
                <div class="project-index">06 · email infrastructure</div>
                <h3>Mass email dispatch system</h3>
              </div>
              <div class="project-links"></div>
            </div>
            <p class="muted">Built a high-volume email delivery system with SMTP rotation, personalized content, HTML templates, scheduling, attachments, and live reporting for opens, clicks, bounces, and failures. The platform also includes consent and compliance-related features such as unsubscribe support and authentication-aware sending workflows. [file:39]</p>
            <div class="tags"><span class="tag">SMTP</span><span class="tag">Reporting</span><span class="tag">Automation</span></div>
          </article>

          <article class="project-card reveal">
            <div class="project-top">
              <div>
                <div class="project-index">07 · browser automation</div>
                <h3>Legacy web automation and data extraction tool</h3>
              </div>
              <div class="project-links"></div>
            </div>
            <p class="muted">Created a Selenium-based automation program for older websites that do not expose modern APIs. It logs into authorized systems, performs repetitive interface actions, and extracts needed information to support reporting, portal maintenance, and workflow continuity. [file:39]</p>
            <div class="tags"><span class="tag">Selenium</span><span class="tag">Legacy systems</span><span class="tag">Automation</span></div>
          </article>

          <article class="project-card reveal">
            <div class="project-top">
              <div>
                <div class="project-index">08 · ERP integration</div>
                <h3>Odoo Gmail integration and procurement module</h3>
              </div>
              <div class="project-links"></div>
            </div>
            <p class="muted">Built an Odoo module that reads authorized Gmail threads, extracts order-related details, checks inventory levels, and automatically prepares quotations or purchase drafts based on stock availability. This reduces manual order-to-procurement work and speeds up operational response time. [file:39]</p>
            <div class="tags"><span class="tag">Odoo</span><span class="tag">Gmail</span><span class="tag">Procurement</span></div>
          </article>

          <article class="project-card reveal">
            <div class="project-top">
              <div>
                <div class="project-index">09 · Rust security</div>
                <h3 style="color: #d9ccff;">Selective file encryption with remote key escrow</h3>
              </div>
              <div class="project-links"></div>
            </div>
            <p class="muted">Developed a Rust-based encryption utility that protects selected files individually with separate keys and supports controlled off-site key escrow for recovery. The design focuses on compartmentalization, strong encryption standards, and auditable access to decryption material. [file:39]</p>
            <div class="tags"><span class="tag">Rust</span><span class="tag">AES-256-GCM</span><span class="tag">Encryption</span></div>
          </article>

          <article class="project-card reveal">
            <div class="project-top">
              <div>
                <div class="project-index">10 · backup integrity</div>
                <h3 style="color: #d9ccff;">Offline backup verification and integrity scanner</h3>
              </div>
              <div class="project-links"></div>
            </div>
            <p class="muted">Built a Rust tool for verifying offline backups against stored checksum manifests, detecting missing or corrupted data, and producing detailed health reports. The scanner is designed for cold storage validation, disaster recovery readiness, and long-term archival confidence. [file:39]</p>
            <div class="tags"><span class="tag">Rust</span><span class="tag">BLAKE3</span><span class="tag">Backup validation</span></div>
          </article>
        </div>
      </div>
    </section>

    <section class="section" id="story">
      <div class="container">
        <div class="section-head reveal">
          <span class="eyebrow">Journey</span>
          <h2 class="section-title">The path is technical, practical, and still expanding.</h2>
          <p class="section-copy">This section is designed to help you present your study path, internship experience, and self-driven growth without making the portfolio feel like a plain CV.</p>
        </div>
        <div class="story-grid">
          <article class="story-card reveal">
            <h3>Frontend foundation</h3>
            <p class="muted">Built confidence through repeated layout work, Bootstrap customization, structure cleanup, and learning what makes a page feel finished.</p>
          </article>
          <article class="story-card reveal">
            <h3>Operational perspective</h3>
            <p class="muted">Real work environments added practical awareness of processes, systems, friction points, and the value of tools that save time.</p>
          </article>
          <article class="story-card reveal">
            <h3>Security curiosity</h3>
            <p class="muted">Ongoing interest in testing, WordPress behavior, Linux usage, and understanding systems beyond the visible interface.</p>
          </article>
          <article class="story-card reveal">
            <h3>Next phase</h3>
            <p class="muted">Publish stronger public projects, document them better, and keep moving toward full-stack and security-focused work.</p>
          </article>
        </div>
      </div>
    </section>

    <section class="section" id="contact">
      <div class="container contact-grid">
        <div class="section-head reveal">
          <span class="eyebrow" style="border-color: rgba(167,139,250,0.22); color: #c7b8ff;">Contact</span>
          <h2 class="section-title">Open to internships, collaboration, and useful projects.</h2>
          <p class="section-copy">This page stays static and GitHub Pages friendly, which matches your preference for simple, low-cost portfolio hosting. [cite:21][cite:1]</p>
        </div>
        <div class="contact-panel reveal">
          <h3 style="font-family:var(--font-display); font-size:var(--text-xl); line-height:1; letter-spacing:-0.04em;">Replace with your real links</h3>
          <p class="muted">Update these placeholders before publishing so the portfolio points to your actual profile, email, CV, and best repositories.</p>
          <div class="contact-links">
            <a href="https://github.com/yourusername" target="_blank" rel="noopener noreferrer"><span>GitHub</span><span>github.com/yourusername</span></a>
            <a href="https://linkedin.com/in/yourusername" target="_blank" rel="noopener noreferrer"><span>LinkedIn</span><span>linkedin.com/in/yourusername</span></a>
            <a href="mailto:you@example.com"><span>Email</span><span>you@example.com</span></a>
          </div>
          <a href="#top" class="pill-btn" style="width:fit-content;">Back to top</a>
        </div>
      </div>
    </section>
  </main>

  <footer class="footer">
    <div class="container footer-inner">
      <p>Version 2 · sharper editorial dark design</p>
      <p>Built as static HTML for easy GitHub Pages deployment</p>
    </div>
  </footer>

  <script>
    (() => {
      const root = document.documentElement;
      const toggle = document.querySelector('[data-theme-toggle]');
      let theme = 'dark';
      root.setAttribute('data-theme', theme);
      const setIcon = () => {
        toggle.innerHTML = theme === 'dark'
          ? '<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true"><circle cx="12" cy="12" r="5"></circle><path d="M12 1v2M12 21v2M4.22 4.22l1.42 1.42M18.36 18.36l1.42 1.42M1 12h2M21 12h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42"></path></svg>'
          : '<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path></svg>';
        toggle.setAttribute('aria-label', `Switch to ${theme === 'dark' ? 'light' : 'dark'} theme`);
      };
      const lightVars = {
        '--color-bg':'#f4f1ea','--color-surface':'#f8f5ef','--color-surface-2':'#eee8de','--color-surface-offset':'#e4ddd2',
        '--color-border':'rgba(30,34,36,0.10)','--color-divider':'rgba(30,34,36,0.08)','--color-text':'#161817','--color-text-muted':'#636963','--color-text-faint':'#94988f',
        '--color-text-inverse':'#f4f1ea','--color-primary':'#0c6b61','--color-primary-2':'#16638e','--color-primary-dim':'rgba(12,107,97,0.10)','--color-purple':'#7c5ce0','--color-purple-dim':'rgba(124,92,224,0.10)'
      };
      const darkVars = {
        '--color-bg':'#0b0d0e','--color-surface':'#101416','--color-surface-2':'#151a1d','--color-surface-offset':'#1c2327',
        '--color-border':'rgba(228,236,240,0.10)','--color-divider':'rgba(228,236,240,0.08)','--color-text':'#eef2f3','--color-text-muted':'#a4afb5','--color-text-faint':'#6f7a80',
        '--color-text-inverse':'#0b0d0e','--color-primary':'#a78bfa','--color-primary-2':'#70d6ff','--color-primary-dim':'rgba(167,139,250,0.12)','--color-purple':'#a78bfa','--color-purple-dim':'rgba(167,139,250,0.12)'
      };
      const applyTheme = vars => Object.entries(vars).forEach(([k,v]) => root.style.setProperty(k,v));
      applyTheme(darkVars); setIcon();
      toggle.addEventListener('click', () => {
        theme = theme === 'dark' ? 'light' : 'dark';
        root.setAttribute('data-theme', theme);
        applyTheme(theme === 'dark' ? darkVars : lightVars);
        setIcon();
      });

      const reveals = document.querySelectorAll('.reveal');
      if ('IntersectionObserver' in window) {
        const obs = new IntersectionObserver((entries) => {
          entries.forEach(entry => {
            if (entry.isIntersecting) {
              entry.target.classList.add('visible');
              obs.unobserve(entry.target);
            }
          });
        }, { threshold: 0.12 });
        reveals.forEach(el => obs.observe(el));
      } else {
        reveals.forEach(el => el.classList.add('visible'));
      }

      const sections = [...document.querySelectorAll('main section[id]')];
      const links = [...document.querySelectorAll('.nav a')];
      const highlight = () => {
        const pos = window.scrollY + 150;
        let current = sections[0]?.id;
        sections.forEach(section => { if (pos >= section.offsetTop) current = section.id; });
        links.forEach(link => link.classList.toggle('active', link.getAttribute('href') === `#${current}`));
      };
      highlight();
      window.addEventListener('scroll', highlight, { passive: true });
    })();
  </script>
</body>
</html>
