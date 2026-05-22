<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Yuktha Priya Masupalli — Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=Syne:wght@400;500;700;800&display=swap" rel="stylesheet" />
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/dist/tabler-icons.min.css" />
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --cream: #F7F5F0;
    --ink: #1A1814;
    --muted: #6B6760;
    --accent: #C85A2A;
    --accent-light: #F0E8E0;
    --border: rgba(26,24,20,0.12);
    --card-bg: #FFFFFF;
  }

  body {
    font-family: 'Syne', sans-serif;
    background: var(--cream);
    color: var(--ink);
    min-height: 100vh;
    padding: 0 0 4rem;
  }

  /* HERO */
  .hero {
    padding: 3.5rem 2.5rem 2.5rem;
    border-bottom: 0.5px solid var(--border);
    position: relative;
    overflow: hidden;
  }

  .hero::before {
    content: 'YPM';
    font-family: 'DM Serif Display', serif;
    font-size: 220px;
    color: rgba(200, 90, 42, 0.06);
    position: absolute;
    top: -20px;
    right: -20px;
    line-height: 1;
    pointer-events: none;
    letter-spacing: -8px;
  }

  .eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 1rem;
  }

  .hero-name {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(38px, 5vw, 58px);
    font-weight: 400;
    line-height: 1.05;
    letter-spacing: -1px;
    margin-bottom: 0.75rem;
  }

  .hero-name em {
    font-style: italic;
    color: var(--accent);
  }

  .hero-tagline {
    font-size: 14px;
    color: var(--muted);
    font-weight: 400;
    max-width: 560px;
    line-height: 1.7;
    margin-bottom: 1.75rem;
  }

  .hero-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .pill {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    padding: 5px 12px;
    border: 0.5px solid var(--border);
    border-radius: 100px;
    color: var(--muted);
    background: transparent;
  }

  .pill.accent {
    border-color: var(--accent);
    color: var(--accent);
    background: var(--accent-light);
  }

  /* SECTION */
  .section {
    padding: 2.5rem 2.5rem 0;
  }

  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 1.25rem;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 0.5px;
    background: var(--border);
  }

  /* STAT STRIP */
  .stat-strip {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 0;
    border-bottom: 0.5px solid var(--border);
    margin-top: 2.5rem;
  }

  .stat-cell {
    padding: 1.25rem 2.5rem;
    border-right: 0.5px solid var(--border);
  }

  .stat-cell:last-child { border-right: none; }

  .stat-num {
    font-family: 'DM Serif Display', serif;
    font-size: 32px;
    color: var(--ink);
    line-height: 1;
    margin-bottom: 4px;
  }

  .stat-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.08em;
  }

  /* SKILLS GRID */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 8px;
  }

  .skill-card {
    background: var(--card-bg);
    border: 0.5px solid var(--border);
    border-radius: 12px;
    padding: 1rem 1.1rem;
    cursor: pointer;
    transition: border-color 0.2s, transform 0.15s;
  }

  .skill-card:hover { border-color: var(--accent); transform: translateY(-1px); }

  .skill-card.active {
    border-color: var(--accent);
    background: var(--accent-light);
  }

  .skill-icon {
    font-size: 18px;
    margin-bottom: 8px;
    color: var(--accent);
  }

  .skill-title {
    font-size: 13px;
    font-weight: 700;
    color: var(--ink);
    margin-bottom: 4px;
  }

  .skill-tags {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    line-height: 1.6;
  }

  /* SKILL DETAIL */
  .skill-detail {
    display: none;
    background: var(--card-bg);
    border: 0.5px solid var(--accent);
    border-radius: 12px;
    padding: 1.25rem;
    margin-top: 12px;
    animation: fadeUp 0.2s ease;
  }

  .skill-detail.visible { display: block; }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(4px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .detail-label {
    font-size: 12px;
    color: var(--muted);
    margin-bottom: 10px;
  }

  .detail-items {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .detail-item {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    padding: 4px 10px;
    border: 0.5px solid var(--border);
    border-radius: 6px;
    color: var(--ink);
    background: var(--cream);
  }

  /* PROJECTS */
  .projects-list {
    display: flex;
    flex-direction: column;
  }

  .project-row {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 1.5rem;
    padding: 1.25rem 0;
    border-bottom: 0.5px solid var(--border);
    align-items: start;
    cursor: pointer;
    transition: padding-left 0.2s;
  }

  .project-row:hover { padding-left: 8px; }
  .project-row:first-child { border-top: 0.5px solid var(--border); }

  .project-num {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: var(--accent);
    margin-bottom: 4px;
  }

  .project-title {
    font-size: 15px;
    font-weight: 700;
    margin-bottom: 4px;
    color: var(--ink);
  }

  .project-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.6;
  }

  .project-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
    justify-content: flex-end;
  }

  .tag {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    padding: 3px 8px;
    background: var(--accent-light);
    border: 0.5px solid rgba(200,90,42,0.2);
    color: var(--accent);
    border-radius: 4px;
  }

  /* PUBLICATIONS */
  .pub-list {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .pub-item {
    background: var(--card-bg);
    border: 0.5px solid var(--border);
    border-left: 2px solid var(--accent);
    border-radius: 0 8px 8px 0;
    padding: 0.85rem 1rem;
  }

  .pub-title {
    font-size: 13px;
    font-weight: 500;
    color: var(--ink);
    line-height: 1.5;
  }

  .pub-venue {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    margin-top: 4px;
  }

  /* CONNECT */
  .connect-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 1rem;
  }

  .connect-btn {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    padding: 9px 16px;
    border: 0.5px solid var(--border);
    border-radius: 8px;
    background: var(--card-bg);
    color: var(--ink);
    cursor: pointer;
    text-decoration: none;
    transition: border-color 0.2s, background 0.2s, color 0.2s;
  }

  .connect-btn:hover {
    border-color: var(--accent);
    background: var(--accent-light);
    color: var(--accent);
  }

  .connect-btn i { font-size: 14px; }

  @media (max-width: 640px) {
    .stat-strip { grid-template-columns: repeat(2, 1fr); }
    .stat-cell { border-right: 0.5px solid var(--border); border-bottom: 0.5px solid var(--border); }
    .project-row { grid-template-columns: 1fr; }
    .project-stack { justify-content: flex-start; }
    .hero::before { font-size: 120px; }
  }
</style>
</head>
<body>

<!-- HERO -->
<div class="hero">
  <div class="eyebrow">Portfolio · 2025</div>
  <h1 class="hero-name">Yuktha Priya<br><em>Masupalli</em></h1>
  <p class="hero-tagline">AI/ML Engineer & Full-Stack Developer — building reliable user experiences and ML-enabled applications with a strong focus on quality and scalability. M.S. Computer Science, Texas A&M University–San Antonio.</p>
  <div class="hero-pills">
    <span class="pill accent">Open to opportunities</span>
    <span class="pill">Medical AI Research</span>
    <span class="pill">Angular · TypeScript</span>
    <span class="pill">PyTorch · TensorFlow</span>
    <span class="pill">Distributed Systems</span>
  </div>
</div>

<!-- STATS -->
<div class="stat-strip">
  <div class="stat-cell">
    <div class="stat-num">1+</div>
    <div class="stat-label">Years industry</div>
  </div>
  <div class="stat-cell">
    <div class="stat-num">3</div>
    <div class="stat-label">Publications</div>
  </div>
  <div class="stat-cell">
    <div class="stat-num">5</div>
    <div class="stat-label">Featured projects</div>
  </div>
  <div class="stat-cell">
    <div class="stat-num">12+</div>
    <div class="stat-label">Technologies</div>
  </div>
</div>

<!-- SKILLS -->
<div class="section" style="margin-top: 2.5rem;">
  <div class="section-label">Areas of expertise</div>
  <div class="skills-grid" id="skillsGrid">
    <div class="skill-card" data-idx="0" onclick="toggleSkill(this)">
      <div class="skill-icon"><i class="ti ti-layout-dashboard" aria-hidden="true"></i></div>
      <div class="skill-title">Frontend</div>
      <div class="skill-tags">Angular · RxJS · TypeScript</div>
    </div>
    <div class="skill-card" data-idx="1" onclick="toggleSkill(this)">
      <div class="skill-icon"><i class="ti ti-server" aria-hidden="true"></i></div>
      <div class="skill-title">Backend & Data</div>
      <div class="skill-tags">Node.js · Flask · PostgreSQL</div>
    </div>
    <div class="skill-card" data-idx="2" onclick="toggleSkill(this)">
      <div class="skill-icon"><i class="ti ti-brain" aria-hidden="true"></i></div>
      <div class="skill-title">AI / ML</div>
      <div class="skill-tags">PyTorch · TensorFlow · Scikit-Learn</div>
    </div>
    <div class="skill-card" data-idx="3" onclick="toggleSkill(this)">
      <div class="skill-icon"><i class="ti ti-cloud" aria-hidden="true"></i></div>
      <div class="skill-title">Cloud & DevOps</div>
      <div class="skill-tags">AWS · GCP · Docker · K8s</div>
    </div>
    <div class="skill-card" data-idx="4" onclick="toggleSkill(this)">
      <div class="skill-icon"><i class="ti ti-shield-lock" aria-hidden="true"></i></div>
      <div class="skill-title">Systems & Security</div>
      <div class="skill-tags">Rust · LLVM IR · Static Analysis</div>
    </div>
    <div class="skill-card" data-idx="5" onclick="toggleSkill(this)">
      <div class="skill-icon"><i class="ti ti-hierarchy-2" aria-hidden="true"></i></div>
      <div class="skill-title">Distributed Systems</div>
      <div class="skill-tags">HPC · Parallel ML · Inference</div>
    </div>
  </div>
  <div class="skill-detail" id="skillDetail">
    <div class="detail-label" id="detailLabel"></div>
    <div class="detail-items" id="detailItems"></div>
  </div>
</div>

<!-- PROJECTS -->
<div class="section" style="margin-top: 2.5rem;">
  <div class="section-label">Featured projects</div>
  <div class="projects-list">
    <div class="project-row">
      <div>
        <div class="project-num">01</div>
        <div class="project-title">AI-Powered Multimodal Feedback System</div>
        <div class="project-desc">Analyzes audio, video, and text signals for automated feedback with scalable inference pipelines deployed on Google Cloud.</div>
      </div>
      <div class="project-stack">
        <span class="tag">PyTorch</span><span class="tag">GCP</span><span class="tag">Multimodal</span>
      </div>
    </div>
    <div class="project-row">
      <div>
        <div class="project-num">02</div>
        <div class="project-title">Graph-Based Vulnerability Detection</div>
        <div class="project-desc">Neo4j + ML pipeline using code property graphs for vulnerability classification. Hybrid static analysis + ML approach.</div>
      </div>
      <div class="project-stack">
        <span class="tag">Neo4j</span><span class="tag">LLVM</span><span class="tag">Rust</span>
      </div>
    </div>
    <div class="project-row">
      <div>
        <div class="project-num">03</div>
        <div class="project-title">Full-Stack Intelligent Task Manager</div>
        <div class="project-desc">React + Node.js productivity platform with ML-based task prioritization, clean REST APIs, and structured persistence.</div>
      </div>
      <div class="project-stack">
        <span class="tag">React</span><span class="tag">Node.js</span><span class="tag">ML Ranking</span>
      </div>
    </div>
    <div class="project-row">
      <div>
        <div class="project-num">04</div>
        <div class="project-title">Medical Image–Report Retrieval</div>
        <div class="project-desc">Contrastive learning (CLIP-style) for cross-modal medical retrieval. Robustness evaluation under distribution shift and occlusion.</div>
      </div>
      <div class="project-stack">
        <span class="tag">CLIP</span><span class="tag">PyTorch</span><span class="tag">Research</span>
      </div>
    </div>
    <div class="project-row">
      <div>
        <div class="project-num">05</div>
        <div class="project-title">HPC Parallel ML Training</div>
        <div class="project-desc">Parallel training workflows with profiled performance bottlenecks, optimized throughput across multi-core environments.</div>
      </div>
      <div class="project-stack">
        <span class="tag">HPC</span><span class="tag">MPI</span><span class="tag">Profiling</span>
      </div>
    </div>
  </div>
</div>

<!-- PUBLICATIONS -->
<div class="section" style="margin-top: 2.5rem;">
  <div class="section-label">Publications</div>
  <div class="pub-list">
    <div class="pub-item">
      <div class="pub-title">Improving Medical Imaging Model Calibration through Probabilistic Embedding</div>
      <div class="pub-venue">Peer-reviewed · Medical AI · Trustworthiness</div>
    </div>
    <div class="pub-item">
      <div class="pub-title">Benchmarking the Robustness of Contrastive Learning Models for Medical Image-Report Retrieval</div>
      <div class="pub-venue">Peer-reviewed · Contrastive Learning · Distribution Shift</div>
    </div>
    <div class="pub-item">
      <div class="pub-title">Probabilistic Embedding for Enhancing Medical Imaging Model Trustworthiness</div>
      <div class="pub-venue">Peer-reviewed · Probabilistic ML · Medical Imaging</div>
    </div>
  </div>
</div>

<!-- CONNECT -->
<div class="section" style="margin-top: 2.5rem;">
  <div class="section-label">Let's connect</div>
  <div class="connect-row">
    <a class="connect-btn" href="mailto:myukthapriya@gmail.com">
      <i class="ti ti-mail" aria-hidden="true"></i> myukthapriya@gmail.com
    </a>
    <a class="connect-btn" href="https://linkedin.com/in/yukthapriya" target="_blank">
      <i class="ti ti-brand-linkedin" aria-hidden="true"></i> LinkedIn
    </a>
    <a class="connect-btn" href="https://github.com/yukthapriya" target="_blank">
      <i class="ti ti-brand-github" aria-hidden="true"></i> GitHub
    </a>
    <a class="connect-btn" href="https://scholar.google.com/citations?hl=en&user=UkX-bOYAAAAJ" target="_blank">
      <i class="ti ti-school" aria-hidden="true"></i> Google Scholar
    </a>
    <a class="connect-btn" href="https://www.researchgate.net/profile/Yuktha-Priya-Masupalli" target="_blank">
      <i class="ti ti-microscope" aria-hidden="true"></i> ResearchGate
    </a>
  </div>
</div>

<script>
const skillDetails = [
  {
    label: "Frontend engineering",
    items: ["Angular 16+", "RxJS operators", "Reactive Forms", "Component architecture", "Accessibility (a11y)", "Performance profiling", "Multi-step onboarding", "Document upload & validation"]
  },
  {
    label: "Backend & data engineering",
    items: ["Node.js REST APIs", "Flask microservices", "PostgreSQL", "MongoDB", "ETL pipelines", "Auth flows", "Caching basics", "Error handling patterns"]
  },
  {
    label: "AI / machine learning",
    items: ["PyTorch", "TensorFlow", "Scikit-Learn", "Contrastive learning", "Multimodal systems", "Model calibration", "Training pipelines", "Evaluation under distribution shift"]
  },
  {
    label: "Cloud & DevOps",
    items: ["AWS basics", "Google Cloud Platform", "Docker", "Kubernetes fundamentals", "CI/CD pipelines", "Observability (logs/metrics/tracing)"]
  },
  {
    label: "Systems & security",
    items: ["Rust fundamentals", "Static analysis", "LLVM IR", "Code property graphs", "Vulnerability detection", "Performance profiling"]
  },
  {
    label: "Distributed & parallel systems",
    items: ["Parallel ML training", "HPC workflows", "Multi-core optimization", "Data loading pipelines", "Scalable inference", "Throughput profiling"]
  }
];

let activeIdx = null;

function toggleSkill(el) {
  const idx = parseInt(el.dataset.idx);
  const panel = document.getElementById('skillDetail');
  const cards = document.querySelectorAll('.skill-card');

  if (activeIdx === idx) {
    panel.classList.remove('visible');
    el.classList.remove('active');
    activeIdx = null;
    return;
  }

  cards.forEach(c => c.classList.remove('active'));
  el.classList.add('active');
  activeIdx = idx;

  const d = skillDetails[idx];
  document.getElementById('detailLabel').textContent = d.label;
  document.getElementById('detailItems').innerHTML = d.items.map(i => `<span class="detail-item">${i}</span>`).join('');
  panel.classList.add('visible');
}
</script>

</body>
</html>
