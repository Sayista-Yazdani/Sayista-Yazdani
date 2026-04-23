
<style>
  @import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  .profile-root {
    font-family: 'Syne', sans-serif;
    background: #0a0a0f;
    color: #e8e6f0;
    min-height: 100vh;
    padding: 0;
    overflow-x: hidden;
  }

  .hero {
    position: relative;
    padding: 48px 32px 36px;
    border-bottom: 1px solid #1e1b2e;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse 80% 60% at 70% 50%, #1a1040 0%, transparent 70%);
    pointer-events: none;
  }

  .grid-lines {
    position: absolute;
    inset: 0;
    background-image: 
      linear-gradient(rgba(139, 92, 246, 0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(139, 92, 246, 0.04) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
  }

  .hero-inner {
    position: relative;
    z-index: 1;
    display: flex;
    align-items: center;
    gap: 32px;
    max-width: 760px;
  }

  .avatar-ring {
    position: relative;
    flex-shrink: 0;
  }

  .avatar-circle {
    width: 88px;
    height: 88px;
    border-radius: 50%;
    background: linear-gradient(135deg, #7c3aed, #4f46e5, #0ea5e9);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 32px;
    font-weight: 800;
    color: #fff;
    letter-spacing: -1px;
    position: relative;
    z-index: 1;
  }

  .avatar-ring::before {
    content: '';
    position: absolute;
    inset: -3px;
    border-radius: 50%;
    background: linear-gradient(135deg, #7c3aed, #0ea5e9, #7c3aed);
    z-index: 0;
    animation: spin 4s linear infinite;
  }

  @keyframes spin {
    to { transform: rotate(360deg); }
  }

  .hero-text h1 {
    font-size: 28px;
    font-weight: 800;
    color: #fff;
    line-height: 1.1;
    margin-bottom: 6px;
    letter-spacing: -0.5px;
  }

  .hero-text h1 span {
    background: linear-gradient(90deg, #a78bfa, #38bdf8);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-text .role {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: #7c6fa0;
    margin-bottom: 14px;
  }

  .hero-text .role span {
    color: #a78bfa;
  }

  .badge-row {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    padding: 4px 10px;
    border-radius: 20px;
    border: 1px solid;
    letter-spacing: 0.3px;
  }

  .badge-purple { background: #1e1040; border-color: #4c2889; color: #c4b5fd; }
  .badge-blue { background: #0c1a2e; border-color: #1e3a5f; color: #7dd3fc; }
  .badge-green { background: #0a1f10; border-color: #14532d; color: #86efac; }

  .section {
    padding: 28px 32px;
    border-bottom: 1px solid #1e1b2e;
  }

  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #4c4469;
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 18px;
  }

  .info-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .info-card {
    background: #0f0d1a;
    border: 1px solid #1e1b2e;
    border-radius: 10px;
    padding: 14px 16px;
    display: flex;
    align-items: flex-start;
    gap: 12px;
    transition: border-color 0.2s;
    cursor: default;
  }

  .info-card:hover { border-color: #3b2d6e; }

  .info-icon {
    width: 32px;
    height: 32px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 15px;
    flex-shrink: 0;
  }

  .icon-purple { background: #1e1040; }
  .icon-blue { background: #0c1a2e; }
  .icon-green { background: #0a1f10; }
  .icon-amber { background: #1f1400; }

  .info-content p {
    font-size: 12px;
    color: #4c4469;
    margin-bottom: 2px;
    font-family: 'JetBrains Mono', monospace;
  }

  .info-content a, .info-content span {
    font-size: 13px;
    color: #c4b5fd;
    text-decoration: none;
    word-break: break-all;
    line-height: 1.3;
  }

  .info-content a:hover { color: #a78bfa; text-decoration: underline; }

  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .tech-pill {
    display: flex;
    align-items: center;
    gap: 8px;
    background: #0f0d1a;
    border: 1px solid #1e1b2e;
    border-radius: 8px;
    padding: 8px 14px;
    transition: all 0.2s;
    cursor: default;
  }

  .tech-pill:hover {
    border-color: #4c2889;
    background: #150f28;
    transform: translateY(-1px);
  }

  .tech-pill img {
    width: 20px;
    height: 20px;
    object-fit: contain;
  }

  .tech-pill span {
    font-size: 12px;
    color: #9d8ec4;
    font-family: 'JetBrains Mono', monospace;
  }

  .stats-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .stat-card {
    background: #0f0d1a;
    border: 1px solid #1e1b2e;
    border-radius: 10px;
    overflow: hidden;
  }

  .stat-card img {
    width: 100%;
    display: block;
    filter: brightness(0.9);
  }

  .stat-card iframe {
    width: 100%;
    border: none;
    display: block;
  }

  .connect-row {
    display: flex;
    gap: 12px;
    align-items: center;
  }

  .connect-link {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 10px 18px;
    background: #0f0d1a;
    border: 1px solid #1e1b2e;
    border-radius: 8px;
    text-decoration: none;
    transition: all 0.2s;
    font-size: 13px;
    color: #9d8ec4;
    font-family: 'JetBrains Mono', monospace;
  }

  .connect-link:hover {
    border-color: #4c2889;
    background: #150f28;
    color: #c4b5fd;
  }

  .connect-link svg { width: 16px; height: 16px; fill: currentColor; }

  .fun-fact {
    background: linear-gradient(135deg, #150f28, #0c1a2e);
    border: 1px solid #2d1f5e;
    border-radius: 10px;
    padding: 14px 18px;
    display: flex;
    align-items: center;
    gap: 12px;
    margin-top: 14px;
  }

  .fun-fact-icon {
    font-size: 20px;
    flex-shrink: 0;
  }

  .fun-fact p {
    font-size: 13px;
    color: #7c6fa0;
  }

  .fun-fact p strong {
    color: #a78bfa;
    font-weight: 600;
  }

  .divider-label {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 16px;
  }

  .divider-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: #1e1b2e;
  }

  .views-pill {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: #0f0d1a;
    border: 1px solid #1e1b2e;
    border-radius: 20px;
    padding: 5px 14px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: #4c4469;
    margin-bottom: 20px;
  }

  .views-pill span { color: #6457a6; }

  @media (max-width: 500px) {
    .info-grid { grid-template-columns: 1fr; }
    .stats-row { grid-template-columns: 1fr; }
    .hero-inner { flex-direction: column; gap: 20px; }
  }
</style>

<div class="profile-root">

  <div class="hero">
    <div class="grid-lines"></div>
    <div class="hero-inner">
      <div class="avatar-ring">
        <div class="avatar-circle">SY</div>
      </div>
      <div class="hero-text">
        <h1>Hi 👋, I'm <span>Sayista Yazdani</span></h1>
        <p class="role">// <span>passionate software developer</span> · India</p>
        <div class="badge-row">
          <span class="badge badge-purple">⚡ curious by nature</span>
          <span class="badge badge-blue">☕ code + coffee</span>
          <span class="badge badge-green">🌱 always learning</span>
        </div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="views-pill">
      <span>◎</span> profile views &nbsp;<img src="https://komarev.com/ghpvc/?username=siya&label=&color=6457a6&style=flat" alt="views" style="height:16px; vertical-align:middle;" />
    </div>

    <div class="section-label">// about me</div>
    <div class="info-grid">
      <div class="info-card">
        <div class="info-icon icon-purple">💻</div>
        <div class="info-content">
          <p>projects</p>
          <a href="https://github.com/Sayista-Yazdani?tab=repositories" target="_blank">github.com/Sayista-Yazdani</a>
        </div>
      </div>
      <div class="info-card">
        <div class="info-icon icon-blue">📬</div>
        <div class="info-content">
          <p>email</p>
          <a href="mailto:sayistayazdani1999@gmail.com">sayistayazdani1999@gmail.com</a>
        </div>
      </div>
      <div class="info-card">
        <div class="info-icon icon-purple">🔗</div>
        <div class="info-content">
          <p>linkedin</p>
          <a href="https://www.linkedin.com/in/sayista-yazdani-465769215/" target="_blank">sayista-yazdani</a>
        </div>
      </div>
      <div class="info-card">
        <div class="info-icon icon-amber">📍</div>
        <div class="info-content">
          <p>location</p>
          <span>India 🇮🇳</span>
        </div>
      </div>
    </div>

    <div class="fun-fact">
      <div class="fun-fact-icon">⚡</div>
      <p><strong>Fun fact:</strong> I think, therefore I am curious — always exploring something new.</p>
    </div>
  </div>

  <div class="section">
    <div class="divider-label">
      <span class="section-label" style="margin-bottom:0">// languages & frameworks</span>
    </div>
    <div class="tech-grid">
      <div class="tech-pill">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="java" />
        <span>Java</span>
      </div>
      <div class="tech-pill">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/dot-net/dot-net-original-wordmark.svg" alt="dotnet" />
        <span>.NET</span>
      </div>
      <div class="tech-pill">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" />
        <span>HTML5</span>
      </div>
      <div class="tech-pill">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="css3" />
        <span>CSS3</span>
      </div>
      <div class="tech-pill">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/bootstrap/bootstrap-plain-wordmark.svg" alt="bootstrap" />
        <span>Bootstrap</span>
      </div>
      <div class="tech-pill">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="javascript" />
        <span>JavaScript</span>
      </div>
      <div class="tech-pill">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="mysql" />
        <span>MySQL</span>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="divider-label">
      <span class="section-label" style="margin-bottom:0">// familiar with</span>
    </div>
    <div class="tech-grid">
      <div class="tech-pill">
        <img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt="figma" />
        <span>Figma</span>
      </div>
      <div class="tech-pill">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/photoshop/photoshop-line.svg" alt="photoshop" />
        <span>Photoshop</span>
      </div>
    </div>
  </div>

  <div class="section" style="border-bottom:none">
    <div class="divider-label">
      <span class="section-label" style="margin-bottom:0">// github stats</span>
    </div>
    <div class="stats-row">
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api/top-langs?username=sayista-yazdani&show_icons=true&locale=en&layout=compact&theme=midnight-purple&bg_color=0f0d1a&border_color=1e1b2e&title_color=a78bfa&text_color=9d8ec4" alt="top langs" />
      </div>
      <div class="stat-card">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=sayista-yazdani&theme=midnight-purple&background=0f0d1a&border=1e1b2e&stroke=a78bfa&ring=7c3aed&fire=38bdf8&currStreakLabel=a78bfa" alt="streak stats" />
      </div>
    </div>
  </div>

</div>
