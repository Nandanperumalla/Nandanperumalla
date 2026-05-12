
<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --c1: #00ffcc;
    --c2: #7b2ff7;
    --c3: #ff3e6c;
    --c4: #f7c900;
    --dark: #050510;
    --panel: #0d0d2b;
    --panelb: #13132e;
    --muted: #6b6b9a;
    --text: #e8e8ff;
    --mono: 'JetBrains Mono', monospace;
    --display: 'Syne', sans-serif;
  }

  body { background: var(--dark); color: var(--text); font-family: var(--display); overflow-x: hidden; }

  .sr-only { position: absolute; width: 1px; height: 1px; overflow: hidden; clip: rect(0,0,0,0); }

  /* HERO */
  .hero {
    position: relative;
    padding: 48px 32px 36px;
    overflow: hidden;
    border-bottom: 1px solid #1a1a40;
  }

  .hero-grid {
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(0,255,204,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,255,204,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
  }

  .hero-glow {
    position: absolute; top: -80px; left: -80px;
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(123,47,247,0.25) 0%, transparent 70%);
    pointer-events: none;
  }
  .hero-glow2 {
    position: absolute; bottom: -60px; right: -40px;
    width: 300px; height: 300px;
    background: radial-gradient(circle, rgba(0,255,204,0.15) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-inner { position: relative; z-index: 1; }

  .status-pill {
    display: inline-flex; align-items: center; gap: 8px;
    background: rgba(0,255,204,0.08);
    border: 1px solid rgba(0,255,204,0.3);
    border-radius: 100px;
    padding: 4px 14px;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--c1);
    margin-bottom: 20px;
    letter-spacing: 0.08em;
  }
  .status-dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: var(--c1);
    animation: pulse 2s infinite;
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.85); }
  }

  .hero-name {
    font-size: 48px;
    font-weight: 800;
    line-height: 1;
    letter-spacing: -0.02em;
    margin-bottom: 6px;
  }
  .hero-name span { color: var(--c1); }
  .hero-role {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--muted);
    margin-bottom: 20px;
    letter-spacing: 0.05em;
  }
  .hero-role em { color: var(--c2); font-style: normal; }

  .hero-bio {
    font-size: 15px;
    color: #9999cc;
    line-height: 1.7;
    max-width: 520px;
    margin-bottom: 28px;
  }

  .hero-links {
    display: flex; flex-wrap: wrap; gap: 10px;
  }
  .hl {
    display: inline-flex; align-items: center; gap: 7px;
    padding: 8px 16px;
    border-radius: 8px;
    border: 1px solid;
    font-family: var(--mono);
    font-size: 12px;
    font-weight: 700;
    text-decoration: none;
    transition: transform 0.15s, box-shadow 0.15s;
    cursor: pointer;
    letter-spacing: 0.04em;
  }
  .hl:hover { transform: translateY(-2px); }
  .hl-gh { border-color: rgba(255,255,255,0.2); color: #fff; background: rgba(255,255,255,0.05); }
  .hl-gh:hover { box-shadow: 0 4px 24px rgba(255,255,255,0.08); }
  .hl-li { border-color: rgba(0,119,255,0.4); color: #4da6ff; background: rgba(0,119,255,0.07); }
  .hl-li:hover { box-shadow: 0 4px 24px rgba(0,119,255,0.15); }
  .hl-lc { border-color: rgba(247,201,0,0.4); color: var(--c4); background: rgba(247,201,0,0.07); }
  .hl-lc:hover { box-shadow: 0 4px 24px rgba(247,201,0,0.15); }
  .hl-em { border-color: rgba(255,62,108,0.4); color: var(--c3); background: rgba(255,62,108,0.07); }
  .hl-em:hover { box-shadow: 0 4px 24px rgba(255,62,108,0.15); }

  /* SECTION */
  .sec { padding: 32px; border-bottom: 1px solid #1a1a40; }
  .sec-label {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.18em;
    color: var(--muted);
    text-transform: uppercase;
    margin-bottom: 20px;
    display: flex; align-items: center; gap: 10px;
  }
  .sec-label::after { content: ''; flex: 1; height: 1px; background: #1a1a40; }

  /* STATS ROW */
  .stats-row { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; margin-bottom: 24px; }
  .stat-card {
    background: var(--panel);
    border: 1px solid #1a1a40;
    border-radius: 12px;
    padding: 16px;
    position: relative;
    overflow: hidden;
  }
  .stat-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0;
    height: 2px;
  }
  .stat-card.green::before { background: var(--c1); }
  .stat-card.purple::before { background: var(--c2); }
  .stat-card.pink::before { background: var(--c3); }
  .stat-card.yellow::before { background: var(--c4); }
  .stat-num {
    font-size: 28px;
    font-weight: 800;
    line-height: 1;
    margin-bottom: 4px;
  }
  .stat-card.green .stat-num { color: var(--c1); }
  .stat-card.purple .stat-num { color: var(--c2); }
  .stat-card.pink .stat-num { color: var(--c3); }
  .stat-card.yellow .stat-num { color: var(--c4); }
  .stat-lbl { font-family: var(--mono); font-size: 10px; color: var(--muted); letter-spacing: 0.1em; }

  /* TECH STACK */
  .tech-grid { display: flex; flex-wrap: wrap; gap: 8px; }
  .tech-tag {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 7px 13px;
    border-radius: 8px;
    border: 1px solid;
    font-family: var(--mono);
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 0.03em;
    transition: transform 0.15s;
    cursor: default;
  }
  .tech-tag:hover { transform: translateY(-2px); }
  .tech-tag.cat-frontend { border-color: rgba(0,255,204,0.3); color: var(--c1); background: rgba(0,255,204,0.06); }
  .tech-tag.cat-backend  { border-color: rgba(123,47,247,0.3); color: #a78bfa; background: rgba(123,47,247,0.06); }
  .tech-tag.cat-db       { border-color: rgba(255,62,108,0.3); color: var(--c3); background: rgba(255,62,108,0.06); }
  .tech-tag.cat-lang     { border-color: rgba(247,201,0,0.3); color: var(--c4); background: rgba(247,201,0,0.06); }
  .tech-tag.cat-tool     { border-color: #1a1a40; color: var(--muted); background: var(--panel); }

  .cat-title { font-family: var(--mono); font-size: 10px; color: var(--muted); letter-spacing: 0.15em; text-transform: uppercase; margin: 18px 0 10px; }
  .cat-title:first-child { margin-top: 0; }

  /* PROJECTS */
  .projects-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  .proj-card {
    background: var(--panel);
    border: 1px solid #1a1a40;
    border-radius: 14px;
    padding: 20px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.2s, transform 0.2s;
    cursor: pointer;
    text-decoration: none;
    display: block;
  }
  .proj-card:hover { border-color: rgba(0,255,204,0.3); transform: translateY(-3px); }
  .proj-card:hover .proj-arrow { opacity: 1; transform: translate(2px, -2px); }
  .proj-tag {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 3px 8px;
    border-radius: 4px;
    margin-bottom: 12px;
    display: inline-block;
  }
  .ts-tag { background: rgba(0,119,255,0.15); color: #60a5fa; }
  .py-tag { background: rgba(255,201,0,0.12); color: #fbbf24; }
  .jv-tag { background: rgba(255,62,108,0.12); color: var(--c3); }
  .proj-name { font-size: 15px; font-weight: 700; color: var(--text); margin-bottom: 8px; display: flex; align-items: flex-start; justify-content: space-between; gap: 8px; }
  .proj-arrow { font-size: 16px; color: var(--c1); opacity: 0; transition: opacity 0.2s, transform 0.2s; flex-shrink: 0; }
  .proj-desc { font-family: var(--mono); font-size: 11px; color: var(--muted); line-height: 1.7; }

  /* CURRENTLY */
  .currently-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  .curr-card {
    background: var(--panel);
    border: 1px solid #1a1a40;
    border-radius: 12px;
    padding: 18px;
  }
  .curr-icon { font-size: 22px; margin-bottom: 10px; }
  .curr-title { font-size: 14px; font-weight: 700; color: var(--text); margin-bottom: 6px; }
  .curr-items { list-style: none; }
  .curr-items li {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    padding: 4px 0;
    border-bottom: 1px solid #1a1a40;
    display: flex; align-items: center; gap: 6px;
  }
  .curr-items li:last-child { border-bottom: none; }
  .curr-items li::before { content: '▸'; color: var(--c1); font-size: 9px; flex-shrink: 0; }

  /* PHILOSOPHY */
  .philosophy {
    background: var(--panelb);
    border: 1px solid rgba(0,255,204,0.15);
    border-radius: 16px;
    padding: 24px;
    position: relative;
    overflow: hidden;
  }
  .philosophy::before {
    content: '"';
    position: absolute;
    top: -20px; left: 16px;
    font-size: 120px;
    color: rgba(0,255,204,0.06);
    font-family: Georgia, serif;
    line-height: 1;
    pointer-events: none;
  }
  .philosophy p {
    font-size: 15px;
    line-height: 1.8;
    color: #b8b8e8;
    font-style: italic;
    position: relative;
  }
  .philosophy cite {
    display: block;
    margin-top: 12px;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--c1);
    font-style: normal;
    letter-spacing: 0.08em;
  }

  /* ROUTINE */
  .routine { display: flex; gap: 12px; margin-top: 20px; }
  .routine-step {
    flex: 1;
    background: var(--panel);
    border: 1px solid #1a1a40;
    border-radius: 12px;
    padding: 16px;
    display: flex; flex-direction: column; align-items: center; text-align: center; gap: 8px;
  }
  .routine-icon { font-size: 20px; }
  .routine-time { font-family: var(--mono); font-size: 10px; color: var(--c1); letter-spacing: 0.1em; text-transform: uppercase; }
  .routine-act { font-size: 12px; color: var(--muted); line-height: 1.5; }

  /* GOALS */
  .goals-list { display: flex; flex-direction: column; gap: 10px; }
  .goal-item {
    display: flex; align-items: center; gap: 14px;
    background: var(--panel);
    border: 1px solid #1a1a40;
    border-radius: 10px;
    padding: 14px 16px;
    font-size: 13px;
    color: #b8b8e8;
  }
  .goal-num {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--c2);
    font-weight: 700;
    min-width: 28px;
    background: rgba(123,47,247,0.15);
    border-radius: 6px;
    text-align: center;
    padding: 3px 0;
  }

  /* OPEN FOR */
  .open-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
  .open-item {
    background: var(--panel);
    border: 1px solid #1a1a40;
    border-radius: 10px;
    padding: 14px;
    display: flex; flex-direction: column; gap: 6px;
  }
  .open-ico { font-size: 18px; }
  .open-title { font-size: 12px; font-weight: 700; color: var(--text); }
  .open-sub { font-family: var(--mono); font-size: 10px; color: var(--muted); line-height: 1.5; }

  /* FUN FACTS */
  .facts-row { display: flex; flex-direction: column; gap: 8px; }
  .fact {
    display: flex; align-items: center; gap: 12px;
    font-family: var(--mono);
    font-size: 12px;
    color: var(--muted);
    padding: 10px 14px;
    background: var(--panel);
    border: 1px solid #1a1a40;
    border-radius: 8px;
  }
  .fact-icon { font-size: 16px; flex-shrink: 0; }

  /* FOOTER */
  .footer {
    padding: 28px 32px;
    text-align: center;
  }
  .footer-quote {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--muted);
    margin-bottom: 16px;
  }
  .footer-quote span { color: var(--c1); }
  .footer-tag {
    display: inline-block;
    font-family: var(--mono);
    font-size: 10px;
    color: rgba(123,47,247,0.6);
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  /* GITHUB STATS SECTION */
  .gh-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }
  .gh-img {
    border-radius: 10px;
    overflow: hidden;
    background: var(--panel);
    border: 1px solid #1a1a40;
    display: flex; align-items: center; justify-content: center;
  }
  .gh-img img { width: 100%; display: block; }
  .gh-full { grid-column: 1 / -1; }

  /* ANIMATE IN */
  .fade-in { animation: fadeIn 0.6s ease both; }
  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(16px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .d1 { animation-delay: 0.05s; }
  .d2 { animation-delay: 0.1s; }
  .d3 { animation-delay: 0.15s; }
  .d4 { animation-delay: 0.2s; }
  .d5 { animation-delay: 0.25s; }
</style>

<h2 class="sr-only">Nandan Perumalla — Portfolio & GitHub Profile</h2>

<!-- HERO -->
<div class="hero fade-in d1">
  <div class="hero-grid"></div>
  <div class="hero-glow"></div>
  <div class="hero-glow2"></div>
  <div class="hero-inner">
    <div class="status-pill"><div class="status-dot"></div>Available for opportunities</div>
    <div class="hero-name">NANDAN<br><span>PERUMALLA</span></div>
    <div class="hero-role">CSE Student @ <em>SRM AP</em> &nbsp;·&nbsp; Full-Stack Developer &nbsp;·&nbsp; Algorithm Enthusiast</div>
    <div class="hero-bio">Passionate Computer Science Engineering student from India who lives and breathes code. On a mission to solve real-world problems through technology — one commit at a time.</div>
    <div class="hero-links">
      <a class="hl hl-gh" href="https://github.com/Nandanperumalla" target="_blank"><i class="ti ti-brand-github" aria-hidden="true"></i>GitHub</a>
      <a class="hl hl-li" href="https://www.linkedin.com/in/nandan-perumalla-580a78319/" target="_blank"><i class="ti ti-brand-linkedin" aria-hidden="true"></i>LinkedIn</a>
      <a class="hl hl-lc" href="https://leetcode.com/u/nandan15/" target="_blank"><i class="ti ti-code" aria-hidden="true"></i>LeetCode</a>
      <a class="hl hl-em" href="mailto:nandanperumalla15@gmail.com"><i class="ti ti-mail" aria-hidden="true"></i>Email</a>
    </div>
  </div>
</div>

<!-- STATS -->
<div class="sec fade-in d2">
  <div class="sec-label">at a glance</div>
  <div class="stats-row">
    <div class="stat-card green"><div class="stat-num">14</div><div class="stat-lbl">REPOSITORIES</div></div>
    <div class="stat-card purple"><div class="stat-num">100+</div><div class="stat-lbl">PROBLEMS SOLVED</div></div>
    <div class="stat-card pink"><div class="stat-num">4+</div><div class="stat-lbl">LIVE PROJECTS</div></div>
    <div class="stat-card yellow"><div class="stat-num">∞</div><div class="stat-lbl">COFFEES CONSUMED</div></div>
  </div>

  <!-- GitHub Stats Images -->
  <div class="gh-stats">
    <div class="gh-img">
      <img src="https://github-readme-stats.vercel.app/api?username=Nandanperumalla&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true&bg_color=0d0d2b&title_color=00ffcc&icon_color=7b2ff7&text_color=9999cc" alt="GitHub Stats" loading="lazy"/>
    </div>
    <div class="gh-img">
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Nandanperumalla&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d0d2b&title_color=00ffcc&text_color=9999cc" alt="Top Languages" loading="lazy"/>
    </div>
    <div class="gh-img gh-full">
      <img src="https://streak-stats.demolab.com?user=Nandanperumalla&theme=tokyonight&hide_border=true&background=0d0d2b&ring=00ffcc&fire=7b2ff7&currStreakLabel=00ffcc&sideLabels=9999cc&sideNums=e8e8ff&dates=6b6b9a" alt="GitHub Streak" loading="lazy"/>
    </div>
  </div>
</div>

<!-- TECH STACK -->
<div class="sec fade-in d3">
  <div class="sec-label">technology stack</div>
  <div class="cat-title">Frontend</div>
  <div class="tech-grid">
    <span class="tech-tag cat-frontend"><i class="ti ti-brand-html5" aria-hidden="true"></i>HTML5</span>
    <span class="tech-tag cat-frontend"><i class="ti ti-brand-css3" aria-hidden="true"></i>CSS3</span>
    <span class="tech-tag cat-frontend"><i class="ti ti-brand-javascript" aria-hidden="true"></i>JavaScript</span>
    <span class="tech-tag cat-frontend"><i class="ti ti-brand-react" aria-hidden="true"></i>React</span>
  </div>
  <div class="cat-title">Backend</div>
  <div class="tech-grid">
    <span class="tech-tag cat-backend"><i class="ti ti-brand-nodejs" aria-hidden="true"></i>Node.js</span>
    <span class="tech-tag cat-backend"><i class="ti ti-server" aria-hidden="true"></i>Express.js</span>
    <span class="tech-tag cat-backend"><i class="ti ti-brand-python" aria-hidden="true"></i>Python</span>
    <span class="tech-tag cat-backend"><i class="ti ti-coffee" aria-hidden="true"></i>Java</span>
  </div>
  <div class="cat-title">Databases</div>
  <div class="tech-grid">
    <span class="tech-tag cat-db"><i class="ti ti-database" aria-hidden="true"></i>MongoDB</span>
    <span class="tech-tag cat-db"><i class="ti ti-database" aria-hidden="true"></i>MySQL</span>
  </div>
  <div class="cat-title">Problem Solving</div>
  <div class="tech-grid">
    <span class="tech-tag cat-lang"><i class="ti ti-code" aria-hidden="true"></i>C++</span>
    <span class="tech-tag cat-lang"><i class="ti ti-brand-python" aria-hidden="true"></i>Python</span>
    <span class="tech-tag cat-lang"><i class="ti ti-coffee" aria-hidden="true"></i>Java</span>
  </div>
  <div class="cat-title">Tools</div>
  <div class="tech-grid">
    <span class="tech-tag cat-tool"><i class="ti ti-brand-git" aria-hidden="true"></i>Git</span>
    <span class="tech-tag cat-tool"><i class="ti ti-brand-github" aria-hidden="true"></i>GitHub</span>
    <span class="tech-tag cat-tool"><i class="ti ti-brand-vscode" aria-hidden="true"></i>VS Code</span>
  </div>
</div>

<!-- PROJECTS -->
<div class="sec fade-in d3">
  <div class="sec-label">featured projects</div>
  <div class="projects-grid">
    <a class="proj-card" href="https://github.com/Nandanperumalla/JusticeGPT" target="_blank">
      <span class="proj-tag ts-tag">TypeScript</span>
      <div class="proj-name">JusticeGPT <span class="proj-arrow">↗</span></div>
      <div class="proj-desc">AI-powered legal education platform for India — IPC analysis, constitutional articles, case templates with multi-language support.</div>
    </a>
    <a class="proj-card" href="https://github.com/Nandanperumalla/Genome_Ownership_platform" target="_blank">
      <span class="proj-tag ts-tag">TypeScript</span>
      <div class="proj-name">Genome Ownership <span class="proj-arrow">↗</span></div>
      <div class="proj-desc">Decentralized genome ownership via blockchain — stores genetic data and mints NFT tokens for true data sovereignty.</div>
    </a>
    <a class="proj-card" href="https://github.com/Nandanperumalla/Smart-home-autmation-system" target="_blank">
      <span class="proj-tag py-tag">Python</span>
      <div class="proj-name">Smart Home Automation <span class="proj-arrow">↗</span></div>
      <div class="proj-desc">Intelligent home automation system built with Python — control and monitor your environment programmatically.</div>
    </a>
    <a class="proj-card" href="https://github.com/Nandanperumalla/House-price-Prediction-ML" target="_blank">
      <span class="proj-tag py-tag">Python / ML</span>
      <div class="proj-name">House Price Predictor <span class="proj-arrow">↗</span></div>
      <div class="proj-desc">ML model estimating property prices from bedrooms, area, ZIP, year & tax — Streamlit UI with full preprocessing pipeline.</div>
    </a>
    <a class="proj-card" href="https://github.com/Nandanperumalla/treasure-hunt-" target="_blank" style="grid-column: 1 / -1;">
      <span class="proj-tag jv-tag">Java</span>
      <div class="proj-name">Treasure Hunt Game <span class="proj-arrow">↗</span></div>
      <div class="proj-desc">A Java-based interactive treasure hunt game — built for fun and showcasing OOP design patterns and game logic.</div>
    </a>
  </div>
</div>

<!-- CURRENTLY & ROUTINE -->
<div class="sec fade-in d4">
  <div class="sec-label">what I'm up to</div>
  <div class="currently-grid">
    <div class="curr-card">
      <div class="curr-icon">🏗️</div>
      <div class="curr-title">Building</div>
      <ul class="curr-items">
        <li>Full-stack e-commerce platform</li>
        <li>Personal portfolio website</li>
        <li>Algorithm visualization tools</li>
      </ul>
    </div>
    <div class="curr-card">
      <div class="curr-icon">📚</div>
      <div class="curr-title">Learning</div>
      <ul class="curr-items">
        <li>Advanced system design patterns</li>
        <li>Microservices architecture</li>
        <li>Cloud computing (AWS/Azure)</li>
        <li>GraphQL & modern APIs</li>
      </ul>
    </div>
    <div class="curr-card">
      <div class="curr-icon">🧠</div>
      <div class="curr-title">Mastering</div>
      <ul class="curr-items">
        <li>Data structures & algorithms</li>
        <li>Design patterns</li>
        <li>System design principles</li>
      </ul>
    </div>
    <div class="curr-card">
      <div class="curr-icon">🤝</div>
      <div class="curr-title">Contributing</div>
      <ul class="curr-items">
        <li>Open source React libraries</li>
        <li>Tech communities</li>
        <li>Mentoring developers</li>
      </ul>
    </div>
  </div>

  <div class="routine" style="margin-top: 20px;">
    <div class="routine-step">
      <div class="routine-icon">🌅</div>
      <div class="routine-time">Morning</div>
      <div class="routine-act">Solve 2–3 LeetCode problems</div>
    </div>
    <div class="routine-step">
      <div class="routine-icon">💡</div>
      <div class="routine-time">Afternoon</div>
      <div class="routine-act">Build projects & learn new tech</div>
    </div>
    <div class="routine-step">
      <div class="routine-icon">🌙</div>
      <div class="routine-time">Evening</div>
      <div class="routine-act">Review solutions & explore algorithms</div>
    </div>
  </div>
</div>

<!-- PHILOSOPHY -->
<div class="sec fade-in d4">
  <div class="sec-label">philosophy</div>
  <div class="philosophy">
    <p>Every problem is an opportunity to learn something new. I don't just solve problems — I understand them, break them down, and find the most elegant solution possible.</p>
    <cite>— Nandan Perumalla &nbsp;·&nbsp; Code → Learn → Build → Repeat ♾️</cite>
  </div>
</div>

<!-- GOALS -->
<div class="sec fade-in d4">
  <div class="sec-label">goals 2025</div>
  <div class="goals-list">
    <div class="goal-item"><span class="goal-num">01</span>Contribute to 10+ open source projects</div>
    <div class="goal-item"><span class="goal-num">02</span>Build 3 production-ready applications</div>
    <div class="goal-item"><span class="goal-num">03</span>Master system design principles</div>
    <div class="goal-item"><span class="goal-num">04</span>Help 100+ developers through mentoring</div>
  </div>
</div>

<!-- OPEN FOR -->
<div class="sec fade-in d5">
  <div class="sec-label">open for</div>
  <div class="open-grid">
    <div class="open-item"><div class="open-ico">💼</div><div class="open-title">Internships & Jobs</div><div class="open-sub">Full-time or intern roles in software engineering</div></div>
    <div class="open-item"><div class="open-ico">🚀</div><div class="open-title">Collaborations</div><div class="open-sub">Exciting projects worth building together</div></div>
    <div class="open-item"><div class="open-ico">👥</div><div class="open-title">Open Source</div><div class="open-sub">Contributing to impactful OSS projects</div></div>
    <div class="open-item"><div class="open-ico">💡</div><div class="open-title">Tech Discussions</div><div class="open-sub">Ideas, architecture, mentorship</div></div>
    <div class="open-item"><div class="open-ico">🎯</div><div class="open-title">Hackathons</div><div class="open-sub">Competitive coding & build sprints</div></div>
    <div class="open-item"><div class="open-ico">🌍</div><div class="open-title">Remote Work</div><div class="open-sub">Open to remote collaboration globally</div></div>
  </div>
</div>

<!-- FUN FACTS -->
<div class="sec fade-in d5">
  <div class="sec-label">fun facts</div>
  <div class="facts-row">
    <div class="fact"><span class="fact-icon">🎯</span>Solved 100+ coding problems and still counting</div>
    <div class="fact"><span class="fact-icon">☕</span>Code-to-coffee ratio: approximately 100:1</div>
    <div class="fact"><span class="fact-icon">🌙</span>Most productive during late-night coding sessions</div>
    <div class="fact"><span class="fact-icon">🎮</span>Treats debugging like a puzzle game — and loves winning</div>
    <div class="fact"><span class="fact-icon">🚀</span>Dream: Build products that impact millions of lives</div>
  </div>
</div>

<!-- FOOTER -->
<div class="footer fade-in d5">
  <div class="footer-quote">"Code is like humor. When you have to explain it, it's bad." <span>— Cory House</span></div>
  <div class="footer-tag">thanks for visiting · let's build something amazing</div>
</div>
