
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Rohit Singh — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Sora:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #080c14;
    --surface: #0e1420;
    --card: #121929;
    --border: rgba(99,179,237,0.12);
    --accent: #63b3ed;
    --accent2: #9f7aea;
    --accent3: #68d391;
    --text: #e2e8f0;
    --muted: #718096;
    --highlight: #fbd38d;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Sora', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* NOISE OVERLAY */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
    opacity: 0.4;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 0 24px 80px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    position: relative;
    text-align: center;
    padding: 72px 0 56px;
    overflow: hidden;
  }
  .hero-bg {
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse 70% 60% at 50% 0%, rgba(99,179,237,0.13) 0%, transparent 70%),
                radial-gradient(ellipse 40% 30% at 80% 80%, rgba(159,122,234,0.08) 0%, transparent 60%);
    pointer-events: none;
  }
  .avatar-ring {
    width: 96px;
    height: 96px;
    margin: 0 auto 24px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    padding: 3px;
    animation: pulse-ring 3s ease-in-out infinite;
  }
  @keyframes pulse-ring {
    0%,100% { box-shadow: 0 0 0 0 rgba(99,179,237,0.3); }
    50% { box-shadow: 0 0 0 12px rgba(99,179,237,0); }
  }
  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: var(--surface);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 38px;
  }
  .hero h1 {
    font-size: clamp(2rem, 5vw, 3.2rem);
    font-weight: 800;
    letter-spacing: -0.03em;
    background: linear-gradient(135deg, #e2e8f0 30%, var(--accent) 70%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 10px;
    animation: fadeUp 0.7s ease both;
  }
  .hero-role {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.85rem;
    color: var(--accent);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 20px;
    animation: fadeUp 0.7s 0.1s ease both;
  }
  .hero-tags {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 8px;
    animation: fadeUp 0.7s 0.2s ease both;
  }
  .hero-tag {
    background: rgba(99,179,237,0.08);
    border: 1px solid rgba(99,179,237,0.2);
    color: var(--accent);
    padding: 4px 14px;
    border-radius: 999px;
    font-size: 0.78rem;
    font-weight: 500;
  }
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(18px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* ── SECTION ── */
  section { margin-bottom: 56px; animation: fadeUp 0.6s ease both; }
  .section-label {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 20px;
  }
  .section-label span:first-child {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.72rem;
    color: var(--accent);
    letter-spacing: 0.14em;
    text-transform: uppercase;
    background: rgba(99,179,237,0.08);
    border: 1px solid rgba(99,179,237,0.15);
    padding: 3px 10px;
    border-radius: 4px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, rgba(99,179,237,0.2), transparent);
  }

  /* ── ABOUT ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }
  @media(max-width:560px){ .about-grid { grid-template-columns: 1fr; } }
  .about-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 16px 18px;
    display: flex;
    align-items: flex-start;
    gap: 12px;
    transition: border-color 0.2s, transform 0.2s;
  }
  .about-item:hover { border-color: rgba(99,179,237,0.35); transform: translateY(-2px); }
  .about-icon { font-size: 1.2rem; flex-shrink: 0; margin-top: 1px; }
  .about-text { font-size: 0.88rem; color: var(--text); line-height: 1.5; }
  .about-text strong { color: var(--accent); font-weight: 600; }

  /* ── LEARNING ── */
  .learning-list {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 22px 24px;
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }
  .learning-pill {
    background: rgba(159,122,234,0.08);
    border: 1px solid rgba(159,122,234,0.2);
    color: #c4b5fd;
    padding: 5px 14px;
    border-radius: 999px;
    font-size: 0.82rem;
    font-weight: 500;
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .learning-pill::before { content: '→'; color: var(--accent2); font-size: 0.7rem; }

  /* ── TECH STACK ── */
  .stack-group { margin-bottom: 20px; }
  .stack-group-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.7rem;
    color: var(--muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .badge-grid { display: flex; flex-wrap: wrap; gap: 8px; }
  .badge {
    display: flex;
    align-items: center;
    gap: 7px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 7px 13px;
    font-size: 0.82rem;
    font-weight: 500;
    transition: border-color 0.2s, transform 0.15s, background 0.2s;
    cursor: default;
  }
  .badge:hover { border-color: rgba(99,179,237,0.4); transform: translateY(-2px); background: rgba(99,179,237,0.06); }
  .badge img { width: 16px; height: 16px; object-fit: contain; }

  /* ── STATS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }
  @media(max-width:560px){ .stats-grid { grid-template-columns: 1fr; } }
  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    overflow: hidden;
    transition: border-color 0.2s;
  }
  .stat-card:hover { border-color: rgba(99,179,237,0.3); }
  .stat-card img { width: 100%; display: block; }
  .stat-card.full { grid-column: 1 / -1; }
  .stat-placeholder {
    padding: 28px;
    text-align: center;
    color: var(--muted);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.8rem;
  }
  .stat-note {
    font-size: 0.75rem;
    color: var(--muted);
    font-family: 'JetBrains Mono', monospace;
    margin-top: 4px;
    display: block;
  }

  /* ── PROFILES & CONNECT ── */
  .link-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 12px;
  }
  .link-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 18px 16px;
    display: flex;
    align-items: center;
    gap: 12px;
    text-decoration: none;
    transition: border-color 0.2s, transform 0.2s, background 0.2s;
    color: var(--text);
  }
  .link-card:hover { border-color: rgba(99,179,237,0.4); transform: translateY(-3px); background: rgba(99,179,237,0.04); }
  .link-icon {
    width: 38px;
    height: 38px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.1rem;
    flex-shrink: 0;
  }
  .link-meta { flex: 1; min-width: 0; }
  .link-name { font-size: 0.88rem; font-weight: 600; }
  .link-sub { font-size: 0.72rem; color: var(--muted); font-family: 'JetBrains Mono', monospace; margin-top: 2px; }

  /* ── QUOTE ── */
  .quote-block {
    text-align: center;
    padding: 40px 24px;
    position: relative;
  }
  .quote-block::before {
    content: '"';
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    font-size: 8rem;
    color: rgba(99,179,237,0.07);
    font-family: Georgia, serif;
    line-height: 1;
    pointer-events: none;
  }
  .quote-text {
    font-size: 1.05rem;
    font-style: italic;
    color: var(--text);
    max-width: 560px;
    margin: 0 auto;
    line-height: 1.7;
    position: relative;
  }
  .quote-text em {
    color: var(--highlight);
    font-style: normal;
    font-weight: 600;
  }
  .quote-divider {
    width: 48px;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    margin: 14px auto 0;
    border-radius: 2px;
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding: 24px 0;
    border-top: 1px solid var(--border);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.72rem;
    color: var(--muted);
    letter-spacing: 0.08em;
  }
  .footer span { color: var(--accent2); }
</style>
</head>
<body>
<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-bg"></div>
    <div class="avatar-ring">
      <div class="avatar-inner">🧑‍💻</div>
    </div>
    <h1>Rohit Singh</h1>
    <div class="hero-role">// Computer Science Student &amp; Developer</div>
    <div class="hero-tags">
      <span class="hero-tag">Full Stack</span>
      <span class="hero-tag">Problem Solver</span>
      <span class="hero-tag">AI &amp; ML</span>
      <span class="hero-tag">DSA</span>
      <span class="hero-tag">Open Source</span>
    </div>
  </div>

  <!-- ABOUT -->
  <section style="animation-delay:0.1s">
    <div class="section-label"><span>01 · About</span></div>
    <div class="about-grid">
      <div class="about-item"><span class="about-icon">🎓</span><div class="about-text"><strong>CS Student</strong> from India, passionate about building things that matter.</div></div>
      <div class="about-item"><span class="about-icon">💻</span><div class="about-text">Interested in <strong>Software Development</strong> &amp; <strong>Artificial Intelligence</strong>.</div></div>
      <div class="about-item"><span class="about-icon">🚀</span><div class="about-text">Building projects consistently to sharpen real-world engineering skills.</div></div>
      <div class="about-item"><span class="about-icon">🎯</span><div class="about-text">Goal: Become a <strong>strong Software Engineer</strong> who ships impactful products.</div></div>
    </div>
  </section>

  <!-- LEARNING -->
  <section style="animation-delay:0.15s">
    <div class="section-label"><span>02 · Currently Learning</span></div>
    <div class="learning-list">
      <span class="learning-pill">Data Structures &amp; Algorithms</span>
      <span class="learning-pill">Full Stack Development</span>
      <span class="learning-pill">Machine Learning</span>
      <span class="learning-pill">Cloud Basics</span>
    </div>
  </section>

  <!-- TECH STACK -->
  <section style="animation-delay:0.2s">
    <div class="section-label"><span>03 · Tech Stack</span></div>

    <div class="stack-group">
      <div class="stack-group-title">Languages</div>
      <div class="badge-grid">
        <div class="badge"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt=""/>Python</div>
        <div class="badge"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" alt=""/>Java</div>
        <div class="badge"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" alt=""/>C</div>
        <div class="badge"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt=""/>JavaScript</div>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-title">Web Development</div>
      <div class="badge-grid">
        <div class="badge"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt=""/>HTML5</div>
        <div class="badge"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt=""/>CSS3</div>
        <div class="badge"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt=""/>React</div>
        <div class="badge"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" alt=""/>Node.js</div>
      </div>
    </div>

    <div class="stack-group">
      <div class="stack-group-title">Databases &amp; Tools</div>
      <div class="badge-grid">
        <div class="badge"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt=""/>MySQL</div>
        <div class="badge"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg" alt=""/>MongoDB</div>
        <div class="badge"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt=""/>Git</div>
        <div class="badge"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt=""/>GitHub</div>
        <div class="badge"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" alt=""/>VS Code</div>
      </div>
    </div>
  </section>

  <!-- GITHUB STATS -->
  <section style="animation-delay:0.25s">
    <div class="section-label"><span>04 · GitHub Stats</span></div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-placeholder">
          📊 GitHub Stats<br>
          <span class="stat-note">Replace YOUR_USERNAME in the README src</span>
        </div>
      </div>
      <div class="stat-card">
        <div class="stat-placeholder">
          🗣 Top Languages<br>
          <span class="stat-note">Replace YOUR_USERNAME in the README src</span>
        </div>
      </div>
      <div class="stat-card full">
        <div class="stat-placeholder">
          🔥 Streak Stats<br>
          <span class="stat-note">Replace YOUR_USERNAME in the README src</span>
        </div>
      </div>
    </div>
  </section>

  <!-- CODING PROFILES -->
  <section style="animation-delay:0.3s">
    <div class="section-label"><span>05 · Coding Profiles</span></div>
    <div class="link-grid">
      <a class="link-card" href="YOUR_LEETCODE_LINK" target="_blank">
        <div class="link-icon" style="background:rgba(255,161,22,0.12);">🧩</div>
        <div class="link-meta">
          <div class="link-name">LeetCode</div>
          <div class="link-sub">DSA practice</div>
        </div>
      </a>
      <a class="link-card" href="YOUR_CODECHEF_LINK" target="_blank">
        <div class="link-icon" style="background:rgba(93,64,55,0.25);">🍴</div>
        <div class="link-meta">
          <div class="link-name">CodeChef</div>
          <div class="link-sub">Competitive coding</div>
        </div>
      </a>
    </div>
  </section>

  <!-- CONNECT -->
  <section style="animation-delay:0.35s">
    <div class="section-label"><span>06 · Connect</span></div>
    <div class="link-grid">
      <a class="link-card" href="YOUR_LINKEDIN_LINK" target="_blank">
        <div class="link-icon" style="background:rgba(10,102,194,0.15);">💼</div>
        <div class="link-meta">
          <div class="link-name">LinkedIn</div>
          <div class="link-sub">Let's connect</div>
        </div>
      </a>
      <a class="link-card" href="mailto:YOUR_EMAIL">
        <div class="link-icon" style="background:rgba(234,67,53,0.12);">✉️</div>
        <div class="link-meta">
          <div class="link-name">Gmail</div>
          <div class="link-sub">Drop a message</div>
        </div>
      </a>
    </div>
  </section>

  <!-- QUOTE -->
  <div class="quote-block">
    <p class="quote-text">Consistency beats talent when <em>talent doesn't work consistently.</em></p>
    <div class="quote-divider"></div>
  </div>

  <!-- FOOTER -->
  <div class="footer">made with <span>♥</span> by rohit singh · open to opportunities</div>

</div>
</body>
</html>
