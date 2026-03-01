<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Burhan Mehdi – GitHub README</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0d14;
    --surface: #111520;
    --surface2: #161c2e;
    --border: #1e2740;
    --accent: #00e5ff;
    --accent2: #7c3aed;
    --accent3: #10b981;
    --text: #e2e8f0;
    --muted: #64748b;
    --gold: #f59e0b;
    --pink: #ec4899;
    --mono: 'JetBrains Mono', monospace;
    --sans: 'Syne', sans-serif;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 40px 20px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    text-align: center;
    padding: 60px 0 40px;
    position: relative;
  }

  .header::before {
    content: '< dev />';
    position: absolute;
    top: 20px;
    right: 0;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 2px;
  }

  .greeting {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--accent);
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-bottom: 12px;
    animation: fadeDown 0.6s ease both;
  }

  .name {
    font-size: clamp(36px, 7vw, 64px);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -1px;
    background: linear-gradient(135deg, #fff 0%, var(--accent) 50%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: fadeDown 0.6s 0.1s ease both;
  }

  .tagline {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--muted);
    margin-top: 16px;
    animation: fadeDown 0.6s 0.2s ease both;
  }

  .tagline span { color: var(--accent3); }

  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
    margin-top: 24px;
    animation: fadeDown 0.6s 0.3s ease both;
  }

  .badge {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 5px 12px;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    display: flex;
    align-items: center;
    gap: 6px;
    transition: border-color 0.2s, color 0.2s;
  }

  .badge:hover { border-color: var(--accent); color: var(--accent); }
  .badge .dot { width: 6px; height: 6px; border-radius: 50%; background: var(--accent3); }
  .badge .dot.blue { background: var(--accent); }
  .badge .dot.purple { background: var(--accent2); }

  .social-row {
    display: flex;
    gap: 12px;
    justify-content: center;
    margin-top: 28px;
    animation: fadeDown 0.6s 0.4s ease both;
  }

  .social-link {
    display: flex;
    align-items: center;
    gap: 7px;
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 8px 16px;
    font-size: 12px;
    font-family: var(--mono);
    color: var(--muted);
    text-decoration: none;
    transition: all 0.2s;
  }

  .social-link:hover {
    border-color: var(--accent);
    color: var(--accent);
    transform: translateY(-2px);
    box-shadow: 0 4px 20px rgba(0,229,255,0.15);
  }

  /* ── CODE BLOCK ── */
  .code-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    margin: 40px 0;
    animation: fadeUp 0.6s 0.5s ease both;
  }

  .code-header {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 12px 16px;
    background: var(--surface2);
    border-bottom: 1px solid var(--border);
  }

  .dot-red { width: 12px; height: 12px; border-radius: 50%; background: #ff5f57; }
  .dot-yellow { width: 12px; height: 12px; border-radius: 50%; background: #febc2e; }
  .dot-green { width: 12px; height: 12px; border-radius: 50%; background: #28c840; }
  .code-filename { margin-left: auto; font-family: var(--mono); font-size: 11px; color: var(--muted); }

  .code-body {
    padding: 24px 28px;
    font-family: var(--mono);
    font-size: 13px;
    line-height: 1.9;
  }

  .kw { color: #c084fc; }
  .var { color: var(--accent); }
  .str { color: var(--accent3); }
  .num { color: var(--gold); }
  .prop { color: #7dd3fc; }
  .cmt { color: var(--muted); font-style: italic; }
  .punct { color: #94a3b8; }

  /* ── SECTION ── */
  .section {
    margin: 48px 0;
    animation: fadeUp 0.6s ease both;
  }

  .section-label {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 24px;
  }

  .section-label span {
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: 3px;
    color: var(--accent);
    text-transform: uppercase;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  /* ── SKILLS ── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
    gap: 10px;
  }

  .skill-chip {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 14px;
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text);
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: all 0.2s;
  }

  .skill-chip::before {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: var(--accent);
    transform: scaleX(0);
    transition: transform 0.2s;
  }

  .skill-chip:hover { border-color: var(--accent); transform: translateY(-2px); }
  .skill-chip:hover::before { transform: scaleX(1); }

  .skill-chip.green::before { background: var(--accent3); }
  .skill-chip.green:hover { border-color: var(--accent3); }
  .skill-chip.purple::before { background: var(--accent2); }
  .skill-chip.purple:hover { border-color: var(--accent2); }

  /* ── EXPERIENCE ── */
  .exp-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px 28px;
    margin-bottom: 16px;
    position: relative;
    transition: border-color 0.2s, transform 0.2s;
  }

  .exp-card:hover {
    border-color: var(--accent);
    transform: translateX(4px);
  }

  .exp-card::before {
    content: '';
    position: absolute;
    left: 0; top: 16px; bottom: 16px;
    width: 3px;
    background: linear-gradient(180deg, var(--accent), var(--accent2));
    border-radius: 0 3px 3px 0;
  }

  .exp-title {
    font-weight: 700;
    font-size: 16px;
    color: #fff;
  }

  .exp-company {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--accent);
    margin-top: 4px;
  }

  .exp-desc {
    font-size: 13px;
    color: var(--muted);
    margin-top: 10px;
    line-height: 1.7;
  }

  .exp-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-top: 14px;
  }

  .tag {
    background: rgba(0,229,255,0.08);
    border: 1px solid rgba(0,229,255,0.2);
    border-radius: 4px;
    padding: 2px 8px;
    font-family: var(--mono);
    font-size: 10px;
    color: var(--accent);
  }

  .tag.green { background: rgba(16,185,129,0.08); border-color: rgba(16,185,129,0.2); color: var(--accent3); }
  .tag.purple { background: rgba(124,58,237,0.08); border-color: rgba(124,58,237,0.2); color: #a78bfa; }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 14px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    transition: all 0.25s;
    cursor: default;
  }

  .project-card:hover {
    border-color: rgba(0,229,255,0.4);
    transform: translateY(-4px);
    box-shadow: 0 12px 40px rgba(0,229,255,0.08);
  }

  .project-icon {
    font-size: 22px;
    margin-bottom: 10px;
  }

  .project-name {
    font-weight: 700;
    font-size: 15px;
    color: #fff;
    margin-bottom: 6px;
  }

  .project-desc {
    font-size: 12px;
    color: var(--muted);
    line-height: 1.6;
  }

  .project-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
    margin-top: 12px;
  }

  /* ── STATS ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 14px;
    margin-top: 24px;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .stat-card::before {
    content: '';
    position: absolute;
    top: -40px; left: 50%;
    transform: translateX(-50%);
    width: 80px; height: 80px;
    background: radial-gradient(circle, rgba(0,229,255,0.15), transparent 70%);
    border-radius: 50%;
  }

  .stat-card.green::before { background: radial-gradient(circle, rgba(16,185,129,0.15), transparent 70%); }
  .stat-card.purple::before { background: radial-gradient(circle, rgba(124,58,237,0.15), transparent 70%); }

  .stat-value {
    font-size: 28px;
    font-weight: 800;
    color: var(--accent);
    font-family: var(--mono);
  }

  .stat-card.green .stat-value { color: var(--accent3); }
  .stat-card.purple .stat-value { color: #a78bfa; }

  .stat-label {
    font-size: 11px;
    color: var(--muted);
    margin-top: 4px;
    letter-spacing: 1px;
    text-transform: uppercase;
  }

  /* ── CERTS ── */
  .cert-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 10px;
  }

  .cert-item {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 12px 16px;
    display: flex;
    align-items: flex-start;
    gap: 10px;
    transition: all 0.2s;
  }

  .cert-item:hover { border-color: var(--gold); }

  .cert-icon { font-size: 18px; flex-shrink: 0; }

  .cert-name {
    font-size: 12px;
    color: var(--text);
    line-height: 1.4;
  }

  .cert-by {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--gold);
    margin-top: 3px;
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding: 40px 0 60px;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    border-top: 1px solid var(--border);
    margin-top: 48px;
  }

  .footer .highlight { color: var(--accent); }

  /* ── ANIMATIONS ── */
  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-16px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* Typing cursor */
  .cursor {
    display: inline-block;
    width: 2px;
    height: 1em;
    background: var(--accent);
    margin-left: 2px;
    vertical-align: text-bottom;
    animation: blink 1s step-end infinite;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }

  .divider {
    text-align: center;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    margin: 8px 0;
  }

  /* Wave banner */
  .banner {
    background: linear-gradient(135deg, var(--surface) 0%, #0d1526 100%);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 36px;
    margin: 40px 0;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .banner::before {
    content: '';
    position: absolute;
    top: -60px; left: -60px;
    width: 200px; height: 200px;
    background: radial-gradient(circle, rgba(0,229,255,0.12), transparent 70%);
    border-radius: 50%;
  }

  .banner::after {
    content: '';
    position: absolute;
    bottom: -60px; right: -60px;
    width: 200px; height: 200px;
    background: radial-gradient(circle, rgba(124,58,237,0.12), transparent 70%);
    border-radius: 50%;
  }

  .banner-text {
    font-size: 20px;
    font-weight: 700;
    position: relative;
    z-index: 1;
  }

  .banner-sub {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--muted);
    margin-top: 8px;
    position: relative;
    z-index: 1;
  }

  /* lang bar */
  .lang-bar {
    display: flex;
    height: 6px;
    border-radius: 99px;
    overflow: hidden;
    margin-top: 12px;
  }

  .lang-seg { height: 100%; }
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <div class="header">
    <div class="greeting">👋 Hey there, I'm</div>
    <div class="name">Burhan Mehdi</div>
    <div class="tagline">
      AI/ML Engineer · <span>Data Scientist</span> · GenAI Builder
      <span class="cursor"></span>
    </div>

    <div class="badges">
      <div class="badge"><span class="dot"></span> B.E. AI & ML — 3rd Year</div>
      <div class="badge"><span class="dot blue"></span> GPA: 8.34 / 10.0</div>
      <div class="badge"><span class="dot purple"></span> Hyderabad, India 🇮🇳</div>
      <div class="badge"><span class="dot"></span> Open to Internships</div>
    </div>

    <div class="social-row">
      <a href="https://github.com/burhanmehdi" class="social-link">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
        GitHub
      </a>
      <a href="https://www.linkedin.com/in/syedburhan05/" class="social-link">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a href="mailto:s.m.burhanxmehdi@gmail.com" class="social-link">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,12 2,6"/></svg>
        Email
      </a>
    </div>
  </div>

  <!-- CODE CARD -->
  <div class="code-card">
    <div class="code-header">
      <div class="dot-red"></div>
      <div class="dot-yellow"></div>
      <div class="dot-green"></div>
      <span class="code-filename">burhan.py</span>
    </div>
    <div class="code-body">
      <span class="kw">class</span> <span class="var">BurhanMehdi</span><span class="punct">:</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="kw">def</span> <span class="var">__init__</span><span class="punct">(</span><span class="prop">self</span><span class="punct">):</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="prop">self</span><span class="punct">.</span><span class="var">name</span> <span class="punct">=</span> <span class="str">"Burhan Mehdi"</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="prop">self</span><span class="punct">.</span><span class="var">role</span> <span class="punct">=</span> <span class="str">"AI/ML Engineer & Data Scientist"</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="prop">self</span><span class="punct">.</span><span class="var">location</span> <span class="punct">=</span> <span class="str">"Hyderabad, India 🇮🇳"</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="prop">self</span><span class="punct">.</span><span class="var">education</span> <span class="punct">=</span> <span class="str">"B.E. AI & ML @ Osmania University"</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="prop">self</span><span class="punct">.</span><span class="var">gpa</span> <span class="punct">=</span> <span class="num">8.34</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="prop">self</span><span class="punct">.</span><span class="var">languages</span> <span class="punct">= [</span><span class="str">"Python"</span><span class="punct">,</span> <span class="str">"SQL"</span><span class="punct">,</span> <span class="str">"JavaScript"</span><span class="punct">,</span> <span class="str">"HTML/CSS"</span><span class="punct">]</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="prop">self</span><span class="punct">.</span><span class="var">domains</span> <span class="punct">= [</span><span class="str">"GenAI"</span><span class="punct">,</span> <span class="str">"LLMs"</span><span class="punct">,</span> <span class="str">"NLP"</span><span class="punct">,</span> <span class="str">"ML"</span><span class="punct">,</span> <span class="str">"Web Dev"</span><span class="punct">]</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="prop">self</span><span class="punct">.</span><span class="var">hireable</span> <span class="punct">=</span> <span class="kw">True</span><br><br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span class="kw">def</span> <span class="var">say_hello</span><span class="punct">(</span><span class="prop">self</span><span class="punct">):</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="kw">return</span> <span class="str">"Building intelligent systems that matter 🚀"</span><br>
    </div>
  </div>

  <!-- STATS -->
  <div class="section">
    <div class="section-label"><span>⚡ At a Glance</span></div>
    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-value">8.34</div>
        <div class="stat-label">GPA / 10.0</div>
      </div>
      <div class="stat-card green">
        <div class="stat-value">10+</div>
        <div class="stat-label">Projects Built</div>
      </div>
      <div class="stat-card purple">
        <div class="stat-value">12+</div>
        <div class="stat-label">Certifications</div>
      </div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section">
    <div class="section-label"><span>🛠 Technical Skills</span></div>

    <div class="divider" style="margin-bottom:10px; font-size:10px; color:var(--accent); letter-spacing:2px;">— LANGUAGES —</div>
    <div class="skills-grid" style="margin-bottom:16px;">
      <div class="skill-chip">🐍 Python</div>
      <div class="skill-chip">🗄️ SQL</div>
      <div class="skill-chip">📜 JavaScript</div>
      <div class="skill-chip">🌐 HTML / CSS</div>
    </div>

    <div class="divider" style="margin-bottom:10px; font-size:10px; color:var(--accent3); letter-spacing:2px;">— LIBRARIES & FRAMEWORKS —</div>
    <div class="skills-grid" style="margin-bottom:16px;">
      <div class="skill-chip green">Pandas</div>
      <div class="skill-chip green">NumPy</div>
      <div class="skill-chip green">Scikit-learn</div>
      <div class="skill-chip green">Matplotlib</div>
      <div class="skill-chip green">FastAPI</div>
      <div class="skill-chip green">React (TS)</div>
      <div class="skill-chip green">SQLAlchemy</div>
      <div class="skill-chip green">OR-Tools</div>
    </div>

    <div class="divider" style="margin-bottom:10px; font-size:10px; color:#a78bfa; letter-spacing:2px;">— DOMAINS —</div>
    <div class="skills-grid">
      <div class="skill-chip purple">Machine Learning</div>
      <div class="skill-chip purple">Generative AI</div>
      <div class="skill-chip purple">NLP</div>
      <div class="skill-chip purple">LLMs</div>
      <div class="skill-chip purple">Data Visualization</div>
      <div class="skill-chip purple">Route Optimization</div>
      <div class="skill-chip purple">REST APIs</div>
      <div class="skill-chip purple">Web Development</div>
    </div>
  </div>

  <!-- EXPERIENCE -->
  <div class="section">
    <div class="section-label"><span>💼 Experience</span></div>

    <div class="exp-card">
      <div class="exp-title">Project Intern — AI & Logistics</div>
      <div class="exp-company">Persevex</div>
      <div class="exp-desc">
        Built an AI-powered ATS Resume Analyzer using LLMs and multi-agent architecture — featuring SWOT analysis, match scoring, and JSON reporting. Also developed a full-stack logistics platform with FastAPI + React (TypeScript), integrating Google OR-Tools for real-time VRP optimization and interactive map visualization.
      </div>
      <div class="exp-tags">
        <span class="tag">LLMs</span>
        <span class="tag">Multi-Agent AI</span>
        <span class="tag green">FastAPI</span>
        <span class="tag green">React</span>
        <span class="tag green">OR-Tools</span>
        <span class="tag purple">VRP Optimization</span>
        <span class="tag">PDF Parsing</span>
      </div>
    </div>

    <div class="exp-card">
      <div class="exp-title">Project Intern — ML Analytics</div>
      <div class="exp-company">Cognifyz Technologies</div>
      <div class="exp-desc">
        Developed a restaurant analytics & recommendation system using ML — built rating prediction with Random Forest regression, cuisine classification models, and a personalized recommendation engine. Evaluated using R², MSE, and accuracy metrics.
      </div>
      <div class="exp-tags">
        <span class="tag">Random Forest</span>
        <span class="tag green">Scikit-learn</span>
        <span class="tag green">Feature Engineering</span>
        <span class="tag purple">Recommendation Systems</span>
        <span class="tag">Python</span>
      </div>
    </div>

    <div class="exp-card">
      <div class="exp-title">Technology Consulting Virtual Intern</div>
      <div class="exp-company">Deloitte Technology Academy</div>
      <div class="exp-desc">
        Completed a job simulation focused on technology consulting and solution delivery. Analyzed client requirements, proposed technology-driven strategies, and developed understanding of cloud computing concepts.
      </div>
      <div class="exp-tags">
        <span class="tag purple">Tech Consulting</span>
        <span class="tag">Cloud Computing</span>
        <span class="tag">Solution Design</span>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-label"><span>🚀 Projects</span></div>
    <div class="projects-grid">

      <div class="project-card">
        <div class="project-icon">🧠</div>
        <div class="project-name">CogniGraph</div>
        <div class="project-desc">NLP text analysis tool that extracts key entities and visualizes their relationships as a knowledge graph.</div>
        <div class="project-stack">
          <span class="tag">NLP</span>
          <span class="tag green">Python</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-icon">📖</div>
        <div class="project-name">Readable</div>
        <div class="project-desc">Text complexity analyzer that calculates readability scores using linguistic metrics to optimize content for audiences.</div>
        <div class="project-stack">
          <span class="tag">NLP</span>
          <span class="tag green">Python</span>
          <span class="tag purple">Text Analysis</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-icon">💰</div>
        <div class="project-name">Frontier Daily Spark</div>
        <div class="project-desc">Full-stack personal finance management app with monthly bill tracking, budgeting, and expenditure trend visualizations.</div>
        <div class="project-stack">
          <span class="tag green">Web Dev</span>
          <span class="tag purple">Database</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-icon">🧾</div>
        <div class="project-name">BillGen</div>
        <div class="project-desc">Automated invoice generation system that streamlines professional bill creation and reduces manual entry errors.</div>
        <div class="project-stack">
          <span class="tag green">Python</span>
          <span class="tag">Automation</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-icon">🚢</div>
        <div class="project-name">VesselTrack</div>
        <div class="project-desc">Logistics tracking system monitoring vessel, port, and container status with route optimization insights.</div>
        <div class="project-stack">
          <span class="tag green">Python</span>
          <span class="tag purple">Data Analysis</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-icon">🌧️</div>
        <div class="project-name">Rainfall Prediction</div>
        <div class="project-desc">ML model predicting daily rainfall from historical weather data (temperature, humidity, pressure) with EDA.</div>
        <div class="project-stack">
          <span class="tag">ML</span>
          <span class="tag green">Scikit-learn</span>
          <span class="tag purple">EDA</span>
        </div>
      </div>

      <div class="project-card">
        <div class="project-icon">💪</div>
        <div class="project-name">FitPath</div>
        <div class="project-desc">AI-powered fitness app providing personalized exercise suggestions with adaptive workout routines based on user inputs.</div>
        <div class="project-stack">
          <span class="tag">AI</span>
          <span class="tag green">Python</span>
          <span class="tag purple">ML</span>
        </div>
      </div>

    </div>
  </div>

  <!-- CERTIFICATIONS -->
  <div class="section">
    <div class="section-label"><span>🎓 Certifications</span></div>
    <div class="cert-list">
      <div class="cert-item">
        <div class="cert-icon">🤖</div>
        <div>
          <div class="cert-name">Generative AI: Prompt Engineering Basics</div>
          <div class="cert-by">IBM / Coursera · 2025</div>
        </div>
      </div>
      <div class="cert-item">
        <div class="cert-icon">✨</div>
        <div>
          <div class="cert-name">Generative AI: Introduction & Applications</div>
          <div class="cert-by">IBM / Coursera · 2025</div>
        </div>
      </div>
      <div class="cert-item">
        <div class="cert-icon">🐍</div>
        <div>
          <div class="cert-name">Python for Data Science, AI & Development</div>
          <div class="cert-by">IBM · 2025</div>
        </div>
      </div>
      <div class="cert-item">
        <div class="cert-icon">🧮</div>
        <div>
          <div class="cert-name">Machine Learning with Python</div>
          <div class="cert-by">IBM · 2025</div>
        </div>
      </div>
      <div class="cert-item">
        <div class="cert-icon">🚀</div>
        <div>
          <div class="cert-name">Developing AI Applications with Flask</div>
          <div class="cert-by">IBM · 2025</div>
        </div>
      </div>
      <div class="cert-item">
        <div class="cert-icon">💻</div>
        <div>
          <div class="cert-name">Introduction to Software Engineering</div>
          <div class="cert-by">IBM · 2025</div>
        </div>
      </div>
      <div class="cert-item">
        <div class="cert-icon">📊</div>
        <div>
          <div class="cert-name">Python Project for Data Science</div>
          <div class="cert-by">IBM · 2025</div>
        </div>
      </div>
      <div class="cert-item">
        <div class="cert-icon">🌐</div>
        <div>
          <div class="cert-name">Intro to HTML, CSS & JavaScript</div>
          <div class="cert-by">IBM · 2025</div>
        </div>
      </div>
    </div>
  </div>

  <!-- LANGUAGES / LANG BAR -->
  <div class="section">
    <div class="section-label"><span>🌍 Languages</span></div>
    <div style="display:flex; gap:20px; flex-wrap:wrap;">
      <div class="badge" style="padding:10px 18px; font-size:13px;">🇬🇧 English — Bilingual</div>
      <div class="badge" style="padding:10px 18px; font-size:13px;">🇩🇪 German — Intermediate</div>
      <div class="badge" style="padding:10px 18px; font-size:13px;">🇵🇰 Urdu — Native</div>
    </div>
  </div>

  <!-- CTA BANNER -->
  <div class="banner">
    <div class="banner-text">
      🤝 Open to internships & collaborations in <span style="color:var(--accent)">AI / ML / GenAI</span>
    </div>
    <div class="banner-sub">
      s.m.burhanxmehdi@gmail.com &nbsp;·&nbsp; github.com/burhanmehdi &nbsp;·&nbsp; linkedin.com/in/syedburhan05
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <span class="highlight">Burhan Mehdi</span> · Built with ❤️ and lots of ☕ · Hyderabad, India
  </div>

</div>
</body>
</html>
