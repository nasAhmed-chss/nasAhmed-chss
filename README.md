<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Naseer Ahmed — Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;500;600&family=DM+Mono:wght@300;400;500&family=Outfit:wght@200;300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #080c10;
    --surface: #0d1117;
    --surface2: #111820;
    --border: rgba(99, 179, 237, 0.12);
    --border-hover: rgba(99, 179, 237, 0.35);
    --accent: #63b3ed;
    --accent2: #4fd1c5;
    --accent3: #f6ad55;
    --text: #e2e8f0;
    --muted: #718096;
    --dimmed: #4a5568;
    --glow: rgba(99, 179, 237, 0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Outfit', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* Ambient background */
  body::before {
    content: '';
    position: fixed;
    top: -50%;
    left: -20%;
    width: 60vw;
    height: 60vw;
    background: radial-gradient(circle, rgba(99,179,237,0.04) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
  }
  body::after {
    content: '';
    position: fixed;
    bottom: -30%;
    right: -10%;
    width: 50vw;
    height: 50vw;
    background: radial-gradient(circle, rgba(79,209,197,0.04) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 0 32px;
    position: relative;
    z-index: 1;
  }

  /* ─── NAV ─── */
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 28px 0;
    border-bottom: 1px solid var(--border);
    position: relative;
    z-index: 10;
  }

  .nav-logo {
    font-family: 'DM Mono', monospace;
    font-size: 13px;
    color: var(--accent);
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  .nav-links {
    display: flex;
    gap: 32px;
    list-style: none;
  }

  .nav-links a {
    font-size: 12px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--muted);
    text-decoration: none;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--text); }

  /* ─── HERO ─── */
  .hero {
    padding: 100px 0 80px;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 60px;
    align-items: center;
    border-bottom: 1px solid var(--border);
  }

  .hero-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .hero-eyebrow::before {
    content: '';
    display: inline-block;
    width: 28px;
    height: 1px;
    background: var(--accent);
  }

  .hero h1 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(48px, 7vw, 72px);
    font-weight: 300;
    line-height: 1.05;
    letter-spacing: -0.02em;
    margin-bottom: 24px;
    color: var(--text);
  }

  .hero h1 em {
    font-style: italic;
    color: var(--accent);
  }

  .hero-desc {
    font-size: 15px;
    color: var(--muted);
    line-height: 1.75;
    max-width: 480px;
    margin-bottom: 36px;
  }

  .hero-cta {
    display: flex;
    gap: 16px;
    align-items: center;
    flex-wrap: wrap;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 11px 24px;
    font-family: 'Outfit', sans-serif;
    font-size: 12px;
    font-weight: 400;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    text-decoration: none;
    border-radius: 2px;
    transition: all 0.2s;
    cursor: pointer;
  }

  .btn-primary {
    background: var(--accent);
    color: var(--bg);
    border: 1px solid var(--accent);
  }
  .btn-primary:hover {
    background: transparent;
    color: var(--accent);
  }

  .btn-ghost {
    background: transparent;
    color: var(--muted);
    border: 1px solid var(--border);
  }
  .btn-ghost:hover {
    border-color: var(--border-hover);
    color: var(--text);
  }

  /* Hero badge */
  .hero-badge {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 6px;
    padding: 24px 20px;
    border: 1px solid var(--border);
    border-radius: 4px;
    background: var(--surface);
    min-width: 120px;
    text-align: center;
  }
  .hero-badge-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 42px;
    font-weight: 300;
    color: var(--accent);
    line-height: 1;
  }
  .hero-badge-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--dimmed);
  }

  /* ─── SKILLS ─── */
  .section {
    padding: 72px 0;
    border-bottom: 1px solid var(--border);
  }

  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--dimmed);
    margin-bottom: 40px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .skills-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .skill-tag {
    padding: 7px 16px;
    border: 1px solid var(--border);
    border-radius: 2px;
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    background: var(--surface);
    transition: all 0.2s;
    letter-spacing: 0.04em;
  }
  .skill-tag:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(99,179,237,0.05);
  }

  /* ─── PROJECTS ─── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }

  .project-card {
    background: var(--surface);
    padding: 28px;
    text-decoration: none;
    display: flex;
    flex-direction: column;
    gap: 12px;
    transition: background 0.2s;
    position: relative;
    overflow: hidden;
  }

  .project-card:hover {
    background: var(--surface2);
  }
  .project-card:hover .project-img {
    opacity: 1;
    transform: scale(1.02);
  }
  .project-card:hover .project-arrow {
    transform: translate(3px, -3px);
    opacity: 1;
  }

  .project-card-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
  }

  .project-icon {
    font-size: 18px;
    line-height: 1;
  }

  .project-arrow {
    font-size: 14px;
    color: var(--dimmed);
    transition: all 0.2s;
    opacity: 0;
  }

  .project-img {
    width: 100%;
    height: 130px;
    object-fit: cover;
    border-radius: 2px;
    opacity: 0.75;
    transition: all 0.3s;
    background: var(--surface2);
    border: 1px solid var(--border);
  }

  .project-img-placeholder {
    width: 100%;
    height: 130px;
    background: linear-gradient(135deg, var(--surface2), var(--bg));
    border-radius: 2px;
    border: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--dimmed);
    letter-spacing: 0.1em;
  }

  .project-title {
    font-size: 15px;
    font-weight: 500;
    color: var(--text);
    letter-spacing: -0.01em;
  }

  .project-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .stack-tag {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: var(--dimmed);
    letter-spacing: 0.05em;
    padding: 3px 8px;
    background: rgba(255,255,255,0.03);
    border-radius: 2px;
  }

  .project-type {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 3px 10px;
    border-radius: 2px;
    width: fit-content;
  }

  .type-web { color: var(--accent); background: rgba(99,179,237,0.08); }
  .type-security { color: var(--accent2); background: rgba(79,209,197,0.08); }
  .type-data { color: var(--accent3); background: rgba(246,173,85,0.08); }
  .type-fullstack { color: #b794f4; background: rgba(183,148,244,0.08); }
  .type-tool { color: #fc8181; background: rgba(252,129,129,0.08); }

  /* Wide card */
  .project-card.wide {
    grid-column: span 2;
    flex-direction: row;
    align-items: center;
    gap: 28px;
  }
  .project-card.wide .project-img {
    width: 240px;
    height: 100px;
    flex-shrink: 0;
  }
  .project-card.wide .project-content {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  .project-card.wide .project-card-header {
    width: 100%;
  }

  /* Script cards row */
  .scripts-row {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
    margin-top: 1px;
  }

  .script-card {
    background: var(--surface);
    padding: 22px 24px;
    text-decoration: none;
    display: flex;
    flex-direction: column;
    gap: 8px;
    transition: background 0.2s;
  }
  .script-card:hover { background: var(--surface2); }
  .script-title {
    font-size: 14px;
    font-weight: 400;
    color: var(--text);
  }
  .script-subtitle {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--dimmed);
  }

  /* ─── CONNECT ─── */
  .connect-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }

  .connect-card {
    background: var(--surface);
    padding: 28px 24px;
    text-decoration: none;
    transition: background 0.2s;
    display: flex;
    flex-direction: column;
    gap: 8px;
  }
  .connect-card:hover { background: var(--surface2); }

  .connect-platform {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--dimmed);
  }
  .connect-handle {
    font-size: 14px;
    color: var(--text);
    font-weight: 400;
  }
  .connect-arrow {
    font-size: 12px;
    color: var(--dimmed);
    margin-top: auto;
    padding-top: 8px;
  }

  /* ─── FOOTER ─── */
  footer {
    padding: 40px 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .footer-left {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--dimmed);
    letter-spacing: 0.08em;
  }

  .footer-right {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--dimmed);
    letter-spacing: 0.08em;
  }

  /* Animations */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero-eyebrow { animation: fadeUp 0.6s ease forwards; }
  .hero h1 { animation: fadeUp 0.6s 0.1s ease both; }
  .hero-desc { animation: fadeUp 0.6s 0.2s ease both; }
  .hero-cta { animation: fadeUp 0.6s 0.3s ease both; }

  @media (max-width: 680px) {
    .hero { grid-template-columns: 1fr; }
    .hero-badge { display: none; }
    .projects-grid { grid-template-columns: 1fr; }
    .project-card.wide { flex-direction: column; grid-column: span 1; }
    .project-card.wide .project-img { width: 100%; }
    .scripts-row { grid-template-columns: 1fr; }
    .connect-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<div class="container">

  <!-- NAV -->
  <nav>
    <div class="nav-logo">NA — Portfolio</div>
    <ul class="nav-links">
      <li><a href="#projects">Projects</a></li>
      <li><a href="#connect">Contact</a></li>
      <li><a href="https://github.com/nasAhmed-chss" target="_blank">GitHub ↗</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section class="hero">
    <div>
      <div class="hero-eyebrow">Masters Student · Stony Brook University</div>
      <h1>Naseer<br><em>Ahmed</em></h1>
      <p class="hero-desc">
        Building at the intersection of software development, cybersecurity, and data-driven applications. Currently focused on web application security and data protection.
      </p>
      <div class="hero-cta">
        <a href="https://www.linkedin.com/in/naseer-ks-ahmed/" class="btn btn-primary" target="_blank">
          <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
          LinkedIn
        </a>
        <a href="mailto:naseer3.14159@gmail.com" class="btn btn-ghost">naseer3.14159@gmail.com</a>
      </div>
    </div>
    <div class="hero-badge">
      <div class="hero-badge-num">45</div>
      <div class="hero-badge-label">Commits</div>
    </div>
  </section>

  <!-- SKILLS -->
  <section class="section">
    <div class="section-label">Skills & Stack</div>
    <div class="skills-grid">
      <span class="skill-tag">Python</span>
      <span class="skill-tag">JavaScript</span>
      <span class="skill-tag">React</span>
      <span class="skill-tag">Next.js</span>
      <span class="skill-tag">Node.js</span>
      <span class="skill-tag">MongoDB</span>
      <span class="skill-tag">TypeScript</span>
      <span class="skill-tag">HTML5</span>
      <span class="skill-tag">CSS3</span>
      <span class="skill-tag">TailwindCSS</span>
      <span class="skill-tag">Framer Motion</span>
      <span class="skill-tag">Express</span>
      <span class="skill-tag">Bash</span>
      <span class="skill-tag">Ruby</span>
    </div>
  </section>

  <!-- PROJECTS -->
  <section class="section" id="projects">
    <div class="section-label">Selected Projects</div>

    <div class="projects-grid">

      <!-- Landing Page -->
      <a href="https://nasahmed-chss.github.io/landingPage/" class="project-card" target="_blank">
        <div class="project-card-header">
          <span class="project-icon">🌐</span>
          <span class="project-arrow">↗</span>
        </div>
        <img class="project-img" src="https://raw.githubusercontent.com/nasAhmed-chss/nasAhmed-chss/main/Landing%20Page.png" alt="Landing Page" onerror="this.style.display='none'">
        <div class="project-title">Landing Page</div>
        <div class="project-stack">
          <span class="stack-tag">HTML</span>
          <span class="stack-tag">CSS</span>
          <span class="stack-tag">JS</span>
        </div>
        <span class="project-type type-web">Web</span>
      </a>

      <!-- Adaptive Keyboard -->
      <a href="https://keyboard-accuracy-testing.vercel.app/" class="project-card" target="_blank">
        <div class="project-card-header">
          <span class="project-icon">🎹</span>
          <span class="project-arrow">↗</span>
        </div>
        <img class="project-img" src="https://raw.githubusercontent.com/nasAhmed-chss/nasAhmed-chss/main/KeyboardApp.png" alt="Keyboard App" onerror="this.style.display='none'">
        <div class="project-title">Adaptive Keyboard Accuracy</div>
        <div class="project-stack">
          <span class="stack-tag">React</span>
          <span class="stack-tag">Next.js</span>
          <span class="stack-tag">Framer Motion</span>
          <span class="stack-tag">Tailwind</span>
        </div>
        <span class="project-type type-web">Interactive</span>
      </a>

      <!-- Income vs Health — Lab 1 -->
      <a href="https://github.com/nasAhmed-chss/Income_vs_Health_County_Data" class="project-card" target="_blank">
        <div class="project-card-header">
          <span class="project-icon">📊</span>
          <span class="project-arrow">↗</span>
        </div>
        <img class="project-img" src="https://raw.githubusercontent.com/nasAhmed-chss/nasAhmed-chss/main/Lab1_website.png" alt="Income vs Health" onerror="this.style.display='none'">
        <div class="project-title">Income vs. Health County Data</div>
        <div class="project-stack">
          <span class="stack-tag">Python</span>
          <span class="stack-tag">Data Analysis</span>
        </div>
        <span class="project-type type-data">Data</span>
      </a>

      <!-- US County Health Analytics — Lab 2a -->
      <a href="https://github.com/nasAhmed-chss/US-County-Health-Analytics" class="project-card" target="_blank">
        <div class="project-card-header">
          <span class="project-icon">🏥</span>
          <span class="project-arrow">↗</span>
        </div>
        <!-- Show Lab2a_Plots and Lab2a_web in a 2-image layout -->
        <div style="display:grid;grid-template-columns:1fr 1fr;gap:6px;">
          <img style="width:100%;height:80px;object-fit:cover;border-radius:2px;opacity:0.8;border:1px solid var(--border);transition:all 0.3s;" 
               src="https://raw.githubusercontent.com/nasAhmed-chss/nasAhmed-chss/main/Lab2a_Plots.png" alt="Lab2a Plots" onerror="this.style.display='none'">
          <img style="width:100%;height:80px;object-fit:cover;border-radius:2px;opacity:0.8;border:1px solid var(--border);transition:all 0.3s;" 
               src="https://raw.githubusercontent.com/nasAhmed-chss/nasAhmed-chss/main/Lab2a_web.png" alt="Lab2a Web" onerror="this.style.display='none'">
        </div>
        <div class="project-title">US County Health Analytics</div>
        <div class="project-stack">
          <span class="stack-tag">Python</span>
          <span class="stack-tag">Visualization</span>
          <span class="stack-tag">Analytics</span>
        </div>
        <span class="project-type type-data">Data</span>
      </a>

      <!-- Network Scan Visualizer -->
      <a href="https://network-scan-visualizer.vercel.app/" class="project-card" target="_blank">
        <div class="project-card-header">
          <span class="project-icon">🛡️</span>
          <span class="project-arrow">↗</span>
        </div>
        <img class="project-img" src="https://raw.githubusercontent.com/nasAhmed-chss/nasAhmed-chss/main/NetScanProj.png" alt="Network Scan" onerror="this.style.display='none'">
        <div class="project-title">Network Scan Visualizer</div>
        <div class="project-stack">
          <span class="stack-tag">Next.js</span>
          <span class="stack-tag">TypeScript</span>
        </div>
        <span class="project-type type-security">Security</span>
      </a>

      <!-- Election Data -->
      <a href="https://github.com/GitHubMahim/416-Project" class="project-card" target="_blank">
        <div class="project-card-header">
          <span class="project-icon">🗳️</span>
          <span class="project-arrow">↗</span>
        </div>
        <img class="project-img" src="https://raw.githubusercontent.com/nasAhmed-chss/nasAhmed-chss/main/Website.png" alt="Election Data" onerror="this.style.display='none'">
        <div class="project-title">Election Data Website</div>
        <div class="project-stack">
          <span class="stack-tag">React</span>
          <span class="stack-tag">Next.js</span>
          <span class="stack-tag">MongoDB</span>
        </div>
        <span class="project-type type-data">Data</span>
      </a>

    </div>

    <!-- Wide: Full Stack Web App -->
    <div style="background: var(--border); border: 1px solid var(--border); border-radius: 4px; overflow: hidden; margin-top: 1px;">
      <a href="https://github.com/nasAhmed-chss/FakeStackOverflow-WebApp/tree/main" class="project-card wide" target="_blank">
        <img class="project-img" src="https://raw.githubusercontent.com/nasAhmed-chss/nasAhmed-chss/main/WebApp.png" alt="FakeStackOverflow" onerror="this.style.display='none'">
        <div class="project-content">
          <div class="project-card-header">
            <span class="project-icon">🛠️</span>
            <span class="project-arrow">↗</span>
          </div>
          <div class="project-title">FakeStackOverflow — Full Stack Web App</div>
          <div class="project-stack">
            <span class="stack-tag">React</span>
            <span class="stack-tag">Node.js</span>
            <span class="stack-tag">MongoDB</span>
            <span class="stack-tag">Express</span>
          </div>
          <span class="project-type type-fullstack">Full Stack</span>
        </div>
      </a>
    </div>

    <!-- Script tools row -->
    <div class="scripts-row">
      <a href="https://github.com/nasAhmed-chss/Bash-Scripts" class="script-card" target="_blank">
        <div style="font-size:18px">🖥️</div>
        <div class="script-title">Bash Scripts</div>
        <div class="script-subtitle">Shell automation</div>
      </a>
      <a href="https://github.com/nasAhmed-chss/ruby-scripts" class="script-card" target="_blank">
        <div style="font-size:18px">💎</div>
        <div class="script-title">Ruby Scripts</div>
        <div class="script-subtitle">Ruby utilities</div>
      </a>
      <a href="https://github.com/nasAhmed-chss/inventory-manger" class="script-card" target="_blank">
        <div style="font-size:18px">📦</div>
        <div class="script-title">Inventory Manager</div>
        <div class="script-subtitle">Management tool</div>
      </a>
    </div>

  </section>

  <!-- CONNECT -->
  <section class="section" id="connect">
    <div class="section-label">Let's Connect</div>
    <div class="connect-grid">
      <a href="https://www.linkedin.com/in/naseer-ks-ahmed/" class="connect-card" target="_blank">
        <div class="connect-platform">LinkedIn</div>
        <div class="connect-handle">Naseer Ahmed</div>
        <div class="connect-arrow">↗</div>
      </a>
      <a href="https://github.com/nasAhmed-chss" class="connect-card" target="_blank">
        <div class="connect-platform">GitHub</div>
        <div class="connect-handle">nasAhmed-chss</div>
        <div class="connect-arrow">↗</div>
      </a>
      <a href="mailto:naseer3.14159@gmail.com" class="connect-card">
        <div class="connect-platform">Email</div>
        <div class="connect-handle">naseer3.14159<br>@gmail.com</div>
        <div class="connect-arrow">→</div>
      </a>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="footer-left">© 2025 Naseer Ahmed</div>
    <div class="footer-right">Masters · Stony Brook University</div>
  </footer>

</div>

</body>
</html>
