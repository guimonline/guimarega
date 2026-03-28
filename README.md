<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Guilherme Gomes — Creative Production Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Bebas+Neue&family=DM+Mono:wght@300;400&display=swap" rel="stylesheet">
<style>
  :root {
    --black: #080808;
    --off-black: #0f0f0f;
    --dark: #141414;
    --gold: #c9a84c;
    --gold-light: #e8c97a;
    --white: #f0ede6;
    --muted: #7a7570;
  }

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }

body {
background: var(–black);
color: var(–white);
font-family: ‘Cormorant Garamond’, serif;
overflow-x: hidden;
cursor: crosshair;
}

body::before {
content: ‘’;
position: fixed;
inset: 0;
background-image: url(“data:image/svg+xml,%3Csvg viewBox=‘0 0 256 256’ xmlns=‘http://www.w3.org/2000/svg’%3E%3Cfilter id=‘noise’%3E%3CfeTurbulence type=‘fractalNoise’ baseFrequency=‘0.9’ numOctaves=‘4’ stitchTiles=‘stitch’/%3E%3C/filter%3E%3Crect width=‘100%25’ height=‘100%25’ filter=‘url(%23noise)’ opacity=‘0.04’/%3E%3C/svg%3E”);
pointer-events: none;
z-index: 1000;
opacity: 0.4;
}

/* HERO */
.hero {
min-height: 100vh;
display: flex;
flex-direction: column;
justify-content: center;
align-items: flex-start;
padding: 80px 8vw;
position: relative;
overflow: hidden;
}

.hero-bg {
position: absolute;
inset: 0;
background:
radial-gradient(ellipse 60% 50% at 80% 50%, rgba(201,168,76,0.06) 0%, transparent 70%),
radial-gradient(ellipse 30% 40% at 20% 80%, rgba(192,57,43,0.04) 0%, transparent 60%),
linear-gradient(180deg, #080808 0%, #0d0b09 100%);
z-index: 0;
}

.hero-lines {
position: absolute;
right: 6vw; top: 0; bottom: 0;
width: 2px;
background: linear-gradient(180deg, transparent 0%, var(–gold) 20%, transparent 40%, var(–gold) 60%, transparent 80%, var(–gold) 100%);
opacity: 0.15;
}
.hero-lines::after {
content: ‘’;
position: absolute;
right: 20px; top: 0; bottom: 0;
width: 1px;
background: inherit;
opacity: 0.5;
}

.hero-content { position: relative; z-index: 1; }

.hero-eyebrow {
font-family: ‘DM Mono’, monospace;
font-size: 11px;
letter-spacing: 0.3em;
color: var(–gold);
text-transform: uppercase;
margin-bottom: 32px;
opacity: 0;
animation: fadeUp 1s ease 0.3s forwards;
}

.hero-name {
font-family: ‘Bebas Neue’, sans-serif;
font-size: clamp(64px, 10vw, 130px);
line-height: 0.9;
letter-spacing: 0.02em;
color: var(–white);
opacity: 0;
animation: fadeUp 1s ease 0.5s forwards;
}
.hero-name span { display: block; color: var(–gold); }

.hero-title {
font-family: ‘Cormorant Garamond’, serif;
font-style: italic;
font-size: clamp(18px, 2.5vw, 28px);
font-weight: 300;
color: var(–muted);
margin-top: 24px;
letter-spacing: 0.05em;
opacity: 0;
animation: fadeUp 1s ease 0.7s forwards;
}

.hero-divider {
width: 0; height: 1px;
background: var(–gold);
margin: 40px 0;
opacity: 0;
animation: expandLine 1s ease 0.9s forwards;
}
@keyframes expandLine { from{width:0;opacity:0} to{width:80px;opacity:1} }

.hero-bio {
max-width: 540px;
font-size: 17px;
font-weight: 300;
line-height: 1.8;
color: rgba(240,237,230,0.7);
opacity: 0;
animation: fadeUp 1s ease 1.1s forwards;
}

.hero-contact {
margin-top: 48px;
display: flex;
gap: 32px;
flex-wrap: wrap;
opacity: 0;
animation: fadeUp 1s ease 1.3s forwards;
}
.hero-contact a {
font-family: ‘DM Mono’, monospace;
font-size: 11px;
letter-spacing: 0.2em;
color: var(–gold);
text-decoration: none;
text-transform: uppercase;
border-bottom: 1px solid rgba(201,168,76,0.3);
padding-bottom: 3px;
transition: border-color 0.3s, color 0.3s;
}
.hero-contact a:hover { border-color: var(–gold); color: var(–gold-light); }

.scroll-hint {
position: absolute;
bottom: 40px; left: 8vw;
font-family: ‘DM Mono’, monospace;
font-size: 10px;
letter-spacing: 0.3em;
color: var(–muted);
text-transform: uppercase;
display: flex;
align-items: center;
gap: 12px;
opacity: 0;
animation: fadeUp 1s ease 1.6s forwards;
}
.scroll-hint::before {
content: ‘’;
width: 40px; height: 1px;
background: var(–muted);
animation: scrollPulse 2s ease-in-out infinite;
}
@keyframes scrollPulse { 0%,100%{opacity:0.3} 50%{opacity:1} }
@keyframes fadeUp { from{opacity:0;transform:translateY(24px)} to{opacity:1;transform:translateY(0)} }

section { padding: 100px 8vw; position: relative; }

.section-label {
font-family: ‘DM Mono’, monospace;
font-size: 10px;
letter-spacing: 0.4em;
color: var(–gold);
text-transform: uppercase;
margin-bottom: 60px;
display: flex;
align-items: center;
gap: 20px;
}
.section-label::after {
content: ‘’;
flex: 1; max-width: 80px; height: 1px;
background: var(–gold);
opacity: 0.4;
}

/* STATS */
.stats {
background: var(–gold);
padding: 48px 8vw;
display: grid;
grid-template-columns: repeat(4, 1fr);
gap: 40px;
}
@media (max-width: 768px) { .stats { grid-template-columns: repeat(2,1fr); } }
.stat-item { text-align: center; }
.stat-number {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 56px;
line-height: 1;
color: var(–black);
display: block;
}
.stat-label {
font-family: ‘DM Mono’, monospace;
font-size: 10px;
letter-spacing: 0.2em;
color: rgba(8,8,8,0.6);
text-transform: uppercase;
margin-top: 8px;
display: block;
}

/* PROJECTS */
.projects { background: var(–off-black); }
.projects-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
gap: 2px;
}

.project-card {
background: var(–dark);
position: relative;
overflow: hidden;
cursor: pointer;
}
.project-card::before {
content: ‘’;
position: absolute; inset: 0;
background: linear-gradient(135deg, rgba(201,168,76,0.08) 0%, transparent 60%);
opacity: 0;
transition: opacity 0.4s;
z-index: 1;
}
.project-card:hover::before { opacity: 1; }

.project-inner { padding: 48px 40px; position: relative; z-index: 2; }

.project-number {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 72px;
line-height: 1;
color: rgba(201,168,76,0.08);
position: absolute;
top: 20px; right: 30px;
transition: color 0.4s;
pointer-events: none;
}
.project-card:hover .project-number { color: rgba(201,168,76,0.15); }

.project-tag {
font-family: ‘DM Mono’, monospace;
font-size: 10px;
letter-spacing: 0.3em;
color: var(–gold);
text-transform: uppercase;
margin-bottom: 16px;
}

.project-title {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 36px;
letter-spacing: 0.05em;
color: var(–white);
line-height: 1.1;
margin-bottom: 8px;
transition: color 0.3s;
}
.project-card:hover .project-title { color: var(–gold-light); }

.project-studio {
font-style: italic;
font-size: 14px;
color: var(–muted);
margin-bottom: 24px;
}

.project-role-label {
font-family: ‘DM Mono’, monospace;
font-size: 9px;
letter-spacing: 0.3em;
color: var(–muted);
text-transform: uppercase;
margin-bottom: 10px;
}

.project-role {
font-size: 15px;
font-weight: 300;
line-height: 1.7;
color: rgba(240,237,230,0.65);
}

.project-divider {
width: 30px; height: 1px;
background: var(–gold);
margin: 28px 0;
opacity: 0.5;
transition: width 0.4s, opacity 0.4s;
}
.project-card:hover .project-divider { width: 60px; opacity: 1; }

.project-link {
display: inline-flex;
align-items: center;
gap: 10px;
font-family: ‘DM Mono’, monospace;
font-size: 10px;
letter-spacing: 0.2em;
color: var(–gold);
text-decoration: none;
text-transform: uppercase;
margin-top: 8px;
transition: gap 0.3s;
}
.project-link:hover { gap: 16px; }
.project-link::after { content: ‘→’; }

.project-card.featured {
grid-column: 1 / -1;
background: linear-gradient(135deg, #141209 0%, #0f0f0f 100%);
border-left: 3px solid var(–gold);
}
.project-card.featured .project-inner {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 60px;
align-items: start;
padding: 64px 56px;
}
.project-card.featured .project-title { font-size: 56px; }
.project-card.featured .project-number { font-size: 140px; top: 0; right: 40px; }
@media (max-width: 768px) {
.project-card.featured .project-inner { grid-template-columns: 1fr; gap: 32px; }
}

/* EXPERTISE — WBD-aligned */
.expertise { background: var(–black); }
.expertise-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
gap: 1px;
background: rgba(201,168,76,0.1);
border: 1px solid rgba(201,168,76,0.1);
}
.expertise-item {
background: var(–black);
padding: 40px 36px;
transition: background 0.3s;
}
.expertise-item:hover { background: var(–dark); }
.expertise-icon { font-size: 26px; margin-bottom: 18px; display: block; }
.expertise-name {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 22px;
letter-spacing: 0.05em;
color: var(–gold);
margin-bottom: 10px;
}
.expertise-desc {
font-size: 14px;
font-weight: 300;
line-height: 1.7;
color: var(–muted);
}

/* TIMELINE */
.experience { background: var(–off-black); }
.timeline {
border-left: 1px solid rgba(201,168,76,0.2);
padding-left: 40px;
margin-left: 20px;
}
.timeline-item { position: relative; margin-bottom: 56px; }
.timeline-item:last-child { margin-bottom: 0; }
.timeline-item::before {
content: ‘’;
position: absolute;
left: -47px; top: 8px;
width: 10px; height: 10px;
border-radius: 50%;
background: var(–gold);
opacity: 0.5;
transition: opacity 0.3s, transform 0.3s;
}
.timeline-item:hover::before { opacity: 1; transform: scale(1.3); }
.timeline-period {
font-family: ‘DM Mono’, monospace;
font-size: 10px;
letter-spacing: 0.3em;
color: var(–gold);
text-transform: uppercase;
margin-bottom: 10px;
}
.timeline-role {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 28px;
letter-spacing: 0.04em;
color: var(–white);
margin-bottom: 4px;
}
.timeline-company {
font-style: italic;
font-size: 15px;
color: var(–muted);
margin-bottom: 16px;
}
.timeline-desc {
font-size: 15px;
font-weight: 300;
line-height: 1.8;
color: rgba(240,237,230,0.6);
max-width: 600px;
}

/* FOOTER */
footer {
background: var(–off-black);
padding: 64px 8vw;
display: flex;
justify-content: space-between;
align-items: center;
flex-wrap: wrap;
gap: 32px;
border-top: 1px solid rgba(201,168,76,0.15);
}
.footer-name {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 28px;
letter-spacing: 0.1em;
color: var(–white);
}
.footer-links { display: flex; gap: 28px; flex-wrap: wrap; }
.footer-links a {
font-family: ‘DM Mono’, monospace;
font-size: 10px;
letter-spacing: 0.25em;
color: var(–muted);
text-decoration: none;
text-transform: uppercase;
transition: color 0.3s;
}
.footer-links a:hover { color: var(–gold); }
.footer-copy {
font-family: ‘DM Mono’, monospace;
font-size: 10px;
color: rgba(122,117,112,0.5);
letter-spacing: 0.15em;
width: 100%;
text-align: right;
margin-top: 16px;
}

.reveal { opacity:0; transform:translateY(32px); transition:opacity 0.8s ease,transform 0.8s ease; }
.reveal.visible { opacity:1; transform:translateY(0); }
.reveal-delay-1 { transition-delay: 0.1s; }
.reveal-delay-2 { transition-delay: 0.2s; }
.reveal-delay-3 { transition-delay: 0.3s; }

.cursor-dot {
width:6px; height:6px;
background:var(–gold);
border-radius:50%;
position:fixed;
pointer-events:none;
z-index:9999;
transform:translate(-50%,-50%);
}
</style>

</head>
<body>

<div class="cursor-dot" id="cursor"></div>

<!-- HERO -->

<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-lines"></div>
  <div class="hero-content">
    <p class="hero-eyebrow">Entertainment Marketing &amp; Creative Production</p>
    <h1 class="hero-name">Guilherme<br><span>Gomes</span></h1>
    <p class="hero-title">Creative Production Manager &nbsp;·&nbsp; Film &amp; Streaming</p>
    <div class="hero-divider"></div>
    <p class="hero-bio">
      Creative production leader with 7+ years managing end-to-end campaigns for
      major entertainment properties. From concept through final delivery — I ensure
      compelling storytelling, consistently high creative standards, and on-time
      execution across platforms. Credits include Fast X (Universal Pictures) and
      Red One (Amazon Prime Video).
    </p>
    <div class="hero-contact">
      <a href="mailto:guimonline@gmail.com">guimonline@gmail.com</a>
      <a href="https://linkedin.com/in/gmarega" target="_blank">linkedin.com/in/gmarega</a>
      <a href="tel:+5514998048900">+55 14 99804-8900</a>
    </div>
  </div>
  <p class="scroll-hint">Scroll to explore</p>
</section>

<!-- STATS -->

<div class="stats">
  <div class="stat-item reveal">
    <span class="stat-number">7+</span>
    <span class="stat-label">Years in Production</span>
  </div>
  <div class="stat-item reveal reveal-delay-1">
    <span class="stat-number">32</span>
    <span class="stat-label">Creative Professionals Led</span>
  </div>
  <div class="stat-item reveal reveal-delay-2">
    <span class="stat-number">3</span>
    <span class="stat-label">Award-Winning Studios</span>
  </div>
  <div class="stat-item reveal reveal-delay-3">
    <span class="stat-number">2</span>
    <span class="stat-label">Hollywood Productions</span>
  </div>
</div>

<!-- PROJECTS -->

<section class="projects">
  <p class="section-label">Selected Work</p>
  <div class="projects-grid">

```
<!-- Fast X — FEATURED -->
<div class="project-card featured reveal">
  <div class="project-inner">
    <div>
      <p class="project-tag">Feature Film &nbsp;·&nbsp; Universal Pictures &nbsp;·&nbsp; 2022–2023</p>
      <h2 class="project-title">Fast X</h2>
      <p class="project-studio">Ghost VFX — Berlin, Germany (Remote)</p>
      <div class="project-divider"></div>
      <p class="project-role-label">Creative Production Role</p>
      <p class="project-role">
        Led the end-to-end production workflow for a team of 32 creative professionals
        across 2 locations. Ensured creative briefs were translated clearly from
        supervisors to teams, maintained visual consistency and delivery quality
        throughout, and served as the primary liaison with the studio client
        from kickoff through final delivery.
      </p>
      <a class="project-link" href="https://linkedin.com/in/gmarega" target="_blank">View on LinkedIn</a>
    </div>
    <div>
      <p class="project-role-label">Key Contributions</p>
      <br>
      <p class="project-role">✦ &nbsp;End-to-end production leadership</p>
      <p class="project-role">✦ &nbsp;32 creatives across 2 locations</p>
      <p class="project-role">✦ &nbsp;Creative brief translation & alignment</p>
      <p class="project-role">✦ &nbsp;Studio client liaison throughout campaign</p>
      <p class="project-role">✦ &nbsp;On-time delivery within studio specifications</p>
    </div>
    <span class="project-number">01</span>
  </div>
</div>

<!-- Red One -->
<div class="project-card reveal reveal-delay-1">
  <div class="project-inner">
    <span class="project-number">02</span>
    <p class="project-tag">Feature Film &nbsp;·&nbsp; Amazon Prime Video &nbsp;·&nbsp; 2023–2024</p>
    <h2 class="project-title">Red One</h2>
    <p class="project-studio">Rise FX — Berlin, Germany (Hybrid)</p>
    <div class="project-divider"></div>
    <p class="project-role-label">Creative Production Role</p>
    <p class="project-role">
      Oversaw the creative production pipeline for a team of 20 professionals
      across 2 locations. Coordinated asset delivery between departments,
      ensured quality standards were met at every stage, and maintained
      clear communication with the studio client throughout the campaign.
    </p>
    <a class="project-link" href="https://linkedin.com/in/gmarega" target="_blank">View on LinkedIn</a>
  </div>
</div>

<!-- PFX -->
<div class="project-card reveal reveal-delay-2">
  <div class="project-inner">
    <span class="project-number">03</span>
    <p class="project-tag">Entertainment Productions &nbsp;·&nbsp; 2024–Present</p>
    <h2 class="project-title">International Campaigns</h2>
    <p class="project-studio">PFX — Berlin, Germany (Remote)</p>
    <div class="project-divider"></div>
    <p class="project-role-label">Creative Production Role</p>
    <p class="project-role">
      Managing end-to-end creative production workflows at an award-winning
      entertainment studio in Central Europe. Tracking tasks and progress across
      departments, ensuring deadlines and delivery quality are met, and acting
      as the primary point of contact for international clients from start
      through final delivery.
    </p>
    <a class="project-link" href="https://linkedin.com/in/gmarega" target="_blank">View on LinkedIn</a>
  </div>
</div>
```

  </div>
</section>

<!-- EXPERTISE — WBD language -->

<section class="expertise">
  <p class="section-label">Areas of Expertise</p>
  <div class="expertise-grid">

```
<div class="expertise-item reveal">
  <span class="expertise-icon">🎬</span>
  <p class="expertise-name">End-to-End Campaign Management</p>
  <p class="expertise-desc">Leading the full creative lifecycle from brief and concept development through production, review cycles, and final delivery.</p>
</div>

<div class="expertise-item reveal reveal-delay-1">
  <span class="expertise-icon">🎯</span>
  <p class="expertise-name">Creative Brief & Alignment</p>
  <p class="expertise-desc">Translating creative vision from senior stakeholders into clear, actionable direction — ensuring teams stay aligned on tone, narrative, and quality standards.</p>
</div>

<div class="expertise-item reveal reveal-delay-2">
  <span class="expertise-icon">🤝</span>
  <p class="expertise-name">Vendor & Partner Management</p>
  <p class="expertise-desc">Collaborating with external studios, agencies, and production partners to deliver high-quality creative work on time and within budget.</p>
</div>

<div class="expertise-item reveal reveal-delay-3">
  <span class="expertise-icon">🌍</span>
  <p class="expertise-name">Cross-Location Team Leadership</p>
  <p class="expertise-desc">Managing distributed creative teams of up to 32 professionals across multiple countries and time zones in remote and hybrid environments.</p>
</div>

<div class="expertise-item reveal">
  <span class="expertise-icon">📺</span>
  <p class="expertise-name">Entertainment Marketing</p>
  <p class="expertise-desc">Passionate consumer of film and streaming content with hands-on experience on major Hollywood and global streaming productions.</p>
</div>

<div class="expertise-item reveal reveal-delay-1">
  <span class="expertise-icon">🏆</span>
  <p class="expertise-name">Brand & Delivery Standards</p>
  <p class="expertise-desc">Ensuring all creative assets meet brand positioning, technical specifications, and client expectations across traditional, digital, and social platforms.</p>
</div>
```

  </div>
</section>

<!-- TIMELINE -->

<section class="experience">
  <p class="section-label">Work History</p>
  <div class="timeline">

```
<div class="timeline-item reveal">
  <p class="timeline-period">May 2024 — Present</p>
  <p class="timeline-role">Creative Production Coordinator</p>
  <p class="timeline-company">PFX · Berlin, Germany (Remote)</p>
  <p class="timeline-desc">
    Managing end-to-end creative production workflows for international entertainment clients.
    Tracking tasks across departments, organizing assets, supporting review cycles,
    and acting as primary client contact from campaign kickoff through final delivery.
  </p>
</div>

<div class="timeline-item reveal reveal-delay-1">
  <p class="timeline-period">Apr 2023 — May 2024</p>
  <p class="timeline-role">Creative Production Lead — Red One (Amazon Prime Video)</p>
  <p class="timeline-company">Rise FX · Berlin, Germany (Hybrid)</p>
  <p class="timeline-desc">
    Oversaw creative asset production for a team of 20 professionals across 2 locations.
    Coordinated delivery between departments, maintained quality standards,
    and managed ongoing client communication throughout the campaign lifecycle.
  </p>
</div>

<div class="timeline-item reveal reveal-delay-2">
  <p class="timeline-period">Dec 2022 — Apr 2023</p>
  <p class="timeline-role">Creative Production Lead — Fast X (Universal Pictures)</p>
  <p class="timeline-company">Ghost VFX · Berlin, Germany (Remote)</p>
  <p class="timeline-desc">
    Led end-to-end production for a team of 32 creative professionals across 2 locations.
    Ensured creative briefs were translated accurately, managed inter-departmental
    dependencies, and liaised with the studio client on delivery accuracy and quality.
  </p>
</div>

<div class="timeline-item reveal reveal-delay-3">
  <p class="timeline-period">Jun 2021 — Jul 2022</p>
  <p class="timeline-role">CEO & Digital Producer</p>
  <p class="timeline-company">Nutelando Vídeos · Brazil</p>
  <p class="timeline-desc">
    Founded and ran a digital content production company. Defined creative strategy,
    managed the full production pipeline from concept through delivery, and built
    long-term relationships with clients and creative partners.
  </p>
</div>
```

  </div>
</section>

<!-- FOOTER -->

<footer>
  <p class="footer-name">Guilherme Gomes</p>
  <div class="footer-links">
    <a href="mailto:guimonline@gmail.com">Email</a>
    <a href="https://linkedin.com/in/gmarega" target="_blank">LinkedIn</a>
    <a href="tel:+5514998048900">+55 14 99804-8900</a>
  </div>
  <p class="footer-copy">São Paulo, Brazil &nbsp;·&nbsp; Open to remote & hybrid opportunities</p>
</footer>

<script>
  const cursor = document.getElementById('cursor');
  document.addEventListener('mousemove', e => {
    cursor.style.left = e.clientX + 'px';
    cursor.style.top = e.clientY + 'px';
  });
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
  }, { threshold: 0.1 });
  document.querySelectorAll('.reveal').forEach(r => observer.observe(r));
</script>

</body>
</html>
