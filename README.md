<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Aashyy — Software Engineer Portfolio</title>

  <style>
    :root {
      --bg: #0b0f14;
      --panel: #111820;
      --panel-2: #151e27;
      --border: #27323d;
      --text: #e7edf3;
      --muted: #8d9aa7;
      --cyan: #00d9ff;
      --blue: #4f8cff;
      --green: #36d399;
      --purple: #a78bfa;
      --orange: #ff9f43;
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      background:
        radial-gradient(circle at 50% -10%, rgba(0, 217, 255, 0.08), transparent 35%),
        var(--bg);
      color: var(--text);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      line-height: 1.6;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    .container {
      width: min(1120px, calc(100% - 36px));
      margin: 0 auto;
    }

    .top-line {
      height: 2px;
      margin-top: 28px;
      background: linear-gradient(90deg, transparent, var(--cyan), var(--blue), var(--cyan), transparent);
      box-shadow: 0 0 18px rgba(0, 217, 255, 0.25);
    }

    .hero {
      min-height: 520px;
      display: grid;
      place-items: center;
      text-align: center;
      padding: 70px 20px 55px;
    }

    .terminal-label {
      display: inline-flex;
      gap: 8px;
      align-items: center;
      padding: 7px 13px;
      border: 1px solid var(--border);
      background: rgba(17, 24, 32, 0.75);
      color: var(--cyan);
      font: 600 12px/1.2 "JetBrains Mono", Consolas, monospace;
      letter-spacing: 1px;
      text-transform: uppercase;
    }

    .terminal-dot {
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: var(--green);
      box-shadow: 0 0 10px rgba(54, 211, 153, .8);
    }

    h1 {
      margin: 22px 0 8px;
      font-size: clamp(48px, 10vw, 92px);
      line-height: .95;
      letter-spacing: -5px;
      font-weight: 850;
    }

    .gradient-text {
      background: linear-gradient(90deg, #fff, #9deeff 45%, #78a9ff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .hero-role {
      margin: 18px 0;
      color: var(--muted);
      font: 600 clamp(14px, 2vw, 19px)/1.4 "JetBrains Mono", Consolas, monospace;
    }

    .hero-role span {
      color: var(--cyan);
    }

    .hero-description {
      max-width: 760px;
      margin: 0 auto;
      color: #aeb9c4;
      font-size: 16px;
    }

    .badges {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 8px;
      margin-top: 28px;
    }

    .badge {
      padding: 7px 11px;
      border: 1px solid var(--border);
      border-radius: 4px;
      background: #141c24;
      color: #dce5ed;
      font: 600 12px/1.2 "JetBrains Mono", Consolas, monospace;
    }

    .badge.cyan { border-color: rgba(0,217,255,.35); color: var(--cyan); }
    .badge.blue { border-color: rgba(79,140,255,.35); color: #8fb4ff; }
    .badge.green { border-color: rgba(54,211,153,.35); color: var(--green); }
    .badge.purple { border-color: rgba(167,139,250,.35); color: var(--purple); }
    .badge.orange { border-color: rgba(255,159,67,.35); color: var(--orange); }

    .section {
      padding: 28px 0 70px;
    }

    .section-divider {
      height: 1px;
      background: linear-gradient(90deg, transparent, var(--border), transparent);
      margin-bottom: 52px;
    }

    .section-title {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 18px;
      margin-bottom: 34px;
      font: 800 22px/1 "JetBrains Mono", Consolas, monospace;
      letter-spacing: 1px;
      text-transform: uppercase;
    }

    .section-title::before,
    .section-title::after {
      content: "";
      width: 55px;
      height: 1px;
      background: var(--border);
    }

    .section-title .symbol {
      color: var(--cyan);
    }

    .profile-terminal {
      max-width: 900px;
      margin: auto;
      padding: 26px;
      border: 1px solid #36424d;
      background:
        linear-gradient(180deg, rgba(255,255,255,.018), transparent),
        #111820;
      box-shadow: 0 20px 60px rgba(0,0,0,.2);
      font-family: "JetBrains Mono", Consolas, monospace;
      position: relative;
    }

    .terminal-header {
      display: flex;
      gap: 7px;
      padding-bottom: 18px;
      margin-bottom: 18px;
      border-bottom: 1px solid var(--border);
    }

    .terminal-header i {
      width: 9px;
      height: 9px;
      border-radius: 50%;
      background: #48545f;
    }

    .terminal-header i:first-child { background: #ff5f56; }
    .terminal-header i:nth-child(2) { background: #ffbd2e; }
    .terminal-header i:nth-child(3) { background: #27c93f; }

    .terminal-grid {
      display: grid;
      grid-template-columns: 170px 1fr;
      gap: 10px 24px;
      font-size: 14px;
    }

    .terminal-grid .key {
      color: #6f8190;
    }

    .terminal-grid .value {
      color: #dfe8ef;
    }

    .terminal-grid .value strong {
      color: var(--cyan);
    }

    .terminal-grid .value .green {
      color: var(--green);
    }

    .tech-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 14px;
    }

    .tech-card {
      min-height: 150px;
      padding: 20px;
      border: 1px solid var(--border);
      background: var(--panel);
      transition: .2s ease;
    }

    .tech-card:hover {
      transform: translateY(-3px);
      border-color: rgba(0,217,255,.45);
      box-shadow: 0 10px 30px rgba(0,0,0,.22);
    }

    .tech-icon {
      font-size: 27px;
      margin-bottom: 12px;
    }

    .tech-card h3 {
      margin: 0 0 10px;
      font-size: 15px;
    }

    .tech-card p {
      margin: 0;
      color: var(--muted);
      font: 12px/1.8 "JetBrains Mono", Consolas, monospace;
    }

    .security-box {
      max-width: 900px;
      margin: auto;
      border: 1px solid var(--border);
      background: var(--panel);
      overflow: hidden;
    }

    .security-head {
      padding: 16px 20px;
      border-bottom: 1px solid var(--border);
      color: var(--cyan);
      font: 700 13px "JetBrains Mono", Consolas, monospace;
    }

    .flow {
      padding: 26px;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-wrap: wrap;
      gap: 8px;
    }

    .flow-item {
      padding: 11px 14px;
      border: 1px solid var(--border);
      background: #0e151c;
      font: 600 12px "JetBrains Mono", Consolas, monospace;
    }

    .flow-arrow {
      color: var(--cyan);
      font-family: monospace;
    }

    .security-note {
      padding: 0 26px 26px;
      text-align: center;
      color: var(--muted);
      font-size: 13px;
    }

    .security-tools {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 8px;
      padding: 0 26px 26px;
    }

    .security-tool {
      padding: 7px 10px;
      border-radius: 3px;
      border: 1px solid var(--border);
      background: #0d141b;
      color: #b9c6d0;
      font: 600 11px "JetBrains Mono", Consolas, monospace;
    }

    .project {
      max-width: 900px;
      margin: auto;
      border: 1px solid var(--border);
      background: var(--panel);
      padding: 28px;
    }

    .project-top {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      gap: 20px;
    }

    .project h3 {
      margin: 0;
      font-size: 25px;
    }

    .project-subtitle {
      margin-top: 5px;
      color: var(--cyan);
      font: 600 12px "JetBrains Mono", Consolas, monospace;
    }

    .project-description {
      color: var(--muted);
      max-width: 700px;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 7px;
      margin-top: 18px;
    }

    .project-tag {
      padding: 6px 9px;
      border: 1px solid var(--border);
      background: #0e151c;
      color: #aebbc6;
      font: 600 11px "JetBrains Mono", Consolas, monospace;
    }

    .project-button {
      display: inline-block;
      margin-top: 22px;
      padding: 10px 15px;
      border: 1px solid rgba(0,217,255,.5);
      color: var(--cyan);
      font: 700 12px "JetBrains Mono", Consolas, monospace;
    }

    .project-button:hover {
      background: rgba(0,217,255,.08);
    }

    .workflow {
      max-width: 950px;
      margin: auto;
      display: grid;
      grid-template-columns: repeat(7, 1fr);
      gap: 8px;
    }

    .workflow-item {
      position: relative;
      text-align: center;
      padding: 16px 6px;
      border: 1px solid var(--border);
      background: var(--panel);
      font: 600 11px "JetBrains Mono", Consolas, monospace;
      color: #c3ced7;
    }

    .workflow-item span {
      display: block;
      font-size: 20px;
      margin-bottom: 7px;
    }

    .stats {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 14px;
      max-width: 900px;
      margin: auto;
    }

    .stat {
      border: 1px solid var(--border);
      background: var(--panel);
      padding: 25px;
      text-align: center;
    }

    .stat strong {
      display: block;
      font: 800 28px "JetBrains Mono", Consolas, monospace;
      color: var(--cyan);
    }

    .stat span {
      color: var(--muted);
      font-size: 12px;
    }

    footer {
      padding: 40px 0 60px;
      text-align: center;
      border-top: 1px solid var(--border);
      color: var(--muted);
    }

    .footer-name {
      color: var(--text);
      font: 800 18px "JetBrains Mono", Consolas, monospace;
    }

    .footer-links {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 10px;
      margin: 18px 0 25px;
    }

    .footer-link {
      padding: 8px 13px;
      border: 1px solid var(--border);
      font: 600 11px "JetBrains Mono", Consolas, monospace;
    }

    .footer-link:hover {
      border-color: var(--cyan);
      color: var(--cyan);
    }

    .quote {
      color: #687784;
      font: 600 12px "JetBrains Mono", Consolas, monospace;
    }

    @media (max-width: 850px) {
      .tech-grid {
        grid-template-columns: repeat(2, 1fr);
      }

      .workflow {
        grid-template-columns: repeat(4, 1fr);
      }
    }

    @media (max-width: 600px) {
      .container {
        width: min(100% - 22px, 1120px);
      }

      .hero {
        padding-top: 50px;
      }

      h1 {
        letter-spacing: -3px;
      }

      .terminal-grid {
        grid-template-columns: 1fr;
        gap: 3px;
      }

      .terminal-grid .key {
        margin-top: 8px;
      }

      .tech-grid,
      .stats {
        grid-template-columns: 1fr;
      }

      .workflow {
        grid-template-columns: repeat(2, 1fr);
      }

      .project-top {
        flex-direction: column;
      }

      .section {
        padding-bottom: 45px;
      }
    }
  </style>
</head>

<body>

  <main class="container">

    <div class="top-line"></div>

    <!-- HERO -->
    <section class="hero">
      <div>
        <div class="terminal-label">
          <span class="terminal-dot"></span>
          Software Engineer // Online
        </div>

        <h1 class="gradient-text">AASHYY</h1>

        <div class="hero-role">
          <span>PHP / Laravel</span>
          · React
          · Linux
          · APIs
          · Security-Aware Development
        </div>

        <p class="hero-description">
          Software Engineer building production-ready web applications,
          SaaS platforms, APIs and business systems — with a security-aware
          mindset shaped by hands-on software and cybersecurity learning.
        </p>

        <div class="badges">
          <span class="badge cyan">PHP</span>
          <span class="badge cyan">Laravel</span>
          <span class="badge blue">React</span>
          <span class="badge green">MySQL</span>
          <span class="badge purple">Redis</span>
          <span class="badge orange">Linux</span>
          <span class="badge blue">REST APIs</span>
          <span class="badge cyan">Git / GitHub</span>
        </div>
      </div>
    </section>

    <!-- PROFILE -->
    <section class="section">
      <div class="section-divider"></div>

      <h2 class="section-title">
        <span class="symbol">&lt;_</span>
        Engineering Profile
        <span class="symbol">_&gt;</span>
      </h2>

      <div class="profile-terminal">
        <div class="terminal-header">
          <i></i><i></i><i></i>
        </div>

        <div class="terminal-grid">
          <div class="key">identity</div>
          <div class="value"><strong>Aashyy</strong></div>

          <div class="key">role</div>
          <div class="value">Software Engineer / PHP Developer</div>

          <div class="key">experience</div>
          <div class="value">3+ years professional development</div>

          <div class="key">primary_stack</div>
          <div class="value">PHP · Laravel · React · MySQL</div>

          <div class="key">infrastructure</div>
          <div class="value">Linux · Nginx · VPS · Redis · Supervisor</div>

          <div class="key">security</div>
          <div class="value">Security-aware software development</div>

          <div class="key">status</div>
          <div class="value"><span class="green">● Building & Learning</span></div>
        </div>
      </div>
    </section>

    <!-- TECH -->
    <section class="section">
      <h2 class="section-title">
        <span class="symbol">&lt;/&gt;</span>
        Tech Arsenal
        <span class="symbol">&lt;/&gt;</span>
      </h2>

      <div class="tech-grid">

        <div class="tech-card">
          <div class="tech-icon">⚙️</div>
          <h3>Backend</h3>
          <p>PHP<br>Laravel<br>CodeIgniter<br>REST APIs</p>
        </div>

        <div class="tech-card">
          <div class="tech-icon">🎨</div>
          <h3>Frontend</h3>
          <p>React<br>JavaScript<br>HTML / CSS<br>Tailwind CSS</p>
        </div>

        <div class="tech-card">
          <div class="tech-icon">🗄️</div>
          <h3>Data</h3>
          <p>MySQL<br>Redis<br>Database Design<br>Query Optimization</p>
        </div>

        <div class="tech-card">
          <div class="tech-icon">🖥️</div>
          <h3>Infrastructure</h3>
          <p>Ubuntu<br>Nginx<br>PHP-FPM<br>Supervisor / Cron</p>
        </div>

        <div class="tech-card">
          <div class="tech-icon">🔧</div>
          <h3>DevOps</h3>
          <p>Git<br>GitHub<br>SSH<br>VPS / Deployment</p>
        </div>

        <div class="tech-card">
          <div class="tech-icon">📱</div>
          <h3>Mobile</h3>
          <p>Flutter<br>Firebase<br>REST Integration<br>Android</p>
        </div>

        <div class="tech-card">
          <div class="tech-icon">💳</div>
          <h3>Integrations</h3>
          <p>Payment APIs<br>SMS APIs<br>Voice APIs<br>Third-party APIs</p>
        </div>

        <div class="tech-card">
          <div class="tech-icon">🔐</div>
          <h3>Security Mindset</h3>
          <p>Auth<br>Access Control<br>Input Validation<br>Secure Design</p>
        </div>

      </div>
    </section>

    <!-- SECURITY -->
    <section class="section">
      <h2 class="section-title">
        <span class="symbol">[</span>
        Security-Aware Development
        <span class="symbol">]</span>
      </h2>

      <div class="security-box">

        <div class="security-head">
          // THINKING ABOUT SECURITY WHILE BUILDING
        </div>

        <div class="flow">
          <div class="flow-item">INPUT</div>
          <div class="flow-arrow">→</div>
          <div class="flow-item">AUTH</div>
          <div class="flow-arrow">→</div>
          <div class="flow-item">ACCESS</div>
          <div class="flow-arrow">→</div>
          <div class="flow-item">LOGIC</div>
          <div class="flow-arrow">→</div>
          <div class="flow-item">DATA</div>
          <div class="flow-arrow">→</div>
          <div class="flow-item">DEPLOY</div>
        </div>

        <div class="security-note">
          Cybersecurity is an area of personal learning rather than my
          professional specialization. It has shaped the way I think about
          vulnerabilities, misuse, authentication, access control and
          secure software design.
        </div>

        <div class="security-tools">
          <span class="security-tool">Kali Linux — Basics</span>
          <span class="security-tool">Nmap — Basics</span>
          <span class="security-tool">Metasploit — Basics</span>
          <span class="security-tool">Wireless Security — Fundamentals</span>
        </div>

      </div>
    </section>

    <!-- PROJECTS -->
    <section class="section">
      <h2 class="section-title">
        <span class="symbol">★</span>
        Featured Project
        <span class="symbol">★</span>
      </h2>

      <div class="project">

        <div class="project-top">
          <div>
            <h3>🏋️ Smarto Gym</h3>
            <div class="project-subtitle">
              GYM MANAGEMENT · SAAS · WEB + MOBILE
            </div>
          </div>

          <div class="badge cyan">ACTIVE PROJECT</div>
        </div>

        <p class="project-description">
          A gym management SaaS platform designed to manage members,
          memberships, attendance, payments, reports and gym operations
          across web and mobile applications.
        </p>

        <div class="project-tags">
          <span class="project-tag">Laravel</span>
          <span class="project-tag">React</span>
          <span class="project-tag">MySQL</span>
          <span class="project-tag">Redis</span>
          <span class="project-tag">Flutter</span>
          <span class="project-tag">REST API</span>
        </div>

        <a class="project-button" href="https://smartogym.in" target="_blank">
          → VISIT SMARTOGYM.IN
        </a>

      </div>
    </section>

    <!-- WORK -->
    <section class="section">
      <h2 class="section-title">
        <span class="symbol">▣</span>
        Professional Experience
        <span class="symbol">▣</span>
      </h2>

      <div class="profile-terminal">

        <div class="terminal-header">
          <i></i><i></i><i></i>
        </div>

        <div class="terminal-grid">
          <div class="key">position</div>
          <div class="value">Software Engineer / PHP Developer</div>

          <div class="key">experience</div>
          <div class="value">3+ years</div>

          <div class="key">domains</div>
          <div class="value">ERP · CRM · LMS · SaaS · Business Applications</div>

          <div class="key">backend</div>
          <div class="value">PHP · Laravel · CodeIgniter · REST APIs</div>

          <div class="key">frontend</div>
          <div class="value">React · JavaScript · HTML · CSS</div>

          <div class="key">collaboration</div>
          <div class="value">Backend · Frontend · Flutter · Infrastructure</div>

          <div class="key">deployment</div>
          <div class="value">Linux · Nginx · VPS · Git · SSH</div>
        </div>

      </div>
    </section>

    <!-- WORKFLOW -->
    <section class="section">
      <h2 class="section-title">
        <span class="symbol">↻</span>
        Engineering Workflow
        <span class="symbol">↻</span>
      </h2>

      <div class="workflow">
        <div class="workflow-item"><span>💡</span>IDEA</div>
        <div class="workflow-item"><span>🏗️</span>DESIGN</div>
        <div class="workflow-item"><span>💻</span>BUILD</div>
        <div class="workflow-item"><span>🛡️</span>SECURE</div>
        <div class="workflow-item"><span>🧪</span>TEST</div>
        <div class="workflow-item"><span>🚀</span>DEPLOY</div>
        <div class="workflow-item"><span>🔁</span>IMPROVE</div>
      </div>
    </section>

    <!-- FOCUS -->
    <section class="section">
      <h2 class="section-title">
        <span class="symbol">+</span>
        Current Focus
        <span class="symbol">+</span>
      </h2>

      <div class="stats">
        <div class="stat">
          <strong>PHP</strong>
          <span>Backend Engineering</span>
        </div>

        <div class="stat">
          <strong>Laravel</strong>
          <span>Application Architecture</span>
        </div>

        <div class="stat">
          <strong>Linux</strong>
          <span>Infrastructure & Deployment</span>
        </div>
      </div>
    </section>

    <footer>
      <div class="footer-name">AASHYY</div>

      <div class="footer-links">
        <a class="footer-link" href="https://github.com/aqashyy" target="_blank">GitHub</a>
        <!-- <a class="footer-link" href="https://smartogym.in" target="_blank">Portfolio</a> -->
        <a class="footer-link" href="https://www.linkedin.com/in/ashiqmuhammedep" onclick="return false;">LinkedIn</a>
        <a class="footer-link" href="mailto:ashiqmuhammedep@gmail.com">Email</a>
      </div>

      <div class="quote">
        Build software. Understand how it can fail. Make it better.
      </div>
    </footer>

  </main>

</body>
</html>
