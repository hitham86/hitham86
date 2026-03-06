<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hitham – GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&family=Inter:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --border: #1e1e2e;
    --accent: #7c6aff;
    --accent2: #00e5ff;
    --accent3: #ff6b6b;
    --text: #e8e8f0;
    --muted: #6b6b8a;
    --card: #13131e;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    font-family: 'Inter', sans-serif;
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated background grid */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: 
      linear-gradient(rgba(124,106,255,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(124,106,255,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
    z-index: 0;
  }

  .container {
    position: relative;
    z-index: 1;
    max-width: 780px;
    margin: 0 auto;
    padding: 48px 24px;
  }

  /* HERO */
  .hero {
    margin-bottom: 48px;
    animation: fadeUp 0.6s ease both;
  }

  .greeting {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2rem, 6vw, 3.2rem);
    font-weight: 800;
    letter-spacing: -0.02em;
    line-height: 1.1;
    margin-bottom: 8px;
  }

  .greeting .wave { display: inline-block; animation: wave 2s ease-in-out infinite; }

  @keyframes wave {
    0%, 100% { transform: rotate(0deg); }
    25% { transform: rotate(20deg); }
    75% { transform: rotate(-10deg); }
  }

  .greeting .name {
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .title-line {
    font-family: 'Space Mono', monospace;
    font-size: 0.85rem;
    color: var(--accent2);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .title-line::before {
    content: '';
    display: block;
    width: 24px;
    height: 1px;
    background: var(--accent2);
  }

  /* BADGES */
  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 36px;
    animation: fadeUp 0.6s 0.1s ease both;
  }

  .badge {
    display: flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 6px;
    font-family: 'Space Mono', monospace;
    font-size: 0.72rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    text-decoration: none;
    border: 1px solid transparent;
    transition: all 0.2s ease;
    cursor: pointer;
  }

  .badge:hover { transform: translateY(-2px); filter: brightness(1.2); }

  .badge-yahoo  { background: rgba(96,1,210,0.2); border-color: #6001d2; color: #b388ff; }
  .badge-gmail  { background: rgba(209,72,54,0.2); border-color: #d14836; color: #ff8a73; }
  .badge-github { background: rgba(255,255,255,0.05); border-color: #444; color: #ccc; }
  .badge-linkedin { background: rgba(0,119,181,0.2); border-color: #0077b5; color: #64b5f6; }

  /* DIVIDER */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), var(--accent)/30, var(--border), transparent);
    margin: 32px 0;
  }

  /* SECTION */
  .section {
    margin-bottom: 40px;
    animation: fadeUp 0.6s ease both;
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 1rem;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .section-title span { font-size: 1.1rem; }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ABOUT */
  .about-text {
    font-size: 0.95rem;
    line-height: 1.8;
    color: #a0a0c0;
    border-left: 2px solid var(--accent);
    padding-left: 16px;
  }

  .about-text strong {
    color: var(--text);
    font-weight: 500;
  }

  /* CURRENTLY GRID */
  .currently-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 12px;
  }

  .currently-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px;
    transition: border-color 0.2s, transform 0.2s;
  }

  .currently-card:hover {
    border-color: var(--accent);
    transform: translateY(-2px);
  }

  .currently-card .icon { font-size: 1.3rem; margin-bottom: 8px; }

  .currently-card p {
    font-size: 0.82rem;
    color: var(--muted);
    line-height: 1.5;
  }

  .currently-card strong { color: var(--text); font-weight: 500; }

  /* TECH ICONS */
  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .tech-pill {
    display: flex;
    align-items: center;
    gap: 6px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 8px 14px;
    font-family: 'Space Mono', monospace;
    font-size: 0.75rem;
    color: var(--muted);
    transition: all 0.2s;
  }

  .tech-pill:hover {
    border-color: var(--accent);
    color: var(--text);
    transform: translateY(-2px);
  }

  .tech-pill .dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: var(--accent);
    flex-shrink: 0;
  }

  .tech-pill .dot.go     { background: #00acd7; }
  .tech-pill .dot.js     { background: #f7df1e; }
  .tech-pill .dot.py     { background: #3776ab; }
  .tech-pill .dot.swift  { background: #fa7343; }
  .tech-pill .dot.sql    { background: #00758f; }
  .tech-pill .dot.html   { background: #e34f26; }
  .tech-pill .dot.css    { background: #264de4; }
  .tech-pill .dot.vscode { background: #007acc; }
  .tech-pill .dot.github { background: #aaa; }

  /* WHAT I BUILD */
  .build-list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    list-style: none;
  }

  @media (max-width: 500px) { .build-list { grid-template-columns: 1fr; } }

  .build-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 12px 16px;
    font-size: 0.85rem;
    color: #9090b0;
    display: flex;
    align-items: center;
    gap: 10px;
    transition: all 0.2s;
  }

  .build-item:hover {
    border-color: var(--accent2);
    color: var(--text);
    transform: translateX(3px);
  }

  .build-item::before {
    content: '→';
    color: var(--accent2);
    font-family: 'Space Mono', monospace;
    font-size: 0.8rem;
    flex-shrink: 0;
  }

  /* CONTACT */
  .contact-row {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
  }

  .contact-link {
    display: flex;
    align-items: center;
    gap: 8px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 16px;
    font-size: 0.82rem;
    color: var(--muted);
    text-decoration: none;
    transition: all 0.2s;
    font-family: 'Space Mono', monospace;
  }

  .contact-link:hover {
    border-color: var(--accent);
    color: var(--accent);
  }

  /* CALLOUT */
  .callout {
    background: linear-gradient(135deg, rgba(124,106,255,0.08), rgba(0,229,255,0.06));
    border: 1px solid rgba(124,106,255,0.3);
    border-radius: 10px;
    padding: 16px 20px;
    font-size: 0.875rem;
    color: #a0a0c0;
    font-style: italic;
    display: flex;
    align-items: center;
    gap: 12px;
    margin-top: 40px;
  }

  .callout .bulb { font-size: 1.2rem; font-style: normal; }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .section:nth-child(2)  { animation-delay: 0.05s; }
  .section:nth-child(3)  { animation-delay: 0.10s; }
  .section:nth-child(4)  { animation-delay: 0.15s; }
  .section:nth-child(5)  { animation-delay: 0.20s; }
  .section:nth-child(6)  { animation-delay: 0.25s; }
</style>
</head>
<body>
<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="greeting">
      <span class="wave">👋</span> Hello, I'm <span class="name">Hitham</span>
    </div>
    <div class="title-line">Python Developer</div>

    <div class="badges">
      <a class="badge badge-yahoo" href="mailto:hithamhauter@yahoo.com">
        <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M14.5 11L12 4 9.5 11H14.5zM12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm2.5 13.5L13 20h-2l-1.5-6.5L7 20H5l3.5-8.5L5 4h2l2.5 5.5L12 4h2l-3.5 7.5L13.5 20h-2l-1.5-6.5z"/></svg>
        Yahoo
      </a>
      <a class="badge badge-gmail" href="mailto:hithamhauter5@gmail.com">
        <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4-8 5-8-5V6l8 5 8-5v2z"/></svg>
        Gmail
      </a>
      <a class="badge badge-github" href="https://github.com/hitham86" target="_blank">
        <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
        GitHub
      </a>
      <a class="badge badge-linkedin" href="https://www.linkedin.com/in/hitham-hauter" target="_blank">
        <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ABOUT -->
  <div class="section">
    <div class="section-title"><span>🙋‍♂️</span> About Me</div>
    <p class="about-text">
      Developer passionate about <strong>Python</strong>, <strong>JavaScript</strong>, <strong>SQL</strong>, <strong>Golang</strong>, and <strong>Swift</strong>.<br>
      Always eager to learn new technologies and solve challenging problems.<br>
      Driven by curiosity and a love for building things that matter.
    </p>
  </div>

  <div class="divider"></div>

  <!-- CURRENTLY -->
  <div class="section">
    <div class="section-title"><span>🔍</span> Currently</div>
    <div class="currently-grid">
      <div class="currently-card">
        <div class="icon">🔭</div>
        <p>Building <strong>Python Projects</strong> focused on automation & data</p>
      </div>
      <div class="currently-card">
        <div class="icon">🌱</div>
        <p>Deepening skills in <strong>Artificial Intelligence</strong> & <strong>Data Science</strong></p>
      </div>
      <div class="currently-card">
        <div class="icon">💬</div>
        <p>Happy to chat about <strong>Programming</strong> & <strong>SQL</strong></p>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- TECH -->
  <div class="section">
    <div class="section-title"><span>⚒️</span> Languages, Frameworks & Tools</div>
    <div class="tech-grid">
      <div class="tech-pill"><span class="dot py"></span>Python</div>
      <div class="tech-pill"><span class="dot js"></span>JavaScript</div>
      <div class="tech-pill"><span class="dot html"></span>HTML</div>
      <div class="tech-pill"><span class="dot css"></span>CSS</div>
      <div class="tech-pill"><span class="dot sql"></span>MySQL</div>
      <div class="tech-pill"><span class="dot go"></span>Go</div>
      <div class="tech-pill"><span class="dot swift"></span>Swift</div>
      <div class="tech-pill"><span class="dot github"></span>Git / GitHub</div>
      <div class="tech-pill"><span class="dot vscode"></span>VS Code</div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- WHAT I BUILD -->
  <div class="section">
    <div class="section-title"><span>🚀</span> What I Build</div>
    <ul class="build-list">
      <li class="build-item">AI-powered web apps & automation tools</li>
      <li class="build-item">Django & full-stack systems</li>
      <li class="build-item">Business dashboards & data pipelines</li>
      <li class="build-item">Trading, finance & analytics apps</li>
      <li class="build-item">Custom tools for real businesses</li>
    </ul>
  </div>

  <div class="divider"></div>

  <!-- CONTACT -->
  <div class="section">
    <div class="section-title"><span>📫</span> Contact Me</div>
    <div class="contact-row">
      <a class="contact-link" href="mailto:hithamhauter@yahoo.com">✉ hithamhauter@yahoo.com</a>
      <a class="contact-link" href="mailto:hithamhauter5@gmail.com">✉ hithamhauter5@gmail.com</a>
      <a class="contact-link" href="https://www.linkedin.com/in/hitham-hauter" target="_blank">🔗 linkedin.com/in/hitham-hauter</a>
    </div>
  </div>

  <!-- CALLOUT -->
  <div class="callout">
    <span class="bulb">💡</span>
    Open to collaboration, learning, and new opportunities — feel free to reach out!
  </div>

</div>
</body>
</html>
