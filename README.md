<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Suraj Bhosale — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --bg: #0a0e1a; --bg2: #0f1420; --bg3: #141927; --card: #161c2e;
    --border: rgba(99,140,255,0.15); --border-glow: rgba(99,140,255,0.4);
    --accent: #638cff; --accent2: #a78bfa; --accent3: #34d399;
    --text: #e8ecf4; --muted: #7b88a8; --muted2: #4a5568;
  }
  html { scroll-behavior: smooth; }
  body { font-family: 'Syne', sans-serif; background: var(--bg); color: var(--text); min-height: 100vh; overflow-x: hidden; }

  body::before {
    content: ''; position: fixed; inset: 0;
    background-image: linear-gradient(rgba(99,140,255,0.04) 1px, transparent 1px), linear-gradient(90deg, rgba(99,140,255,0.04) 1px, transparent 1px);
    background-size: 48px 48px; z-index: 0; animation: gridPulse 8s ease-in-out infinite;
  }
  @keyframes gridPulse { 0%,100%{opacity:.5} 50%{opacity:1} }

  .orb { position: fixed; border-radius: 50%; filter: blur(80px); z-index: 0; pointer-events: none; animation: orbFloat 12s ease-in-out infinite; }
  .orb1 { width:500px;height:500px;background:rgba(99,140,255,0.12);top:-200px;right:-100px; }
  .orb2 { width:400px;height:400px;background:rgba(167,139,250,0.1);bottom:-150px;left:-100px;animation-delay:-4s; }
  .orb3 { width:300px;height:300px;background:rgba(52,211,153,0.08);top:40%;left:40%;animation-delay:-8s; }
  @keyframes orbFloat { 0%,100%{transform:translate(0,0) scale(1)} 33%{transform:translate(30px,-30px) scale(1.05)} 66%{transform:translate(-20px,20px) scale(.95)} }

  .container { position: relative; z-index: 1; max-width: 860px; margin: 0 auto; padding: 60px 24px 80px; }

  @keyframes revealUp { to { opacity:1; transform:translateY(0); } }

  /* HERO */
  .hero { text-align: center; padding: 20px 0 60px; }
  .avatar-wrap { display:inline-block; position:relative; margin-bottom:28px; animation: revealUp .7s .1s cubic-bezier(.22,1,.36,1) both; opacity:0; transform:translateY(32px); }
  .avatar { width:120px;height:120px;border-radius:50%;background:linear-gradient(135deg,var(--accent),var(--accent2));display:flex;align-items:center;justify-content:center;font-size:42px;font-weight:800;color:#fff;border:3px solid var(--border-glow);box-shadow:0 0 40px rgba(99,140,255,.3);animation:avatarPulse 3s ease-in-out infinite; }
  @keyframes avatarPulse { 0%,100%{box-shadow:0 0 40px rgba(99,140,255,.3)} 50%{box-shadow:0 0 70px rgba(99,140,255,.5)} }
  .online-dot { position:absolute;bottom:6px;right:6px;width:18px;height:18px;background:var(--accent3);border-radius:50%;border:3px solid var(--bg);animation:dotPulse 2s ease-in-out infinite; }
  @keyframes dotPulse { 0%,100%{box-shadow:0 0 0 0 rgba(52,211,153,.4)} 50%{box-shadow:0 0 0 6px rgba(52,211,153,0)} }

  .hero-name { font-size:clamp(36px,6vw,60px);font-weight:800;letter-spacing:-1.5px;line-height:1.1;background:linear-gradient(135deg,#fff 0%,var(--accent) 50%,var(--accent2) 100%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;margin-bottom:12px;animation:revealUp .7s .2s cubic-bezier(.22,1,.36,1) both;opacity:0;transform:translateY(32px); }
  .hero-title { font-size:18px;color:var(--muted);font-weight:400;margin-bottom:24px;animation:revealUp .7s .3s cubic-bezier(.22,1,.36,1) both;opacity:0;transform:translateY(32px); }
  .hero-title span { color:var(--accent);font-weight:600; }
  .cursor { display:inline-block;width:2px;height:1em;background:var(--accent);vertical-align:text-bottom;margin-left:2px;animation:blink 1s step-end infinite; }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  .contact-row { display:flex;flex-wrap:wrap;gap:10px;justify-content:center;margin-bottom:32px;animation:revealUp .7s .4s cubic-bezier(.22,1,.36,1) both;opacity:0;transform:translateY(32px); }
  .contact-pill { display:inline-flex;align-items:center;gap:7px;padding:7px 16px;border-radius:100px;background:var(--card);border:1px solid var(--border);font-size:13px;color:var(--muted);text-decoration:none;transition:all .25s ease;font-family:'DM Mono',monospace; }
  .contact-pill:hover { border-color:var(--border-glow);color:var(--text);background:rgba(99,140,255,.1);transform:translateY(-2px);box-shadow:0 8px 24px rgba(99,140,255,.15); }
  .contact-pill svg { width:14px;height:14px;flex-shrink:0; }

  .stats-row { display:flex;flex-wrap:wrap;gap:12px;justify-content:center;animation:revealUp .7s .5s cubic-bezier(.22,1,.36,1) both;opacity:0;transform:translateY(32px); }
  .stat-card { background:var(--card);border:1px solid var(--border);border-radius:16px;padding:16px 24px;text-align:center;min-width:110px;transition:all .25s ease; }
  .stat-card:hover { border-color:var(--border-glow);transform:translateY(-3px);box-shadow:0 12px 30px rgba(99,140,255,.12); }
  .stat-num { font-size:28px;font-weight:800;background:linear-gradient(135deg,var(--accent),var(--accent2));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;line-height:1;margin-bottom:4px; }
  .stat-label { font-size:11px;color:var(--muted);text-transform:uppercase;letter-spacing:.08em;font-family:'DM Mono',monospace; }

  /* SECTIONS */
  .section { margin-top:64px;opacity:0;transform:translateY(32px);transition:opacity .7s ease,transform .7s ease; }
  .section.visible { opacity:1;transform:translateY(0); }
  .section-label { display:flex;align-items:center;gap:12px;font-size:12px;font-weight:600;color:var(--accent);text-transform:uppercase;letter-spacing:.15em;font-family:'DM Mono',monospace;margin-bottom:24px; }
  .section-label::after { content:'';flex:1;height:1px;background:linear-gradient(90deg,var(--border-glow),transparent); }

  /* ABOUT */
  .about-card { background:var(--card);border:1px solid var(--border);border-radius:20px;padding:28px 32px;position:relative;overflow:hidden;transition:border-color .3s; }
  .about-card::before { content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--accent),var(--accent2),var(--accent3));border-radius:20px 20px 0 0; }
  .about-card:hover { border-color:var(--border-glow); }
  .about-grid { display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:16px;margin-top:20px; }
  .about-item { display:flex;align-items:flex-start;gap:12px;padding:12px;border-radius:12px;background:rgba(99,140,255,.04);border:1px solid rgba(99,140,255,.08);transition:all .2s; }
  .about-item:hover { background:rgba(99,140,255,.08);border-color:var(--border);transform:translateX(4px); }
  .about-icon { font-size:20px;flex-shrink:0;margin-top:2px; }
  .about-text { font-size:14px;color:var(--muted);line-height:1.5; }
  .about-text strong { color:var(--text);font-weight:600;display:block;font-size:13px;margin-bottom:2px; }

  /* TECH STACK */
  .tech-groups { display:flex;flex-direction:column;gap:24px; }
  .tech-group-name { font-size:12px;color:var(--muted2);font-family:'DM Mono',monospace;text-transform:uppercase;letter-spacing:.1em;margin-bottom:12px; }
  .tech-pills { display:flex;flex-wrap:wrap;gap:8px; }

  .tech-pill {
    display:inline-flex;align-items:center;gap:8px;padding:8px 14px;border-radius:10px;
    background:var(--card);border:1px solid var(--border);font-size:13px;font-weight:600;
    color:var(--text);cursor:default;transition:all .25s ease;
  }
  .tech-pill:hover { transform:translateY(-3px) scale(1.03);border-color:var(--border-glow);box-shadow:0 8px 20px rgba(0,0,0,.3); }
  .tech-pill img { width:18px;height:18px;object-fit:contain;flex-shrink:0; }
  .tech-pill .logo-svg { width:18px;height:18px;flex-shrink:0;display:flex;align-items:center;justify-content:center; }
  .tech-pill .logo-svg svg { width:18px;height:18px; }

  /* PROJECTS */
  .projects-grid { display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:16px; }
  .project-card { background:var(--card);border:1px solid var(--border);border-radius:20px;padding:24px;position:relative;overflow:hidden;transition:all .3s ease; }
  .project-card::after { content:'';position:absolute;inset:0;border-radius:20px;background:linear-gradient(135deg,rgba(99,140,255,.05),rgba(167,139,250,.05));opacity:0;transition:opacity .3s; }
  .project-card:hover { border-color:var(--border-glow);transform:translateY(-6px);box-shadow:0 20px 48px rgba(0,0,0,.4),0 0 0 1px rgba(99,140,255,.2); }
  .project-card:hover::after { opacity:1; }
  .project-icon { width:44px;height:44px;border-radius:12px;display:flex;align-items:center;justify-content:center;font-size:22px;margin-bottom:16px;position:relative;z-index:1; }
  .project-name { font-size:16px;font-weight:700;color:var(--text);margin-bottom:8px;position:relative;z-index:1; }
  .project-desc { font-size:13px;color:var(--muted);line-height:1.6;margin-bottom:16px;position:relative;z-index:1; }
  .project-metrics { display:flex;gap:8px;flex-wrap:wrap;margin-bottom:16px;position:relative;z-index:1; }
  .metric-badge { padding:3px 10px;border-radius:100px;font-size:12px;font-weight:600;font-family:'DM Mono',monospace; }
  .metric-green { background:rgba(52,211,153,.12);color:#34d399;border:1px solid rgba(52,211,153,.2); }
  .metric-blue { background:rgba(99,140,255,.12);color:#638cff;border:1px solid rgba(99,140,255,.2); }
  .metric-amber { background:rgba(251,191,36,.12);color:#fbbf24;border:1px solid rgba(251,191,36,.2); }
  .project-tags { display:flex;flex-wrap:wrap;gap:6px;position:relative;z-index:1; }
  .project-tag { font-size:11px;color:var(--muted2);background:var(--bg3);padding:3px 8px;border-radius:6px;font-family:'DM Mono',monospace; }

  /* LEARNING */
  .learning-card { background:var(--card);border:1px solid var(--border);border-radius:20px;padding:24px 28px;display:flex;align-items:center;gap:20px;transition:all .3s; }
  .learning-card:hover { border-color:var(--border-glow); }
  .learning-icon-wrap { width:52px;height:52px;border-radius:14px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:linear-gradient(135deg,rgba(99,140,255,.15),rgba(167,139,250,.15));border:1px solid var(--border);animation:spinSlow 8s linear infinite; }
  @keyframes spinSlow { from{transform:rotate(0deg)} to{transform:rotate(360deg)} }
  .learning-title { font-size:15px;font-weight:700;margin-bottom:6px; }
  .learning-list { font-size:13px;color:var(--muted);line-height:1.8; }
  .learning-list span { color:var(--accent);font-weight:600; }

  /* FUN */
  .fun-card { background:linear-gradient(135deg,rgba(99,140,255,.08),rgba(167,139,250,.08));border:1px solid rgba(99,140,255,.2);border-radius:20px;padding:28px 32px;text-align:center;position:relative;overflow:hidden; }
  .fun-card::before { content:'⚡';position:absolute;font-size:120px;opacity:.04;top:-20px;right:-20px;transform:rotate(15deg); }
  .fun-quote { font-size:16px;line-height:1.7;color:var(--text);font-style:italic;max-width:600px;margin:0 auto; }
  .fun-quote em { color:var(--accent);font-style:normal;font-weight:700; }

  .footer { margin-top:60px;text-align:center;font-size:13px;color:var(--muted2);font-family:'DM Mono',monospace;padding-bottom:20px; }
  .footer span { color:var(--accent); }

  @media (prefers-reduced-motion: reduce) {
    .section{opacity:1;transform:none} .orb{animation:none} body::before{animation:none}
    .avatar{animation:none} .online-dot{animation:none} .learning-icon-wrap{animation:none}
  }
</style>
</head>
<body>

<div class="orb orb1"></div>
<div class="orb orb2"></div>
<div class="orb orb3"></div>

<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="avatar-wrap">
      <div class="avatar">SB</div>
      <div class="online-dot"></div>
    </div>
    <h1 class="hero-name">Suraj Bhosale</h1>
    <p class="hero-title">
      <span id="typed-text">Java Backend Developer</span><span class="cursor"></span>
    </p>
    <div class="contact-row">
      <a href="mailto:dev.surajbhosale@gmail.com" class="contact-pill">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-10 7L2 7"/></svg>
        dev.surajbhosale@gmail.com
      </a>
      <a href="#" class="contact-pill">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.5 2h-17A1.5 1.5 0 002 3.5v17A1.5 1.5 0 003.5 22h17a1.5 1.5 0 001.5-1.5v-17A1.5 1.5 0 0020.5 2zM8 19H5v-9h3zM6.5 8.25A1.75 1.75 0 118.3 6.5a1.78 1.78 0 01-1.8 1.75zM19 19h-3v-4.74c0-1.42-.6-1.93-1.38-1.93A1.74 1.74 0 0013 14.19V19h-3v-9h2.9v1.3a3.11 3.11 0 012.7-1.4c1.55 0 3.36.86 3.36 3.66z"/></svg>
        LinkedIn
      </a>
      <a href="#" class="contact-pill">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2A10 10 0 002 12c0 4.42 2.87 8.17 6.84 9.5.5.08.66-.23.66-.5v-1.69c-2.77.6-3.36-1.34-3.36-1.34-.46-1.16-1.11-1.47-1.11-1.47-.91-.62.07-.6.07-.6 1 .07 1.53 1.03 1.53 1.03.87 1.52 2.34 1.07 2.91.83.09-.65.35-1.09.63-1.34-2.22-.25-4.55-1.11-4.55-4.92 0-1.11.38-2 1.03-2.71-.1-.25-.45-1.29.1-2.64 0 0 .84-.27 2.75 1.02.79-.22 1.65-.33 2.5-.33.85 0 1.71.11 2.5.33 1.91-1.29 2.75-1.02 2.75-1.02.55 1.35.2 2.39.1 2.64.65.71 1.03 1.6 1.03 2.71 0 3.82-2.34 4.66-4.57 4.91.36.31.69.92.69 1.85V21c0 .27.16.59.67.5C19.14 20.16 22 16.42 22 12A10 10 0 0012 2z"/></svg>
        GitHub
      </a>
      <span class="contact-pill">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
        Pune, India
      </span>
    </div>
    <div class="stats-row">
      <div class="stat-card"><div class="stat-num" id="s1">4+</div><div class="stat-label">Years Exp</div></div>
      <div class="stat-card"><div class="stat-num" id="s2">3</div><div class="stat-label">Projects</div></div>
      <div class="stat-card"><div class="stat-num" id="s3">30%</div><div class="stat-label">API Boost</div></div>
      <div class="stat-card"><div class="stat-num" id="s4">25%</div><div class="stat-label">Defect Drop</div></div>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="section" id="s-about">
    <div class="section-label">About me</div>
    <div class="about-card">
      <p style="font-size:15px;color:var(--muted);line-height:1.8;">
        Java Developer at <strong style="color:var(--text)">Cognizant</strong> with <strong style="color:var(--accent)">4 years</strong> of experience building enterprise-grade banking applications. I care about clean architecture, observable systems, and shipping code that actually works in production. Currently levelling up on <strong style="color:var(--accent)">Azure DevOps</strong> and cloud-native patterns.
      </p>
      <div class="about-grid">
        <div class="about-item"><div class="about-icon">🏦</div><div class="about-text"><strong>Banking Domain</strong>Core Banking & Deposits, event-driven microservices</div></div>
        <div class="about-item"><div class="about-icon">☁️</div><div class="about-text"><strong>Cloud Upskilling</strong>Azure DevOps, Key Vault, Managed Identity</div></div>
        <div class="about-item"><div class="about-icon">⚡</div><div class="about-text"><strong>Performance Focus</strong>Redis caching, optimized queries, exception handling</div></div>
        <div class="about-item"><div class="about-icon">🤖</div><div class="about-text"><strong>AI-Aware</strong>Tracking how AI reshapes software engineering careers</div></div>
      </div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section" id="s-stack">
    <div class="section-label">Tech stack</div>
    <div class="tech-groups">

      <div class="tech-group">
        <div class="tech-group-name">Backend</div>
        <div class="tech-pills">
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#f89820"><path d="M8.851 18.56s-.917.534.653.714c1.902.218 2.874.187 4.969-.211 0 0 .552.346 1.321.646-4.699 2.013-10.633-.118-6.943-1.149M8.276 15.933s-1.028.761.542.924c2.032.209 3.636.227 6.413-.308 0 0 .384.389.987.602-5.679 1.661-12.007.13-7.942-1.218M13.116 11.475c1.158 1.333-.304 2.533-.304 2.533s2.939-1.518 1.589-3.418c-1.261-1.772-2.228-2.652 3.007-5.688 0 0-8.216 2.051-4.292 6.573M19.33 20.504s.679.559-.747.991c-2.712.822-11.288 1.069-13.669.033-.856-.373.75-.89 1.254-.998.527-.114.828-.093.828-.093-.953-.671-6.156 1.317-2.643 1.887 9.58 1.553 17.462-.7 14.977-1.82M9.292 13.21s-4.362 1.036-1.544 1.412c1.189.159 3.561.123 5.77-.062 1.806-.152 3.618-.477 3.618-.477s-.637.272-1.098.587c-4.429 1.165-12.986.623-10.522-.568 2.082-1.006 3.776-.892 3.776-.892M17.116 17.584c4.503-2.34 2.421-4.589.968-4.285-.355.074-.515.138-.515.138s.132-.207.385-.297c2.875-1.011 5.086 2.981-.928 4.562 0-.001.07-.062.09-.118M14.401 0s2.494 2.494-2.365 6.33c-3.896 3.077-.888 4.832-.001 6.836-2.274-2.053-3.943-3.858-2.824-5.539 1.644-2.469 6.197-3.665 5.19-7.627M9.734 23.924c4.322.277 10.959-.153 11.116-2.19 0 0-.302.775-3.572 1.391-3.688.694-8.239.613-10.937.168 0-.001.553.457 3.393.631"/></svg></span>
            Java
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#6db33f"><path d="M20.205 16.392c-2.469 3.289-7.741 2.179-11.122 2.338 0 0-.599.034-1.201.133 0 0 .228-.097.519-.198 2.374-.821 3.496-.986 4.939-1.727 2.71-1.388 5.408-4.413 5.957-7.555-1.032 3.022-4.17 5.623-7.027 6.679-1.955.722-5.492 1.424-5.493 1.424a5.28 5.28 0 01-.143-.076C5.004 16.96 4.802 13.93 7.439 12.3c1.139-.695 2.24-.301 3.478-.777 1.322-.508 2.803-2.492 2.803-2.492s-4.344 1.254-6.14 2.95c-1.498 1.399-2.031 4.143-.532 5.812-.805-.438-1.664-1.133-2.283-2.026-3.014-4.34 1.643-10.867 7.556-10.8 2.98.034 6.124 1.261 7.891 3.485 1.521 1.919 1.72 4.399.993 5.94z"/></svg></span>
            Spring Boot
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#6db33f"><path d="M20.205 16.392c-2.469 3.289-7.741 2.179-11.122 2.338 0 0-.599.034-1.201.133 0 0 .228-.097.519-.198 2.374-.821 3.496-.986 4.939-1.727 2.71-1.388 5.408-4.413 5.957-7.555-1.032 3.022-4.17 5.623-7.027 6.679-1.955.722-5.492 1.424-5.493 1.424a5.28 5.28 0 01-.143-.076C5.004 16.96 4.802 13.93 7.439 12.3c1.139-.695 2.24-.301 3.478-.777 1.322-.508 2.803-2.492 2.803-2.492s-4.344 1.254-6.14 2.95c-1.498 1.399-2.031 4.143-.532 5.812-.805-.438-1.664-1.133-2.283-2.026-3.014-4.34 1.643-10.867 7.556-10.8 2.98.034 6.124 1.261 7.891 3.485 1.521 1.919 1.72 4.399.993 5.94z"/></svg></span>
            Spring Cloud
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24"><path fill="#231F20" d="M1.539 12.006l.003-.023 2.812-5.001 2.851 5.112-2.851 5.097-2.815-5.185zm9.8 5.165l-2.85-5.097 2.85-5.112 2.813 5.001-2.813 5.208zm-1.277 2.274L7.21 24 4.35 18.903l2.86-5.113 2.852 5.113v.542zm2.554 0v-.542l2.853-5.113 2.859 5.113L15.476 24l-2.86-4.555zm4.13-7.439l2.851-5.112 2.813 5.001-.003.023-2.815 5.185-2.847-5.097z"/><path fill="#231F20" d="M10.062 4.555V5.1L7.21 10.211 4.35 5.099 7.21 0l2.852 4.555zm4.132 0L17.046 0l2.86 5.097-2.86 5.114-2.852-5.114v-.542zm-2.554-.003L8.788 0H15.2l-2.852 2.272-.001.001-1.207.818v1.461z"/></svg></span>
            Apache Kafka
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24"><path fill="#59666C" d="M19.389.119L13.7 5.789c1.471 1.453.89 3.428-.593 4.259-.3.168-.622.275-.936.349L9.642 13.02c.099.2.168.412.207.634l1.74 1.728 1.94-1.93 1.93 1.938-1.93 1.929 1.211 1.207-1.938 1.93-2.147-2.13c-.236.051-.483.066-.73.045l-2.3 2.29c.059.203.087.416.082.634a2.576 2.576 0 01-2.623 2.51 2.576 2.576 0 01-2.51-2.623 2.576 2.576 0 012.623-2.51c.172.003.341.026.503.069l2.297-2.285a2.576 2.576 0 01.349-2.73L6.682 12.5a2.571 2.571 0 01-2.074.32 2.576 2.576 0 01-1.814-3.143 2.576 2.576 0 013.143-1.814 2.574 2.574 0 011.578 1.271l2.62-2.604A2.576 2.576 0 0112.5 4.024a2.58 2.58 0 011.07.232L18.23.595l1.16-.476z"/></svg></span>
            Hibernate / JPA
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#DC382D"><path d="M10.29 0a.1.1 0 00-.073.032C9.89.358 7.294 3.44 7.294 6.66c0 2.35 1.442 4.263 3.48 5.25a.1.1 0 00.046.011.1.1 0 00.1-.1V6.659C10.92 3.44 10.624.358 10.363.032A.1.1 0 0010.29 0zM6.765 2.388a.1.1 0 00-.068.025C5.13 3.785 3.77 5.92 3.77 8.217c0 2.63 1.666 4.88 4.035 5.74a.1.1 0 00.07 0 .1.1 0 00.066-.093V8.217a7.61 7.61 0 00-1.108-4.015 5.97 5.97 0 00-.073-.1 .1.1 0 00-.063-.025 .1.1 0 00-.068.025-.068.025 0 00.068-.025zm7.07.006a.1.1 0 00-.056.017.1.1 0 00-.027.025 5.97 5.97 0 00-.073.1 7.61 7.61 0 00-1.108 4.015v5.647a.1.1 0 00.066.093.1.1 0 00.07 0c2.369-.86 4.035-3.11 4.035-5.74 0-2.297-1.36-4.432-2.927-5.804a.1.1 0 00-.068-.025 .1.1 0 00-.068.025.068.025 0 00.068-.025zM10.29 13.58a.1.1 0 00-.046.011c-2.038.987-3.48 2.9-3.48 5.25 0 3.22 2.596 6.302 2.923 6.628a.1.1 0 00.073.032.1.1 0 00.073-.032c.327-.326 2.923-3.408 2.923-6.628 0-2.35-1.442-4.263-3.48-5.25a.1.1 0 00-.046-.011z"/></svg></span>
            Redis
          </div>
        </div>
      </div>

      <div class="tech-group">
        <div class="tech-group-name">Frontend</div>
        <div class="tech-pills">
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#DD0031"><path d="M9.931 12.645h4.138l-2.07-4.908m0-7.737L.68 3.982l1.726 14.771L12 24l9.596-5.242L23.32 3.982 11.999.0zm7.064 18.31h-2.638l-1.422-3.503H8.996l-1.422 3.504h-2.64L12 2.65z"/></svg></span>
            Angular 17
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#3178C6"><path d="M1.125 0C.502 0 0 .502 0 1.125v21.75C0 23.498.502 24 1.125 24h21.75c.623 0 1.125-.502 1.125-1.125V1.125C24 .502 23.498 0 22.875 0zm17.363 9.75c.612 0 1.154.037 1.627.111a6.38 6.38 0 0 1 1.306.34v2.458a3.95 3.95 0 0 0-.643-.361 5.093 5.093 0 0 0-.717-.26 5.453 5.453 0 0 0-1.426-.2c-.3 0-.573.028-.819.086a2.1 2.1 0 0 0-.623.242c-.17.104-.3.229-.393.374a.888.888 0 0 0-.14.49c0 .196.053.373.156.529.104.156.252.304.443.444s.423.276.696.41c.273.135.582.274.926.416.47.197.892.407 1.266.628.374.222.695.473.963.753.268.279.472.598.614.957.142.359.214.776.214 1.253 0 .657-.125 1.21-.373 1.656a3.033 3.033 0 0 1-1.012 1.085 4.38 4.38 0 0 1-1.487.596c-.566.12-1.163.18-1.79.18a9.916 9.916 0 0 1-1.84-.164 5.544 5.544 0 0 1-1.512-.493v-2.63a5.033 5.033 0 0 0 3.237 1.2c.333 0 .624-.03.872-.09.249-.06.456-.144.623-.25.166-.108.29-.234.373-.38a1.023 1.023 0 0 0-.074-1.089 2.12 2.12 0 0 0-.537-.5 5.597 5.597 0 0 0-.807-.444 27.72 27.72 0 0 0-1.007-.436c-.918-.383-1.602-.852-2.053-1.405-.45-.553-.676-1.222-.676-2.005 0-.614.123-1.141.369-1.582.246-.441.58-.804 1.004-1.089a4.494 4.494 0 0 1 1.47-.629 7.536 7.536 0 0 1 1.77-.201zm-15.113.188h9.563v2.166H9.506v9.646H6.789v-9.646H3.375z"/></svg></span>
            TypeScript
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#B7178C"><path d="M12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm-.64 3.336c.306 0 .608.032.897.09v4.606l-1.788-3.094a7.104 7.104 0 0 0-.891.521L11.36 3.37c0-.023-.001-.023 0-.034zm1.28 0v.002c.306.01.608.04.897.09v4.605l1.788-3.095a7.116 7.116 0 0 0-.891-.521L12.64 3.338zm-2.527.534l2.884 4.996-5.768.002a7.12 7.12 0 0 0-.185 1.02l3.069-5.316zm3.774 0L12 9.87H6.232a7.03 7.03 0 0 0-.185 1.02l3.069-5.316 2.884-4.996zM5.857 8.39l3.069 5.317H2.893a7.12 7.12 0 0 0 .185 1.02l2.779-4.813zm12.286 0L20 13.707a7.12 7.12 0 0 0 .186-1.02h-6.033l3.069-5.316zm.928 5.317l-2.779 4.813a7.12 7.12 0 0 0 .891-.522l1.888-3.27zm-14.142 0L5.817 17a7.12 7.12 0 0 0 .891.522l-2.779-4.814zm12.886.002h-5.769l2.884 4.995a7.116 7.116 0 0 0 .891-.52l2.186-3.785c-.066-.228-.12-.459-.192-.69zm-11.629 0c-.072.231-.126.462-.192.69L8.38 17.904a7.104 7.104 0 0 0 .891.52l2.884-4.995H6.186zM9.97 17.076l1.788 3.095c.306.01.608.022.897.022.306 0 .608-.01.897-.022l1.788-3.095-2.685-.001zm1.03.964l-.897 1.554a7.12 7.12 0 0 0 .897.09v-1.644zm1.28 0v1.644a7.12 7.12 0 0 0 .897-.09l-.897-1.554z"/></svg></span>
            RxJS
          </div>
        </div>
      </div>

      <div class="tech-group">
        <div class="tech-group-name">Databases</div>
        <div class="tech-pills">
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#F80000"><path d="M12 2C6.477 2 2 6.477 2 12s4.477 10 10 10 10-4.477 10-10S17.523 2 12 2zm0 1.5c4.687 0 8.5 3.813 8.5 8.5s-3.813 8.5-8.5 8.5S3.5 16.687 3.5 12 7.313 3.5 12 3.5zm0 2.5a6 6 0 100 12A6 6 0 0012 6zm0 2a4 4 0 110 8 4 4 0 010-8z"/></svg></span>
            Oracle
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#336791"><path d="M23.5454 11.9048c-.3806-3.3948-3.2567-6.0022-6.5899-6.5899-.3806-.0953-1.1418-.1906-1.6271-.1906H5.1807C2.3046 5.1243.018 7.4109.018 10.287v8.354c0 2.8761 2.2866 5.1627 5.1627 5.1627h8.4493c2.8761 0 5.1627-2.2866 5.1627-5.1627v-1.5224c2.5121-.4806 4.5138-2.4823 4.9944-4.9944.0953-.4806.0953-.9612.0953-1.4418v-.859c-.2853-.1906-.2853-.5712-.2853-.8566zm-1.2371.3806c0 .2853 0 .5706-.0953.8559-.3806 2.3819-2.4776 4.1942-4.9897 4.1942-2.7808 0-4.9897-2.2089-4.9897-4.9897s2.2089-4.9897 4.9897-4.9897c2.4168 0 4.4185 1.7171 4.8991 3.9942.0953.3806.0953.6659.0953.9512h-.905zM5.1807 6.0795h10.0791c.3806 0 .8612.0953 1.2418.1906 2.7855.5706 4.8825 2.9574 4.8825 5.8335v.4806c-.1906-.0953-.3806-.0953-.6659-.0953h-.5706v-.4806c0-2.5121-2.0017-4.5138-4.5138-4.5138H5.1807c-2.5121 0-4.5138 2.0017-4.5138 4.5138v8.354c0 2.5121 2.0017 4.5138 4.5138 4.5138h8.4493c2.5121 0 4.5138-2.0017 4.5138-4.5138v-1.5224h.5706c.2853 0 .5706 0 .8559.0953v1.427c0 3.2567-2.6074 5.9594-5.9594 5.9594H5.1807C1.9241 21.8056-.018 19.0029-.018 15.7462V10.287c0-2.3819 1.4271-4.4789 3.5241-5.4354.5706-.2853 1.1412-.4759 1.7118-.5706l.5706-.0953h-.5706z"/></svg></span>
            PostgreSQL
          </div>
        </div>
      </div>

      <div class="tech-group">
        <div class="tech-group-name">Cloud & DevOps</div>
        <div class="tech-pills">
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#0078D7"><path d="M0 0v11.408l2.656 2.65V2.656L11.408 0zm12.594 0l-4.25 4.25 2.65 2.65 4.25-4.25zm7.75 0l-9.994 9.994 2.65 2.65L24 2.656V0zm3.656 12.594L22.344 11.41l-2.65 2.65 1.906 1.906zM0 12.594v1.906l2.656-2.65V9.94zm10.9 1.056L0 24h9.406l8.594-8.6zm2.5 2.5L5.8 24h9.4l8.8-8.8z"/></svg></span>
            Azure DevOps
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#0078D4"><path d="M13.05 4.24L6.56 8.95l-4.4-.8L0 10.14l4.91 3.57v.01l1.32.96 4.58-1.02 5.37 1.03L24 10.14l-2.16-1.99-4.07.86zM1.75 14.97l1.17 4.66 5.22-3.53-4.83-2.36zm20.5 0l-1.56-1.23-4.82 2.36 5.21 3.53zm-10.25.73l-4.97 1.11 4.97 3.02 4.97-3.02z"/></svg></span>
            Azure
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#F05032"><path d="M23.546 10.93L13.067.452c-.604-.603-1.582-.603-2.188 0L8.708 2.627l2.76 2.76c.645-.215 1.379-.07 1.889.441.516.515.658 1.258.438 1.9l2.658 2.66c.645-.223 1.387-.078 1.9.435.721.72.721 1.884 0 2.604-.719.719-1.881.719-2.6 0-.539-.541-.674-1.337-.404-1.996L12.86 8.955v6.525c.176.086.342.203.488.348.713.721.713 1.883 0 2.6-.719.721-1.889.721-2.609 0-.719-.719-.719-1.879 0-2.598.182-.18.387-.316.605-.406V8.835c-.217-.091-.424-.222-.6-.401-.545-.545-.676-1.342-.396-2.009L7.636 3.7.45 10.881c-.6.605-.6 1.584 0 2.189l10.48 10.477c.604.604 1.582.604 2.186 0l10.43-10.43c.605-.603.605-1.582 0-2.187"/></svg></span>
            Git
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#C71A36"><path d="M9.37 3.375H4.656L.844 12h2.438l.703-1.781h4.781L9.47 12h2.438zm-5.11 5.062l1.39-3.515 1.39 3.515zm13.657-5.062h-2.25V12h2.25V3.375zM23.156 3.375h-4.688V12h4.688v-2.062h-2.438V8.812h2.25V6.75h-2.25V5.437h2.438V3.375z"/></svg></span>
            Maven
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#C71A36"><path d="M.5 0h23v24H.5V0zm2 2v20h19V2H2.5zm2 2h15v2h-15V4zm0 4h15v2h-15V8zm0 4h10v2h-10v-2z"/></svg></span>
            Jira
          </div>
        </div>
      </div>

      <div class="tech-group">
        <div class="tech-group-name">Tools</div>
        <div class="tech-pills">
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24"><defs><linearGradient id="ij" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#FC801D"/><stop offset="100%" stop-color="#DE3F65"/></linearGradient></defs><path fill="url(#ij)" d="M0 0h24v24H0z"/><path fill="#fff" d="M7.2 15.6h9.6v1.2H7.2zm0-4.8h9.6v1.2H7.2zm0-4.8h4.8v1.2H7.2z"/></svg></span>
            IntelliJ IDEA
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#FF6C37"><path d="M23.01 11.87C23.01 5.31 17.7 0 11.14 0S-.73 5.31-.73 11.87c0 4.87 2.94 9.08 7.19 10.99v-1.87c-3.18-1.78-5.33-5.15-5.33-9.03 0-5.68 4.62-10.3 10.3-10.3s10.3 4.62 10.3 10.3c0 3.88-2.15 7.25-5.33 9.03v1.87c4.25-1.91 7.19-6.12 7.19-10.99zm-11.87 9.97V9.1l2.36 2.36 1.31-1.31-4.15-4.15L6.51 10.15l1.31 1.31 2.36-2.36v12.74c0 .74.6 1.34 1.34 1.34.74 0 1.34-.6 1.34-1.34h.28z"/></svg></span>
            Postman
          </div>
          <div class="tech-pill">
            <span class="logo-svg"><svg viewBox="0 0 24 24" fill="#0052CC"><path d="M11.571 11.513H0a5.218 5.218 0 0 0 5.232 5.215h2.13v2.057A5.215 5.215 0 0 0 12.575 24V12.518a1.005 1.005 0 0 0-1.004-1.005zm5.723-5.756H5.757a5.215 5.215 0 0 0 5.215 5.214h2.129v2.058a5.218 5.218 0 0 0 5.215 5.214V6.762a1.005 1.005 0 0 0-1.022-1.005zM23.013 0H11.459a5.215 5.215 0 0 0 5.215 5.215h2.129v2.057A5.215 5.215 0 0 0 24.018 12.5V1.005A1.005 1.005 0 0 0 23.013 0z"/></svg></span>
            Jira
          </div>
        </div>
      </div>

    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section" id="s-projects">
    <div class="section-label">Projects</div>
    <div class="projects-grid">
      <div class="project-card">
        <div class="project-icon" style="background:linear-gradient(135deg,rgba(248,152,32,.15),rgba(99,140,255,.15))">🏦</div>
        <div class="project-name">KeyBank — Core Banking</div>
        <div class="project-desc">Deposit Service module handling multi-channel deposits with real-time validation and Redis-backed performance.</div>
        <div class="project-metrics">
          <span class="metric-badge metric-green">+30% API speed</span>
          <span class="metric-badge metric-blue">−25% defects</span>
        </div>
        <div class="project-tags">
          <span class="project-tag">Java</span><span class="project-tag">Spring Boot</span><span class="project-tag">Kafka</span><span class="project-tag">Redis</span><span class="project-tag">Oracle</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-icon" style="background:linear-gradient(135deg,rgba(52,211,153,.15),rgba(99,140,255,.15))">📝</div>
        <div class="project-name">Blogging App Backend</div>
        <div class="project-desc">Scalable REST API with full CRUD, search & filtering by category/tags. Clean MVC architecture with PostgreSQL.</div>
        <div class="project-metrics">
          <span class="metric-badge metric-blue">REST API</span>
          <span class="metric-badge metric-amber">MVC</span>
        </div>
        <div class="project-tags">
          <span class="project-tag">Spring Boot</span><span class="project-tag">PostgreSQL</span><span class="project-tag">JPA</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-icon" style="background:linear-gradient(135deg,rgba(167,139,250,.15),rgba(52,211,153,.15))">📓</div>
        <div class="project-name">Google Keep Clone</div>
        <div class="project-desc">Full-stack clone with layered Angular service architecture, OnPush change detection, and BehaviorSubject state.</div>
        <div class="project-metrics">
          <span class="metric-badge metric-blue">Full-Stack</span>
          <span class="metric-badge metric-green">Angular 17</span>
        </div>
        <div class="project-tags">
          <span class="project-tag">Angular 17</span><span class="project-tag">Spring Boot</span><span class="project-tag">RxJS</span>
        </div>
      </div>
    </div>
  </div>

  <!-- LEARNING -->
  <div class="section" id="s-learning">
    <div class="section-label">Currently learning</div>
    <div class="learning-card">
      <div class="learning-icon-wrap">⚙️</div>
      <div>
        <div class="learning-title">Azure DevOps — 6-week deep dive</div>
        <div class="learning-list">
          <span>Boards</span> · <span>Repos</span> · <span>Pipelines</span> · <span>Artifacts</span> · <span>Azure Key Vault</span> · <span>Managed Identity</span>
        </div>
      </div>
    </div>
  </div>

  <!-- FUN FACT -->
  <div class="section" id="s-fun">
    <div class="section-label">Fun fact</div>
    <div class="fun-card">
      <p class="fun-quote">
        "I once traced a production bug through <em>4 microservices</em>, 2 Kafka topics, and a Redis cache — only to find it was a missing null check. 🐛 → ✅"
      </p>
    </div>
  </div>

  <div class="footer section" id="s-footer">
    <p>Built with <span>♥</span> and too much caffeine · Pune, India · <span>4 years of Java</span></p>
    <p style="margin-top:6px">Open to opportunities · 2026</p>
  </div>

</div>

<script>
  const titles = ['Java Backend Developer','Spring Boot Engineer','Microservices Builder','Azure DevOps Learner'];
  let ti=0,ci=0,deleting=false;
  const el=document.getElementById('typed-text');
  function type(){
    const cur=titles[ti];
    if(!deleting){el.textContent=cur.slice(0,++ci);if(ci===cur.length){deleting=true;setTimeout(type,2200);return;}}
    else{el.textContent=cur.slice(0,--ci);if(ci===0){deleting=false;ti=(ti+1)%titles.length;}}
    setTimeout(type,deleting?40:80);
  }
  setTimeout(type,1200);

  const obs=new IntersectionObserver(entries=>{entries.forEach(e=>{if(e.isIntersecting){e.target.classList.add('visible');obs.unobserve(e.target);}});},{threshold:.12});
  document.querySelectorAll('.section').forEach(s=>obs.observe(s));

  function animateCount(el,target,suffix,decimals){
    const dur=1400,start=performance.now();
    function upd(now){
      const p=Math.min((now-start)/dur,1),ease=1-Math.pow(1-p,3),val=target*ease;
      el.textContent=decimals?val.toFixed(decimals)+suffix:Math.round(val)+suffix;
      if(p<1)requestAnimationFrame(upd);
    }
    requestAnimationFrame(upd);
  }

  const statsObs=new IntersectionObserver(entries=>{entries.forEach(e=>{if(e.isIntersecting){
    animateCount(document.getElementById('s1'),4,'+',0);
    animateCount(document.getElementById('s2'),3,'',0);
    animateCount(document.getElementById('s3'),30,'%',0);
    animateCount(document.getElementById('s4'),25,'%',0);
    statsObs.unobserve(e.target);
  }});},{threshold:.5});
  statsObs.observe(document.querySelector('.stats-row'));
</script>
</body>
</html>
