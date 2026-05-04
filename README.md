
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap');

  * { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --accent: #00d4aa;
    --accent2: #7c6fff;
    --dark: #0d1117;
    --card-bg: #161b22;
    --border: #30363d;
    --text: #e6edf3;
    --muted: #8b949e;
  }

  .profile-card {
    background: var(--dark);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 2rem;
    font-family: 'Syne', sans-serif;
    color: var(--text);
    position: relative;
    overflow: hidden;
  }

  .profile-card::before {
    content: '';
    position: absolute;
    top: -80px; right: -80px;
    width: 240px; height: 240px;
    background: radial-gradient(circle, rgba(0,212,170,0.12) 0%, transparent 70%);
    pointer-events: none;
  }

  .profile-card::after {
    content: '';
    position: absolute;
    bottom: -60px; left: -60px;
    width: 200px; height: 200px;
    background: radial-gradient(circle, rgba(124,111,255,0.1) 0%, transparent 70%);
    pointer-events: none;
  }

  .header {
    display: flex;
    align-items: center;
    gap: 1.5rem;
    margin-bottom: 2rem;
  }

  .avatar {
    width: 80px; height: 80px;
    border-radius: 50%;
    background: linear-gradient(135deg, #00d4aa, #7c6fff);
    display: flex; align-items: center; justify-content: center;
    font-size: 28px; font-weight: 800;
    color: #fff;
    flex-shrink: 0;
    position: relative;
  }

  .avatar::after {
    content: '';
    position: absolute;
    inset: -3px;
    border-radius: 50%;
    border: 2px solid transparent;
    background: linear-gradient(135deg, #00d4aa, #7c6fff) border-box;
    -webkit-mask: linear-gradient(#fff 0 0) padding-box, linear-gradient(#fff 0 0);
    -webkit-mask-composite: destination-out;
    mask-composite: exclude;
  }

  .header-text h1 {
    font-size: 26px;
    font-weight: 800;
    letter-spacing: -0.5px;
    background: linear-gradient(90deg, #e6edf3, #00d4aa);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .header-text p {
    color: var(--muted);
    font-size: 14px;
    margin-top: 4px;
    font-family: 'Space Mono', monospace;
  }

  .location-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    margin-top: 8px;
    background: rgba(0,212,170,0.08);
    border: 1px solid rgba(0,212,170,0.2);
    border-radius: 20px;
    padding: 3px 12px;
    font-size: 12px;
    color: #00d4aa;
    font-family: 'Space Mono', monospace;
  }

  .section-title {
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 1rem;
    font-family: 'Space Mono', monospace;
  }

  .divider { border: none; border-top: 1px solid var(--border); margin: 1.5rem 0; }

  .stats-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin-bottom: 1.5rem;
  }

  .stat-card {
    background: var(--card-bg);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px;
    text-align: center;
    transition: border-color 0.2s, transform 0.2s;
    cursor: default;
  }

  .stat-card:hover {
    border-color: #00d4aa;
    transform: translateY(-2px);
  }

  .stat-num {
    font-size: 22px;
    font-weight: 800;
    color: #fff;
    display: block;
  }

  .stat-label {
    font-size: 11px;
    color: var(--muted);
    font-family: 'Space Mono', monospace;
    margin-top: 2px;
  }

  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tech-badge {
    display: flex;
    align-items: center;
    gap: 6px;
    background: var(--card-bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 6px 12px;
    font-size: 13px;
    font-weight: 600;
    color: var(--text);
    transition: all 0.2s;
    cursor: default;
  }

  .tech-badge:hover {
    border-color: var(--accent2);
    color: #fff;
    background: rgba(124,111,255,0.08);
  }

  .tech-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  .socials {
    display: flex;
    gap: 10px;
  }

  .social-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--card-bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 8px 16px;
    font-size: 13px;
    font-weight: 600;
    color: var(--text);
    text-decoration: none;
    transition: all 0.2s;
    font-family: 'Space Mono', monospace;
    cursor: pointer;
  }

  .social-btn:hover {
    border-color: #00d4aa;
    color: #00d4aa;
  }

  .skill-bars { display: flex; flex-direction: column; gap: 10px; }

  .skill-row { display: flex; align-items: center; gap: 12px; }

  .skill-name {
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    color: var(--muted);
    width: 80px;
    flex-shrink: 0;
  }

  .skill-bar-track {
    flex: 1;
    height: 4px;
    background: var(--border);
    border-radius: 2px;
    overflow: hidden;
  }

  .skill-bar-fill {
    height: 100%;
    border-radius: 2px;
    animation: fillBar 1.2s cubic-bezier(.4,0,.2,1) forwards;
    transform-origin: left;
  }

  @keyframes fillBar {
    from { width: 0; }
  }

  .skill-pct {
    font-size: 11px;
    font-family: 'Space Mono', monospace;
    color: var(--muted);
    width: 32px;
    text-align: right;
  }

  .currently {
    background: var(--card-bg);
    border: 1px solid var(--border);
    border-left: 3px solid #00d4aa;
    border-radius: 8px;
    padding: 12px 16px;
    font-size: 13px;
    font-family: 'Space Mono', monospace;
    color: var(--muted);
    margin-top: 1.5rem;
  }

  .currently span {
    color: #00d4aa;
    font-weight: 700;
  }

  .pulse-dot {
    display: inline-block;
    width: 8px; height: 8px;
    border-radius: 50%;
    background: #00d4aa;
    margin-right: 8px;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }

  .contribution-row {
    display: flex;
    gap: 3px;
    flex-wrap: wrap;
    margin-top: 8px;
  }

  .contrib-cell {
    width: 14px; height: 14px;
    border-radius: 3px;
    background: var(--border);
    transition: transform 0.15s;
  }

  .contrib-cell:hover { transform: scale(1.3); }
  .contrib-cell.l1 { background: #0e4429; }
  .contrib-cell.l2 { background: #006d32; }
  .contrib-cell.l3 { background: #26a641; }
  .contrib-cell.l4 { background: #39d353; }

  .footer-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 1.5rem;
    padding-top: 1rem;
    border-top: 1px solid var(--border);
  }

  .footer-row p {
    font-size: 12px;
    color: var(--muted);
    font-family: 'Space Mono', monospace;
  }

  .open-to-work {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: rgba(57,211,83,0.08);
    border: 1px solid rgba(57,211,83,0.2);
    border-radius: 20px;
    padding: 4px 12px;
    font-size: 11px;
    font-family: 'Space Mono', monospace;
    color: #39d353;
  }

  .fade-in {
    animation: fadeIn 0.6s ease forwards;
    opacity: 0;
  }

  @keyframes fadeIn {
    to { opacity: 1; }
  }

  .fade-in:nth-child(1) { animation-delay: 0s; }
  .fade-in:nth-child(2) { animation-delay: 0.1s; }
  .fade-in:nth-child(3) { animation-delay: 0.2s; }
  .fade-in:nth-child(4) { animation-delay: 0.3s; }
  .fade-in:nth-child(5) { animation-delay: 0.4s; }
</style>

<div class="profile-card">

  <div class="header fade-in">
    <div class="avatar">HA</div>
    <div class="header-text">
      <h1>Houssam Alhyane</h1>
      <p>@skizman · passionate developer</p>
      <div class="location-badge">
        <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/></svg>
        Morocco
      </div>
    </div>
  </div>

  <div class="stats-grid fade-in">
    <div class="stat-card">
      <span class="stat-num" style="color:#00d4aa">∞</span>
      <span class="stat-label">Commits</span>
    </div>
    <div class="stat-card">
      <span class="stat-num" style="color:#7c6fff">10+</span>
      <span class="stat-label">Languages</span>
    </div>
    <div class="stat-card">
      <span class="stat-num" style="color:#f78166">Full</span>
      <span class="stat-label">Stack</span>
    </div>
  </div>

  <hr class="divider">

  <div class="fade-in">
    <div class="section-title">— Tech Stack</div>
    <div class="tech-grid">
      <div class="tech-badge"><div class="tech-dot" style="background:#e34c26"></div>HTML5</div>
      <div class="tech-badge"><div class="tech-dot" style="background:#264de4"></div>CSS3</div>
      <div class="tech-badge"><div class="tech-dot" style="background:#f7df1e"></div>JavaScript</div>
      <div class="tech-badge"><div class="tech-dot" style="background:#777bb4"></div>PHP</div>
      <div class="tech-badge"><div class="tech-dot" style="background:#007396"></div>Java</div>
      <div class="tech-badge"><div class="tech-dot" style="background:#00ADD8"></div>Go</div>
      <div class="tech-badge"><div class="tech-dot" style="background:#4DB33D"></div>MongoDB</div>
      <div class="tech-badge"><div class="tech-dot" style="background:#4479a1"></div>MySQL</div>
      <div class="tech-badge"><div class="tech-dot" style="background:#38BDF8"></div>Tailwind</div>
      <div class="tech-badge"><div class="tech-dot" style="background:#f05032"></div>Git</div>
      <div class="tech-badge"><div class="tech-dot" style="background:#FCC624"></div>Linux</div>
    </div>
  </div>

  <hr class="divider">

  <div class="fade-in">
    <div class="section-title">— Proficiency</div>
    <div class="skill-bars">
      <div class="skill-row">
        <span class="skill-name">JavaScript</span>
        <div class="skill-bar-track"><div class="skill-bar-fill" style="width:82%;background:linear-gradient(90deg,#7c6fff,#00d4aa)"></div></div>
        <span class="skill-pct">82%</span>
      </div>
      <div class="skill-row">
        <span class="skill-name">PHP</span>
        <div class="skill-bar-track"><div class="skill-bar-fill" style="width:75%;background:linear-gradient(90deg,#7c6fff,#00d4aa)"></div></div>
        <span class="skill-pct">75%</span>
      </div>
      <div class="skill-row">
        <span class="skill-name">Java</span>
        <div class="skill-bar-track"><div class="skill-bar-fill" style="width:68%;background:linear-gradient(90deg,#7c6fff,#00d4aa)"></div></div>
        <span class="skill-pct">68%</span>
      </div>
      <div class="skill-row">
        <span class="skill-name">Go</span>
        <div class="skill-bar-track"><div class="skill-bar-fill" style="width:55%;background:linear-gradient(90deg,#7c6fff,#00d4aa)"></div></div>
        <span class="skill-pct">55%</span>
      </div>
      <div class="skill-row">
        <span class="skill-name">Databases</span>
        <div class="skill-bar-track"><div class="skill-bar-fill" style="width:70%;background:linear-gradient(90deg,#7c6fff,#00d4aa)"></div></div>
        <span class="skill-pct">70%</span>
      </div>
    </div>
  </div>

  <hr class="divider">

  <div class="fade-in">
    <div class="section-title">— Activity</div>
    <div class="contribution-row" id="contribGrid"></div>
  </div>

  <div class="currently fade-in">
    <span class="pulse-dot"></span><span>Currently:</span> Building cool things from Morocco — open to collaboration
  </div>

  <div class="footer-row fade-in">
    <div class="socials">
      <a class="social-btn" href="https://dev.to/skizman" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M7.42 10.05c-.18-.16-.46-.23-.84-.23H6l.02 2.44.04 2.45.56-.02c.41 0 .63-.07.83-.26.24-.24.26-.36.26-2.2 0-1.91-.02-1.96-.29-2.18zM0 4.94v14.12h24V4.94H0zM8.56 15.3c-.44.58-1.06.77-2.53.77H4.71V8.53h1.4c1.67 0 2.16.18 2.6.9.27.43.29.6.32 2.57.05 2.23-.02 2.73-.47 3.3zm5.09-5.47h-2.47v1.77h1.52v1.28l-.72.04-.75.03v1.77l1.22.03 1.2.04v1.28h-1.6c-1.53 0-1.6-.01-1.87-.3l-.3-.28v-3.16c0-3.02.01-3.18.25-3.48.23-.31.25-.31 1.88-.31h1.64v1.29zm4.68 5.45c-.17.43-.64.79-1 .79-.18 0-.45-.15-.67-.39-.32-.32-.45-.63-.82-2.08l-.9-3.39-.45-1.67h.76c.4 0 .75.02.75.05 0 .06 1.16 4.54 1.26 4.83.04.15.32-.7.73-2.3l.64-2.52.74-.04c.4-.02.73 0 .73.04 0 .14-1.67 6.38-1.8 6.68z"/></svg>
        dev.to
      </a>
      <a class="social-btn" href="https://discord.com/channels/@skizman_23" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M20.317 4.492c-1.53-.69-3.17-1.2-4.885-1.49a.075.075 0 0 0-.079.036c-.21.369-.444.85-.608 1.23a18.566 18.566 0 0 0-5.487 0 12.36 12.36 0 0 0-.617-1.23A.077.077 0 0 0 8.562 3c-1.714.29-3.354.8-4.885 1.491a.07.07 0 0 0-.032.027C.533 9.093-.32 13.555.099 17.961a.08.08 0 0 0 .031.055 20.03 20.03 0 0 0 5.993 2.98.078.078 0 0 0 .084-.026c.462-.62.874-1.275 1.226-1.963.021-.04.001-.088-.041-.104a13.201 13.201 0 0 1-1.872-.878.075.075 0 0 1-.008-.125c.126-.093.252-.19.372-.287a.075.075 0 0 1 .078-.01c3.927 1.764 8.18 1.764 12.061 0a.075.075 0 0 1 .079.009c.12.098.245.195.372.288a.075.075 0 0 1-.006.125c-.598.344-1.22.635-1.873.877a.075.075 0 0 0-.041.105c.36.687.772 1.341 1.225 1.962a.077.077 0 0 0 .084.028 19.963 19.963 0 0 0 6.002-2.981.076.076 0 0 0 .032-.054c.5-5.094-.838-9.52-3.549-13.442a.06.06 0 0 0-.031-.028z"/></svg>
        Discord
      </a>
    </div>
    <div class="open-to-work">
      <div class="pulse-dot" style="width:6px;height:6px;margin:0"></div>
      Open to work
    </div>
  </div>

</div>

<script>
  const grid = document.getElementById('contribGrid');
  const levels = ['', 'l1', 'l2', 'l3', 'l4'];
  for (let i = 0; i < 105; i++) {
    const cell = document.createElement('div');
    cell.className = 'contrib-cell';
    const r = Math.random();
    if (r > 0.6) cell.classList.add(levels[Math.floor(Math.random() * 4) + 1]);
    grid.appendChild(cell);
  }
</script>
