<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Tishan Dhanuja — Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=Space+Mono:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #050a12;
    --surface: #0c1422;
    --border: #1a2840;
    --accent: #00e5ff;
    --accent2: #7b61ff;
    --accent3: #ff4ecd;
    --text: #cdd9f0;
    --muted: #4a6080;
    --glow: 0 0 30px rgba(0,229,255,0.25);
    --glow2: 0 0 30px rgba(123,97,255,0.25);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Space Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,255,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  /* Radial ambient glow */
  body::after {
    content: '';
    position: fixed;
    top: -40%;
    left: -20%;
    width: 80vw;
    height: 80vw;
    background: radial-gradient(circle, rgba(0,229,255,0.06) 0%, transparent 65%);
    pointer-events: none;
    z-index: 0;
  }

  .wrapper {
    position: relative;
    z-index: 1;
    max-width: 860px;
    margin: 0 auto;
    padding: 60px 24px 80px;
  }

  /* ── HERO ── */
  .hero {
    position: relative;
    text-align: center;
    padding: 60px 0 48px;
    animation: fadeUp 0.7s ease both;
  }

  .avatar-ring {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 100px;
    height: 100px;
    border-radius: 50%;
    background: conic-gradient(from 0deg, var(--accent), var(--accent2), var(--accent3), var(--accent));
    padding: 3px;
    animation: spin 6s linear infinite;
    margin-bottom: 28px;
  }

  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: var(--bg);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Syne', sans-serif;
    font-size: 2.2rem;
    font-weight: 800;
    color: var(--accent);
    animation: counter-spin 6s linear infinite;
  }

  @keyframes spin { to { transform: rotate(360deg); } }
  @keyframes counter-spin { to { transform: rotate(-360deg); } }

  .badge {
    display: inline-block;
    font-family: 'Space Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
    border: 1px solid var(--accent);
    padding: 4px 14px;
    border-radius: 100px;
    margin-bottom: 16px;
    animation: fadeUp 0.7s 0.1s ease both;
  }

  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.2rem, 6vw, 3.6rem);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.02em;
    background: linear-gradient(135deg, #fff 30%, var(--accent) 70%, var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 10px;
    animation: fadeUp 0.7s 0.15s ease both;
  }

  .role {
    font-size: 0.8rem;
    color: var(--muted);
    letter-spacing: 0.08em;
    animation: fadeUp 0.7s 0.2s ease both;
  }

  .role span { color: var(--accent2); }

  /* ── ABOUT CARD ── */
  .about-card {
    position: relative;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 32px 36px;
    margin: 40px 0;
    overflow: hidden;
    animation: fadeUp 0.7s 0.3s ease both;
  }

  .about-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent3));
  }

  .about-card::after {
    content: '//';
    position: absolute;
    top: 24px; right: 28px;
    font-size: 2rem;
    color: var(--border);
    font-family: 'Syne', sans-serif;
    font-weight: 800;
  }

  .card-label {
    font-size: 0.6rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 14px;
  }

  .about-card p {
    font-size: 0.88rem;
    line-height: 1.85;
    color: var(--text);
  }

  .about-card p b {
    color: #fff;
    font-weight: 700;
  }

  /* ── STATS ROW ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
    margin: 32px 0;
    animation: fadeUp 0.7s 0.35s ease both;
  }

  .stat-cell {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    text-align: center;
    transition: border-color 0.2s, box-shadow 0.2s;
  }

  .stat-cell:hover {
    border-color: var(--accent);
    box-shadow: var(--glow);
  }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 1.9rem;
    font-weight: 800;
    color: var(--accent);
    display: block;
    line-height: 1;
  }

  .stat-label {
    font-size: 0.65rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
    margin-top: 6px;
  }

  /* ── TECH STACK ── */
  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 0.65rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .stack-section {
    animation: fadeUp 0.7s 0.4s ease both;
    margin-bottom: 40px;
  }

  .stack-groups {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .stack-group {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 24px;
    transition: border-color 0.2s;
  }

  .stack-group:hover { border-color: rgba(0,229,255,0.2); }

  .group-label {
    font-size: 0.6rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--accent2);
    margin-bottom: 14px;
  }

  .chips {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .chip {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: rgba(0,229,255,0.05);
    border: 1px solid rgba(0,229,255,0.12);
    border-radius: 6px;
    padding: 5px 12px;
    font-size: 0.72rem;
    color: var(--text);
    transition: background 0.2s, border-color 0.2s, color 0.2s, transform 0.15s;
    cursor: default;
  }

  .chip:hover {
    background: rgba(0,229,255,0.12);
    border-color: var(--accent);
    color: #fff;
    transform: translateY(-2px);
  }

  .chip-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent);
    flex-shrink: 0;
  }

  .chip.alt .chip-dot { background: var(--accent2); }
  .chip.alt {
    background: rgba(123,97,255,0.05);
    border-color: rgba(123,97,255,0.12);
  }
  .chip.alt:hover {
    background: rgba(123,97,255,0.12);
    border-color: var(--accent2);
  }

  .chip.hot .chip-dot { background: var(--accent3); }
  .chip.hot {
    background: rgba(255,78,205,0.05);
    border-color: rgba(255,78,205,0.12);
  }
  .chip.hot:hover {
    background: rgba(255,78,205,0.12);
    border-color: var(--accent3);
  }

  /* ── STREAK CARD ── */
  .streak-section {
    animation: fadeUp 0.7s 0.45s ease both;
    margin-bottom: 40px;
  }

  .streak-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px 32px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 24px;
    flex-wrap: wrap;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, box-shadow 0.3s;
  }

  .streak-card:hover {
    border-color: var(--accent);
    box-shadow: var(--glow);
  }

  .streak-card::before {
    content: '';
    position: absolute;
    bottom: -40px; right: -40px;
    width: 160px; height: 160px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(0,229,255,0.1), transparent 70%);
    pointer-events: none;
  }

  .streak-text {}
  .streak-text h3 {
    font-family: 'Syne', sans-serif;
    font-size: 1.1rem;
    font-weight: 700;
    color: #fff;
    margin-bottom: 4px;
  }
  .streak-text p {
    font-size: 0.72rem;
    color: var(--muted);
  }

  .streak-img img {
    border-radius: 8px;
    max-width: 100%;
    height: auto;
    display: block;
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    animation: fadeUp 0.7s 0.5s ease both;
  }

  .github-link {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 100px;
    padding: 12px 28px;
    font-family: 'Space Mono', monospace;
    font-size: 0.78rem;
    color: var(--text);
    text-decoration: none;
    transition: border-color 0.2s, color 0.2s, box-shadow 0.2s, transform 0.15s;
  }

  .github-link:hover {
    border-color: var(--accent);
    color: var(--accent);
    box-shadow: var(--glow);
    transform: translateY(-2px);
  }

  .github-link svg { fill: currentColor; width: 16px; height: 16px; }

  .footer-muted {
    margin-top: 20px;
    font-size: 0.62rem;
    color: var(--muted);
    letter-spacing: 0.1em;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(22px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @media (max-width: 540px) {
    .stats-row { grid-template-columns: 1fr 1fr; }
    .streak-card { flex-direction: column; text-align: center; }
    .about-card { padding: 24px 20px; }
  }
</style>
</head>
<body>
<div class="wrapper">

  <!-- HERO -->
  <div class="hero">
    <div class="avatar-ring">
      <div class="avatar-inner">TD</div>
    </div>
    <div class="badge">Available for Opportunities</div>
    <h1>Tishan Dhanuja</h1>
    <p class="role">Trainee Software Engineer · <span>LOLC Technologies</span></p>
  </div>

  <!-- ABOUT -->
  <div class="about-card">
    <div class="card-label">about.init()</div>
    <p>
      I'm an aspiring developer eager to dive into the world of coding. I've always been captivated
      by technology's ability to shape the future. As a trainee developer, I'm here to absorb knowledge,
      tackle challenges, and grow alongside an incredible team.
      <br/><br/>
      <b>Excited to get started!</b> 🚀
    </p>
  </div>

  <!-- STATS -->
  <div class="stats-row">
    <div class="stat-cell">
      <span class="stat-num">22+</span>
      <div class="stat-label">Technologies</div>
    </div>
    <div class="stat-cell">
      <span class="stat-num" style="color:var(--accent2)">∞</span>
      <div class="stat-label">Curiosity</div>
    </div>
    <div class="stat-cell">
      <span class="stat-num" style="color:var(--accent3)">100%</span>
      <div class="stat-label">Committed</div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="stack-section">
    <div class="section-title">Languages &amp; Tools</div>
    <div class="stack-groups">

      <div class="stack-group">
        <div class="group-label">Frontend</div>
        <div class="chips">
          <span class="chip"><span class="chip-dot"></span>HTML</span>
          <span class="chip"><span class="chip-dot"></span>CSS</span>
          <span class="chip"><span class="chip-dot"></span>JavaScript</span>
          <span class="chip"><span class="chip-dot"></span>TypeScript</span>
          <span class="chip"><span class="chip-dot"></span>React</span>
          <span class="chip"><span class="chip-dot"></span>Figma</span>
        </div>
      </div>

      <div class="stack-group">
        <div class="group-label">Backend &amp; Languages</div>
        <div class="chips">
          <span class="chip alt"><span class="chip-dot"></span>Java</span>
          <span class="chip alt"><span class="chip-dot"></span>Spring Boot</span>
          <span class="chip alt"><span class="chip-dot"></span>Python</span>
          <span class="chip alt"><span class="chip-dot"></span>C++</span>
          <span class="chip alt"><span class="chip-dot"></span>MySQL</span>
          <span class="chip alt"><span class="chip-dot"></span>MongoDB</span>
        </div>
      </div>

      <div class="stack-group">
        <div class="group-label">DevOps &amp; Tooling</div>
        <div class="chips">
          <span class="chip hot"><span class="chip-dot"></span>Docker</span>
          <span class="chip hot"><span class="chip-dot"></span>Kubernetes</span>
          <span class="chip hot"><span class="chip-dot"></span>Jenkins</span>
          <span class="chip hot"><span class="chip-dot"></span>Git</span>
          <span class="chip hot"><span class="chip-dot"></span>GitHub</span>
          <span class="chip hot"><span class="chip-dot"></span>Postman</span>
          <span class="chip hot"><span class="chip-dot"></span>Selenium</span>
          <span class="chip hot"><span class="chip-dot"></span>IntelliJ IDEA</span>
        </div>
      </div>

      <div class="stack-group">
        <div class="group-label">Design</div>
        <div class="chips">
          <span class="chip"><span class="chip-dot"></span>Photoshop</span>
          <span class="chip"><span class="chip-dot"></span>Illustrator</span>
        </div>
      </div>

    </div>
  </div>

  <!-- STREAK -->
  <div class="streak-section">
    <div class="section-title">GitHub Activity</div>
    <div class="streak-card">
      <div class="streak-text">
        <h3>Contribution Streak</h3>
        <p>Consistently shipping · @TishanGamage</p>
      </div>
      <div class="streak-img">
        <img
          src="https://github-readme-streak-stats.herokuapp.com/?user=TishanGamage&theme=tokyonight&hide_border=true&background=0c1422&ring=00e5ff&fire=7b61ff&currStreakLabel=00e5ff"
          alt="Tishan GitHub Streak"
        />
      </div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <a class="github-link" href="https://github.com/TishanGamage" target="_blank">
      <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577
          0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61-.546-1.387-1.333-1.756
          -1.333-1.756-1.09-.745.083-.73.083-.73 1.205.085 1.84 1.236 1.84 1.236 1.07 1.835
          2.807 1.305 3.492.998.108-.776.418-1.305.762-1.605-2.665-.3-5.466-1.332-5.466-5.93
          0-1.31.468-2.38 1.235-3.22-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.3 1.23
          .957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.29-1.552 3.297-1.23
          3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.91 1.235 3.22 0 4.61-2.807
          5.625-5.479 5.92.43.372.823 1.102.823 2.222 0 1.606-.015 2.896-.015 3.286 0 .322.216
          .694.825.576C20.565 21.795 24 17.295 24 12c0-6.63-5.37-12-12-12z"/>
      </svg>
      @TishanGamage
    </a>
    <p class="footer-muted">⭐ Star the repo if you like the vibe</p>
  </div>

</div>
</body>
</html>
