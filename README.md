<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>A. Nalla Perumal — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700;800&family=Space+Grotesk:wght@300;400;600;700&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0d1117;
    --bg2: #0f3460;
    --bg3: #16213e;
    --bg4: #1a1a2e;
    --cyan: #00d4ff;
    --gold: #ffd700;
    --orange: #ff6b35;
    --purple: #7c3aed;
    --green: #00ff88;
    --text: #c9d1d9;
    --text2: #8b949e;
    --white: #ffffff;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Space Grotesk', sans-serif;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* HEADER WAVE */
  .header-wave {
    width: 100%;
    background: linear-gradient(135deg, var(--bg) 0%, var(--bg2) 30%, var(--bg3) 60%, var(--bg4) 100%);
    padding: 60px 20px 40px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .header-wave::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse 80% 60% at 50% 0%, rgba(0,212,255,0.12) 0%, transparent 70%);
  }
  .header-wave::after {
    content: '';
    position: absolute;
    bottom: -1px; left: 0; right: 0;
    height: 60px;
    background: var(--bg);
    clip-path: ellipse(55% 100% at 50% 100%);
  }
  .header-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: clamp(28px, 7vw, 56px);
    font-weight: 800;
    color: var(--cyan);
    letter-spacing: 2px;
    text-shadow: 0 0 30px rgba(0,212,255,0.5), 0 0 60px rgba(0,212,255,0.2);
    position: relative;
    z-index: 1;
    animation: fadeInDown 0.8s ease;
  }
  .header-desc {
    font-family: 'JetBrains Mono', monospace;
    font-size: clamp(11px, 2.5vw, 15px);
    color: var(--text2);
    margin-top: 10px;
    position: relative; z-index: 1;
    animation: fadeInUp 0.8s ease 0.2s both;
  }

  /* TYPING ANIMATION */
  .typing-wrap {
    text-align: center;
    padding: 20px 16px 0;
    min-height: 44px;
  }
  .typing-text {
    font-family: 'JetBrains Mono', monospace;
    font-size: clamp(14px, 3.5vw, 22px);
    font-weight: 800;
    color: var(--cyan);
    border-right: 3px solid var(--cyan);
    white-space: nowrap;
    overflow: hidden;
    display: inline-block;
    animation: blink 0.7s step-end infinite;
  }

  /* BADGES SECTION */
  .badges-section { padding: 24px 16px 0; }
  .badges-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
    margin-bottom: 10px;
  }
  .badge {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    padding: 7px 14px;
    border-radius: 8px;
    font-family: 'JetBrains Mono', monospace;
    font-size: clamp(10px, 2.2vw, 13px);
    font-weight: 700;
    background: var(--bg4);
    border: 1px solid rgba(255,255,255,0.08);
    transition: transform 0.2s, box-shadow 0.2s;
    cursor: default;
    white-space: nowrap;
  }
  .badge:hover { transform: translateY(-2px); box-shadow: 0 4px 16px rgba(0,212,255,0.15); }
  .badge .dot { width: 8px; height: 8px; border-radius: 50%; flex-shrink: 0; }
  .badge.cyan { color: var(--cyan); border-color: rgba(0,212,255,0.3); }
  .badge.gold { color: var(--gold); border-color: rgba(255,215,0,0.3); }
  .badge.green { color: var(--green); border-color: rgba(0,255,136,0.3); }
  .badge.orange { color: var(--orange); border-color: rgba(255,107,53,0.3); }
  .badge.purple { color: #a78bfa; border-color: rgba(124,58,237,0.3); }

  /* SECTION TITLE */
  .section-title {
    text-align: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: clamp(16px, 4vw, 22px);
    font-weight: 800;
    color: var(--white);
    padding: 36px 16px 16px;
    position: relative;
  }
  .section-title span { color: var(--cyan); }
  .section-title::after {
    content: '';
    display: block;
    width: 60px; height: 3px;
    background: linear-gradient(90deg, var(--cyan), transparent);
    margin: 8px auto 0;
    border-radius: 2px;
  }

  /* SKILL PROGRESS */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 14px;
    padding: 0 16px 20px;
    max-width: 1100px;
    margin: 0 auto;
  }
  .skill-card {
    background: var(--bg4);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 12px;
    padding: 14px 18px;
    transition: transform 0.2s, border-color 0.2s;
  }
  .skill-card:hover { transform: translateY(-3px); border-color: rgba(0,212,255,0.3); }
  .skill-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 8px;
  }
  .skill-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    font-weight: 700;
    color: var(--white);
  }
  .skill-pct {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    font-weight: 700;
    color: var(--cyan);
  }
  .skill-bar {
    height: 6px;
    background: rgba(255,255,255,0.08);
    border-radius: 3px;
    overflow: hidden;
  }
  .skill-fill {
    height: 100%;
    border-radius: 3px;
    background: linear-gradient(90deg, var(--cyan), var(--purple));
    transform-origin: left;
    animation: fillBar 1.2s ease-out both;
  }

  /* STATS SECTION */
  .stats-wrap {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 16px;
    padding: 0 16px 20px;
    max-width: 1100px;
    margin: 0 auto;
  }
  .stat-card {
    background: var(--bg4);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 14px;
    overflow: hidden;
    transition: transform 0.2s;
  }
  .stat-card:hover { transform: translateY(-3px); }
  .stat-card img { width: 100%; display: block; }
  .stat-card-wide { grid-column: 1 / -1; }

  /* TECH STACK */
  .tech-section { padding: 0 16px 20px; max-width: 900px; margin: 0 auto; }
  .tech-category { margin-bottom: 22px; }
  .tech-category-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    font-weight: 700;
    color: var(--text2);
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 12px;
    padding-left: 4px;
    border-left: 3px solid var(--cyan);
    padding-left: 10px;
  }
  .tech-icons {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    align-items: center;
  }
  .tech-chip {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 12px;
    background: var(--bg4);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 8px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 600;
    color: var(--text);
    transition: all 0.2s;
    white-space: nowrap;
  }
  .tech-chip:hover { border-color: var(--cyan); color: var(--cyan); transform: translateY(-2px); }

  /* REPO TABLE */
  .repo-table-wrap { padding: 0 16px 20px; max-width: 1100px; margin: 0 auto; overflow-x: auto; }
  .repo-table {
    width: 100%;
    border-collapse: collapse;
    font-family: 'JetBrains Mono', monospace;
    font-size: clamp(10px, 2vw, 13px);
  }
  .repo-table thead tr {
    background: rgba(0,212,255,0.08);
    border-bottom: 2px solid rgba(0,212,255,0.3);
  }
  .repo-table th {
    padding: 12px 16px;
    text-align: left;
    color: var(--cyan);
    font-weight: 700;
    white-space: nowrap;
  }
  .repo-table tbody tr {
    border-bottom: 1px solid rgba(255,255,255,0.05);
    transition: background 0.2s;
  }
  .repo-table tbody tr:hover { background: rgba(0,212,255,0.04); }
  .repo-table td { padding: 11px 16px; color: var(--text); vertical-align: middle; }
  .repo-table td a {
    color: var(--cyan);
    text-decoration: none;
    font-size: 11px;
    border: 1px solid rgba(0,212,255,0.3);
    padding: 3px 8px;
    border-radius: 5px;
    transition: all 0.2s;
  }
  .repo-table td a:hover { background: rgba(0,212,255,0.1); }

  /* FEATURED PROJECTS */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 16px;
    padding: 0 16px 20px;
    max-width: 1100px;
    margin: 0 auto;
  }
  .project-card {
    background: var(--bg4);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 14px;
    padding: 22px;
    transition: transform 0.2s, border-color 0.2s, box-shadow 0.2s;
  }
  .project-card:hover {
    transform: translateY(-4px);
    border-color: rgba(0,212,255,0.35);
    box-shadow: 0 8px 32px rgba(0,212,255,0.1);
  }
  .project-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 15px;
    font-weight: 800;
    color: var(--white);
    margin-bottom: 6px;
  }
  .project-desc {
    font-size: 12px;
    color: var(--text2);
    margin-bottom: 14px;
  }
  .project-features { list-style: none; margin-bottom: 14px; }
  .project-features li {
    font-size: 12px;
    color: var(--text);
    padding: 3px 0;
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .project-features li::before { content: '▸'; color: var(--cyan); font-size: 10px; }
  .project-tags { display: flex; flex-wrap: wrap; gap: 6px; }
  .tag {
    padding: 3px 9px;
    border-radius: 5px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    font-weight: 700;
    background: rgba(255,255,255,0.05);
    border: 1px solid rgba(255,255,255,0.1);
    color: var(--text2);
  }

  /* QUOTE */
  .quote-wrap {
    max-width: 700px;
    margin: 0 auto;
    padding: 20px 24px;
    text-align: center;
  }
  .quote-text {
    font-style: italic;
    color: var(--text2);
    font-size: clamp(13px, 2.5vw, 16px);
    line-height: 1.7;
    border-left: 3px solid var(--cyan);
    padding: 16px 20px;
    background: var(--bg4);
    border-radius: 0 12px 12px 0;
    text-align: left;
  }
  .quote-author {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--cyan);
    margin-top: 8px;
    text-align: right;
  }

  /* CONNECT */
  .connect-wrap {
    text-align: center;
    padding: 16px 16px 30px;
  }
  .connect-buttons {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
    margin-top: 14px;
  }
  .connect-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 20px;
    border-radius: 10px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    font-weight: 700;
    color: var(--white);
    text-decoration: none;
    border: 1px solid rgba(255,255,255,0.12);
    background: var(--bg4);
    transition: all 0.2s;
    cursor: pointer;
  }
  .connect-btn:hover { transform: translateY(-3px); box-shadow: 0 6px 20px rgba(0,0,0,0.3); }
  .connect-btn.gmail { border-color: rgba(209,72,54,0.5); }
  .connect-btn.gmail:hover { background: rgba(209,72,54,0.1); }
  .connect-btn.linkedin { border-color: rgba(0,119,181,0.5); }
  .connect-btn.linkedin:hover { background: rgba(0,119,181,0.1); }
  .connect-btn.whatsapp { border-color: rgba(37,211,102,0.5); }
  .connect-btn.whatsapp:hover { background: rgba(37,211,102,0.1); }
  .connect-btn.portfolio { border-color: rgba(255,255,255,0.3); }
  .connect-btn.portfolio:hover { background: rgba(255,255,255,0.05); }
  .connect-btn.github { border-color: rgba(255,255,255,0.3); }
  .connect-btn.github:hover { background: rgba(255,255,255,0.05); }

  /* FOOTER WAVE */
  .footer-wave {
    width: 100%;
    background: linear-gradient(135deg, var(--bg) 0%, var(--bg2) 50%, var(--cyan) 100%);
    padding: 40px 20px 24px;
    text-align: center;
    clip-path: ellipse(100% 100% at 50% 100%);
    margin-top: 20px;
  }
  .star-badge {
    display: inline-block;
    padding: 10px 24px;
    background: rgba(0,212,255,0.12);
    border: 1px solid var(--cyan);
    border-radius: 10px;
    font-family: 'JetBrains Mono', monospace;
    font-size: clamp(10px, 2.5vw, 13px);
    font-weight: 700;
    color: var(--cyan);
    margin-bottom: 16px;
    animation: pulse 2s ease-in-out infinite;
  }

  /* DIVIDER */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(0,212,255,0.3), transparent);
    margin: 16px 0;
  }

  /* ANIMATIONS */
  @keyframes fadeInDown { from { opacity:0; transform:translateY(-20px); } to { opacity:1; transform:translateY(0); } }
  @keyframes fadeInUp   { from { opacity:0; transform:translateY(20px); }  to { opacity:1; transform:translateY(0); } }
  @keyframes blink      { 50% { border-color: transparent; } }
  @keyframes fillBar    { from { width: 0; } to { width: var(--w); } }
  @keyframes pulse      { 0%,100% { box-shadow: 0 0 0 0 rgba(0,212,255,0.3); } 50% { box-shadow: 0 0 0 8px rgba(0,212,255,0); } }

  /* RESPONSIVE TWEAKS */
  @media (max-width: 480px) {
    .skills-grid { grid-template-columns: 1fr; }
    .stats-wrap   { grid-template-columns: 1fr; }
    .projects-grid{ grid-template-columns: 1fr; }
    .repo-table th, .repo-table td { padding: 8px 10px; }
    .header-wave  { padding: 40px 16px 30px; }
  }
</style>
</head>
<body>

<!-- HEADER -->
<div class="header-wave">
  <div class="header-name">A. NALLA PERUMAL</div>
  <div class="header-desc">⚡ Full Stack Developer &nbsp;|&nbsp; 275+ Repositories &nbsp;|&nbsp; Open Source Enthusiast</div>
</div>

<!-- TYPING -->
<div class="typing-wrap">
  <span class="typing-text" id="typer"></span>
</div>

<!-- BADGES -->
<div class="badges-section">
  <div class="badges-row">
    <span class="badge cyan">👁️ Profile Views &nbsp;·&nbsp; Live</span>
    <span class="badge cyan">👥 Followers</span>
    <span class="badge gold">⭐ Total Stars</span>
    <span class="badge cyan">📦 Public Repos</span>
  </div>
  <div class="badges-row">
    <span class="badge purple">📝 Public Gists</span>
    <span class="badge cyan">💼 Experience · 3+ Years</span>
    <span class="badge green">🚀 Status · Open to Work</span>
    <span class="badge orange">🌍 Location · India</span>
  </div>
</div>

<!-- CONTRIBUTION GRAPH -->
<div class="section-title">🌆 3D Contribution Graph</div>
<div style="padding:0 16px 20px;max-width:1100px;margin:0 auto;">
  <div class="stat-card stat-card-wide">
    <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=nallaperumal007&theme=github_dark" alt="Profile Details" loading="lazy"/>
  </div>
</div>

<!-- SKILL PROGRESS -->
<div class="section-title">💻 <span>Skill Progress</span></div>
<div class="skills-grid">
  <div class="skill-card">
    <div class="skill-top"><span class="skill-name">MERN Stack</span><span class="skill-pct">90%</span></div>
    <div class="skill-bar"><div class="skill-fill" style="--w:90%; width:90%;"></div></div>
  </div>
  <div class="skill-card">
    <div class="skill-top"><span class="skill-name">Laravel / PHP</span><span class="skill-pct">90%</span></div>
    <div class="skill-bar"><div class="skill-fill" style="--w:90%; width:90%;"></div></div>
  </div>
  <div class="skill-card">
    <div class="skill-top"><span class="skill-name">Next.js / React</span><span class="skill-pct">90%</span></div>
    <div class="skill-bar"><div class="skill-fill" style="--w:90%; width:90%;"></div></div>
  </div>
  <div class="skill-card">
    <div class="skill-top"><span class="skill-name">MEAN Stack</span><span class="skill-pct">70%</span></div>
    <div class="skill-bar"><div class="skill-fill" style="--w:70%; width:70%;"></div></div>
  </div>
  <div class="skill-card">
    <div class="skill-top"><span class="skill-name">Spring Boot</span><span class="skill-pct">70%</span></div>
    <div class="skill-bar"><div class="skill-fill" style="--w:70%; width:70%;"></div></div>
  </div>
  <div class="skill-card">
    <div class="skill-top"><span class="skill-name">Flutter</span><span class="skill-pct">70%</span></div>
    <div class="skill-bar"><div class="skill-fill" style="--w:70%; width:70%;"></div></div>
  </div>
  <div class="skill-card">
    <div class="skill-top"><span class="skill-name">React Native</span><span class="skill-pct">70%</span></div>
    <div class="skill-bar"><div class="skill-fill" style="--w:70%; width:70%;"></div></div>
  </div>
</div>

<!-- STATS DASHBOARD -->
<div class="section-title">🔴 LIVE — GitHub Real-Time Dashboard</div>
<div class="stats-wrap">
  <div class="stat-card">
    <img src="https://github-readme-stats.vercel.app/api?username=nallaperumal007&show_icons=true&theme=github_dark&hide_border=true&count_private=true&bg_color=0d1117&title_color=00d4ff&icon_color=00d4ff&text_color=c9d1d9&include_all_commits=true" alt="GitHub Stats" loading="lazy"/>
  </div>
  <div class="stat-card">
    <img src="https://github-readme-streak-stats.herokuapp.com/?user=nallaperumal007&theme=github-dark-blue&hide_border=true&background=0d1117&stroke=00d4ff&ring=00d4ff&fire=ff6b35&currStreakLabel=00d4ff&sideLabels=c9d1d9&dates=8b949e&currStreakNum=ffffff&sideNums=ffffff" alt="Streak Stats" loading="lazy"/>
  </div>
  <div class="stat-card">
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=nallaperumal007&layout=donut&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=00d4ff&text_color=c9d1d9&langs_count=12" alt="Top Langs Donut" loading="lazy"/>
  </div>
  <div class="stat-card">
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=nallaperumal007&layout=compact&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=00d4ff&text_color=c9d1d9&langs_count=12" alt="Top Langs Compact" loading="lazy"/>
  </div>
  <div class="stat-card stat-card-wide">
    <img src="https://github-readme-activity-graph.vercel.app/graph?username=nallaperumal007&bg_color=0d1117&color=00d4ff&line=0f3460&point=00d4ff&area_color=00d4ff&area=true&hide_border=true&custom_title=Nalla+Perumal%27s+Contribution+Graph+(Live)" alt="Activity Graph" loading="lazy"/>
  </div>
</div>

<!-- PROFILE SUMMARY CARDS -->
<div class="section-title">📊 Profile Summary — Live Analytics</div>
<div style="display:flex;flex-wrap:wrap;gap:14px;padding:0 16px 20px;max-width:1100px;margin:0 auto;justify-content:center;">
  <div style="flex:1;min-width:200px;max-width:260px;" class="stat-card">
    <img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=nallaperumal007&theme=github_dark" alt="Repos Per Language" loading="lazy"/>
  </div>
  <div style="flex:1;min-width:200px;max-width:260px;" class="stat-card">
    <img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=nallaperumal007&theme=github_dark" alt="Most Commit Language" loading="lazy"/>
  </div>
  <div style="flex:1;min-width:200px;max-width:260px;" class="stat-card">
    <img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=nallaperumal007&theme=github_dark" alt="Stats" loading="lazy"/>
  </div>
  <div style="flex:1;min-width:200px;max-width:260px;" class="stat-card">
    <img src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=nallaperumal007&theme=github_dark&utcOffset=5.5" alt="Productive Time" loading="lazy"/>
  </div>
</div>

<div class="divider" style="max-width:1100px;margin:0 auto;"></div>

<!-- REPO TABLE -->
<div class="section-title">📦 Live Framework & Technology Repository Counter</div>
<div class="repo-table-wrap">
  <table class="repo-table">
    <thead>
      <tr>
        <th>🔧 Technology</th>
        <th>📊 Live Badge</th>
        <th>🔗 Browse</th>
      </tr>
    </thead>
    <tbody>
      <tr><td>🔴 Laravel / PHP</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+laravel+in:name,description,topics&query=$.total_count&label=Repos&style=flat-square&color=FF2D20&labelColor=0d1117" alt="Laravel"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&q=laravel" target="_blank">View →</a></td></tr>
      <tr><td>⚛️ React.js</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+react+in:name,description,topics&query=$.total_count&label=Repos&style=flat-square&color=61DAFB&labelColor=0d1117" alt="React"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&q=react" target="_blank">View →</a></td></tr>
      <tr><td>▲ Next.js</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+next+in:name,description,topics&query=$.total_count&label=Repos&style=flat-square&color=ffffff&labelColor=0d1117" alt="Next"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&q=next" target="_blank">View →</a></td></tr>
      <tr><td>🟢 Node.js / Express</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+node+in:name,description,topics&query=$.total_count&label=Repos&style=flat-square&color=339933&labelColor=0d1117" alt="Node"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&q=node" target="_blank">View →</a></td></tr>
      <tr><td>☕ Spring Boot</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+spring+in:name,description,topics&query=$.total_count&label=Repos&style=flat-square&color=6DB33F&labelColor=0d1117" alt="Spring"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&q=spring" target="_blank">View →</a></td></tr>
      <tr><td>📱 Flutter</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+flutter+in:name,description,topics&query=$.total_count&label=Repos&style=flat-square&color=02569B&labelColor=0d1117" alt="Flutter"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&q=flutter" target="_blank">View →</a></td></tr>
      <tr><td>🅰️ Angular</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+angular+in:name,description,topics&query=$.total_count&label=Repos&style=flat-square&color=DD0031&labelColor=0d1117" alt="Angular"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&q=angular" target="_blank">View →</a></td></tr>
      <tr><td>🗄️ MongoDB</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+mongodb+in:name,description,topics&query=$.total_count&label=Repos&style=flat-square&color=47A248&labelColor=0d1117" alt="Mongo"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&q=mongodb" target="_blank">View →</a></td></tr>
      <tr><td>🐳 Docker</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+docker+in:name,description,topics&query=$.total_count&label=Repos&style=flat-square&color=2496ED&labelColor=0d1117" alt="Docker"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&q=docker" target="_blank">View →</a></td></tr>
      <tr><td>🏗️ TypeScript</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+language:typescript&query=$.total_count&label=Repos&style=flat-square&color=007ACC&labelColor=0d1117" alt="TypeScript"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&l=TypeScript" target="_blank">View →</a></td></tr>
      <tr><td>🐘 PHP Total</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+language:php&query=$.total_count&label=Repos&style=flat-square&color=777BB4&labelColor=0d1117" alt="PHP"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&l=PHP" target="_blank">View →</a></td></tr>
      <tr><td>☕ Java Total</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+language:java&query=$.total_count&label=Repos&style=flat-square&color=ED8B00&labelColor=0d1117" alt="Java"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&l=Java" target="_blank">View →</a></td></tr>
      <tr><td>🎯 JavaScript Total</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+language:javascript&query=$.total_count&label=Repos&style=flat-square&color=F7DF1E&labelColor=0d1117" alt="JS"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&l=JavaScript" target="_blank">View →</a></td></tr>
      <tr><td>🎯 Dart / Flutter</td><td><img src="https://img.shields.io/badge/dynamic/json?url=https://api.github.com/search/repositories?q=user:nallaperumal007+language:dart&query=$.total_count&label=Repos&style=flat-square&color=0175C2&labelColor=0d1117" alt="Dart"/></td><td><a href="https://github.com/nallaperumal007?tab=repositories&l=Dart" target="_blank">View →</a></td></tr>
    </tbody>
  </table>
</div>

<div class="divider" style="max-width:1100px;margin:16px auto;"></div>

<!-- TECH STACK -->
<div class="section-title">🛠️ Complete Tech Stack</div>
<div class="tech-section">
  <div class="tech-category">
    <div class="tech-category-title">Frontend Development</div>
    <div class="tech-icons">
      <span class="tech-chip">⚛️ React</span><span class="tech-chip">▲ Next.js</span><span class="tech-chip">🅰️ Angular</span><span class="tech-chip">📘 TypeScript</span><span class="tech-chip">🟨 JavaScript</span><span class="tech-chip">🌐 HTML</span><span class="tech-chip">🎨 CSS</span><span class="tech-chip">💨 Tailwind</span><span class="tech-chip">🅱️ Bootstrap</span><span class="tech-chip">💅 Sass</span><span class="tech-chip">🔁 Redux</span><span class="tech-chip">⚡ Vite</span>
    </div>
  </div>
  <div class="tech-category">
    <div class="tech-category-title">Backend Development</div>
    <div class="tech-icons">
      <span class="tech-chip">🟢 Node.js</span><span class="tech-chip">🚂 Express</span><span class="tech-chip">🔴 Laravel</span><span class="tech-chip">🐘 PHP</span><span class="tech-chip">🌱 Spring Boot</span><span class="tech-chip">☕ Java</span><span class="tech-chip">🐍 Python</span><span class="tech-chip">📡 GraphQL</span>
    </div>
  </div>
  <div class="tech-category">
    <div class="tech-category-title">Mobile Development</div>
    <div class="tech-icons">
      <span class="tech-chip">📱 Flutter</span><span class="tech-chip">🎯 Dart</span><span class="tech-chip">🤖 Android Studio</span>
    </div>
  </div>
  <div class="tech-category">
    <div class="tech-category-title">Database & Storage</div>
    <div class="tech-icons">
      <span class="tech-chip">🍃 MongoDB</span><span class="tech-chip">🐬 MySQL</span><span class="tech-chip">🐘 PostgreSQL</span><span class="tech-chip">🔴 Redis</span><span class="tech-chip">🔥 Firebase</span>
    </div>
  </div>
  <div class="tech-category">
    <div class="tech-category-title">DevOps & Cloud</div>
    <div class="tech-icons">
      <span class="tech-chip">🐳 Docker</span><span class="tech-chip">☁️ AWS</span><span class="tech-chip">🐙 GitHub</span><span class="tech-chip">⚙️ GitHub Actions</span><span class="tech-chip">🐧 Linux</span><span class="tech-chip">🌐 Nginx</span>
    </div>
  </div>
</div>

<div class="divider" style="max-width:1100px;margin:16px auto;"></div>

<!-- FEATURED PROJECTS -->
<div class="section-title">🌟 Featured Projects</div>
<div class="projects-grid">
  <div class="project-card">
    <div class="project-title">🏢 Enterprise CRM Platform</div>
    <div class="project-desc">Full-featured Customer Relationship Management system</div>
    <ul class="project-features">
      <li>Multi-tenant architecture</li>
      <li>Real-time sales pipeline & analytics</li>
      <li>Automated email/SMS notifications</li>
      <li>Mobile-responsive PWA</li>
    </ul>
    <div class="project-tags">
      <span class="tag">Laravel</span><span class="tag">React</span><span class="tag">MySQL</span><span class="tag">Redis</span>
    </div>
  </div>
  <div class="project-card">
    <div class="project-title">🏥 Hospital Management System</div>
    <div class="project-desc">Scalable HMS with enterprise-grade features</div>
    <ul class="project-features">
      <li>Patient EMR & medical records</li>
      <li>Smart appointment scheduling</li>
      <li>Pharmacy & inventory management</li>
      <li>Integrated billing & insurance</li>
    </ul>
    <div class="project-tags">
      <span class="tag">Spring Boot</span><span class="tag">Angular</span><span class="tag">PostgreSQL</span><span class="tag">Docker</span>
    </div>
  </div>
  <div class="project-card">
    <div class="project-title">✅ Task Tracker Pro</div>
    <div class="project-desc">Real-time team collaboration platform</div>
    <ul class="project-features">
      <li>Kanban + Sprint board views</li>
      <li>Time tracking & productivity stats</li>
      <li>In-app team messaging</li>
      <li>Burndown charts & analytics</li>
    </ul>
    <div class="project-tags">
      <span class="tag">MongoDB</span><span class="tag">Node.js</span><span class="tag">React</span><span class="tag">Socket.io</span>
    </div>
  </div>
  <div class="project-card">
    <div class="project-title">✨ GSAP Animated Website</div>
    <div class="project-desc">Award-worthy animated web experience</div>
    <ul class="project-features">
      <li>Scroll-triggered cinematic animations</li>
      <li>3D WebGL elements with Three.js</li>
      <li>95+ Lighthouse performance score</li>
      <li>Custom cursor & micro-interactions</li>
    </ul>
    <div class="project-tags">
      <span class="tag">Next.js</span><span class="tag">GSAP</span><span class="tag">TypeScript</span><span class="tag">Three.js</span>
    </div>
  </div>
</div>

<div class="divider" style="max-width:1100px;margin:16px auto;"></div>

<!-- QUOTE -->
<div class="section-title">💬 Developer Philosophy</div>
<div class="quote-wrap">
  <div class="quote-text">
    "Any fool can write code that a computer can understand.<br/>
    Good programmers write code that humans can understand."
  </div>
  <div class="quote-author">— Martin Fowler</div>
</div>

<!-- CONNECT -->
<div class="section-title">📬 Connect & Collaborate</div>
<div class="connect-wrap">
  <div class="connect-buttons">
    <a href="mailto:nallaperumal007@gmail.com" class="connect-btn gmail">📧 Gmail</a>
    <a href="https://linkedin.com/in/nallaperumal007" target="_blank" class="connect-btn linkedin">💼 LinkedIn</a>
    <a href="https://wa.me/your-number" target="_blank" class="connect-btn whatsapp">💬 WhatsApp</a>
    <a href="https://nallaperumal007.github.io" target="_blank" class="connect-btn portfolio">🌐 Portfolio</a>
    <a href="https://github.com/nallaperumal007" target="_blank" class="connect-btn github">🐙 GitHub</a>
  </div>
</div>

<!-- FOOTER -->
<div class="footer-wave">
  <div class="star-badge">⭐ Star this profile if it inspired you!</div>
</div>

<script>
  // TYPING ANIMATION
  const lines = [
    "Full Stack Developer",
    "MERN Stack Engineer",
    "MEAN Stack Developer",
    "Laravel / PHP Backend Expert",
    "Spring Boot Java Developer",
    "Next.js / React Frontend Engineer",
    "Flutter Mobile App Developer",
    "React Native Mobile Developer",
    "300+ Public Repositories",
    "Open Source Contributor",
    "Always Learning New Technologies",
    "Hard Worker & Problem Solver",
    "Building Scalable Applications",
    "Passionate About Coding"
  ];
  let li = 0, ci = 0, del = false;
  const el = document.getElementById('typer');
  function type() {
    const cur = lines[li];
    if (!del) {
      el.textContent = cur.slice(0, ++ci);
      if (ci === cur.length) { del = true; setTimeout(type, 1800); return; }
    } else {
      el.textContent = cur.slice(0, --ci);
      if (ci === 0) { del = false; li = (li + 1) % lines.length; }
    }
    setTimeout(type, del ? 40 : 60);
  }
  type();
</script>
</body>
</html>
