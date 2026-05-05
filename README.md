# READvolution
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>READvolution — IPG Kampus Tuanku Bainun | Year 4 Reading Platform</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --yellow:#D4A524;--coral:#C9963E;--teal:#4A8FD4;--purple:#003087;
  --blue:#5BAEF5;--orange:#B8860B;--green:#1A5276;--pink:#1F618D;
  --dark:#0D1B3E;--white:#FFFEF9;--ink:#1A2A4A;--light:#EBF3FF;
}
html{scroll-behavior:smooth}
body{font-family:'Poppins',sans-serif;background:var(--white);color:var(--ink);margin:0}

/* ── TOP NAV ── */
.topbar{background:linear-gradient(90deg,#0D1B3E,#003087);padding:.6rem 1.5rem;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:200;box-shadow:0 4px 16px rgba(0,0,0,.4)}
.logo{font-family:'Poppins',sans-serif;font-weight:800;font-size:1.4rem;color:#D4A524;letter-spacing:1px;cursor:pointer}
.logo span{color:var(--coral)}
.nav-scroll{display:flex;gap:.3rem;overflow-x:auto;scrollbar-width:none;align-items:center}
.nav-scroll::-webkit-scrollbar{display:none}
.nav-btn{font-family:'Poppins',sans-serif;font-weight:700;font-size:.78rem;padding:.4rem .85rem;border-radius:50px;border:1.5px solid rgba(255,255,255,.2);color:#ccc;background:transparent;cursor:pointer;white-space:nowrap;transition:all .2s}
.nav-btn:hover{border-color:var(--teal);color:var(--teal)}
.nav-btn.active{background:#D4A524;border-color:#D4A524;color:#0D1B3E}

/* ── SECTIONS ── */
.section{display:none;min-height:80vh;animation:fadeIn .3s ease}
.section.active{display:block}
@keyframes fadeIn{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}

/* ── HERO ── */
.hero{background:linear-gradient(160deg,#0D1B3E 0%,#003087 60%,#1A5276 100%);padding:4rem 2rem 3rem;text-align:center;position:relative;overflow:hidden}
.hero::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse 70% 50% at 50% 40%,#845EC222,transparent),radial-gradient(ellipse 40% 40% at 15% 80%,#FF6B6B11,transparent),radial-gradient(ellipse 40% 40% at 85% 20%,#06D6A011,transparent)}
.hero-inner{position:relative;z-index:1;max-width:780px;margin:0 auto}
.hero-badge{display:inline-block;background:#D4A524;color:#0D1B3E;font-size:.78rem;font-weight:800;padding:.35rem 1rem;border-radius:50px;margin-bottom:1.2rem;letter-spacing:1px;text-transform:uppercase}
.hero h1{font-family:'Poppins',sans-serif;font-weight:800;font-size:clamp(2.6rem,7vw,5rem);color:var(--white);line-height:1.05;margin-bottom:1rem}
.hero h1 em{color:#D4A524;font-style:normal}
.hero p{font-size:1.05rem;color:#aab;max-width:560px;margin:0 auto 2rem;line-height:1.8}
.hero-btns{display:flex;gap:.8rem;justify-content:center;flex-wrap:wrap}
.btn{font-family:'Poppins',sans-serif;font-weight:800;font-size:.95rem;padding:.75rem 1.8rem;border-radius:50px;cursor:pointer;border:none;text-decoration:none;transition:transform .15s,box-shadow .15s;display:inline-block}
.btn:hover{transform:translateY(-2px);box-shadow:0 6px 20px rgba(0,0,0,.2)}
.btn-yellow{background:#D4A524;color:#0D1B3E}
.btn-outline{background:transparent;color:var(--white);border:2px solid rgba(255,255,255,.3)}
.btn-outline:hover{border-color:var(--coral);color:var(--coral)}
.btn-teal{background:#4A8FD4;color:#fff}
.btn-purple{background:#003087;color:#fff}

/* ── TEAM STRIP ── */
.team-strip{background:#EBF3FF;padding:2.5rem 2rem;text-align:center}
.team-strip h3{font-family:'Poppins',sans-serif;font-weight:800;font-size:1.1rem;color:#003087;margin-bottom:1.2rem}
.team-cards{display:flex;gap:1rem;justify-content:center;flex-wrap:wrap;max-width:900px;margin:0 auto}
.team-card{background:var(--white);border-radius:16px;padding:1.2rem 1.5rem;border:2px solid #e8e2f8;min-width:200px;flex:1;max-width:240px}
.team-avatar{width:48px;height:48px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-family:'Poppins',sans-serif;font-weight:800;font-size:1.2rem;margin:0 auto .7rem}
.team-card h4{font-size:.88rem;font-weight:800;color:var(--ink);margin-bottom:.2rem}
.team-card p{font-size:.75rem;color:#888;line-height:1.5}

/* ── SECTION WRAPPER ── */
.sec-wrap{max-width:1100px;margin:0 auto;padding:3rem 2rem}
.sec-header{text-align:center;margin-bottom:2.5rem}
.sec-tag{display:inline-block;font-size:.75rem;font-weight:800;text-transform:uppercase;letter-spacing:1.5px;padding:.3rem .9rem;border-radius:50px;margin-bottom:.7rem}
.sec-title{font-family:'Poppins',sans-serif;font-weight:800;font-size:clamp(1.8rem,4vw,2.5rem);color:var(--ink);margin-bottom:.5rem}
.sec-sub{color:#666;font-size:.95rem;max-width:580px;margin:0 auto;line-height:1.7}

/* ── CARDS ── */
.card-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:1.2rem}
.card{background:var(--white);border-radius:18px;padding:1.5rem;border:2.5px solid #f0f0f0;transition:transform .2s,border-color .2s;box-shadow:0 4px 16px rgba(0,0,0,.05)}
.card:hover{transform:translateY(-3px)}
.card-icon{font-size:2rem;margin-bottom:.8rem}
.card h3{font-family:'Poppins',sans-serif;font-weight:800;font-size:1.1rem;margin-bottom:.4rem}
.card p{font-size:.88rem;color:#555;line-height:1.65}

/* ── COLOURED PANELS ── */
.panel{border-radius:20px;padding:2rem;margin-bottom:1.5rem}
.panel-yellow{background:#FFFBEC;border:2px solid #FFD23F}
.panel-teal{background:#EDFFF9;border:2px solid #06D6A0}
.panel-purple{background:#F3EDFF;border:2px solid #845EC2}
.panel-coral{background:#FFF0EF;border:2px solid #FF6B6B}
.panel-blue{background:#EBF8FF;border:2px solid #4CC9F0}
.panel-green{background:#ECFCF7;border:2px solid #43AA8B}
.panel h3{font-family:'Poppins',sans-serif;font-weight:800;font-size:1.15rem;margin-bottom:.6rem}
.panel ul{padding-left:1.2rem;font-size:.9rem;line-height:2}
.panel p{font-size:.9rem;line-height:1.7;color:#444}

/* ── CEFR TABLE ── */
.cefr-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:1.2rem}
.cefr-card{border-radius:18px;padding:1.8rem;color:var(--white)}
.cefr-low{background:linear-gradient(135deg,#1A6E8E,#0D4F6E)}
.cefr-mid{background:linear-gradient(135deg,#003087,#1A4A8A)}
.cefr-high{background:linear-gradient(135deg,#B8860B,#8B6508)}
.cefr-card h3{font-family:'Poppins',sans-serif;font-weight:800;font-size:1.3rem;margin-bottom:.3rem}
.cefr-card .level-badge{display:inline-block;background:rgba(255,255,255,.25);font-size:.75rem;font-weight:800;padding:.25rem .7rem;border-radius:50px;margin-bottom:1rem}
.cefr-card ul{padding-left:1.2rem;font-size:.85rem;line-height:2;opacity:.95}

/* ── SEAPLM GRID ── */
.seaplm-cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:1rem}
.seaplm-card{background:linear-gradient(135deg,#0D1B3E,#1A3060);color:var(--white);border-radius:18px;padding:1.5rem;text-align:center}
.seaplm-big{font-family:'Poppins',sans-serif;font-weight:800;font-size:2.5rem;color:#D4A524;margin-bottom:.3rem}
.seaplm-card h3{font-size:.95rem;font-weight:800;margin-bottom:.4rem;color:var(--teal)}
.seaplm-card p{font-size:.82rem;color:#aab;line-height:1.6}

/* ── ACTIVITY TABS ── */
.tab-bar{display:flex;gap:.5rem;flex-wrap:wrap;margin-bottom:1.5rem}
.tab{font-family:'Poppins',sans-serif;font-weight:700;font-size:.85rem;padding:.5rem 1.2rem;border-radius:50px;border:2px solid #e0e0e0;cursor:pointer;background:var(--white);color:#666;transition:all .2s}
.tab.active{background:#003087;border-color:#003087;color:#fff}
.tab-content{display:none}
.tab-content.active{display:block}

/* ── QUIZ ── */
.quiz-box{background:var(--white);border-radius:20px;padding:2rem;border:2.5px solid #f0f0f0;box-shadow:0 4px 20px rgba(0,0,0,.06)}
.quiz-passage{background:#F8F6FF;border-radius:12px;padding:1.2rem;font-size:.9rem;line-height:1.9;color:#444;margin-bottom:1.5rem;border-left:4px solid var(--purple)}
.quiz-q{font-family:'Poppins',sans-serif;font-weight:800;font-size:1rem;color:var(--ink);margin-bottom:.8rem}
.quiz-opts{display:flex;flex-direction:column;gap:.5rem;margin-bottom:1rem}
.quiz-opt{padding:.7rem 1rem;border-radius:10px;border:2px solid #e8e8e8;font-size:.88rem;font-weight:600;cursor:pointer;background:var(--white);text-align:left;transition:all .15s}
.quiz-opt:hover{border-color:#003087;background:#EBF3FF}
.quiz-opt.correct{background:#EBF3FF;border-color:#003087;color:#003087}
.quiz-opt.wrong{background:#FFF0EF;border-color:var(--coral);color:#CC3333}
.quiz-feedback{font-size:.88rem;font-weight:700;padding:.5rem .8rem;border-radius:8px;margin-top:.5rem;display:none}
.quiz-score{font-family:'Poppins',sans-serif;font-weight:800;font-size:1.5rem;color:var(--purple);margin-top:1rem}

/* ── WORD GAME ── */
.word-game{background:var(--white);border-radius:20px;padding:2rem;border:2.5px solid #f0e8ff;box-shadow:0 4px 20px rgba(0,0,0,.06)}
.word-display{font-family:'Poppins',sans-serif;font-weight:800;font-size:2.5rem;color:var(--purple);text-align:center;letter-spacing:6px;margin:1rem 0;min-height:3.5rem}
.word-hint{text-align:center;color:#888;font-size:.88rem;margin-bottom:1rem}
.letter-grid{display:flex;flex-wrap:wrap;gap:.4rem;justify-content:center;margin-bottom:1rem}
.letter-btn{width:44px;height:44px;border-radius:10px;border:2px solid #e0e0e0;font-family:'Poppins',sans-serif;font-weight:800;font-size:1.1rem;cursor:pointer;background:var(--white);transition:all .15s}
.letter-btn:hover{background:#003087;color:#fff;border-color:#003087}
.letter-btn:disabled{opacity:.3;cursor:not-allowed}
.word-lives{text-align:center;font-size:1.4rem;margin-bottom:.8rem}
.wg-score{font-family:'Poppins',sans-serif;font-weight:800;text-align:center;font-size:1.1rem;color:var(--teal)}

/* ── DIFF SECTION ── */
.diff-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(270px,1fr));gap:1.2rem;margin-top:1rem}
.diff-card{border-radius:18px;padding:1.8rem;border:2.5px solid transparent}
.diff-low{background:#EDFFF9;border-color:var(--teal)}
.diff-mid{background:#EBF8FF;border-color:var(--blue)}
.diff-high{background:#F3EDFF;border-color:var(--purple)}
.diff-badge{display:inline-block;font-size:.72rem;font-weight:800;text-transform:uppercase;letter-spacing:1px;padding:.25rem .7rem;border-radius:50px;margin-bottom:.7rem}
.diff-low .diff-badge{background:#06D6A0;color:var(--dark)}
.diff-mid .diff-badge{background:var(--blue);color:var(--dark)}
.diff-high .diff-badge{background:var(--purple);color:#fff}
.diff-card h3{font-family:'Poppins',sans-serif;font-weight:800;font-size:1.05rem;margin-bottom:.5rem}
.diff-card ul{padding-left:1.1rem;font-size:.86rem;line-height:2;color:#444}

/* ── DSKP TABLE ── */
.dskp-table{width:100%;border-collapse:collapse;font-size:.88rem;margin-top:1rem}
.dskp-table th{background:#003087;color:#fff;padding:.7rem 1rem;text-align:left;font-weight:700}
.dskp-table td{padding:.65rem 1rem;border-bottom:1px solid #f0f0f0;line-height:1.5}
.dskp-table tr:nth-child(even) td{background:#F8F6FF}
.dskp-table tr:hover td{background:#EDE4FF}
.badge-small{display:inline-block;font-size:.7rem;font-weight:800;padding:.15rem .55rem;border-radius:50px}

/* ── CRITICAL READ ── */
.cr-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:1rem}
.cr-card{border-radius:16px;padding:1.5rem;border:2px solid #f0f0f0;position:relative;overflow:hidden}
.cr-num{position:absolute;top:-10px;right:-10px;font-family:'Poppins',sans-serif;font-weight:800;font-size:5rem;color:rgba(0,0,0,.04);line-height:1}
.cr-icon{font-size:2rem;margin-bottom:.6rem}
.cr-card h3{font-family:'Poppins',sans-serif;font-weight:800;font-size:1.05rem;margin-bottom:.4rem}
.cr-card p{font-size:.85rem;color:#555;line-height:1.65}
.cr-activity{background:#FFF8E7;border-radius:12px;padding:1rem;margin-top:.8rem;font-size:.82rem;color:#665500;border-left:3px solid var(--orange)}

/* ── IFRAME SECTION ── */
.iframe-wrap{border-radius:20px;overflow:hidden;border:3px solid #D4A524;box-shadow:0 8px 30px rgba(0,0,0,.12)}
.iframe-wrap iframe{width:100%;height:700px;border:none;display:block}

/* ── FOOTER ── */
footer{background:linear-gradient(135deg,#0D1B3E,#003087);color:rgba(255,255,255,.5);text-align:center;padding:2rem;font-size:.82rem;margin-top:2rem}
footer .ft-logo{font-family:'Poppins',sans-serif;font-weight:800;font-size:1.2rem;color:#D4A524;margin-bottom:.4rem}
footer a{color:var(--teal);text-decoration:none}

/* ── INFO STRIP ── */
.info-strip{background:linear-gradient(135deg,#003087,#1A5276);padding:1.2rem 2rem;display:flex;gap:2rem;justify-content:center;flex-wrap:wrap}
.info-item{text-align:center;color:#fff}
.info-big{font-family:'Poppins',sans-serif;font-weight:800;font-size:1.6rem}
.info-label{font-size:.72rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;opacity:.85}

/* ── SENTENCE SORT ── */
.sentence-sort{background:var(--white);border-radius:20px;padding:2rem;border:2.5px solid #f0e8ff;margin-top:1.5rem}
.sort-instruction{font-size:.88rem;color:#555;margin-bottom:1rem;line-height:1.7}
.word-tokens{display:flex;flex-wrap:wrap;gap:.5rem;margin-bottom:1.2rem;min-height:50px;padding:.5rem;background:#F8F6FF;border-radius:10px;border:2px dashed #ccc}
.token{padding:.4rem .9rem;border-radius:8px;font-size:.88rem;font-weight:700;cursor:pointer;transition:all .15s;user-select:none}
.token.available{background:var(--purple);color:#fff}
.token.available:hover{transform:scale(1.05)}
.token.placed{background:#e8e8e8;color:#999;cursor:not-allowed}
.answer-zone{display:flex;flex-wrap:wrap;gap:.5rem;min-height:50px;padding:.5rem;background:#EDFFF9;border-radius:10px;border:2px dashed var(--teal);margin-bottom:1rem}
.placed-token{padding:.4rem .9rem;border-radius:8px;font-size:.88rem;font-weight:700;background:var(--teal);color:var(--dark);cursor:pointer}

/* responsive */
@media(max-width:600px){.topbar{padding:.5rem .8rem}.nav-btn{font-size:.7rem;padding:.35rem .65rem}}
</style>
</head>
<body>

<!-- TOP NAV -->
<header class="topbar">
  <div style="display:flex;align-items:center;gap:9px;cursor:pointer" onclick="showSection('home')">
    <div class="logo">READ<span>volution</span></div>
  </div>
  <nav class="nav-scroll">
    <button class="nav-btn active" onclick="showSection('home')">🏠 Home</button>
    <button class="nav-btn" onclick="showSection('dskp')">📋 DSKP</button>
    <button class="nav-btn" onclick="showSection('cefr')">🎯 CEFR</button>
    <button class="nav-btn" onclick="showSection('seaplm')">🌏 SEA PLM</button>
    <button class="nav-btn" onclick="showSection('seamat')">📄 PLM Materials</button>
    <button class="nav-btn" onclick="showSection('critical')">🧠 Critical Reading</button>
    <button class="nav-btn" onclick="showSection('activities')">⚡ Activities</button>
    <button class="nav-btn" onclick="showSection('diff')">🌈 Differentiation</button>
    <button class="nav-btn" onclick="showSection('smartlit')">🔗 Smart Literacy</button>
  </nav>
</header>


<!-- ══════════════════════════════════════════════════
     SECTION 1: HOME
══════════════════════════════════════════════════ -->
<div id="section-home" class="section active">
  <div class="hero">
    <div class="hero-inner">
      <div class="hero-badge">📚 IPG Kampus Tuanku Bainun · Year 4 Digital Reading Platform</div>
      <h1>Welcome to <em>READvolution!</em></h1>
      <p>A digital platform to help Year 4 pupils read better, think deeper, and love learning — supporting teachers and parents across Malaysia.</p>
      <div class="hero-btns">
        <button class="btn btn-yellow" onclick="showSection('dskp')">Start Learning 📖</button>
        <button class="btn btn-outline" onclick="showSection('activities')">Try Activities ⚡</button>
      </div>
    </div>
  </div>

  <div class="info-strip">
    <div class="info-item"><div class="info-big">Year 4</div><div class="info-label">Target Pupils</div></div>
    <div class="info-item"><div class="info-big">A2</div><div class="info-label">CEFR Level</div></div>
    <div class="info-item"><div class="info-big">SEA PLM</div><div class="info-label">Assessment Ready</div></div>
    <div class="info-item"><div class="info-big">3 Worlds</div><div class="info-label">Content Themes</div></div>
    <div class="info-item"><div class="info-big">Free</div><div class="info-label">Open Access</div></div>
  </div>

  <div class="sec-wrap">
    <div class="sec-header">
      <div class="sec-tag" style="background:#FFD23F22;color:#A07800;">✨ About READvolution</div>
      <h2 class="sec-title">What Is This Platform?</h2>
      <p class="sec-sub">READvolution is a free digital platform for Year 4 English reading. It brings together the curriculum, CEFR levels, SEA PLM, and interactive activities in one easy place.</p>
    </div>
    <div class="card-grid">
      <div class="card" style="border-color:#FFD23F">
        <div class="card-icon">📋</div>
        <h3 style="color:#A07800">DSKP & Textbook</h3>
        <p>Aligned with the Year 4 Malaysian English curriculum and DSKP standards for effective teaching and learning.</p>
      </div>
      <div class="card" style="border-color:#06D6A0">
        <div class="card-icon">🎯</div>
        <h3 style="color:#047A5A">CEFR Levels</h3>
        <p>Content is organised at A2 Low, A2 Mid, and A2 High — so every pupil learns at the right pace.</p>
      </div>
      <div class="card" style="border-color:#4CC9F0">
        <div class="card-icon">🌏</div>
        <h3 style="color:#1A6A99">SEA PLM</h3>
        <p>Understand what SEA PLM is, why it matters, and practise with real-style reading materials.</p>
      </div>
      <div class="card" style="border-color:#FF6B6B">
        <div class="card-icon">🧠</div>
        <h3 style="color:#CC2222">Critical Reading</h3>
        <p>Go beyond reading the words — learn to think, question, infer, and evaluate what you read.</p>
      </div>
      <div class="card" style="border-color:#845EC2">
        <div class="card-icon">⚡</div>
        <h3 style="color:#5A3A8A">Interactive Activities</h3>
        <p>Fun games, quizzes, and sentence tasks that make practising English reading enjoyable.</p>
      </div>
      <div class="card" style="border-color:#FF9F1C">
        <div class="card-icon">🌈</div>
        <h3 style="color:#995500">Differentiation</h3>
        <p>Activities for every learner — A2 Low, Mid, and High — so no pupil is left behind.</p>
      </div>
    </div>

    <div style="margin-top:3rem">
      <div class="sec-header">
        <div class="sec-tag" style="background:#845EC222;color:#5A3A8A;">👩‍🏫 Our Team</div>
        <h2 class="sec-title">Meet the READvolution Team</h2>
        <p class="sec-sub">Institut Pendidikan Guru Kampus Tuanku Bainun, Mengkuang, Penang</p>
      </div>
      <div class="team-cards">
        <div class="team-card">
          <div class="team-avatar" style="background:#EDE4FF;color:#6A3DAA">KR</div>
          <h4>Kogila Ramakrishnan</h4>
          <p>M.Ed (TESOL) · 27+ years · Teacher coaching, PLC, CBAR, ELT research</p>
        </div>
        <div class="team-card">
          <div class="team-avatar" style="background:#DAFFF5;color:#047A5A">MK</div>
          <h4>Moganashwari Kandasamy</h4>
          <p>PhD · 20+ years · Pedagogical content knowledge, language learning strategies</p>
        </div>
        <div class="team-card">
          <div class="team-avatar" style="background:#FFEDD5;color:#995500">AC</div>
          <h4>Agelya Chitambaram</h4>
          <p>PhD · TESL · User-centred innovation, transformative education solutions</p>
        </div>
        <div class="team-card">
          <div class="team-avatar" style="background:#FFF0EF;color:#CC3333">NZ</div>
          <h4>Nizaha</h4>
          <p>TESL/TESOL · Reading & writing literacy, innovative teaching practices</p>
        </div>
      </div>
    </div>


    <div style="margin-top:3rem">
      <div style="background:linear-gradient(135deg,#0D1B3E,#003087);border-radius:24px;padding:2.5rem;color:#fff;text-align:center">
        <div style="font-family:'Poppins',sans-serif;font-weight:800;font-size:.75rem;text-transform:uppercase;letter-spacing:2px;color:#D4A524;margin-bottom:.8rem">Co-Authors &amp; Innovation Team</div>
        <div style="font-family:'Poppins',sans-serif;font-weight:800;font-size:1.5rem;color:#fff;margin-bottom:.3rem">READvolution</div>
        <div style="font-size:.88rem;color:rgba(255,255,255,.7);margin-bottom:1.2rem">A Digital Reading Innovation for Year 4 English Language Learners</div>
        <div style="display:flex;justify-content:center;gap:1.5rem;flex-wrap:wrap;margin-bottom:1.2rem">
          <div style="font-size:.82rem;color:rgba(255,255,255,.85)"><strong style="color:#D4A524">Kogila Ramakrishnan</strong><br>M.Ed (TESOL) · Principal Innovator</div>
          <div style="font-size:.82rem;color:rgba(255,255,255,.85)"><strong style="color:#D4A524">Moganashwari Kandasamy</strong><br>PhD · Co-Innovator</div>
          <div style="font-size:.82rem;color:rgba(255,255,255,.85)"><strong style="color:#D4A524">Agelya Chitambaram</strong><br>PhD · Co-Innovator</div>
          <div style="font-size:.82rem;color:rgba(255,255,255,.85)"><strong style="color:#D4A524">Nizaha</strong><br>TESL/TESOL · Co-Innovator</div>
        </div>
        <div style="border-top:1px solid rgba(255,255,255,.15);padding-top:1rem;font-size:.78rem;color:rgba(255,255,255,.55)">
          Institut Pendidikan Guru Kampus Tuanku Bainun &nbsp;·&nbsp; Mengkuang, Penang, Malaysia
        </div>
      </div>
    </div>

    <div style="margin-top:3rem">
      <div class="panel" style="background:#EBF3FF;border:2px solid #4A8FD4">
        <h3 style="color:#003087">📱 Share READvolution!</h3>
        <p>This platform is <strong>free and open</strong> for all teachers, pupils, and parents. Share it on <strong>TikTok, Instagram</strong>, and <strong>Facebook</strong> to help more Year 4 pupils across Malaysia improve their reading!</p>
        <p style="margin-top:.5rem;font-size:.82rem;color:#1A5276">📧 Contact: <a href="mailto:kogirn@gmail.com" style="color:#003087">kogirn@gmail.com</a></p>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════════════
     SECTION 2: YEAR 4 DSKP
══════════════════════════════════════════════════ -->
<div id="section-dskp" class="section">
  <div class="sec-wrap">
    <div class="sec-header">
      <div class="sec-tag" style="background:#FFD23F33;color:#A07800;">📋 Curriculum Alignment</div>
      <h2 class="sec-title">Year 4 DSKP & Textbook</h2>
      <p class="sec-sub">The DSKP (Dokumen Standard Kurikulum dan Pentaksiran) sets out what Year 4 pupils should learn. This platform supports all DSKP reading standards.</p>
    </div>

    <div class="panel panel-yellow">
      <h3 style="color:#A07800">📚 Year 4 Textbook Themes</h3>
      <p>The Year 4 English textbook follows three main worlds. Each world has reading materials at different levels.</p>
    </div>

    <div class="card-grid" style="margin-top:1.2rem">
      <div class="card" style="border-color:#FF9F1C">
        <div class="card-icon">👨‍👩‍👧‍👦</div>
        <h3 style="color:#995500">World 1: Self, Family & Friends</h3>
        <p>Topics about daily life, family, friends, and feelings. Pupils read about things they know well.</p>
        <div style="margin-top:.8rem;font-size:.8rem;color:#888">Level 1 · Level 2 · Level 3</div>
      </div>
      <div class="card" style="border-color:#FF6B6B">
        <div class="card-icon">📖</div>
        <h3 style="color:#CC2222">World 2: Stories</h3>
        <p>Fun stories, fables, and adventures from Malaysia and around the world. Pupils enjoy reading and respond to texts.</p>
        <div style="margin-top:.8rem;font-size:.8rem;color:#888">Level 1 · Level 2 · Level 3</div>
      </div>
      <div class="card" style="border-color:#4CC9F0">
        <div class="card-icon">🔬</div>
        <h3 style="color:#1A6A99">World 3: Knowledge</h3>
        <p>Information texts about nature, science, the environment, and the world around us.</p>
        <div style="margin-top:.8rem;font-size:.8rem;color:#888">Level 1 · Level 2 · Level 3</div>
      </div>
    </div>

    <div style="margin-top:2.5rem">
      <div class="sec-header" style="margin-bottom:1rem">
        <h2 class="sec-title" style="font-size:1.8rem">DSKP Reading Standards — Year 4</h2>
        <p class="sec-sub">Key Content Standards and Learning Standards for reading in Year 4 English.</p>
      </div>

      <div style="overflow-x:auto">
        <table class="dskp-table">
          <thead>
            <tr>
              <th>Content Standard</th>
              <th>Learning Standard</th>
              <th>Description</th>
              <th>Level</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><strong>3.1</strong> Word Recognition &amp; Decoding</td>
              <td>3.1.1</td>
              <td>Recognise and decode familiar words using phonics knowledge</td>
              <td><span class="badge-small" style="background:#DAFFF5;color:#047A5A">A2 Low</span></td>
            </tr>
            <tr>
              <td><strong>3.2</strong> Read Aloud</td>
              <td>3.2.1</td>
              <td>Read aloud with correct pronunciation, stress, and intonation</td>
              <td><span class="badge-small" style="background:#DAFFF5;color:#047A5A">A2 Low</span></td>
            </tr>
            <tr>
              <td><strong>3.3</strong> Reading Comprehension</td>
              <td>3.3.1</td>
              <td>Understand the main idea of a paragraph or short text</td>
              <td><span class="badge-small" style="background:#DCF4FF;color:#0088CC">A2 Mid</span></td>
            </tr>
            <tr>
              <td><strong>3.3</strong> Reading Comprehension</td>
              <td>3.3.2</td>
              <td>Identify specific details and supporting information in a text</td>
              <td><span class="badge-small" style="background:#DCF4FF;color:#0088CC">A2 Mid</span></td>
            </tr>
            <tr>
              <td><strong>3.3</strong> Reading Comprehension</td>
              <td>3.3.3</td>
              <td>Make simple inferences about what a character thinks or feels</td>
              <td><span class="badge-small" style="background:#EDE4FF;color:#6A3DAA">A2 High</span></td>
            </tr>
            <tr>
              <td><strong>3.4</strong> Reading for Information</td>
              <td>3.4.1</td>
              <td>Locate and use information from factual texts and digital sources</td>
              <td><span class="badge-small" style="background:#DCF4FF;color:#0088CC">A2 Mid</span></td>
            </tr>
            <tr>
              <td><strong>3.5</strong> Extensive Reading</td>
              <td>3.5.1</td>
              <td>Read and respond to age-appropriate fiction and non-fiction</td>
              <td><span class="badge-small" style="background:#EDE4FF;color:#6A3DAA">A2 High</span></td>
            </tr>
            <tr>
              <td><strong>3.6</strong> Language for Reading</td>
              <td>3.6.1</td>
              <td>Identify and understand high-frequency and topic vocabulary</td>
              <td><span class="badge-small" style="background:#DAFFF5;color:#047A5A">A2 Low</span></td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

    <div style="margin-top:2rem">
      <div class="panel panel-purple" style="background:#F3EDFF">
        <h3 style="color:#5A3A8A">🔗 Scaffolding Approach — Levels 1, 2 & 3</h3>
        <p>READvolution uses a scaffolding approach so that pupils move from simple to more complex reading. Level 1 supports beginners, Level 2 develops independence, and Level 3 challenges more capable readers — all within the same theme.</p>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════════════
     SECTION 3: CEFR
══════════════════════════════════════════════════ -->
<div id="section-cefr" class="section">
  <div class="sec-wrap">
    <div class="sec-header">
      <div class="sec-tag" style="background:#06D6A022;color:#047A5A;">🎯 Language Proficiency</div>
      <h2 class="sec-title">CEFR Levels for Year 4</h2>
      <p class="sec-sub">The Common European Framework of Reference (CEFR) describes language levels. Year 4 pupils in Malaysia are expected to achieve <strong>A2</strong> — with three bands: Low, Mid, and High.</p>
    </div>

    <div class="panel panel-teal" style="margin-bottom:2rem">
      <h3 style="color:#047A5A">❓ What is CEFR?</h3>
      <p>CEFR stands for <strong>Common European Framework of Reference for Languages</strong>. It is used worldwide to describe what a learner can do with a language. In Malaysia, CEFR guides how English is taught from Year 1 to Form 5. For Year 4, the target level is <strong>A2</strong>.</p>
    </div>

    <div class="cefr-grid">
      <div class="cefr-card cefr-low">
        <div class="level-badge">A2 LOW</div>
        <h3>📗 Beginning A2</h3>
        <p style="font-size:.85rem;opacity:.9;margin-bottom:.8rem">Pupils can understand and use very basic English. They need lots of support.</p>
        <ul>
          <li>Recognise familiar words</li>
          <li>Read very short, simple sentences</li>
          <li>Understand texts with pictures</li>
          <li>Answer Yes/No questions</li>
          <li>Match words to pictures</li>
          <li>Fill in simple missing words</li>
        </ul>
      </div>
      <div class="cefr-card cefr-mid">
        <div class="level-badge">A2 MID</div>
        <h3>📘 Developing A2</h3>
        <p style="font-size:.85rem;opacity:.9;margin-bottom:.8rem">Pupils can read simple texts on familiar topics with some support.</p>
        <ul>
          <li>Understand main ideas in a text</li>
          <li>Answer Wh- questions (Who, What, Where, When)</li>
          <li>Identify details from a passage</li>
          <li>Sequence events in a story</li>
          <li>Read simple information texts</li>
          <li>Use context to guess meaning</li>
        </ul>
      </div>
      <div class="cefr-card cefr-high">
        <div class="level-badge">A2 HIGH</div>
        <h3>📙 Extending A2</h3>
        <p style="font-size:.85rem;opacity:.9;margin-bottom:.8rem">Pupils can read with greater independence and begin to show early B1 features.</p>
        <ul>
          <li>Make simple inferences</li>
          <li>Identify the purpose of a text</li>
          <li>Compare ideas across sentences</li>
          <li>Predict what happens next</li>
          <li>Read without needing pictures</li>
          <li>Explain ideas using text evidence</li>
        </ul>
      </div>
    </div>

    <div style="margin-top:2rem">
      <div class="sec-header" style="margin-bottom:1.2rem">
        <h2 class="sec-title" style="font-size:1.8rem">CEFR Can-Do Statements — Reading</h2>
      </div>
      <div style="overflow-x:auto">
        <table class="dskp-table">
          <thead>
            <tr>
              <th>Skill</th>
              <th>A2 Low — I can...</th>
              <th>A2 Mid — I can...</th>
              <th>A2 High — I can...</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><strong>Word Reading</strong></td>
              <td>Read familiar sight words</td>
              <td>Decode new words using phonics</td>
              <td>Read multi-syllable words fluently</td>
            </tr>
            <tr>
              <td><strong>Comprehension</strong></td>
              <td>Answer Yes/No questions</td>
              <td>Answer Who/What/Where questions</td>
              <td>Answer Why/How questions</td>
            </tr>
            <tr>
              <td><strong>Inference</strong></td>
              <td>Use pictures as clues</td>
              <td>Guess meanings from context</td>
              <td>Make inferences without clues</td>
            </tr>
            <tr>
              <td><strong>Text Types</strong></td>
              <td>Read labels and captions</td>
              <td>Read simple stories and emails</td>
              <td>Read information texts and articles</td>
            </tr>
            <tr>
              <td><strong>Vocabulary</strong></td>
              <td>Understand basic nouns/verbs</td>
              <td>Understand topic vocabulary</td>
              <td>Use vocabulary strategies independently</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

    <div style="margin-top:1.5rem">
      <div class="panel panel-yellow">
        <h3 style="color:#A07800">💡 CEFR and the Malaysian Curriculum</h3>
        <p>Malaysia adopted the CEFR framework in 2017. By the end of Year 4, pupils should reach A2. The DSKP learning standards and the Pentaksiran Bilik Darjah (PBD) are both aligned with CEFR descriptors, making it important for teachers to know their pupils' current CEFR band when planning lessons.</p>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════════════
     SECTION 4: SEA PLM
══════════════════════════════════════════════════ -->
<div id="section-seaplm" class="section">
  <div class="sec-wrap">
    <div class="sec-header">
      <div class="sec-tag" style="background:#4CC9F022;color:#1A6A99;">🌏 Regional Assessment</div>
      <h2 class="sec-title">SEA PLM — All You Need to Know</h2>
      <p class="sec-sub">Southeast Asia Primary Learning Metrics (SEA PLM) is an important regional reading assessment. Understanding it helps Year 4 teachers prepare their pupils effectively.</p>
    </div>

    <div class="seaplm-cards">
      <div class="seaplm-card">
        <div class="seaplm-big">WHAT?</div>
        <h3>What is SEA PLM?</h3>
        <p>SEA PLM stands for Southeast Asia Primary Learning Metrics. It is a regional assessment that measures reading, writing, and maths skills of primary school pupils.</p>
      </div>
      <div class="seaplm-card">
        <div class="seaplm-big">WHO?</div>
        <h3>Who Takes Part?</h3>
        <p>Grade 5 pupils (around Year 5) across 6 countries: Malaysia, Cambodia, Myanmar, the Philippines, Vietnam, and Timor-Leste.</p>
      </div>
      <div class="seaplm-card">
        <div class="seaplm-big">WHEN?</div>
        <h3>When Is It Held?</h3>
        <p>SEA PLM is conducted periodically by SEAMEO. The first cycle was in 2019. Year 4 is the preparation year — building skills before the assessment year.</p>
      </div>
      <div class="seaplm-card">
        <div class="seaplm-big">HOW?</div>
        <h3>How Does It Work?</h3>
        <p>Pupils read texts and answer comprehension questions. The assessment measures literal and inferential reading, plus global reading (overall text meaning).</p>
      </div>
    </div>

    <div style="margin-top:2rem">
      <div class="panel panel-blue">
        <h3 style="color:#1A6A99">📊 What SEA PLM Assesses in Reading</h3>
        <p>SEA PLM reading tasks use <strong>three levels of thinking</strong>:</p>
        <ul>
          <li><strong>Literal comprehension</strong> — Finding facts stated directly in the text</li>
          <li><strong>Inferential comprehension</strong> — Reading between the lines to understand ideas not directly stated</li>
          <li><strong>Global comprehension</strong> — Understanding the overall meaning, purpose, or structure of a text</li>
        </ul>
      </div>
    </div>

    <div style="margin-top:1.2rem">
      <div class="card-grid">
        <div class="card" style="border-color:#4CC9F0">
          <div class="card-icon">📝</div>
          <h3 style="color:#1A6A99">Text Types Used</h3>
          <p>Continuous texts (stories, reports), non-continuous texts (charts, tables, maps), and mixed texts — similar to real-life reading.</p>
        </div>
        <div class="card" style="border-color:#06D6A0">
          <div class="card-icon">📈</div>
          <h3 style="color:#047A5A">Malaysia's Results</h3>
          <p>Malaysian pupils showed room for improvement in inferential and global reading. This highlights the need for higher-order reading skills from Year 4 onwards.</p>
        </div>
        <div class="card" style="border-color:#FF9F1C">
          <div class="card-icon">🎯</div>
          <h3 style="color:#995500">Why Year 4 Matters</h3>
          <p>Year 4 is the foundation year. Building strong literal and inferential reading now prepares pupils to perform better in Year 5 SEA PLM tasks.</p>
        </div>
        <div class="card" style="border-color:#845EC2">
          <div class="card-icon">🌏</div>
          <h3 style="color:#5A3A8A">SEAMEO</h3>
          <p>SEA PLM is organised by SEAMEO (Southeast Asian Ministers of Education Organisation) to help improve education quality across the region.</p>
        </div>
      </div>
    </div>

    <div style="margin-top:1.5rem">
      <div class="panel panel-coral">
        <h3 style="color:#CC2222">⚡ Key Takeaway for Year 4 Teachers</h3>
        <p>The most important preparation for SEA PLM is <strong>practising inferential reading</strong> — helping pupils read between the lines. This means asking "Why?" and "How do you know?" questions, not just "What happened?" Reading longer texts regularly and discussing them in class is the most effective preparation strategy.</p>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════════════
     SECTION 5: SEA PLM MATERIALS
══════════════════════════════════════════════════ -->
<div id="section-seamat" class="section">
  <div class="sec-wrap">
    <div class="sec-header">
      <div class="sec-tag" style="background:#FF6B6B22;color:#CC2222;">📄 Practice Resources</div>
      <h2 class="sec-title">SEA PLM Materials</h2>
      <p class="sec-sub">These reading passages and tasks are designed to prepare Year 4 pupils for SEA PLM-style reading. Each text is followed by literal, inferential, and global comprehension questions.</p>
    </div>

    <div class="tab-bar" id="seaMatTabs">
      <div class="tab active" onclick="switchTab('seaMatTabs','seamat-',1)">📗 Literal Reading</div>
      <div class="tab" onclick="switchTab('seaMatTabs','seamat-',2)">📘 Inferential Reading</div>
      <div class="tab" onclick="switchTab('seaMatTabs','seamat-',3)">📙 Global Reading</div>
    </div>

    <div id="seamat-1" class="tab-content active">
      <div class="panel panel-teal">
        <h3 style="color:#047A5A">📗 Literal Reading — Finding Information in the Text</h3>
        <p>Literal reading means finding facts that are clearly stated in the text. The answer is written in the text — you just need to find it.</p>
      </div>
      <div class="quiz-box" style="margin-top:1.2rem">
        <div class="quiz-passage">
          <strong>Text: A Busy Saturday</strong><br><br>
          Amir woke up early on Saturday. He ate bread and drank a glass of milk for breakfast. Then his mother drove him to the library. Amir chose three books about animals. He read quietly for two hours. In the afternoon, he helped his father water the plants in the garden. Amir felt happy at the end of the day.
        </div>
        <div id="seaLit1">
          <div class="quiz-q">1. What did Amir eat for breakfast?</div>
          <div class="quiz-opts">
            <button class="quiz-opt" onclick="checkAns(this,'seaLit1','a','a')">A. Rice and eggs</button>
            <button class="quiz-opt" onclick="checkAns(this,'seaLit1','b','a')">B. Bread and milk</button>
            <button class="quiz-opt" onclick="checkAns(this,'seaLit1','c','a')">C. Noodles and juice</button>
          </div>
          <div class="quiz-feedback" id="seaLit1-fb"></div>
        </div>
        <div id="seaLit2" style="margin-top:1rem">
          <div class="quiz-q">2. How many books did Amir choose?</div>
          <div class="quiz-opts">
            <button class="quiz-opt" onclick="checkAns(this,'seaLit2','b','b')">A. Two books</button>
            <button class="quiz-opt" onclick="checkAns(this,'seaLit2','b','b')">B. Three books</button>
            <button class="quiz-opt" onclick="checkAns(this,'seaLit2','c','b')">C. Five books</button>
          </div>
          <div class="quiz-feedback" id="seaLit2-fb"></div>
        </div>
      </div>
    </div>

    <div id="seamat-2" class="tab-content">
      <div class="panel panel-blue">
        <h3 style="color:#1A6A99">📘 Inferential Reading — Reading Between the Lines</h3>
        <p>Inferential reading means working out ideas that are NOT written in the text. You use clues from the text and what you already know to find the answer.</p>
      </div>
      <div class="quiz-box" style="margin-top:1.2rem">
        <div class="quiz-passage">
          <strong>Text: The Old Tree</strong><br><br>
          Every day after school, Siti sat under the big mango tree in her garden. She would bring her books and read until the sun went down. One day, she noticed the tree's leaves turning yellow. Some branches looked thin and dry. Siti felt sad. She went inside and asked her father what was wrong with the tree.
        </div>
        <div id="seaInf1">
          <div class="quiz-q">1. How does Siti feel about the mango tree? How do you know?</div>
          <div class="quiz-opts">
            <button class="quiz-opt" onclick="checkAns(this,'seaInf1','b','c')">A. She does not care about the tree.</button>
            <button class="quiz-opt" onclick="checkAns(this,'seaInf1','b','c')">B. She dislikes the tree because it is old.</button>
            <button class="quiz-opt" onclick="checkAns(this,'seaInf1','c','c')">C. She loves the tree and is worried about it.</button>
          </div>
          <div class="quiz-feedback" id="seaInf1-fb"></div>
        </div>
        <div id="seaInf2" style="margin-top:1rem">
          <div class="quiz-q">2. What do the yellow leaves and dry branches tell us?</div>
          <div class="quiz-opts">
            <button class="quiz-opt" onclick="checkAns(this,'seaInf2','a','c')">A. The tree is growing well.</button>
            <button class="quiz-opt" onclick="checkAns(this,'seaInf2','b','c')">B. The tree is very old and tall.</button>
            <button class="quiz-opt" onclick="checkAns(this,'seaInf2','c','c')">C. The tree may be sick or dying.</button>
          </div>
          <div class="quiz-feedback" id="seaInf2-fb"></div>
        </div>
      </div>
    </div>

    <div id="seamat-3" class="tab-content">
      <div class="panel panel-purple" style="background:#F3EDFF">
        <h3 style="color:#5A3A8A">📙 Global Reading — Understanding the Whole Text</h3>
        <p>Global reading means understanding the overall message, purpose, or structure of the whole text. You think about WHY the writer wrote this text and WHAT the main message is.</p>
      </div>
      <div class="quiz-box" style="margin-top:1.2rem">
        <div class="quiz-passage">
          <strong>Text: Save Water</strong><br><br>
          Water is very important for all living things. Without water, plants, animals, and people cannot survive. However, clean water is getting less every year. Many people waste water by leaving taps running or taking very long showers. We all need to do our part. Turn off taps when you brush your teeth. Use a bucket instead of a hose when washing the car. Small actions every day can make a big difference to our world.
        </div>
        <div id="seaGlob1">
          <div class="quiz-q">1. What is the MAIN purpose of this text?</div>
          <div class="quiz-opts">
            <button class="quiz-opt" onclick="checkAns(this,'seaGlob1','a','c')">A. To explain how water is made</button>
            <button class="quiz-opt" onclick="checkAns(this,'seaGlob1','b','c')">B. To tell a story about water</button>
            <button class="quiz-opt" onclick="checkAns(this,'seaGlob1','c','c')">C. To persuade people to save water</button>
          </div>
          <div class="quiz-feedback" id="seaGlob1-fb"></div>
        </div>
        <div id="seaGlob2" style="margin-top:1rem">
          <div class="quiz-q">2. Who is the writer most likely talking to?</div>
          <div class="quiz-opts">
            <button class="quiz-opt" onclick="checkAns(this,'seaGlob2','a','c')">A. Scientists who study water</button>
            <button class="quiz-opt" onclick="checkAns(this,'seaGlob2','b','c')">B. Everyone who uses water</button>
            <button class="quiz-opt" onclick="checkAns(this,'seaGlob2','c','c')">C. Only people in dry countries</button>
          </div>
          <div class="quiz-feedback" id="seaGlob2-fb"></div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════════════
     SECTION 6: CRITICAL READING
══════════════════════════════════════════════════ -->
<div id="section-critical" class="section">
  <div class="sec-wrap">
    <div class="sec-header">
      <div class="sec-tag" style="background:#845EC222;color:#5A3A8A;">🧠 Higher-Order Thinking</div>
      <h2 class="sec-title">Critical Reading — Think Deeper!</h2>
      <p class="sec-sub">Critical reading means thinking carefully about what you read. You do not just understand words — you question, analyse, and evaluate the text.</p>
    </div>

    <div class="panel panel-purple" style="background:#F3EDFF;margin-bottom:2rem">
      <h3 style="color:#5A3A8A">❓ What Is Critical Reading?</h3>
      <p>Critical reading is when a reader <strong>actively thinks</strong> about a text. It means asking questions like: <em>Is this true? How does the writer know this? What does the writer want me to think? What is missing from this text?</em> At Year 4, pupils begin developing these skills using short, familiar texts.</p>
    </div>

    <div class="cr-grid">
      <div class="cr-card" style="border-color:#FFD23F">
        <div class="cr-num">1</div>
        <div class="cr-icon">🔮</div>
        <h3 style="color:#A07800">Predicting</h3>
        <p>Use clues in the text to guess what will happen next. Good readers think ahead!</p>
        <div class="cr-activity">💡 <strong>Try this:</strong> Read the title and first line. What do you think this text will be about? Why do you think so?</div>
      </div>
      <div class="cr-card" style="border-color:#06D6A0">
        <div class="cr-num">2</div>
        <div class="cr-icon">🔍</div>
        <h3 style="color:#047A5A">Questioning</h3>
        <p>Ask questions while you read. Good readers ask WHO, WHAT, WHERE, WHEN, WHY, and HOW.</p>
        <div class="cr-activity">💡 <strong>Try this:</strong> After reading a paragraph, write one "Why" question that the text has not answered.</div>
      </div>
      <div class="cr-card" style="border-color:#4CC9F0">
        <div class="cr-num">3</div>
        <div class="cr-icon">🧩</div>
        <h3 style="color:#1A6A99">Inferring</h3>
        <p>Work out meaning that is NOT written in the text. Use clues + your knowledge to infer.</p>
        <div class="cr-activity">💡 <strong>Try this:</strong> "Mei cried when she heard the news." — What might have happened? How do you know?</div>
      </div>
      <div class="cr-card" style="border-color:#FF6B6B">
        <div class="cr-num">4</div>
        <div class="cr-icon">💬</div>
        <h3 style="color:#CC2222">Connecting</h3>
        <p>Link the text to your own life, other books, or what is happening in the world.</p>
        <div class="cr-activity">💡 <strong>Try this:</strong> Text-to-Self: "This reminds me of when I..." Text-to-World: "This is similar to..."</div>
      </div>
      <div class="cr-card" style="border-color:#845EC2">
        <div class="cr-num">5</div>
        <div class="cr-icon">⚖️</div>
        <h3 style="color:#5A3A8A">Evaluating</h3>
        <p>Judge the quality of what you read. Decide if the information is facts or opinions.</p>
        <div class="cr-activity">💡 <strong>Try this:</strong> Read two sentences — identify which is a FACT and which is an OPINION. Give your reasons.</div>
      </div>
      <div class="cr-card" style="border-color:#FF9F1C">
        <div class="cr-num">6</div>
        <div class="cr-icon">📝</div>
        <h3 style="color:#995500">Summarising</h3>
        <p>After reading, explain the key ideas in your own words. Use only the most important information.</p>
        <div class="cr-activity">💡 <strong>Try this:</strong> After reading, complete: "This text is about ___ . The most important idea is ___."</div>
      </div>
    </div>

    <div style="margin-top:2rem">
      <div class="sec-header" style="margin-bottom:1.2rem">
        <h2 class="sec-title" style="font-size:1.7rem">Critical Reading Materials — Classroom Ready</h2>
      </div>

      <div class="panel panel-yellow" style="margin-bottom:1rem">
        <h3 style="color:#A07800">📄 Fact or Opinion? (A2 Mid–High)</h3>
        <p>Read these sentences. Decide: Is it a FACT or an OPINION? A fact can be proved. An opinion is what someone thinks.</p>
        <ul style="margin-top:.8rem">
          <li>Malaysia has 13 states. → <strong style="color:#047A5A">FACT</strong></li>
          <li>Durian is the best fruit in the world. → <strong style="color:#CC2222">OPINION</strong></li>
          <li>The sun rises in the east. → <strong style="color:#047A5A">FACT</strong></li>
          <li>School is more fun than staying at home. → <strong style="color:#CC2222">OPINION</strong></li>
          <li>Tigers are endangered animals. → <strong style="color:#047A5A">FACT</strong></li>
        </ul>
      </div>

      <div class="panel panel-teal">
        <h3 style="color:#047A5A">🧩 Reading Between the Lines (A2 High)</h3>
        <p><strong>Read and infer:</strong></p>
        <p style="margin-top:.6rem;font-style:italic;background:rgba(255,255,255,.6);padding:.8rem;border-radius:8px">"When Priya arrived home, she saw her birthday cake on the table. There were balloons everywhere. Her whole family was standing in the living room, smiling at her."</p>
        <p style="margin-top:.8rem"><strong>Questions to discuss:</strong></p>
        <ul>
          <li>How is Priya likely feeling? How do you know?</li>
          <li>What had her family been doing before she arrived?</li>
          <li>Did Priya know about the surprise? What clues tell you this?</li>
        </ul>
      </div>

      <div class="panel panel-coral" style="margin-top:1rem">
        <h3 style="color:#CC2222">🔮 Prediction Activity (A2 Low–Mid)</h3>
        <p>Read only the TITLE. Write what you think the text will be about. Then read and check!</p>
        <ul style="margin-top:.8rem">
          <li><strong>Title: "The Lost Kitten"</strong> — What do you think will happen?</li>
          <li><strong>Title: "A Strange Noise at Night"</strong> — Who might be in the story?</li>
          <li><strong>Title: "Why Do Leaves Change Colour?"</strong> — What type of text is this?</li>
        </ul>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════════════
     SECTION 7: INTERACTIVE ACTIVITIES
══════════════════════════════════════════════════ -->
<div id="section-activities" class="section">
  <div class="sec-wrap">
    <div class="sec-header">
      <div class="sec-tag" style="background:#FF6B6B22;color:#CC2222;">⚡ Let's Play & Learn!</div>
      <h2 class="sec-title">Interactive Activities</h2>
      <p class="sec-sub">Fun reading activities for Year 4 pupils. Choose an activity below and get started!</p>
    </div>

    <div class="tab-bar" id="actTabs">
      <div class="tab active" onclick="switchTab('actTabs','act-',1)">🔤 Word Game</div>
      <div class="tab" onclick="switchTab('actTabs','act-',2)">📖 Story Quiz</div>
      <div class="tab" onclick="switchTab('actTabs','act-',3)">🔀 Sentence Sort</div>
      <div class="tab" onclick="switchTab('actTabs','act-',4)">🧠 Think & Infer</div>
    </div>

    <!-- WORD GAME -->
    <div id="act-1" class="tab-content active">
      <div class="word-game">
        <h3 style="font-family:'Poppins',sans-serif;font-weight:800;font-size:1.3rem;color:var(--purple);margin-bottom:.5rem">🔤 Word Guessing Game</h3>
        <p style="font-size:.88rem;color:#666;margin-bottom:1rem">Guess the hidden word! Click the letters. You have 6 lives. 🏆</p>
        <div class="word-lives" id="wg-lives">❤️ ❤️ ❤️ ❤️ ❤️ ❤️</div>
        <div class="word-hint" id="wg-hint">Hint: loading...</div>
        <div class="word-display" id="wg-display">_ _ _ _ _</div>
        <div class="letter-grid" id="wg-letters"></div>
        <div class="wg-score">Score: <span id="wg-score">0</span> pts</div>
        <div style="text-align:center;margin-top:1rem">
          <button class="btn btn-purple" onclick="startWordGame()">New Word 🔄</button>
        </div>
      </div>
    </div>

    <!-- STORY QUIZ -->
    <div id="act-2" class="tab-content">
      <div class="quiz-box">
        <h3 style="font-family:'Poppins',sans-serif;font-weight:800;font-size:1.3rem;color:var(--coral);margin-bottom:1rem">📖 Story Comprehension Quiz</h3>
        <div class="quiz-passage">
          <strong>The Helpful Robot</strong><br><br>
          Zara had a small blue robot called Beep. Beep could talk, walk, and carry things. One morning, Zara forgot her homework at home. She was already on the school bus! She called Beep on her smartwatch. "Beep, please bring my homework to school," she said. Beep picked up the blue folder from the table, walked carefully to the school gate, and gave it to the guard. The guard gave it to Zara's teacher. When Zara got home, she gave Beep a sticker to say thank you. Beep beeped happily.
        </div>
        <div id="sq-container"></div>
        <div id="sq-result" style="display:none" class="quiz-score"></div>
        <button class="btn btn-coral" id="sq-next" onclick="nextSQ()" style="margin-top:1rem;background:var(--coral);color:#fff">Next Question →</button>
      </div>
    </div>

    <!-- SENTENCE SORT -->
    <div id="act-3" class="tab-content">
      <div class="sentence-sort">
        <h3 style="font-family:'Poppins',sans-serif;font-weight:800;font-size:1.3rem;color:var(--teal);margin-bottom:.5rem">🔀 Sentence Builder</h3>
        <p class="sort-instruction" id="ss-instruction">Put the words in the correct order to make a sentence. Tap a word to add it. Tap a placed word to remove it.</p>
        <div id="ss-answer" class="answer-zone"></div>
        <div id="ss-tokens" class="word-tokens"></div>
        <div style="display:flex;gap:.8rem;flex-wrap:wrap">
          <button class="btn btn-teal" onclick="checkSentence()">Check ✓</button>
          <button class="btn btn-outline" style="border-color:#ccc;color:#666" onclick="clearSentence()">Clear ✗</button>
          <button class="btn btn-purple" onclick="nextSentence()">Next Sentence →</button>
        </div>
        <div id="ss-feedback" style="margin-top:.8rem;font-size:.9rem;font-weight:700;display:none"></div>
        <div style="margin-top:.8rem;font-size:.85rem;color:#888">Sentences completed: <span id="ss-count">0</span> / <span id="ss-total">5</span></div>
      </div>
    </div>

    <!-- THINK & INFER -->
    <div id="act-4" class="tab-content">
      <div class="quiz-box">
        <h3 style="font-family:'Poppins',sans-serif;font-weight:800;font-size:1.3rem;color:var(--purple);margin-bottom:1rem">🧠 Think &amp; Infer</h3>
        <div id="inf-container"></div>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════════════
     SECTION 8: DIFFERENTIATION
══════════════════════════════════════════════════ -->
<div id="section-diff" class="section">
  <div class="sec-wrap">
    <div class="sec-header">
      <div class="sec-tag" style="background:#FF9F1C22;color:#995500;">🌈 Every Learner Matters</div>
      <h2 class="sec-title">Differentiation Strategies & Activities</h2>
      <p class="sec-sub">Every pupil learns differently. READvolution provides strategies and activities for A2 Low, Mid, and High learners so that everyone can grow as a reader.</p>
    </div>

    <div class="panel panel-yellow" style="margin-bottom:2rem">
      <h3 style="color:#A07800">❓ What Is Differentiation?</h3>
      <p>Differentiation means adjusting the way you teach and the activities you give so that all pupils can learn. It is NOT about giving some pupils easy work and others hard work. It is about giving <strong>the right support and challenge to every pupil</strong>, based on where they are now.</p>
    </div>

    <div class="sec-header" style="margin-bottom:1rem">
      <h2 class="sec-title" style="font-size:1.7rem">Key Differentiation Strategies</h2>
    </div>
    <div class="card-grid" style="margin-bottom:2rem">
      <div class="card" style="border-color:#06D6A0">
        <div class="card-icon">📐</div>
        <h3 style="color:#047A5A">By Scaffolding</h3>
        <p>Give sentence starters, graphic organisers, or word banks to pupils who need support. Remove these for pupils who are ready to work independently.</p>
      </div>
      <div class="card" style="border-color:#4CC9F0">
        <div class="card-icon">❓</div>
        <h3 style="color:#1A6A99">By Task</h3>
        <p>All pupils read the same text but answer different questions. Low: literal questions. Mid: inferential questions. High: evaluative questions.</p>
      </div>
      <div class="card" style="border-color:#845EC2">
        <div class="card-icon">⏱️</div>
        <h3 style="color:#5A3A8A">By Time</h3>
        <p>Give pupils who need more time a shorter text or fewer questions. More capable pupils can read longer or more complex texts in the same time.</p>
      </div>
      <div class="card" style="border-color:#FF9F1C">
        <div class="card-icon">🤝</div>
        <h3 style="color:#995500">By Grouping</h3>
        <p>Use flexible groups: paired reading (stronger pupil supports weaker), small group work, or independent reading. Mix groups regularly.</p>
      </div>
      <div class="card" style="border-color:#FF6B6B">
        <div class="card-icon">🖼️</div>
        <h3 style="color:#CC2222">By Resources</h3>
        <p>Use picture-supported texts for lower ability pupils. Use texts with fewer visuals for higher ability pupils who rely on the text itself for meaning.</p>
      </div>
      <div class="card" style="border-color:#43AA8B">
        <div class="card-icon">📊</div>
        <h3 style="color:#2A6E5A">By Outcome</h3>
        <p>Allow pupils to show understanding in different ways — drawing, writing, speaking, or using digital tools. The goal (comprehension) stays the same.</p>
      </div>
    </div>

    <div class="sec-header" style="margin-bottom:1rem">
      <h2 class="sec-title" style="font-size:1.7rem">Differentiated Reading Activities</h2>
      <p class="sec-sub">Use the same reading text with different task levels.</p>
    </div>

    <div class="panel panel-teal" style="margin-bottom:1.2rem">
      <h3 style="color:#047A5A">📄 Reading Text (Same for All Levels)</h3>
      <p style="font-style:italic;margin-top:.6rem;background:rgba(255,255,255,.6);padding:.8rem;border-radius:8px;line-height:1.8">"Every morning, Lina walks to the market with her grandmother. They buy fresh vegetables and fish. Her grandmother knows all the sellers by name. Lina enjoys listening to her grandmother talk and laugh with them. On the way home, they always stop for a bowl of hot soup at a small stall near the river."</p>
    </div>

    <div class="diff-grid">
      <div class="diff-card diff-low">
        <span class="diff-badge">A2 Low</span>
        <h3 style="color:#047A5A">🟢 Supported Tasks</h3>
        <ul>
          <li>Circle the correct answer: Lina walks to the <strong>market / school</strong> every morning.</li>
          <li>Tick True or False: Lina goes alone. (False ✓)</li>
          <li>Fill in the blank: They buy _____ and _____. (vegetables, fish)</li>
          <li>Draw what Lina and her grandmother buy.</li>
          <li>Match: grandmother — (picture of old woman)</li>
        </ul>
      </div>
      <div class="diff-card diff-mid">
        <span class="diff-badge">A2 Mid</span>
        <h3 style="color:#1A6A99">🔵 Independent Tasks</h3>
        <ul>
          <li>Who does Lina go to the market with?</li>
          <li>What do they buy at the market?</li>
          <li>Where do they stop on the way home?</li>
          <li>Sequence the events: (1) buy fish, (2) stop for soup, (3) walk to market</li>
          <li>Write one sentence about what Lina enjoys.</li>
        </ul>
      </div>
      <div class="diff-card diff-high">
        <span class="diff-badge">A2 High</span>
        <h3 style="color:#5A3A8A">🟣 Extension Tasks</h3>
        <ul>
          <li>Why do you think Lina enjoys these mornings with her grandmother?</li>
          <li>What does "knows all the sellers by name" tell us about her grandmother?</li>
          <li>How do you think the grandmother feels about Lina coming along?</li>
          <li>Write 3 sentences: How is Lina's morning similar to or different from yours?</li>
          <li>Is this text about facts or feelings? Give evidence from the text.</li>
        </ul>
      </div>
    </div>

    <div style="margin-top:2rem">
      <div class="sec-header" style="margin-bottom:1rem">
        <h2 class="sec-title" style="font-size:1.7rem">Differentiated Word Work</h2>
      </div>
      <div class="diff-grid">
        <div class="diff-card diff-low">
          <span class="diff-badge">A2 Low</span>
          <h3 style="color:#047A5A">Word Recognition</h3>
          <ul>
            <li>Sight word matching with pictures</li>
            <li>CVC word building (cat, pen, top)</li>
            <li>Word family activities (-at: bat, cat, hat)</li>
            <li>Colour the word: Find and colour all the word "the"</li>
          </ul>
        </div>
        <div class="diff-card diff-mid">
          <span class="diff-badge">A2 Mid</span>
          <h3 style="color:#1A6A99">Word Meaning</h3>
          <ul>
            <li>Match word to definition</li>
            <li>Fill in the blank with the correct word</li>
            <li>Word in context: What does "fresh" mean here?</li>
            <li>Synonyms: another word for "happy" is ___</li>
          </ul>
        </div>
        <div class="diff-card diff-high">
          <span class="diff-badge">A2 High</span>
          <h3 style="color:#5A3A8A">Word in Context</h3>
          <ul>
            <li>Use a new word in an original sentence</li>
            <li>Identify connotation: Is "thin" positive or negative here?</li>
            <li>Prefix/suffix work (un-, re-, -ful, -less)</li>
            <li>Vocabulary expansion: Find 3 words related to "market"</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════════════
     SECTION 9: SMART LITERACY (EMBED)
══════════════════════════════════════════════════ -->
<div id="section-smartlit" class="section">
  <div class="sec-wrap">
    <div class="sec-header">
      <div class="sec-tag" style="background:#06D6A022;color:#047A5A;">🔗 Previous Innovation</div>
      <h2 class="sec-title">Smart Literacy — Word Recognition</h2>
      <p class="sec-sub">Our previous innovation (2023) — Smart Literacy — focuses on Word Recognition. Explore the full site below!</p>
    </div>
    <div class="panel panel-teal" style="margin-bottom:1.5rem">
      <h3 style="color:#047A5A">📌 About Smart Literacy</h3>
      <p>Smart Literacy is our earlier Google Sites platform covering <strong>Reading Material, Word Recognition, Comprehension Tasks, Self-Assessed Materials</strong>, and a <strong>Teacher's Manual</strong>. READvolution builds on Smart Literacy with additional CEFR alignment, SEA PLM preparation, critical reading, and differentiation strategies.</p>
    </div>
    <div class="iframe-wrap">
      <iframe src="https://sites.google.com/view/smartliteracy/word-recognition?authuser=0" title="Smart Literacy — Word Recognition" allowfullscreen></iframe>
    </div>
    <div style="margin-top:1.2rem;text-align:center">
      <a class="btn btn-teal" href="https://sites.google.com/view/smartliteracy/word-recognition?authuser=0" target="_blank" rel="noopener">Open Smart Literacy in New Tab ↗</a>
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div style="display:flex;align-items:center;justify-content:center;gap:12px;margin-bottom:.6rem">
    <div class="ft-logo">READvolution 📚</div>
  </div>
  <p>Jabatan Pengajian Inggeris · Institut Pendidikan Guru Kampus Tuanku Bainun</p>
  <p style="margin-top:.3rem">Kogila Ramakrishnan · Moganashwari Kandasamy · Agelya Chitambaram · Nizaha</p>
  <p style="margin-top:.5rem">📧 <a href="mailto:kogirn@gmail.com">kogirn@gmail.com</a> &nbsp;·&nbsp; Free for all teachers, pupils, and parents</p>
  <p style="margin-top:.5rem;font-size:.75rem">Supporting SEA PLM reading goals · CEFR A2 aligned · Year 4 DSKP</p>
</footer>

<script>
// ── NAVIGATION ──
function showSection(id){
  document.querySelectorAll('.section').forEach(s=>s.classList.remove('active'));
  document.querySelectorAll('.nav-btn').forEach(b=>b.classList.remove('active'));
  document.getElementById('section-'+id).classList.add('active');
  const btns=document.querySelectorAll('.nav-btn');
  const map={home:0,dskp:1,cefr:2,seaplm:3,seamat:4,critical:5,activities:6,diff:7,smartlit:8};
  if(map[id]!==undefined)btns[map[id]].classList.add('active');
  window.scrollTo({top:0,behavior:'smooth'});
}

// ── TAB SWITCHING ──
function switchTab(barId,prefix,num){
  const bar=document.getElementById(barId);
  bar.querySelectorAll('.tab').forEach((t,i)=>{
    t.classList.toggle('active',i===num-1);
  });
  document.querySelectorAll('[id^="'+prefix+'"]').forEach(el=>{
    el.classList.remove('active');
  });
  document.getElementById(prefix+num).classList.add('active');
}

// ── QUIZ ANSWER CHECK ──
function checkAns(btn,qId,chosen,correct){
  const container=document.getElementById(qId);
  container.querySelectorAll('.quiz-opt').forEach(b=>{b.disabled=true;b.style.opacity=.7});
  const fb=document.getElementById(qId+'-fb');
  if(chosen===correct){
    btn.classList.add('correct');
    fb.style.display='block';fb.style.background='#EDFFF9';fb.style.color='#047A5A';
    fb.textContent='✅ Correct! Well done!';
  } else {
    btn.classList.add('wrong');
    fb.style.display='block';fb.style.background='#FFF0EF';fb.style.color='#CC3333';
    fb.textContent='❌ Not quite. Look at the text again.';
    container.querySelectorAll('.quiz-opt').forEach(b=>{
      if(b.getAttribute('onclick')&&b.getAttribute('onclick').includes("'"+correct+"','"+correct+"'")){b.classList.add('correct')}
    });
  }
}

// ── WORD GAME ──
const wordBank=[
  {word:'HAPPY',hint:'How you feel when something good happens'},
  {word:'GARDEN',hint:'A place where plants and flowers grow'},
  {word:'PENCIL',hint:'You use this to write or draw'},
  {word:'MONKEY',hint:'A furry animal that can climb trees'},
  {word:'BRIDGE',hint:'A structure that goes over water or a road'},
  {word:'MOTHER',hint:'A female parent'},
  {word:'RABBIT',hint:'A small furry animal with long ears'},
  {word:'CANDLE',hint:'It gives light and melts when it burns'},
  {word:'FOREST',hint:'A large area with many trees'},
  {word:'BUTTER',hint:'You spread this on bread'},
];
let wgWord='',wgGuessed=[],wgLives=6,wgScore=0,wgPicked=[];

function startWordGame(){
  const avail=wordBank.filter(w=>!wgPicked.includes(w.word));
  if(avail.length===0){wgPicked=[];}
  const choice=avail.length>0?avail[Math.floor(Math.random()*avail.length)]:wordBank[0];
  wgWord=choice.word;wgGuessed=[];wgLives=6;wgPicked.push(wgWord);
  document.getElementById('wg-hint').textContent='Hint: '+choice.hint;
  renderWG();buildLetters();
}

function renderWG(){
  const disp=wgWord.split('').map(c=>wgGuessed.includes(c)?c:'_').join(' ');
  document.getElementById('wg-display').textContent=disp;
  const hearts='❤️'.repeat(wgLives)+'🖤'.repeat(6-wgLives);
  document.getElementById('wg-lives').textContent=hearts;
  if(!disp.includes('_')){document.getElementById('wg-display').textContent+=' 🎉';document.getElementById('wg-score').textContent=wgScore+=10;}
  if(wgLives<=0){document.getElementById('wg-display').textContent='💔 '+wgWord;}
}

function buildLetters(){
  const grid=document.getElementById('wg-letters');grid.innerHTML='';
  'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('').forEach(l=>{
    const b=document.createElement('button');b.className='letter-btn';b.textContent=l;
    b.onclick=()=>{b.disabled=true;b.style.opacity=.3;guessLetter(l)};
    grid.appendChild(b);
  });
}

function guessLetter(l){
  if(wgWord.includes(l)){wgGuessed.push(l);}else{wgLives--;}
  renderWG();
  if(wgLives<=0)document.querySelectorAll('.letter-btn').forEach(b=>b.disabled=true);
}
startWordGame();

// ── STORY QUIZ ──
const sqQs=[
  {q:'What colour is the robot?',opts:['Red','Blue','Green'],ans:1},
  {q:'What did Zara forget at home?',opts:['Her lunchbox','Her homework','Her shoes'],ans:1},
  {q:'How did Zara contact Beep?',opts:['By phone','By letter','By smartwatch'],ans:2},
  {q:'Who gave the homework to Zara\'s teacher?',opts:['Beep the robot','The school guard','Zara\'s mother'],ans:1},
  {q:'How did Zara say thank you to Beep?',opts:['She gave Beep a sticker','She bought Beep a cake','She gave Beep a hug'],ans:0},
];
let sqIdx=0,sqScore=0;

function renderSQ(){
  if(sqIdx>=sqQs.length){
    document.getElementById('sq-container').innerHTML='';
    document.getElementById('sq-result').style.display='block';
    document.getElementById('sq-result').textContent='🏆 Score: '+sqScore+' / '+sqQs.length+' — '+(sqScore>=4?'Excellent reading!':sqScore>=3?'Good job!':'Keep practising!');
    document.getElementById('sq-next').textContent='Play Again 🔄';
    document.getElementById('sq-next').onclick=()=>{sqIdx=0;sqScore=0;document.getElementById('sq-result').style.display='none';document.getElementById('sq-next').onclick=nextSQ;document.getElementById('sq-next').textContent='Next Question →';renderSQ()};
    return;
  }
  const q=sqQs[sqIdx];
  let html='<div class="quiz-q">'+(sqIdx+1)+'. '+q.q+'</div><div class="quiz-opts">';
  q.opts.forEach((o,i)=>html+='<button class="quiz-opt" onclick="answerSQ(this,'+i+')">'+o+'</button>');
  html+='</div><div id="sq-fb" class="quiz-feedback"></div>';
  document.getElementById('sq-container').innerHTML=html;
}

function answerSQ(btn,i){
  document.querySelectorAll('#sq-container .quiz-opt').forEach(b=>b.disabled=true);
  const q=sqQs[sqIdx];const fb=document.getElementById('sq-fb');
  if(i===q.ans){btn.classList.add('correct');sqScore++;fb.style.display='block';fb.style.background='#EDFFF9';fb.style.color='#047A5A';fb.textContent='✅ Correct!';}
  else{btn.classList.add('wrong');document.querySelectorAll('#sq-container .quiz-opt')[q.ans].classList.add('correct');fb.style.display='block';fb.style.background='#FFF0EF';fb.style.color='#CC3333';fb.textContent='❌ The correct answer is highlighted.';}
}

function nextSQ(){sqIdx++;renderSQ();}
renderSQ();

// ── SENTENCE SORT ──
const sentences=[
  {words:['Amir','reads','books','every','day.'],correct:'Amir reads books every day.'},
  {words:['The','cat','sat','on','the','mat.'],correct:'The cat sat on the mat.'},
  {words:['She','likes','eating','mangoes','and','apples.'],correct:'She likes eating mangoes and apples.'},
  {words:['The','children','played','football','at','school.'],correct:'The children played football at school.'},
  {words:['My','grandmother','cooks','delicious','rice','every','Sunday.'],correct:'My grandmother cooks delicious rice every Sunday.'},
];
let ssIdx=0,ssPlaced=[],ssCompleted=0;

function loadSentence(){
  const s=sentences[ssIdx];
  const shuffled=[...s.words].sort(()=>Math.random()-.5);
  ssPlaced=[];
  document.getElementById('ss-answer').innerHTML='';
  const tokBox=document.getElementById('ss-tokens');tokBox.innerHTML='';
  shuffled.forEach((w,i)=>{
    const t=document.createElement('div');t.className='token available';t.textContent=w;t.dataset.word=w;t.dataset.idx=i;
    t.onclick=()=>placeToken(t,w);tokBox.appendChild(t);
  });
  document.getElementById('ss-feedback').style.display='none';
  document.getElementById('ss-total').textContent=sentences.length;
  document.getElementById('ss-count').textContent=ssCompleted;
}

function placeToken(el,word){
  if(el.classList.contains('placed'))return;
  el.classList.remove('available');el.classList.add('placed');
  ssPlaced.push(word);
  const pEl=document.createElement('div');pEl.className='placed-token';pEl.textContent=word;
  pEl.onclick=()=>{ssPlaced.splice(ssPlaced.indexOf(word),1);pEl.remove();el.classList.remove('placed');el.classList.add('available')};
  document.getElementById('ss-answer').appendChild(pEl);
}

function checkSentence(){
  const ans=ssPlaced.join(' ');const correct=sentences[ssIdx].correct;
  const fb=document.getElementById('ss-feedback');fb.style.display='block';
  if(ans===correct){fb.style.background='#EDFFF9';fb.style.color='#047A5A';fb.textContent='✅ Correct! Great sentence!';ssCompleted++;document.getElementById('ss-count').textContent=ssCompleted;}
  else{fb.style.background='#FFF0EF';fb.style.color='#CC3333';fb.textContent='❌ Not quite. Try again! Correct: '+correct;}
}

function clearSentence(){ssPlaced=[];document.getElementById('ss-answer').innerHTML='';document.querySelectorAll('.token').forEach(t=>{t.classList.remove('placed');t.classList.add('available')});document.getElementById('ss-feedback').style.display='none';}

function nextSentence(){ssIdx=(ssIdx+1)%sentences.length;loadSentence();}
loadSentence();

// ── INFER ACTIVITY ──
const inferScenes=[
  {scene:'"Sam looked at his plate. He pushed his vegetables to the side and sighed. His mother watched him from across the table."',question:'How does Sam feel about eating vegetables?',opts:['He loves them very much','He does not want to eat them','He is happy to eat everything'],ans:1,explain:'Sam pushing his vegetables away and sighing tells us he does not want to eat them.'},
  {scene:'"Maya walked into the classroom and saw everyone wearing party hats. There was a big cake on the teacher\'s table."',question:'What is probably happening in the classroom?',opts:['It is a normal school day','Someone is having a birthday party','The teacher is angry'],ans:1,explain:'Party hats and a cake are clues that someone is celebrating a birthday.'},
  {scene:'"Raju ran into the house. His shoes left muddy marks on the floor. He did not stop to take them off."',question:'Why did Raju not take off his shoes?',opts:['He forgot his shoes were muddy','He was in a big hurry','He did not like taking off shoes'],ans:1,explain:'"Ran" and not stopping tell us Raju was in a big hurry.'},
];
let infIdx=0;

function renderInf(){
  const sc=inferScenes[infIdx];
  let html='<div style="font-size:.78rem;color:#888;margin-bottom:.5rem">Scene '+(infIdx+1)+' of '+inferScenes.length+'</div>';
  html+='<div class="quiz-passage">'+sc.scene+'</div>';
  html+='<div class="quiz-q">🔍 '+sc.question+'</div><div class="quiz-opts">';
  sc.opts.forEach((o,i)=>html+='<button class="quiz-opt" onclick="answerInf(this,'+i+')">'+o+'</button>');
  html+='</div><div id="inf-fb" class="quiz-feedback"></div>';
  html+='<button class="btn btn-purple" onclick="nextInf()" style="margin-top:1rem">Next Scene →</button>';
  document.getElementById('inf-container').innerHTML=html;
}

function answerInf(btn,i){
  const sc=inferScenes[infIdx];
  document.querySelectorAll('#inf-container .quiz-opt').forEach(b=>b.disabled=true);
  const fb=document.getElementById('inf-fb');fb.style.display='block';
  if(i===sc.ans){btn.classList.add('correct');fb.style.background='#EDFFF9';fb.style.color='#047A5A';fb.textContent='✅ Correct! '+sc.explain;}
  else{btn.classList.add('wrong');document.querySelectorAll('#inf-container .quiz-opt')[sc.ans].classList.add('correct');fb.style.background='#FFF0EF';fb.style.color='#CC3333';fb.textContent='❌ Not quite. '+sc.explain;}
}

function nextInf(){infIdx=(infIdx+1)%inferScenes.length;renderInf();}
renderInf();
</script>
</body>
</html>
