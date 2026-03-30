<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Ana Catalina Torres — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:wght@300;400;500&family=DM+Mono&display=swap" rel="stylesheet"/>
<style>
  :root {
    --linen:    #F9EDE8;
    --blush:    #F2D5CB;
    --rose:     #E8B8AC;
    --terra:    #D4967E;
    --sand:     #EDE0D4;
    --beige:    #D8C4B0;
    --caramel:  #C4A882;
    --mauve:    #7A4F45;
    --mauve-lt: #A07060;
    --text:     #3D2016;
  }

  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--linen);
    font-family: 'DM Sans', sans-serif;
    color: var(--text);
    min-height: 100vh;
    padding: 40px 20px 80px;
  }

  .page {
    max-width: 720px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 36px;
  }

  /* ── HEADER ── */
  .header {
    background: var(--blush);
    border: 1.5px solid var(--rose);
    border-radius: 20px;
    padding: 40px 40px 32px;
    position: relative;
    overflow: hidden;
    animation: fadeUp 0.6s ease both;
  }

  .header::before {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 200px; height: 200px;
    background: var(--rose);
    border-radius: 50%;
    opacity: 0.35;
  }

  .header::after {
    content: '';
    position: absolute;
    bottom: -40px; left: -40px;
    width: 140px; height: 140px;
    background: var(--terra);
    border-radius: 50%;
    opacity: 0.18;
  }

  .greeting {
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 400;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--mauve-lt);
    margin-bottom: 8px;
  }

  .name {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(36px, 6vw, 54px);
    color: var(--mauve);
    line-height: 1.1;
    margin-bottom: 16px;
    position: relative;
  }

  .tagline {
    font-size: 15px;
    font-weight: 300;
    color: var(--mauve-lt);
    max-width: 480px;
    line-height: 1.7;
    position: relative;
  }

  .tagline strong {
    font-weight: 500;
    color: var(--mauve);
  }

  /* ── ABOUT ── */
  .about {
    background: var(--sand);
    border: 1.5px solid var(--beige);
    border-radius: 16px;
    padding: 28px 32px;
    animation: fadeUp 0.6s 0.1s ease both;
  }

  .section-label {
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--terra);
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--beige);
  }

  .about p {
    font-size: 15px;
    line-height: 1.8;
    color: var(--mauve);
    font-weight: 300;
  }

  .about p strong {
    font-weight: 500;
    color: var(--mauve);
  }

  /* ── CURRENTLY ── */
  .currently {
    background: var(--blush);
    border: 1.5px solid var(--rose);
    border-radius: 16px;
    padding: 28px 32px;
    animation: fadeUp 0.6s 0.2s ease both;
  }

  .currently-items {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 4px;
  }

  .currently-item {
    display: flex;
    align-items: baseline;
    gap: 12px;
    font-size: 14px;
    color: var(--mauve);
    font-weight: 300;
  }

  .currently-item .dot {
    width: 6px; height: 6px;
    background: var(--terra);
    border-radius: 50%;
    flex-shrink: 0;
    margin-top: 6px;
  }

  .currently-item strong { font-weight: 500; }

  /* ── TECH ── */
  .tech {
    background: var(--linen);
    border: 1.5px solid var(--beige);
    border-radius: 16px;
    padding: 28px 32px;
    animation: fadeUp 0.6s 0.3s ease both;
  }

  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 4px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 100px;
    font-size: 12px;
    font-weight: 500;
    border: 1.5px solid transparent;
    transition: transform 0.15s ease, box-shadow 0.15s ease;
    cursor: default;
  }

  .badge:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(122,79,69,0.15);
  }

  .badge-html  { background:#F2D5CB; color:#7A4F45; border-color:#E8B8AC; }
  .badge-css   { background:#EDE0D4; color:#5C4232; border-color:#D8C4B0; }
  .badge-js    { background:#F9EDE8; color:#7A4F45; border-color:#E8B8AC; }
  .badge-java  { background:#E8B8AC; color:#3D2016; border-color:#D4967E; }
  .badge-py    { background:#D8C4B0; color:#3D2016; border-color:#C4A882; }
  .badge-git   { background:#D4967E; color:#F9EDE8; border-color:#C4A882; }
  .badge-gh    { background:#7A4F45; color:#F9EDE8; border-color:#3D2016; }

  .badge svg   { width: 14px; height: 14px; flex-shrink: 0; }

  /* ── PROJECTS ── */
  .projects {
    background: var(--sand);
    border: 1.5px solid var(--beige);
    border-radius: 16px;
    padding: 28px 32px;
    animation: fadeUp 0.6s 0.4s ease both;
  }

  .project-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    margin-top: 4px;
  }

  .project-card {
    background: var(--linen);
    border: 1.5px solid var(--rose);
    border-radius: 12px;
    padding: 16px 18px;
    transition: transform 0.15s ease;
    cursor: default;
  }

  .project-card:hover { transform: translateY(-2px); }

  .project-card .icon {
    font-size: 18px;
    margin-bottom: 8px;
    display: block;
  }

  .project-card h4 {
    font-size: 13px;
    font-weight: 500;
    color: var(--mauve);
    margin-bottom: 4px;
  }

  .project-card p {
    font-size: 12px;
    font-weight: 300;
    color: var(--mauve-lt);
    line-height: 1.6;
  }

  /* ── STATS ── */
  .stats {
    background: var(--blush);
    border: 1.5px solid var(--rose);
    border-radius: 16px;
    padding: 28px 32px;
    animation: fadeUp 0.6s 0.45s ease both;
  }

  .stats-note {
    font-size: 12px;
    color: var(--mauve-lt);
    margin-bottom: 16px;
    font-weight: 300;
  }

  .stats-imgs {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
  }

  .stats-imgs img {
    border-radius: 10px;
    border: 1px solid var(--rose);
    max-width: 100%;
    height: auto;
  }

  .stats-code {
    background: var(--linen);
    border: 1.5px solid var(--beige);
    border-radius: 10px;
    padding: 14px 16px;
    font-family: 'DM Mono', monospace;
    font-size: 11.5px;
    color: var(--mauve);
    line-height: 1.9;
    white-space: pre;
    overflow-x: auto;
    margin-top: 12px;
  }

  /* ── CONTACT ── */
  .contact {
    background: var(--mauve);
    border-radius: 16px;
    padding: 28px 32px;
    animation: fadeUp 0.6s 0.5s ease both;
  }

  .contact .section-label {
    color: var(--rose);
  }

  .contact .section-label::after {
    background: rgba(255,255,255,0.15);
  }

  .contact-links {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 4px;
  }

  .contact-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 9px 18px;
    border-radius: 100px;
    font-size: 13px;
    font-weight: 500;
    text-decoration: none;
    border: 1.5px solid transparent;
    transition: transform 0.15s ease, opacity 0.15s ease;
    cursor: pointer;
  }

  .contact-btn:hover { transform: translateY(-2px); opacity: 0.9; }

  .btn-github   { background: var(--linen);   color: var(--mauve);  border-color: var(--beige); }
  .btn-linkedin { background: var(--blush);   color: var(--mauve);  border-color: var(--rose); }
  .btn-email    { background: var(--terra);   color: var(--linen);  border-color: var(--caramel); }

  .contact-btn svg { width: 14px; height: 14px; }

  /* ── MARKDOWN HINT ── */
  .hint {
    background: var(--linen);
    border: 1.5px dashed var(--beige);
    border-radius: 12px;
    padding: 20px 24px;
    animation: fadeUp 0.6s 0.55s ease both;
  }

  .hint p {
    font-size: 13px;
    color: var(--mauve-lt);
    line-height: 1.7;
  }

  .hint code {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    background: var(--blush);
    color: var(--mauve);
    padding: 2px 7px;
    border-radius: 5px;
  }

  /* ── ANIMATION ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(18px); }
    to   { opacity: 1; transform: translateY(0); }
  }
</style>
</head>
<body>
<div class="page">

  <!-- HEADER -->
  <div class="header">
    <div class="greeting">Hey there, I'm</div>
    <div class="name">Ana Catalina Torres</div>
    <div class="tagline">
      <strong>Systems Engineering student</strong> · Developer at Cooweb ·
      Curious about AI, design, and building things that actually matter.
    </div>
  </div>

  <!-- ABOUT -->
  <div class="about">
    <div class="section-label">About me</div>
    <p>
      I'm a Systems Engineering student based in <strong>Barranquilla, Colombia</strong>,
      working as a developer while studying full-time. I don't like narrow lanes —
      I'm into <strong>AI development</strong>, UI/UX design, hardware prototyping,
      and wherever curiosity takes me next. The best engineers never stop asking <em>why</em>.
    </p>
  </div>

  <!-- CURRENTLY -->
  <div class="currently">
    <div class="section-label">Currently</div>
    <div class="currently-items">
      <div class="currently-item">
        <div class="dot"></div>
        <span>Working with <strong>Cooweb</strong> as a developer</span>
      </div>
      <div class="currently-item">
        <div class="dot"></div>
        <span>Studying <strong>Systems Engineering</strong> at Universidad del Norte</span>
      </div>
      <div class="currently-item">
        <div class="dot"></div>
        <span>Always learning something new</span>
      </div>
    </div>
  </div>

  <!-- TECH -->
  <div class="tech">
    <div class="section-label">Tech stack</div>
    <div class="badges">

      <!-- HTML5 -->
      <span class="badge badge-html">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M1.5 0h21l-1.91 21.563L11.977 24l-8.565-2.438L1.5 0zm7.031 9.75l-.232-2.718 10.059.003.23-2.622L5.412 4.41l.698 8.01h9.126l-.326 3.426-2.91.804-2.955-.81-.188-2.11H6.248l.33 4.171L12 19.351l5.379-1.443.744-8.157H8.531z"/></svg>
        HTML5
      </span>

      <!-- CSS3 -->
      <span class="badge badge-css">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M1.5 0h21l-1.91 21.563L11.977 24l-8.564-2.438L1.5 0zm17.09 4.413L5.41 4.41l.213 2.622 10.125.003-.255 2.716h-6.64l.24 2.573h6.182l-.366 3.523-2.91.804-2.956-.81-.188-2.11h-2.61l.29 3.855L12 19.288l5.373-1.53L18.59 4.414z"/></svg>
        CSS3
      </span>

      <!-- JavaScript -->
      <span class="badge badge-js">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M0 0h24v24H0V0zm22.034 18.276c-.175-1.095-.888-2.015-3.003-2.873-.736-.345-1.554-.585-1.797-1.14-.091-.33-.105-.51-.046-.705.15-.646.915-.84 1.515-.66.39.12.75.42.976.9 1.034-.676 1.034-.676 1.755-1.125-.27-.42-.404-.601-.586-.78-.63-.705-1.469-1.065-2.834-1.034l-.705.089c-.676.165-1.32.525-1.71 1.005-1.14 1.291-.811 3.541.569 4.471 1.365 1.02 3.361 1.244 3.616 2.205.24 1.17-.87 1.545-1.966 1.41-.811-.18-1.26-.586-1.755-1.336l-1.83 1.051c.21.48.45.689.81 1.109 1.74 1.756 6.09 1.666 6.871-1.004.029-.09.24-.705.074-1.65l.046.067zm-8.983-7.245h-2.248c0 1.938-.009 3.864-.009 5.805 0 1.232.063 2.363-.138 2.711-.33.689-1.18.601-1.566.48-.396-.196-.597-.466-.83-.855-.063-.105-.11-.196-.127-.196l-1.825 1.125c.305.63.75 1.172 1.324 1.517.855.51 2.004.675 3.207.405.783-.226 1.458-.691 1.811-1.411.51-.93.402-2.07.397-3.346.012-2.054 0-4.109 0-6.179l.004-.056z"/></svg>
        JavaScript
      </span>

      <!-- Java -->
      <span class="badge badge-java">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M8.851 18.56s-.917.534.653.714c1.902.218 2.874.187 4.969-.211 0 0 .552.346 1.321.646-4.699 2.013-10.633-.118-6.943-1.149M8.276 15.933s-1.028.761.542.924c2.032.209 3.636.227 6.413-.308 0 0 .384.389.987.602-5.679 1.661-12.007.13-7.942-1.218M13.116 11.475c1.158 1.333-.304 2.533-.304 2.533s2.939-1.518 1.589-3.418c-1.261-1.772-2.228-2.652 3.007-5.688 0-.001-8.216 2.051-4.292 6.573M19.33 20.504s.679.559-.747.991c-2.712.822-11.288 1.069-13.669.033-.856-.373.75-.89 1.254-.998.527-.132.828-.107.828-.107-.953-.671-6.156 1.317-2.643 1.887 9.58 1.553 17.462-.7 14.977-1.806M9.292 13.21s-4.362 1.036-1.544 1.412c1.189.159 3.561.123 5.77-.062 1.806-.152 3.618-.482 3.618-.482s-.637.272-1.098.587c-4.429 1.165-12.986.623-10.522-.568 2.082-1.006 3.776-.887 3.776-.887M17.116 17.584c4.503-2.34 2.421-4.589.968-4.285-.355.074-.515.138-.515.138s.132-.207.385-.297c2.875-1.011 5.086 2.981-.928 4.562 0-.001.07-.062.09-.118M14.401 0s2.494 2.494-2.365 6.33c-3.896 3.077-.888 4.832-.001 6.836-2.274-2.053-3.943-3.858-2.824-5.539 1.644-2.469 6.197-3.665 5.19-7.627M9.734 23.924c4.322.277 10.959-.153 11.116-2.198 0 0-.302.775-3.572 1.391-3.688.694-8.239.613-10.937.168 0-.001.553.457 3.393.639"/></svg>
        Java
      </span>

      <!-- Python -->
      <span class="badge badge-py">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M14.25.18l.9.2.73.26.59.3.45.32.34.34.25.34.16.33.1.3.04.26.02.2-.01.13V8.5l-.05.63-.13.55-.21.46-.26.38-.3.31-.33.25-.35.19-.35.14-.33.1-.3.07-.26.04-.21.02H8.77l-.69.05-.59.14-.5.22-.41.27-.33.32-.27.35-.2.36-.15.37-.1.35-.07.32-.04.27-.02.21v3.06H3.17l-.21-.03-.28-.07-.32-.12-.35-.18-.36-.26-.36-.36-.35-.46-.32-.59-.28-.73-.21-.88-.14-1.05-.05-1.23.06-1.22.16-1.04.24-.87.32-.71.36-.57.4-.44.42-.33.42-.24.4-.16.36-.1.32-.05.26-.02.24.05.2.08.18.11.15.14.11.17.05.18.01.19-.03.19-.08.2-.14.2-.2.2-.26.19-.33.18-.4.16-.47.14-.54.13-.62-.1.08-.11.08-.12.07-.13.07-.14.06-.16.05-.17.05-.18.04-.19.03-.2.02-.21.02-.22.02-.22.02h-6.2zm0 10.04v-1.51l-.06.08-.1.06-.18.07-.28.07-.38.06-.5.06-.62.05-.72.04-.81.03-.88.03-.93.02-.96.01-.96.01-.93.01-.88.01-.81.02-.72.02-.62.03-.5.03-.38.04-.28.05-.18.06-.1.08-.06.08v1.51l.06.08.1.08.18.07.28.06.38.06.5.05.62.04.72.04.81.03.88.03.93.02.96.01.96.01.93.01.88.01.81.01.72.02.62.03.5.03.38.04.28.04.18.06.1.07.06.08zM17.76 14.2l.22-.11.22-.06.21-.03.21.02.2.06.19.09.18.13.16.16.15.19.12.22.1.25.06.28.04.31.02.33v.34l-.02.35-.04.33-.06.3-.1.26-.12.22-.15.19-.16.16-.18.13-.19.09-.2.06-.21.02-.21-.03-.22-.06-.22-.11-.22-.14-.2-.18-.19-.21-.17-.25-.15-.28-.12-.32-.09-.36-.06-.39-.03-.43V14.3l.03-.43.06-.39.09-.36.12-.32.15-.28.17-.25.19-.21.2-.18.22-.14z"/></svg>
        Python
      </span>

      <!-- Git -->
      <span class="badge badge-git">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M23.546 10.93L13.067.452c-.604-.603-1.582-.603-2.188 0L8.708 2.627l2.76 2.76c.645-.215 1.379-.07 1.889.441.516.515.658 1.258.438 1.9l2.658 2.66c.645-.223 1.387-.078 1.9.435.721.72.721 1.884 0 2.604-.719.719-1.881.719-2.6 0-.539-.541-.674-1.337-.404-1.996L12.86 8.955v6.525c.176.086.342.203.488.348.713.721.713 1.883 0 2.6-.719.721-1.889.721-2.609 0-.719-.719-.719-1.879 0-2.598.182-.18.387-.316.605-.406V8.835c-.217-.091-.424-.222-.6-.401-.545-.545-.676-1.342-.396-2.009L7.636 3.7.45 10.881c-.6.605-.6 1.584 0 2.189l10.48 10.477c.604.604 1.582.604 2.186 0l10.43-10.43c.605-.603.605-1.582 0-2.187"/></svg>
        Git
      </span>

      <!-- GitHub -->
      <span class="badge badge-gh">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
        GitHub
      </span>

    </div>
  </div>

  <!-- PROJECTS -->
  <div class="projects">
    <div class="section-label">What you'll find here</div>
    <div class="project-grid">
      <div class="project-card">
        <span class="icon">🤖</span>
        <h4>AI projects</h4>
        <p>Chatbots, integrations, and experiments with language models</p>
      </div>
      <div class="project-card">
        <span class="icon">🎨</span>
        <h4>UI / UX</h4>
        <p>Interfaces I've built or designed — functional and aesthetic</p>
      </div>
      <div class="project-card">
        <span class="icon">📚</span>
        <h4>Learning repos</h4>
        <p>Notes, exercises, and things I'm figuring out in public</p>
      </div>
      <div class="project-card">
        <span class="icon">🔧</span>
        <h4>Side projects</h4>
        <p>Things I build because I'm curious and can't help myself</p>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats">
    <div class="section-label">GitHub stats</div>
    <p class="stats-note">Replace <code>YOUR_USERNAME</code> with your actual GitHub username in the Markdown version.</p>
    <div class="stats-imgs">
      <img
        src="https://github-readme-stats.vercel.app/api?username=anakaren-rojas&show_icons=true&theme=rose_pine&include_all_commits=true&count_private=true&hide_border=true&bg_color=F9EDE8&title_color=7A4F45&text_color=7A4F45&icon_color=D4967E"
        alt="GitHub Stats"
        style="max-width: 340px;"
        onerror="this.style.display='none'"
      />
      <img
        src="https://github-readme-stats.vercel.app/api/top-langs/?username=anakaren-rojas&layout=compact&langs_count=6&hide_border=true&bg_color=F2D5CB&title_color=7A4F45&text_color=A07060"
        alt="Top Languages"
        style="max-width: 280px;"
        onerror="this.style.display='none'"
      />
    </div>
    <div class="stats-code"><!-- Pega esto en tu README.md -->
![Stats](https://github-readme-stats.vercel.app/api?username=YOUR_USERNAME
  &show_icons=true&hide_border=true
  &bg_color=F9EDE8&title_color=7A4F45
  &text_color=7A4F45&icon_color=D4967E)

![Langs](https://github-readme-stats.vercel.app/api/top-langs/
  ?username=YOUR_USERNAME&layout=compact
  &hide_border=true&bg_color=F2D5CB
  &title_color=7A4F45&text_color=A07060)</div>
  </div>

  <!-- CONTACT -->
  <div class="contact">
    <div class="section-label">Let's connect</div>
    <div class="contact-links">
      <a href="https://github.com/YOUR_USERNAME" class="contact-btn btn-github">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
        GitHub
      </a>
      <a href="https://linkedin.com/in/YOUR_LINKEDIN" class="contact-btn btn-linkedin">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a href="mailto:YOUR_EMAIL@gmail.com" class="contact-btn btn-email">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
        Email
      </a>
    </div>
  </div>

  <!-- HINT -->
  <div class="hint">
    <p>
      <strong style="color:var(--mauve);">Para usar esto como README.md en GitHub:</strong><br/>
      GitHub no renderiza HTML/CSS avanzado en READMEs, pero puedes usar las imágenes de stats con los colores de la paleta (ver sección de arriba) y los badges de shields.io. Este archivo HTML sirve como <strong>preview visual</strong> o como base para tu <strong>portafolio web</strong>.
    </p>
  </div>

</div>
</body>
</html>
