<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Thirunavukkarasu J – GitHub README</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --card: #16161f;
    --border: #1e1e2e;
    --accent: #39ff85;
    --accent2: #00c9ff;
    --accent3: #a78bfa;
    --text: #e2e8f0;
    --muted: #64748b;
    --danger: #ff6b6b;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(57,255,133,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(57,255,133,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 48px 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    text-align: center;
    padding: 56px 0 40px;
    position: relative;
  }

  .hero-glow {
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 500px; height: 300px;
    background: radial-gradient(ellipse at center, rgba(57,255,133,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .greeting {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: var(--accent);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 16px;
    opacity: 0;
    animation: fadeUp 0.6s 0.1s ease forwards;
  }

  .name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(36px, 6vw, 60px);
    font-weight: 800;
    line-height: 1.05;
    margin-bottom: 12px;
    opacity: 0;
    animation: fadeUp 0.6s 0.2s ease forwards;
  }

  .name span {
    background: linear-gradient(135deg, var(--accent) 0%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .role-line {
    font-family: 'DM Sans', sans-serif;
    font-size: 17px;
    font-weight: 300;
    color: var(--muted);
    margin-bottom: 8px;
    opacity: 0;
    animation: fadeUp 0.6s 0.3s ease forwards;
  }

  .role-line strong {
    color: var(--text);
    font-weight: 500;
  }

  .role-tags {
    display: flex;
    gap: 8px;
    justify-content: center;
    flex-wrap: wrap;
    margin: 20px 0 28px;
    opacity: 0;
    animation: fadeUp 0.6s 0.4s ease forwards;
  }

  .tag {
    padding: 4px 14px;
    border-radius: 999px;
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    font-weight: 400;
    letter-spacing: 0.5px;
    border: 1px solid;
  }
  .tag-green { border-color: var(--accent); color: var(--accent); background: rgba(57,255,133,0.06); }
  .tag-blue  { border-color: var(--accent2); color: var(--accent2); background: rgba(0,201,255,0.06); }
  .tag-purple{ border-color: var(--accent3); color: var(--accent3); background: rgba(167,139,250,0.06); }

  /* ── SOCIAL LINKS ── */
  .social-row {
    display: flex;
    gap: 12px;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 48px;
    opacity: 0;
    animation: fadeUp 0.6s 0.5s ease forwards;
  }

  .social-btn {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 8px 18px;
    border-radius: 8px;
    font-size: 13px;
    font-family: 'Space Mono', monospace;
    text-decoration: none;
    border: 1px solid var(--border);
    background: var(--card);
    color: var(--text);
    transition: all 0.2s ease;
    cursor: pointer;
  }
  .social-btn:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); box-shadow: 0 8px 24px rgba(57,255,133,0.1); }
  .social-btn svg { width: 15px; height: 15px; fill: currentColor; }

  /* ── DIVIDER ── */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--accent), var(--accent2), transparent);
    margin: 0 0 40px;
    opacity: 0.3;
  }

  /* ── SECTION HEADER ── */
  .section-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 24px;
  }
  .section-header .icon { font-size: 20px; }
  .section-header h2 {
    font-family: 'Syne', sans-serif;
    font-size: 20px;
    font-weight: 700;
    color: var(--text);
  }
  .section-header .line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── ABOUT ME CARD ── */
  .about-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 28px;
    margin-bottom: 32px;
    position: relative;
    overflow: hidden;
  }
  .about-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
  }

  .about-item {
    display: flex;
    align-items: flex-start;
    gap: 14px;
    padding: 10px 0;
    border-bottom: 1px solid rgba(255,255,255,0.04);
    font-size: 14.5px;
    line-height: 1.6;
  }
  .about-item:last-child { border-bottom: none; }
  .about-emoji { font-size: 18px; flex-shrink: 0; margin-top: 1px; }
  .about-label { color: var(--muted); font-size: 12px; font-family: 'Space Mono', monospace; margin-bottom: 2px; }
  .about-value { color: var(--text); }

  /* ── ACHIEVEMENTS ── */
  .achievements-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 16px;
    margin-bottom: 32px;
  }

  .achievement-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    position: relative;
    overflow: hidden;
    transition: all 0.2s ease;
  }
  .achievement-card:hover { border-color: var(--accent2); transform: translateY(-3px); box-shadow: 0 12px 32px rgba(0,201,255,0.08); }
  .achievement-card .badge {
    font-size: 28px;
    margin-bottom: 10px;
    display: block;
  }
  .achievement-card h3 {
    font-family: 'Syne', sans-serif;
    font-size: 15px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 4px;
  }
  .achievement-card p {
    font-size: 12.5px;
    color: var(--muted);
    line-height: 1.5;
  }
  .achievement-card .accent-dot {
    position: absolute;
    top: 16px; right: 16px;
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--accent);
    box-shadow: 0 0 8px var(--accent);
  }

  /* ── TECH STACK ── */
  .stack-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 28px;
    margin-bottom: 32px;
  }

  .stack-group { margin-bottom: 20px; }
  .stack-group:last-child { margin-bottom: 0; }
  .stack-group-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--accent);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .stack-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  .pill {
    padding: 5px 12px;
    border-radius: 6px;
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    background: var(--surface);
    border: 1px solid var(--border);
    color: var(--text);
    transition: all 0.15s;
  }
  .pill:hover { border-color: var(--accent2); color: var(--accent2); }

  /* ── FOOTER NOTE ── */
  .footer-note {
    text-align: center;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    padding: 32px 0 16px;
    letter-spacing: 1px;
  }
  .footer-note span { color: var(--accent); }

  /* ── COPY BUTTON ── */
  .copy-section {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    margin-bottom: 32px;
  }
  .copy-section h2 {
    font-family: 'Syne', sans-serif;
    font-size: 16px;
    font-weight: 700;
    margin-bottom: 16px;
    color: var(--accent);
  }
  .copy-section p {
    font-size: 13px;
    color: var(--muted);
    margin-bottom: 16px;
    line-height: 1.6;
  }
  pre {
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--accent2);
    overflow-x: auto;
    white-space: pre-wrap;
    word-break: break-all;
    line-height: 1.8;
    margin-bottom: 12px;
  }
  .copy-btn {
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    color: #000;
    border: none;
    padding: 10px 24px;
    border-radius: 8px;
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    font-weight: 700;
    cursor: pointer;
    transition: all 0.2s;
    letter-spacing: 1px;
  }
  .copy-btn:hover { opacity: 0.85; transform: translateY(-1px); }
  .copy-btn:active { transform: translateY(0); }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(18px); }
    to   { opacity: 1; transform: translateY(0); }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-glow"></div>
    <div class="greeting">👋 Hey there, I'm</div>
    <h1 class="name"><span>Thirunavukkarasu J</span></h1>
    <p class="role-line">
      <strong>Software Engineer II</strong> · transitioning into <strong>AI Systems & Applied ML</strong>
    </p>
    <div class="role-tags">
      <span class="tag tag-green">🤖 AI Systems Engineer</span>
      <span class="tag tag-blue">🧠 Applied ML</span>
      <span class="tag tag-purple">⚡ Full-Stack</span>
      <span class="tag tag-green">🔬 3× Patent Inventor</span>
    </div>

    <div class="social-row">
      <a class="social-btn" href="https://github.com/roxtj" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
        github/roxtj
      </a>
      <a class="social-btn" href="https://linkedin.com/in/thirunavukkarasu-j42b43818b" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a class="social-btn" href="mailto:thirunavukkarasuj12@gmail.com">
        <svg viewBox="0 0 24 24"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.910 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
        Email
      </a>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ABOUT ME -->
  <div class="section-header">
    <span class="icon">🧩</span>
    <h2>About Me</h2>
    <div class="line"></div>
  </div>
  <div class="about-card">
    <div class="about-item">
      <span class="about-emoji">🔭</span>
      <div>
        <div class="about-label">Currently Working On</div>
        <div class="about-value">Agentic AI systems, RAG pipelines, and LLM-powered full-stack applications</div>
      </div>
    </div>
    <div class="about-item">
      <span class="about-emoji">👥</span>
      <div>
        <div class="about-label">Looking to Collaborate On</div>
        <div class="about-value">Open-source LLM projects, AI agents, applied ML tools, and GenAI experiments</div>
      </div>
    </div>
    <div class="about-item">
      <span class="about-emoji">💛</span>
      <div>
        <div class="about-label">Looking for Help With</div>
        <div class="about-value">Deepening expertise in ML fundamentals, model fine-tuning, and AI systems design</div>
      </div>
    </div>
    <div class="about-item">
      <span class="about-emoji">🌱</span>
      <div>
        <div class="about-label">Currently Learning</div>
        <div class="about-value">LLM internals, ML system design, AI infrastructure, and staying current with the latest AI research</div>
      </div>
    </div>
    <div class="about-item">
      <span class="about-emoji">💬</span>
      <div>
        <div class="about-label">Ask Me About</div>
        <div class="about-value">Building AI systems end-to-end, RAG, LLM orchestration, full-stack development, or the latest in GenAI</div>
      </div>
    </div>
    <div class="about-item">
      <span class="about-emoji">⚡</span>
      <div>
        <div class="about-label">Fun Fact</div>
        <div class="about-value">I hold 3 patents in multi-agent AI and computer vision — and I'm just getting started in the AI space!</div>
      </div>
    </div>
  </div>

  <!-- ACHIEVEMENTS -->
  <div class="section-header">
    <span class="icon">🏆</span>
    <h2>Achievements</h2>
    <div class="line"></div>
  </div>
  <div class="achievements-grid">
    <div class="achievement-card">
      <span class="badge">📜</span>
      <div class="accent-dot"></div>
      <h3>3× Patent Inventor</h3>
      <p>Multi-agent GenAI, computer vision confidence recovery & federated RAG orchestration</p>
    </div>
    <div class="achievement-card">
      <span class="badge">🏅</span>
      <div class="accent-dot" style="background:var(--accent2);box-shadow:0 0 8px var(--accent2)"></div>
      <h3>Regional Hackathon Winner</h3>
      <p>CSG Hackathon 2024 — Regional Winner</p>
    </div>
    <div class="achievement-card">
      <span class="badge">🎤</span>
      <div class="accent-dot" style="background:var(--accent3);box-shadow:0 0 8px var(--accent3)"></div>
      <h3>Tech Forum Speaker</h3>
      <p>Presented at AI Academy Sparks Tech Forum 2025</p>
    </div>
    <div class="achievement-card">
      <span class="badge">🤖</span>
      <div class="accent-dot"></div>
      <h3>GenAI Platform Builder</h3>
      <p>Contributed to enterprise AI model hub — standardizing NPU-optimized model access</p>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section-header">
    <span class="icon">🛠️</span>
    <h2>Tech Stack</h2>
    <div class="line"></div>
  </div>
  <div class="stack-card">
    <div class="stack-group">
      <div class="stack-group-label">AI / ML</div>
      <div class="stack-pills">
        <span class="pill">Agentic AI</span>
        <span class="pill">RAG Pipelines</span>
        <span class="pill">LLM Orchestration</span>
        <span class="pill">ONNX Runtime</span>
        <span class="pill">YOLOv8</span>
        <span class="pill">PyTorch</span>
        <span class="pill">Scikit-learn</span>
        <span class="pill">Pandas</span>
        <span class="pill">NumPy</span>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label">Backend</div>
      <div class="stack-pills">
        <span class="pill">Java</span>
        <span class="pill">Spring Boot</span>
        <span class="pill">Node.js</span>
        <span class="pill">Python</span>
        <span class="pill">FastAPI</span>
        <span class="pill">Microservices</span>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label">Frontend</div>
      <div class="stack-pills">
        <span class="pill">Angular</span>
        <span class="pill">TypeScript</span>
        <span class="pill">JavaScript</span>
        <span class="pill">React</span>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label">Cloud / DevOps</div>
      <div class="stack-pills">
        <span class="pill">Docker</span>
        <span class="pill">Kubernetes</span>
        <span class="pill">AWS</span>
        <span class="pill">GitHub Actions</span>
        <span class="pill">Jenkins</span>
        <span class="pill">ArgoCD</span>
      </div>
    </div>
  </div>

  <!-- README SNIPPET -->
  <div class="copy-section">
    <h2>📋 Your GPRM Header Block (copy into README)</h2>
    <p>Paste this at the very top of your GitHub README, above the GPRM-generated content. It adds your name, role, tags, and social links in Markdown.</p>
    <pre id="readme-snippet">&lt;div align="center"&gt;

# 👋 Hi, I'm Thirunavukkarasu J

### Software Engineer II → AI Systems Engineer | Applied ML Enthusiast

![AI Systems](https://img.shields.io/badge/AI%20Systems%20Engineer-in%20progress-39ff85?style=flat-square&labelColor=0a0a0f)
![Applied ML](https://img.shields.io/badge/Applied%20ML-Specialist-00c9ff?style=flat-square&labelColor=0a0a0f)
![Patents](https://img.shields.io/badge/Patents-3×%20Inventor-a78bfa?style=flat-square&labelColor=0a0a0f)

[![GitHub](https://img.shields.io/badge/GitHub-roxtj-181717?style=flat-square&logo=github)](https://github.com/roxtj)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Thirunavukkarasu%20J-0A66C2?style=flat-square&logo=linkedin)](https://linkedin.com/in/thirunavukkarasu-j42b43818b)
[![Email](https://img.shields.io/badge/Email-thirunavukkarasuj12%40gmail.com-EA4335?style=flat-square&logo=gmail)](mailto:thirunavukkarasuj12@gmail.com)

&lt;/div&gt;

---</pre>
    <button class="copy-btn" onclick="copySnippet()">⬇ COPY README SNIPPET</button>
    <span id="copy-msg" style="font-size:12px;color:var(--accent);margin-left:12px;font-family:'Space Mono',monospace;display:none">✓ Copied!</span>
  </div>

  <div class="footer-note">
    Built for <span>github.com/roxtj</span> · Transitioning into AI Systems & Applied ML
  </div>

</div>

<script>
function copySnippet() {
  const text = document.getElementById('readme-snippet').innerText;
  navigator.clipboard.writeText(text).then(() => {
    const msg = document.getElementById('copy-msg');
    msg.style.display = 'inline';
    setTimeout(() => msg.style.display = 'none', 2500);
  });
}
</script>
</body>
</html>
