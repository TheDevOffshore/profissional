<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Portfólio de William Oliveira — Piloto RPAS Offshore & Desenvolvedor. Operações críticas em óleo e gás + projetos de software para o setor.">
<title>William Oliveira — RPAS Offshore & Dev</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&family=Inter:wght@400;500&display=swap" rel="stylesheet">
<style>
/* ── RESET ── */
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
:root{
  --black:   #080c10;
  --navy:    #0a1628;
  --deep:    #0d1f3c;
  --card:    #111827;
  --card2:   #1a2435;
  --border:  rgba(255,255,255,0.07);
  --border2: rgba(255,255,255,0.13);
  --text:    #e8eef5;
  --text2:   #8ca0b8;
  --text3:   #4d6480;
  --gold:    #e8a020;
  --gold2:   #f5b830;
  --gold-bg: rgba(232,160,32,0.10);
  --green:   #22c55e;
  --green-bg:rgba(34,197,94,0.10);
  --blue:    #60a5fa;
  --blue-bg: rgba(96,165,250,0.10);
  --red:     #f87171;
  --r:       8px;
  --r-lg:    14px;
  --font:    'Space Grotesk',sans-serif;
  --mono:    'JetBrains Mono',monospace;
  --body:    'Inter',sans-serif;
}

body{
  font-family:var(--body);
  background:var(--black);
  color:var(--text);
  line-height:1.6;
  overflow-x:hidden;
}

/* ── NOISE TEXTURE ── */
body::before{
  content:'';
  position:fixed;inset:0;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
  opacity:0.4;pointer-events:none;z-index:0;
}

/* ── NAV ── */
nav{
  position:fixed;top:0;left:0;right:0;z-index:100;
  padding:0 32px;height:56px;
  display:flex;align-items:center;justify-content:space-between;
  background:rgba(8,12,16,0.85);
  backdrop-filter:blur(16px);
  border-bottom:1px solid var(--border);
}
.nav-logo{
  display:flex;align-items:center;gap:10px;
  font-family:var(--mono);font-size:13px;font-weight:500;color:var(--text2);
  text-decoration:none;
}
.nav-logo-dot{width:8px;height:8px;border-radius:50%;background:var(--gold);box-shadow:0 0 8px var(--gold)}
.nav-links{display:flex;gap:28px}
.nav-links a{
  font-size:12px;font-weight:500;color:var(--text3);
  text-decoration:none;transition:color .15s;letter-spacing:.02em;
}
.nav-links a:hover{color:var(--text)}
.nav-cta{
  background:var(--gold);color:#000;
  font-size:12px;font-weight:700;padding:6px 16px;
  border-radius:6px;text-decoration:none;transition:all .15s;
  font-family:var(--font);
}
.nav-cta:hover{background:var(--gold2)}

/* ── HERO ── */
.hero{
  position:relative;z-index:1;
  min-height:100vh;
  display:flex;align-items:center;
  padding:80px 32px 60px;
  overflow:hidden;
}

/* Grid de radar ao fundo */
.hero-bg{
  position:absolute;inset:0;
  background:
    radial-gradient(ellipse 80% 60% at 60% 40%, rgba(232,160,32,0.06) 0%, transparent 70%),
    radial-gradient(ellipse 50% 50% at 80% 80%, rgba(96,165,250,0.04) 0%, transparent 60%);
}
.radar-ring{
  position:absolute;
  border:1px solid rgba(232,160,32,0.08);
  border-radius:50%;
  top:50%;left:60%;
  transform:translate(-50%,-50%);
  animation:radarPulse 4s ease-in-out infinite;
}
@keyframes radarPulse{0%,100%{opacity:.4;transform:translate(-50%,-50%) scale(1)}50%{opacity:.15;transform:translate(-50%,-50%) scale(1.05)}}

.hero-wrap{
  max-width:1100px;margin:0 auto;width:100%;
  display:grid;grid-template-columns:1fr 420px;gap:60px;align-items:center;
  position:relative;z-index:2;
}

.hero-eyebrow{
  display:inline-flex;align-items:center;gap:8px;
  font-family:var(--mono);font-size:11px;color:var(--gold);
  background:var(--gold-bg);border:1px solid rgba(232,160,32,0.2);
  padding:4px 12px;border-radius:99px;margin-bottom:22px;
  letter-spacing:.08em;
}
.hero-eyebrow-dot{width:5px;height:5px;border-radius:50%;background:var(--gold);animation:pulse 1.5s infinite}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:.4}}

h1{
  font-family:var(--font);
  font-size:clamp(36px,5vw,58px);
  font-weight:700;
  line-height:1.05;
  letter-spacing:-.02em;
  margin-bottom:20px;
}
h1 .name-highlight{
  background:linear-gradient(135deg,var(--gold),var(--gold2),#fff9e0);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
h1 .role-line{
  display:block;
  font-size:clamp(20px,2.5vw,28px);
  color:var(--text2);font-weight:500;letter-spacing:-.01em;margin-top:6px;
}

.hero-desc{
  font-size:15px;color:var(--text2);line-height:1.7;
  max-width:500px;margin-bottom:32px;
}
.hero-desc strong{color:var(--text);font-weight:600}

.hero-actions{display:flex;gap:12px;flex-wrap:wrap;margin-bottom:36px}
.btn-hero-primary{
  background:var(--gold);color:#000;
  font-family:var(--font);font-size:13px;font-weight:700;
  padding:11px 24px;border-radius:var(--r);
  text-decoration:none;transition:all .15s;
  display:inline-flex;align-items:center;gap:7px;
}
.btn-hero-primary:hover{background:var(--gold2);transform:translateY(-1px)}
.btn-hero-ghost{
  background:transparent;color:var(--text2);
  border:1px solid var(--border2);
  font-family:var(--font);font-size:13px;font-weight:500;
  padding:11px 24px;border-radius:var(--r);
  text-decoration:none;transition:all .15s;
  display:inline-flex;align-items:center;gap:7px;
}
.btn-hero-ghost:hover{background:var(--card);color:var(--text);border-color:var(--gold)}

.hero-stats{display:flex;gap:28px;flex-wrap:wrap}
.stat-item{border-left:2px solid var(--gold);padding-left:14px}
.stat-num{font-family:var(--mono);font-size:24px;font-weight:500;color:var(--text);line-height:1}
.stat-lbl{font-size:11px;color:var(--text3);margin-top:3px}

/* HERO CARD LADO DIREITO */
.hero-card{
  background:var(--card);
  border:1px solid var(--border2);
  border-radius:var(--r-lg);
  overflow:hidden;
}
.hc-top{
  background:linear-gradient(135deg,var(--navy) 0%,var(--deep) 100%);
  padding:24px;
  display:flex;align-items:center;gap:16px;
  border-bottom:1px solid var(--border);
}
.hc-avatar{
  width:64px;height:64px;border-radius:50%;
  background:linear-gradient(135deg,var(--gold),#c07000);
  display:flex;align-items:center;justify-content:center;
  font-family:var(--font);font-size:22px;font-weight:700;color:#000;
  flex-shrink:0;
  box-shadow:0 0 0 3px rgba(232,160,32,0.25);
}
.hc-name{font-family:var(--font);font-size:15px;font-weight:700}
.hc-role{font-size:11px;color:var(--text3);margin-top:3px}
.hc-loc{font-size:11px;color:var(--gold);margin-top:4px;display:flex;align-items:center;gap:4px}
.hc-body{padding:20px}
.hc-skill{
  display:flex;align-items:center;justify-content:space-between;
  margin-bottom:14px;
}
.hc-skill:last-child{margin-bottom:0}
.hc-skill-name{font-size:12px;color:var(--text2);font-weight:500}
.hc-skill-bar{width:140px;height:5px;background:rgba(255,255,255,.08);border-radius:99px;overflow:hidden}
.hc-skill-fill{height:100%;border-radius:99px;background:linear-gradient(90deg,var(--gold),var(--gold2))}
.hc-skill-pct{font-family:var(--mono);font-size:10px;color:var(--text3)}
.hc-footer{
  padding:14px 20px;border-top:1px solid var(--border);
  display:flex;gap:10px;
}
.hc-tag{
  font-size:10px;font-weight:600;padding:3px 9px;border-radius:99px;
  font-family:var(--mono);
}
.hc-tag-gold{background:var(--gold-bg);color:var(--gold);border:1px solid rgba(232,160,32,.2)}
.hc-tag-blue{background:var(--blue-bg);color:var(--blue);border:1px solid rgba(96,165,250,.2)}
.hc-tag-green{background:var(--green-bg);color:var(--green);border:1px solid rgba(34,197,94,.2)}

/* ── SECTIONS ── */
section{position:relative;z-index:1;padding:80px 32px}
.section-wrap{max-width:1100px;margin:0 auto}
.section-label{
  font-family:var(--mono);font-size:10px;font-weight:500;
  color:var(--gold);letter-spacing:.12em;text-transform:uppercase;
  margin-bottom:10px;
}
.section-title{
  font-family:var(--font);font-size:clamp(26px,3vw,38px);
  font-weight:700;letter-spacing:-.02em;margin-bottom:10px;
}
.section-sub{font-size:15px;color:var(--text2);max-width:560px;line-height:1.6;margin-bottom:48px}

/* ── SOBRE ── */
#sobre{background:var(--navy)}
.sobre-grid{display:grid;grid-template-columns:1fr 1fr;gap:48px;align-items:start}
.sobre-text p{font-size:14px;color:var(--text2);line-height:1.8;margin-bottom:16px}
.sobre-text p strong{color:var(--text);font-weight:600}
.sobre-tags{display:flex;flex-wrap:wrap;gap:8px;margin-top:24px}
.stag{
  font-size:11px;font-weight:600;padding:5px 12px;border-radius:var(--r);
  background:var(--card2);border:1px solid var(--border2);color:var(--text2);
  font-family:var(--mono);
}
.sobre-cols{display:flex;flex-direction:column;gap:16px}
.info-card{
  background:var(--card);border:1px solid var(--border);
  border-radius:var(--r);padding:18px 20px;
}
.info-card-title{font-size:10px;font-weight:700;color:var(--gold);text-transform:uppercase;letter-spacing:.09em;margin-bottom:12px}
.info-row{display:flex;justify-content:space-between;align-items:baseline;padding:6px 0;border-bottom:1px solid var(--border)}
.info-row:last-child{border-bottom:none}
.ir-key{font-size:11px;color:var(--text3)}
.ir-val{font-size:12px;color:var(--text);font-weight:500;font-family:var(--mono)}

/* ── HABILIDADES ── */
#habilidades{background:var(--black)}
.skills-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:16px}
.skill-card{
  background:var(--card);border:1px solid var(--border);
  border-radius:var(--r-lg);padding:22px;
  transition:border-color .2s,transform .2s;
}
.skill-card:hover{border-color:rgba(232,160,32,.3);transform:translateY(-2px)}
.skill-card-icon{font-size:28px;margin-bottom:14px}
.skill-card-title{font-family:var(--font);font-size:14px;font-weight:700;margin-bottom:6px}
.skill-card-sub{font-size:12px;color:var(--text3);margin-bottom:16px;line-height:1.5}
.skill-tags{display:flex;flex-wrap:wrap;gap:6px}
.sk-tag{font-size:10px;font-family:var(--mono);padding:3px 8px;border-radius:4px;background:rgba(255,255,255,.05);color:var(--text3);border:1px solid var(--border)}

/* ── PROJETOS ── */
#projetos{background:var(--navy)}
.proj-filter{display:flex;gap:8px;margin-bottom:32px;flex-wrap:wrap}
.pf-btn{
  font-size:11px;font-weight:600;padding:6px 14px;border-radius:99px;
  background:transparent;border:1px solid var(--border2);color:var(--text3);
  cursor:pointer;font-family:var(--font);transition:all .15s;
}
.pf-btn:hover,.pf-btn.active{background:var(--gold-bg);color:var(--gold);border-color:rgba(232,160,32,.3)}
.projects-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(320px,1fr));gap:20px}
.proj-card{
  background:var(--card);border:1px solid var(--border);
  border-radius:var(--r-lg);overflow:hidden;
  transition:border-color .2s,transform .2s;
  display:flex;flex-direction:column;
}
.proj-card:hover{border-color:rgba(232,160,32,.3);transform:translateY(-3px)}
.proj-card-top{
  padding:22px 22px 0;
  display:flex;align-items:flex-start;justify-content:space-between;gap:12px;
}
.proj-icon{font-size:28px}
.proj-level{
  font-size:9px;font-weight:700;padding:3px 9px;border-radius:99px;
  font-family:var(--mono);text-transform:uppercase;letter-spacing:.06em;
}
.pl-init{background:var(--green-bg);color:var(--green);border:1px solid rgba(34,197,94,.2)}
.pl-mid{background:var(--gold-bg);color:var(--gold);border:1px solid rgba(232,160,32,.2)}
.pl-adv{background:rgba(248,113,113,.1);color:var(--red);border:1px solid rgba(248,113,113,.2)}
.proj-card-body{padding:16px 22px;flex:1}
.proj-title{font-family:var(--font);font-size:15px;font-weight:700;margin-bottom:8px}
.proj-desc{font-size:12px;color:var(--text2);line-height:1.6;margin-bottom:14px}
.proj-stack{display:flex;flex-wrap:wrap;gap:5px;margin-bottom:14px}
.ps-tag{font-size:10px;font-family:var(--mono);padding:2px 8px;border-radius:4px;background:rgba(255,255,255,.05);color:var(--text3);border:1px solid var(--border)}
.proj-highlights{display:flex;flex-direction:column;gap:5px}
.ph-item{font-size:11px;color:var(--text3);display:flex;align-items:flex-start;gap:6px}
.ph-item::before{content:'→';color:var(--gold);flex-shrink:0;font-size:10px;margin-top:1px}
.proj-card-footer{
  padding:14px 22px;border-top:1px solid var(--border);
  display:flex;gap:8px;
}
.btn-proj{
  flex:1;text-align:center;padding:7px;border-radius:var(--r);
  font-size:11px;font-weight:600;font-family:var(--font);
  text-decoration:none;transition:all .15s;cursor:pointer;border:none;
}
.btn-proj-primary{background:var(--gold);color:#000}
.btn-proj-primary:hover{background:var(--gold2)}
.btn-proj-ghost{background:transparent;color:var(--text3);border:1px solid var(--border2)}
.btn-proj-ghost:hover{background:var(--card2);color:var(--text2)}

/* DESTAQUE SAAS */
.proj-featured{
  grid-column:1/-1;
  display:grid;grid-template-columns:1fr 1fr;
  background:linear-gradient(135deg,var(--card) 0%,var(--card2) 100%);
  border:1px solid rgba(232,160,32,.2);
}
.proj-featured .proj-card-body{padding:28px}
.proj-featured .proj-title{font-size:20px}
.proj-featured-badge{
  display:inline-block;
  font-size:9px;font-weight:700;padding:3px 10px;border-radius:99px;
  background:linear-gradient(90deg,var(--gold),var(--gold2));color:#000;
  font-family:var(--mono);letter-spacing:.06em;margin-bottom:12px;
}
.proj-featured-preview{
  background:var(--black);
  display:flex;align-items:center;justify-content:center;
  font-size:60px;
  border-left:1px solid var(--border);
}

/* ── EXPERIÊNCIA ── */
#experiencia{background:var(--black)}
.exp-grid{display:grid;grid-template-columns:1fr 1fr;gap:32px}
.exp-col-title{
  font-family:var(--mono);font-size:10px;color:var(--text3);
  text-transform:uppercase;letter-spacing:.1em;margin-bottom:20px;
  padding-bottom:8px;border-bottom:1px solid var(--border);
}
.exp-item{margin-bottom:28px;padding-left:20px;border-left:2px solid var(--border2);position:relative}
.exp-item::before{content:'';position:absolute;left:-5px;top:4px;width:8px;height:8px;border-radius:50%;background:var(--gold)}
.exp-company{font-family:var(--font);font-size:14px;font-weight:700;margin-bottom:2px}
.exp-role{font-size:12px;color:var(--gold);font-weight:600;margin-bottom:4px}
.exp-period{font-family:var(--mono);font-size:10px;color:var(--text3);margin-bottom:10px}
.exp-desc{font-size:12px;color:var(--text2);line-height:1.6}
.exp-desc li{list-style:none;padding:3px 0;display:flex;gap:7px}
.exp-desc li::before{content:'▸';color:var(--gold);flex-shrink:0;font-size:10px;margin-top:2px}

/* ── CERTIFICAÇÕES ── */
#certificacoes{background:var(--navy)}
.certs-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));gap:14px}
.cert-card{
  background:var(--card);border:1px solid var(--border);
  border-radius:var(--r);padding:16px 18px;
  display:flex;align-items:flex-start;gap:12px;
  transition:border-color .15s;
}
.cert-card:hover{border-color:rgba(232,160,32,.3)}
.cert-icon{font-size:22px;flex-shrink:0;margin-top:2px}
.cert-name{font-size:12px;font-weight:600;margin-bottom:2px}
.cert-org{font-size:10px;color:var(--text3)}
.cert-status{
  margin-top:8px;font-size:9px;font-weight:700;padding:2px 8px;
  border-radius:99px;font-family:var(--mono);display:inline-block;
}
.cs-ativo{background:var(--green-bg);color:var(--green);border:1px solid rgba(34,197,94,.2)}
.cs-previsto{background:var(--blue-bg);color:var(--blue);border:1px solid rgba(96,165,250,.2)}

/* ── CONTATO ── */
#contato{background:var(--black)}
.contato-wrap{
  max-width:680px;margin:0 auto;text-align:center;
}
.contato-title{
  font-family:var(--font);font-size:clamp(28px,4vw,46px);
  font-weight:700;letter-spacing:-.02em;margin-bottom:14px;
}
.contato-sub{font-size:15px;color:var(--text2);margin-bottom:40px;line-height:1.6}
.contato-links{display:flex;gap:14px;justify-content:center;flex-wrap:wrap}
.contato-link{
  display:flex;align-items:center;gap:9px;
  padding:13px 24px;border-radius:var(--r);
  font-size:13px;font-weight:600;font-family:var(--font);
  text-decoration:none;transition:all .15s;
}
.cl-linkedin{background:rgba(10,102,194,.15);color:#60a5fa;border:1px solid rgba(96,165,250,.2)}
.cl-linkedin:hover{background:rgba(10,102,194,.25)}
.cl-github{background:rgba(255,255,255,.06);color:var(--text2);border:1px solid var(--border2)}
.cl-github:hover{background:rgba(255,255,255,.1);color:var(--text)}
.cl-email{background:var(--gold-bg);color:var(--gold);border:1px solid rgba(232,160,32,.2)}
.cl-email:hover{background:rgba(232,160,32,.18)}
.contato-note{
  margin-top:40px;padding:16px 20px;
  background:var(--card);border:1px solid var(--border);border-radius:var(--r);
  font-size:12px;color:var(--text3);line-height:1.6;
}
.contato-note strong{color:var(--text2)}

/* ── FOOTER ── */
footer{
  background:var(--navy);border-top:1px solid var(--border);
  padding:24px 32px;display:flex;align-items:center;justify-content:space-between;
  position:relative;z-index:1;
}
.footer-left{font-family:var(--mono);font-size:11px;color:var(--text3)}
.footer-right{font-size:11px;color:var(--text3)}

/* ── MOBILE NAV ── */
.hamburger{display:none;background:none;border:none;color:var(--text);cursor:pointer;padding:4px}

/* ── ANIMAÇÕES SCROLL ── */
.reveal{opacity:0;transform:translateY(20px);transition:opacity .5s ease,transform .5s ease}
.reveal.visible{opacity:1;transform:translateY(0)}

/* ── TOOLTIP MODAL PROJETO ── */
.proj-modal-overlay{
  position:fixed;inset:0;z-index:200;
  background:rgba(0,0,0,.8);backdrop-filter:blur(8px);
  display:flex;align-items:center;justify-content:center;padding:20px;
  opacity:0;pointer-events:none;transition:opacity .2s;
}
.proj-modal-overlay.open{opacity:1;pointer-events:all}
.proj-modal{
  background:var(--card);border:1px solid var(--border2);border-radius:var(--r-lg);
  width:100%;max-width:600px;max-height:90vh;overflow-y:auto;
  transform:scale(.96);transition:transform .2s;
}
.proj-modal-overlay.open .proj-modal{transform:scale(1)}
.pm-header{
  padding:22px 24px;border-bottom:1px solid var(--border);
  display:flex;align-items:center;justify-content:space-between;
}
.pm-title{font-family:var(--font);font-size:17px;font-weight:700}
.pm-close{
  width:28px;height:28px;border-radius:6px;background:rgba(255,255,255,.06);
  border:none;color:var(--text3);cursor:pointer;font-size:18px;
  display:flex;align-items:center;justify-content:center;transition:all .15s;
}
.pm-close:hover{background:rgba(248,113,113,.15);color:var(--red)}
.pm-body{padding:24px}
.pm-section{margin-bottom:20px}
.pm-lbl{font-size:10px;font-weight:700;color:var(--gold);text-transform:uppercase;letter-spacing:.09em;margin-bottom:8px}
.pm-text{font-size:13px;color:var(--text2);line-height:1.6}
.pm-feat-list{display:flex;flex-direction:column;gap:6px}
.pm-feat{font-size:12px;color:var(--text2);display:flex;gap:8px}
.pm-feat::before{content:'✓';color:var(--green);flex-shrink:0}
.pm-footer{padding:16px 24px;border-top:1px solid var(--border);display:flex;gap:9px}

/* ── RESPONSIVE ── */
@media(max-width:900px){
  .hero-wrap{grid-template-columns:1fr}
  .hero-card{display:none}
  .sobre-grid,.exp-grid,.proj-featured{grid-template-columns:1fr}
  .proj-featured-preview{display:none}
  nav .nav-links,.nav-cta{display:none}
}
@media(max-width:600px){
  section{padding:60px 18px}
  nav{padding:0 18px}
  .hero{padding:80px 18px 50px}
  .projects-grid{grid-template-columns:1fr}
  footer{flex-direction:column;gap:8px;text-align:center}
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#inicio">
    <div class="nav-logo-dot"></div>
    WD.dev
  </a>
  <div class="nav-links">
    <a href="#sobre">Sobre</a>
    <a href="#habilidades">Skills</a>
    <a href="#projetos">Projetos</a>
    <a href="#experiencia">Experiência</a>
    <a href="#contato">Contato</a>
  </div>
  <a class="nav-cta" href="#contato">Entrar em contato</a>
</nav>

<!-- HERO -->
<section id="inicio" class="hero">
  <div class="hero-bg"></div>
  <div class="radar-ring" style="width:400px;height:400px"></div>
  <div class="radar-ring" style="width:650px;height:650px;animation-delay:1s"></div>
  <div class="radar-ring" style="width:900px;height:900px;animation-delay:2s"></div>

  <div class="hero-wrap">
    <div class="hero-left">
      <div class="hero-eyebrow">
        <span class="hero-eyebrow-dot"></span>
        Aberto a novas oportunidades
      </div>
      <h1>
        <span class="name-highlight">William Oliveira</span>
        <span class="role-line">Piloto RPAS Offshore<br>& Desenvolvedor</span>
      </h1>
      <p class="hero-desc">
        Opero aeronaves não tripuladas em <strong>plataformas de petróleo offshore</strong> há anos e desenvolvo sistemas para o setor. Trago o contexto operacional que a maioria dos devs não tem — e as habilidades técnicas que a indústria precisa.
      </p>
      <div class="hero-actions">
        <a href="#projetos" class="btn-hero-primary">
          <svg width="14" height="14" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 4h10M3 8h6M3 12h8"/></svg>
          Ver projetos
        </a>
        <a href="https://linkedin.com/in/wmdevoffshore" target="_blank" class="btn-hero-ghost">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
          LinkedIn
        </a>
      </div>
      <div class="hero-stats">
        <div class="stat-item">
          <div class="stat-num">6+</div>
          <div class="stat-lbl">Projetos entregues</div>
        </div>
        <div class="stat-item">
          <div class="stat-num">M300</div>
          <div class="stat-lbl">DJI RTK · M30T · M350</div>
        </div>
        <div class="stat-item">
          <div class="stat-num">ANAC</div>
          <div class="stat-lbl">Certificado · SARPAS</div>
        </div>
      </div>
    </div>

    <!-- CARD LADO DIREITO -->
    <div class="hero-card">
      <div class="hc-top">
        <div class="hc-avatar">WD</div>
        <div>
          <div class="hc-name">William Oliveira</div>
          <div class="hc-role">Piloto RPAS Offshore</div>
          <div class="hc-loc">
            <svg width="10" height="10" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M8 2a4 4 0 100 8A4 4 0 008 2zM8 14s-5-3-5-6a5 5 0 0110 0c0 3-5 6-5 6z"/></svg>
            São José dos Campos — SP · Brasil
          </div>
        </div>
      </div>
      <div class="hc-body">
        <div class="hc-skill">
          <span class="hc-skill-name">Operações RPAS</span>
          <div class="hc-skill-bar"><div class="hc-skill-fill" style="width:95%"></div></div>
          <span class="hc-skill-pct">95%</span>
        </div>
        <div class="hc-skill">
          <span class="hc-skill-name">JavaScript / HTML</span>
          <div class="hc-skill-bar"><div class="hc-skill-fill" style="width:78%"></div></div>
          <span class="hc-skill-pct">78%</span>
        </div>
        <div class="hc-skill">
          <span class="hc-skill-name">Python / FastAPI</span>
          <div class="hc-skill-bar"><div class="hc-skill-fill" style="width:65%"></div></div>
          <span class="hc-skill-pct">65%</span>
        </div>
        <div class="hc-skill">
          <span class="hc-skill-name">Análise de Dados</span>
          <div class="hc-skill-bar"><div class="hc-skill-fill" style="width:60%"></div></div>
          <span class="hc-skill-pct">60%</span>
        </div>
        <div class="hc-skill">
          <span class="hc-skill-name">Compliance ANAC/DECEA</span>
          <div class="hc-skill-bar"><div class="hc-skill-fill" style="width:90%"></div></div>
          <span class="hc-skill-pct">90%</span>
        </div>
      </div>
      <div class="hc-footer">
        <span class="hc-tag hc-tag-gold">RPAS Offshore</span>
        <span class="hc-tag hc-tag-blue">Dev</span>
        <span class="hc-tag hc-tag-green">São José dos Campos</span>
      </div>
    </div>
  </div>
</section>

<!-- SOBRE -->
<section id="sobre">
  <div class="section-wrap">
    <div class="section-label">Sobre mim</div>
    <div class="section-title">Operações críticas.<br>Código com propósito.</div>
    <div class="sobre-grid reveal">
      <div class="sobre-text">
        <p>Sou <strong>Piloto de RPAS Offshore</strong>, operando aeronaves DJI M300 RTK, M30T e M350 RTK em plataformas de petróleo nas bacias de Campos e Santos. Cada voo envolve planejamento regulatório, comunicação com controle de tráfego aéreo e execução em ambientes de alto risco.</p>
        <p>Paralelamente, desenvolvo sistemas de software voltados para o setor de <strong>óleo e gás e operações RPAS</strong>. Meu diferencial é justamente esse: entender profundamente o problema antes de escrever a primeira linha de código.</p>
        <p>Busco atuar na interseção de <strong>tecnologia e operações críticas</strong> — seja como desenvolvedor, analista de dados ou engenheiro de sistemas para o setor de óleo e gás, defesa ou aviação não tripulada.</p>
        <div class="sobre-tags">
          <span class="stag">HTML · CSS · JS</span>
          <span class="stag">Python · FastAPI</span>
          <span class="stag">ANAC / SARPAS</span>
          <span class="stag">DJI Enterprise</span>
          <span class="stag">Termografia</span>
          <span class="stag">Fotogrametria</span>
          <span class="stag">NR-34 Offshore</span>
          <span class="stag">Git · GitHub</span>
        </div>
      </div>
      <div class="sobre-cols">
        <div class="info-card">
          <div class="info-card-title">Dados profissionais</div>
          <div class="info-row"><span class="ir-key">Localização</span><span class="ir-val">São José dos Campos — SP</span></div>
          <div class="info-row"><span class="ir-key">Cargo</span><span class="ir-val">Piloto RPAS Offshore</span></div>
          <div class="info-row"><span class="ir-key">Localização</span><span class="ir-val">Brasil</span></div>
          <div class="info-row"><span class="ir-key">LinkedIn</span><span class="ir-val">wmdevoffshore</span></div>
        </div>
        <div class="info-card">
          <div class="info-card-title">Aeronaves operadas</div>
          <div class="info-row"><span class="ir-key">DJI M300 RTK</span><span class="ir-val" style="color:var(--gold)">Principal</span></div>
          <div class="info-row"><span class="ir-key">DJI M30T</span><span class="ir-val" style="color:var(--gold)">Principal</span></div>
          <div class="info-row"><span class="ir-key">DJI M350 RTK</span><span class="ir-val" style="color:var(--text3)">Secundário</span></div>
        </div>
        <div class="info-card">
          <div class="info-card-title">Áreas de interesse</div>
          <div class="info-row"><span class="ir-key">Desenvolvimento Web</span><span class="ir-val" style="color:var(--green)">✓</span></div>
          <div class="info-row"><span class="ir-key">Análise de Dados</span><span class="ir-val" style="color:var(--green)">✓</span></div>
          <div class="info-row"><span class="ir-key">Sistemas RPAS</span><span class="ir-val" style="color:var(--green)">✓</span></div>
          <div class="info-row"><span class="ir-key">Visão Computacional</span><span class="ir-val" style="color:var(--blue)">Em estudo</span></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- HABILIDADES -->
<section id="habilidades">
  <div class="section-wrap">
    <div class="section-label">Habilidades</div>
    <div class="section-title">O que eu faço</div>
    <p class="section-sub">Combinação única de expertise operacional em ambientes críticos com desenvolvimento de software aplicado ao setor.</p>
    <div class="skills-grid reveal">
      <div class="skill-card">
        <div class="skill-card-icon">🛸</div>
        <div class="skill-card-title">Operações RPAS Offshore</div>
        <div class="skill-card-sub">Pilotagem de drones em plataformas offshore, planejamento regulatório e gestão de missões críticas.</div>
        <div class="skill-tags">
          <span class="sk-tag">DJI M300 RTK</span><span class="sk-tag">M30T</span><span class="sk-tag">SARPAS</span><span class="sk-tag">ANAC</span><span class="sk-tag">DECEA</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-card-icon">💻</div>
        <div class="skill-card-title">Desenvolvimento Web</div>
        <div class="skill-card-sub">Criação de aplicações web focadas em operações industriais, dashboards e ferramentas para óleo e gás.</div>
        <div class="skill-tags">
          <span class="sk-tag">HTML</span><span class="sk-tag">CSS</span><span class="sk-tag">JavaScript</span><span class="sk-tag">React</span><span class="sk-tag">Git</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-card-icon">🐍</div>
        <div class="skill-card-title">Back-end & APIs</div>
        <div class="skill-card-sub">Desenvolvimento de APIs REST em Python com FastAPI, integração com serviços externos e automação de processos.</div>
        <div class="skill-tags">
          <span class="sk-tag">Python</span><span class="sk-tag">FastAPI</span><span class="sk-tag">REST API</span><span class="sk-tag">HTTPX</span><span class="sk-tag">Pydantic</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-card-icon">📊</div>
        <div class="skill-card-title">Análise de Dados</div>
        <div class="skill-card-sub">Visualização e análise de dados operacionais, geração de relatórios e extração de insights de missões RPAS.</div>
        <div class="skill-tags">
          <span class="sk-tag">CSV/Excel</span><span class="sk-tag">Chart.js</span><span class="sk-tag">Leaflet.js</span><span class="sk-tag">Meteo API</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-card-icon">📋</div>
        <div class="skill-card-title">Compliance Regulatório</div>
        <div class="skill-card-sub">Conhecimento profundo da regulamentação ANAC, DECEA e procedimentos SARPAS para operações RPAS no Brasil.</div>
        <div class="skill-tags">
          <span class="sk-tag">RBAC-E 94</span><span class="sk-tag">ICA 100-40</span><span class="sk-tag">SISANT</span><span class="sk-tag">NR-34</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-card-icon">🗺️</div>
        <div class="skill-card-title">Cartografia & Fotogrametria</div>
        <div class="skill-card-sub">Planejamento de missões de mapeamento, processamento de imagens aéreas e geração de ortofotos.</div>
        <div class="skill-tags">
          <span class="sk-tag">Pix4D</span><span class="sk-tag">DroneDeploy</span><span class="sk-tag">RTK GPS</span><span class="sk-tag">Termografia</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROJETOS -->
<section id="projetos">
  <div class="section-wrap">
    <div class="section-label">Portfólio</div>
    <div class="section-title">Projetos desenvolvidos</div>
    <p class="section-sub">Aplicações reais criadas para resolver problemas que vivo no dia a dia como piloto offshore. Cada projeto nasce de uma necessidade operacional concreta.</p>

    <div class="proj-filter">
      <button class="pf-btn active" data-filter="all">Todos</button>
      <button class="pf-btn" data-filter="frontend">Front-end</button>
      <button class="pf-btn" data-filter="backend">Back-end</button>
      <button class="pf-btn" data-filter="saas">SaaS</button>
    </div>

    <div class="projects-grid" id="proj-grid">

      <!-- DESTAQUE: PLATAFORMA SAAS -->
      <div class="proj-card proj-featured" data-cat="saas frontend">
        <div class="proj-card-body">
          <div class="proj-featured-badge">⭐ PROJETO DESTAQUE</div>
          <div class="proj-title">Plataforma de Gestão RPAS</div>
          <p class="proj-desc">SaaS completo de gestão operacional para frotas de drones offshore. Autenticação multi-perfil, 8 módulos (missões, frota, manutenção, compliance, kanban, relatórios), alertas em tempo real e exportação CSV.</p>
          <div class="proj-stack">
            <span class="ps-tag">HTML</span><span class="ps-tag">CSS</span><span class="ps-tag">JavaScript</span><span class="ps-tag">LocalStorage</span><span class="ps-tag">SaaS</span>
          </div>
          <div class="proj-highlights">
            <div class="ph-item">Login com 3 perfis — Piloto, Gerente, Compliance</div>
            <div class="ph-item">Gestão de frota com alertas automáticos de manutenção</div>
            <div class="ph-item">Kanban de tarefas operacionais integrado</div>
            <div class="ph-item">Compliance regulatório com rastreio de vencimentos</div>
          </div>
        </div>

        <!-- PREVIEW SVG DO APP -->
        <div class="proj-featured-preview" style="padding:0;overflow:hidden;background:#080c10">
          <svg viewBox="0 0 420 280" xmlns="http://www.w3.org/2000/svg" style="width:100%;height:100%;display:block">
            <defs>
              <linearGradient id="goldG" x1="0%" y1="0%" x2="100%" y2="0%">
                <stop offset="0%" style="stop-color:#e8a020"/>
                <stop offset="100%" style="stop-color:#f5b830"/>
              </linearGradient>
              <linearGradient id="greenG" x1="0%" y1="0%" x2="100%" y2="0%">
                <stop offset="0%" style="stop-color:#22c55e"/>
                <stop offset="100%" style="stop-color:#4ade80"/>
              </linearGradient>
            </defs>

            <!-- BG -->
            <rect width="420" height="280" fill="#080c10"/>

            <!-- SIDEBAR -->
            <rect x="0" y="0" width="72" height="280" fill="#0d1f3c" rx="0"/>
            <!-- logo -->
            <rect x="14" y="14" width="22" height="22" rx="5" fill="#e8a020"/>
            <text x="25" y="29" text-anchor="middle" fill="#000" font-size="10" font-weight="700" font-family="monospace">🛰</text>
            <!-- nav items -->
            <rect x="10" y="48" width="52" height="18" rx="4" fill="rgba(232,160,32,0.15)"/>
            <text x="36" y="60" text-anchor="middle" fill="#e8a020" font-size="7" font-family="sans-serif" font-weight="600">Dashboard</text>
            <rect x="10" y="70" width="52" height="18" rx="4" fill="transparent"/>
            <text x="36" y="82" text-anchor="middle" fill="#4d6480" font-size="7" font-family="sans-serif">Missões</text>
            <rect x="10" y="92" width="52" height="18" rx="4" fill="transparent"/>
            <text x="36" y="104" text-anchor="middle" fill="#4d6480" font-size="7" font-family="sans-serif">Frota</text>
            <rect x="10" y="114" width="52" height="18" rx="4" fill="transparent"/>
            <text x="36" y="126" text-anchor="middle" fill="#4d6480" font-size="7" font-family="sans-serif">Manutenção</text>
            <rect x="10" y="136" width="52" height="18" rx="4" fill="transparent"/>
            <text x="36" y="148" text-anchor="middle" fill="#4d6480" font-size="7" font-family="sans-serif">Compliance</text>
            <rect x="10" y="158" width="52" height="18" rx="4" fill="transparent"/>
            <text x="36" y="170" text-anchor="middle" fill="#4d6480" font-size="7" font-family="sans-serif">Tarefas</text>
            <!-- avatar footer -->
            <circle cx="36" cy="258" r="12" fill="url(#goldG)"/>
            <text x="36" y="262" text-anchor="middle" fill="#000" font-size="8" font-weight="700" font-family="sans-serif">WO</text>

            <!-- TOPBAR -->
            <rect x="72" y="0" width="348" height="32" fill="#0a1628"/>
            <text x="84" y="20" fill="#e8eef5" font-size="9" font-weight="700" font-family="sans-serif">Dashboard</text>
            <!-- live pill -->
            <rect x="360" y="9" width="48" height="14" rx="7" fill="rgba(34,197,94,0.15)"/>
            <circle cx="368" cy="16" r="3" fill="#22c55e"/>
            <text x="380" y="20" fill="#22c55e" font-size="7" font-family="sans-serif" font-weight="600">LIVE</text>
            <!-- time -->
            <text x="330" y="20" fill="#4d6480" font-size="7" font-family="monospace">14:38:22</text>

            <!-- METRIC CARDS -->
            <!-- card 1 -->
            <rect x="82" y="40" width="72" height="44" rx="5" fill="#111827" stroke="rgba(255,255,255,0.07)" stroke-width="1"/>
            <rect x="82" y="40" width="72" height="2" rx="1" fill="#e8a020"/>
            <text x="92" y="53" fill="#4d6480" font-size="6" font-family="sans-serif" font-weight="700">AERONAVES</text>
            <text x="92" y="68" fill="#e8eef5" font-size="16" font-weight="700" font-family="monospace">5</text>
            <text x="92" y="78" fill="#4d6480" font-size="6" font-family="sans-serif">3 disponíveis</text>
            <!-- card 2 -->
            <rect x="160" y="40" width="72" height="44" rx="5" fill="#111827" stroke="rgba(255,255,255,0.07)" stroke-width="1"/>
            <rect x="160" y="40" width="72" height="2" rx="1" fill="#60a5fa"/>
            <text x="170" y="53" fill="#4d6480" font-size="6" font-family="sans-serif" font-weight="700">EM VOO</text>
            <text x="170" y="68" fill="#e8eef5" font-size="16" font-weight="700" font-family="monospace">1</text>
            <text x="170" y="78" fill="#4d6480" font-size="6" font-family="sans-serif">operando</text>
            <!-- card 3 -->
            <rect x="238" y="40" width="72" height="44" rx="5" fill="#111827" stroke="rgba(255,255,255,0.07)" stroke-width="1"/>
            <rect x="238" y="40" width="72" height="2" rx="1" fill="#22c55e"/>
            <text x="248" y="53" fill="#4d6480" font-size="6" font-family="sans-serif" font-weight="700">HORAS VOO</text>
            <text x="248" y="68" fill="#e8eef5" font-size="16" font-weight="700" font-family="monospace">1247h</text>
            <text x="248" y="78" fill="#4d6480" font-size="6" font-family="sans-serif">acumulado</text>
            <!-- card 4 -->
            <rect x="316" y="40" width="94" height="44" rx="5" fill="#111827" stroke="rgba(255,255,255,0.07)" stroke-width="1"/>
            <rect x="316" y="40" width="94" height="2" rx="1" fill="#f87171"/>
            <text x="326" y="53" fill="#4d6480" font-size="6" font-family="sans-serif" font-weight="700">ALERTAS</text>
            <text x="326" y="68" fill="#e8eef5" font-size="16" font-weight="700" font-family="monospace">3</text>
            <text x="326" y="78" fill="#4d6480" font-size="6" font-family="sans-serif">2 docs · 1 aero</text>

            <!-- TABELA MISSÕES -->
            <rect x="82" y="92" width="220" height="110" rx="5" fill="#111827" stroke="rgba(255,255,255,0.07)" stroke-width="1"/>
            <text x="92" y="106" fill="#4d6480" font-size="6" font-weight="700" font-family="sans-serif">MISSÕES RECENTES</text>
            <!-- header row -->
            <rect x="82" y="110" width="220" height="14" fill="rgba(255,255,255,0.03)"/>
            <text x="92" y="120" fill="#4d6480" font-size="5.5" font-family="sans-serif" font-weight="700">ID</text>
            <text x="118" y="120" fill="#4d6480" font-size="5.5" font-family="sans-serif" font-weight="700">AERONAVE</text>
            <text x="168" y="120" fill="#4d6480" font-size="5.5" font-family="sans-serif" font-weight="700">LOCAL</text>
            <text x="238" y="120" fill="#4d6480" font-size="5.5" font-family="sans-serif" font-weight="700">STATUS</text>
            <!-- rows -->
            <text x="92" y="133" fill="#e8a020" font-size="6" font-family="monospace">M001</text>
            <text x="118" y="133" fill="#8ca0b8" font-size="6" font-family="sans-serif">ALPHA-02</text>
            <text x="168" y="133" fill="#8ca0b8" font-size="6" font-family="sans-serif">P-76 Campos</text>
            <rect x="238" y="126" width="40" height="10" rx="5" fill="rgba(96,165,250,0.15)"/>
            <text x="258" y="134" text-anchor="middle" fill="#60a5fa" font-size="5.5" font-family="sans-serif" font-weight="700">Em andamento</text>

            <line x1="82" y1="140" x2="302" y2="140" stroke="rgba(255,255,255,0.04)" stroke-width="1"/>
            <text x="92" y="152" fill="#e8a020" font-size="6" font-family="monospace">M002</text>
            <text x="118" y="152" fill="#8ca0b8" font-size="6" font-family="sans-serif">ALPHA-01</text>
            <text x="168" y="152" fill="#8ca0b8" font-size="6" font-family="sans-serif">P-52 Santos</text>
            <rect x="238" y="145" width="36" height="10" rx="5" fill="rgba(34,197,94,0.15)"/>
            <text x="256" y="153" text-anchor="middle" fill="#22c55e" font-size="5.5" font-family="sans-serif" font-weight="700">Concluída</text>

            <line x1="82" y1="158" x2="302" y2="158" stroke="rgba(255,255,255,0.04)" stroke-width="1"/>
            <text x="92" y="170" fill="#e8a020" font-size="6" font-family="monospace">M003</text>
            <text x="118" y="170" fill="#8ca0b8" font-size="6" font-family="sans-serif">BRAVO-02</text>
            <text x="168" y="170" fill="#8ca0b8" font-size="6" font-family="sans-serif">FPSO Itajaí</text>
            <rect x="238" y="163" width="36" height="10" rx="5" fill="rgba(34,197,94,0.15)"/>
            <text x="256" y="171" text-anchor="middle" fill="#22c55e" font-size="5.5" font-family="sans-serif" font-weight="700">Concluída</text>

            <line x1="82" y1="177" x2="302" y2="177" stroke="rgba(255,255,255,0.04)" stroke-width="1"/>
            <text x="92" y="189" fill="#e8a020" font-size="6" font-family="monospace">M004</text>
            <text x="118" y="189" fill="#8ca0b8" font-size="6" font-family="sans-serif">CHARLIE-01</text>
            <text x="168" y="189" fill="#8ca0b8" font-size="6" font-family="sans-serif">P-66 Campos</text>
            <rect x="238" y="182" width="30" height="10" rx="5" fill="rgba(248,113,113,0.15)"/>
            <text x="253" y="190" text-anchor="middle" fill="#f87171" font-size="5.5" font-family="sans-serif" font-weight="700">Abortada</text>

            <!-- FEED OPERACIONAL -->
            <rect x="308" y="92" width="102" height="110" rx="5" fill="#111827" stroke="rgba(255,255,255,0.07)" stroke-width="1"/>
            <text x="318" y="106" fill="#4d6480" font-size="6" font-weight="700" font-family="sans-serif">FEED OPERACIONAL</text>
            <!-- alert items -->
            <circle cx="320" cy="118" r="3" fill="#60a5fa"/>
            <text x="327" y="121" fill="#8ca0b8" font-size="5.5" font-family="sans-serif">ALPHA-02 em voo</text>
            <circle cx="320" cy="132" r="3" fill="#f87171"/>
            <text x="327" y="135" fill="#8ca0b8" font-size="5.5" font-family="sans-serif">Seguro VENCIDO</text>
            <circle cx="320" cy="146" r="3" fill="#d29922"/>
            <text x="327" y="149" fill="#8ca0b8" font-size="5.5" font-family="sans-serif">SISANT vence 15d</text>
            <circle cx="320" cy="160" r="3" fill="#f87171"/>
            <text x="327" y="163" fill="#8ca0b8" font-size="5.5" font-family="sans-serif">CHARLIE-01 alerta</text>
            <circle cx="320" cy="174" r="3" fill="#22c55e"/>
            <text x="327" y="177" fill="#8ca0b8" font-size="5.5" font-family="sans-serif">Missão M006 plan.</text>

            <!-- GRÁFICO HORAS -->
            <rect x="82" y="210" width="100" height="62" rx="5" fill="#111827" stroke="rgba(255,255,255,0.07)" stroke-width="1"/>
            <text x="92" y="224" fill="#4d6480" font-size="6" font-weight="700" font-family="sans-serif">HORAS DE VOO</text>
            <!-- bars -->
            <rect x="92"  y="260" width="10" height="20" rx="2" fill="#e8a020" opacity="0.4"/>
            <rect x="106" y="252" width="10" height="28" rx="2" fill="#e8a020" opacity="0.5"/>
            <rect x="120" y="245" width="10" height="35" rx="2" fill="#e8a020" opacity="0.65"/>
            <rect x="134" y="250" width="10" height="30" rx="2" fill="#e8a020" opacity="0.55"/>
            <rect x="148" y="240" width="10" height="40" rx="2" fill="#e8a020" opacity="0.8"/>
            <rect x="162" y="234" width="10" height="46" rx="2" fill="url(#goldG)"/>
            <text x="92"  y="278" fill="#4d6480" font-size="5" font-family="sans-serif">jan</text>
            <text x="106" y="278" fill="#4d6480" font-size="5" font-family="sans-serif">fev</text>
            <text x="120" y="278" fill="#4d6480" font-size="5" font-family="sans-serif">mar</text>
            <text x="134" y="278" fill="#4d6480" font-size="5" font-family="sans-serif">abr</text>
            <text x="148" y="278" fill="#4d6480" font-size="5" font-family="sans-serif">mai</text>
            <text x="162" y="278" fill="#4d6480" font-size="5" font-family="sans-serif">jun</text>

            <!-- STATUS FROTA -->
            <rect x="188" y="210" width="114" height="62" rx="5" fill="#111827" stroke="rgba(255,255,255,0.07)" stroke-width="1"/>
            <text x="198" y="224" fill="#4d6480" font-size="6" font-weight="700" font-family="sans-serif">STATUS DA FROTA</text>
            <text x="198" y="237" fill="#8ca0b8" font-size="6" font-family="sans-serif">Disponível</text>
            <rect x="238" y="231" width="54" height="5" rx="2.5" fill="rgba(255,255,255,0.06)"/>
            <rect x="238" y="231" width="36" height="5" rx="2.5" fill="#22c55e"/>
            <text x="198" y="250" fill="#8ca0b8" font-size="6" font-family="sans-serif">Em voo</text>
            <rect x="238" y="244" width="54" height="5" rx="2.5" fill="rgba(255,255,255,0.06)"/>
            <rect x="238" y="244" width="11" height="5" rx="2.5" fill="#60a5fa"/>
            <text x="198" y="263" fill="#8ca0b8" font-size="6" font-family="sans-serif">Manutenção</text>
            <rect x="238" y="257" width="54" height="5" rx="2.5" fill="rgba(255,255,255,0.06)"/>
            <rect x="238" y="257" width="11" height="5" rx="2.5" fill="#d29922"/>
            <text x="198" y="276" fill="#8ca0b8" font-size="6" font-family="sans-serif">Alerta</text>
            <rect x="238" y="270" width="54" height="5" rx="2.5" fill="rgba(255,255,255,0.06)"/>
            <rect x="238" y="270" width="11" height="5" rx="2.5" fill="#f87171"/>

            <!-- COMPLIANCE -->
            <rect x="308" y="210" width="102" height="62" rx="5" fill="#111827" stroke="rgba(255,255,255,0.07)" stroke-width="1"/>
            <text x="318" y="224" fill="#4d6480" font-size="6" font-weight="700" font-family="sans-serif">COMPLIANCE</text>
            <text x="318" y="237" fill="#8ca0b8" font-size="5.5" font-family="sans-serif">Seguro operação</text>
            <text x="390" y="237" text-anchor="end" fill="#f87171" font-size="5.5" font-family="monospace" font-weight="700">VENCIDO</text>
            <text x="318" y="249" fill="#8ca0b8" font-size="5.5" font-family="sans-serif">SISANT ALPHA-02</text>
            <text x="390" y="249" text-anchor="end" fill="#d29922" font-size="5.5" font-family="monospace">15d</text>
            <text x="318" y="261" fill="#8ca0b8" font-size="5.5" font-family="sans-serif">Hab. ANAC William</text>
            <text x="390" y="261" text-anchor="end" fill="#22c55e" font-size="5.5" font-family="monospace">365d</text>
            <text x="318" y="273" fill="#8ca0b8" font-size="5.5" font-family="sans-serif">Cert. DECEA</text>
            <text x="390" y="273" text-anchor="end" fill="#22c55e" font-size="5.5" font-family="monospace">275d</text>
          </svg>
        </div>

        <div class="proj-card-footer" style="grid-column:1/-1">
          <button class="btn-proj btn-proj-ghost" onclick="abrirModal('saas')">Ver detalhes</button>
          <a href="https://github.com/TheDevOffshore" target="_blank" class="btn-proj btn-proj-primary">GitHub →</a>
        </div>
      </div>

      <!-- DASHBOARD FROTA -->
      <div class="proj-card" data-cat="frontend saas">
        <div class="proj-card-top">
          <div class="proj-icon">🗺️</div>
          <span class="proj-level pl-mid">Intermediário</span>
        </div>
        <div class="proj-card-body">
          <div class="proj-title">Dashboard de Frota RPAS</div>
          <p class="proj-desc">Painel com mapa interativo (Leaflet.js) mostrando plataformas offshore, status da frota em tempo real, gráficos e alertas de manutenção.</p>
          <div class="proj-stack">
            <span class="ps-tag">JavaScript</span><span class="ps-tag">Leaflet.js</span><span class="ps-tag">CSS Grid</span>
          </div>
          <div class="proj-highlights">
            <div class="ph-item">Mapa com P-76, P-52, P-66 e bases</div>
            <div class="ph-item">Donut chart + gráfico de horas por mês</div>
            <div class="ph-item">CRUD completo de aeronaves e missões</div>
          </div>
        </div>
        <div class="proj-card-footer">
          <button class="btn-proj btn-proj-ghost" onclick="abrirModal('dashboard')">Ver detalhes</button>
          <a href="https://github.com/TheDevOffshore" target="_blank" class="btn-proj btn-proj-primary">GitHub →</a>
        </div>
      </div>

      <!-- API METEO -->
      <div class="proj-card" data-cat="backend">
        <div class="proj-card-top">
          <div class="proj-icon">🌊</div>
          <span class="proj-level pl-adv">Avançado</span>
        </div>
        <div class="proj-card-body">
          <div class="proj-title">API de Condições Meteo para Voo</div>
          <p class="proj-desc">API REST em Python/FastAPI que consulta dados meteorológicos em tempo real e avalia aptidão de voo RPAS com limites operacionais por modelo de aeronave.</p>
          <div class="proj-stack">
            <span class="ps-tag">Python</span><span class="ps-tag">FastAPI</span><span class="ps-tag">Open-Meteo</span><span class="ps-tag">HTTPX</span>
          </div>
          <div class="proj-highlights">
            <div class="ph-item">7 endpoints REST documentados no Swagger</div>
            <div class="ph-item">Limites operacionais reais do M300 RTK e M30T</div>
            <div class="ph-item">Plataformas P-76, P-52, FPSO pré-configuradas</div>
          </div>
        </div>
        <div class="proj-card-footer">
          <button class="btn-proj btn-proj-ghost" onclick="abrirModal('api')">Ver detalhes</button>
          <a href="https://github.com/TheDevOffshore" target="_blank" class="btn-proj btn-proj-primary">GitHub →</a>
        </div>
      </div>

      <!-- GERADOR SARPAS -->
      <div class="proj-card" data-cat="frontend">
        <div class="proj-card-top">
          <div class="proj-icon">📄</div>
          <span class="proj-level pl-mid">Intermediário</span>
        </div>
        <div class="proj-card-body">
          <div class="proj-title">Gerador de Relatórios SARPAS</div>
          <p class="proj-desc">App web para preenchimento e geração de relatórios operacionais no formato exigido pelo DECEA/SARPAS, com pré-visualização em tempo real do documento oficial.</p>
          <div class="proj-stack">
            <span class="ps-tag">HTML</span><span class="ps-tag">CSS</span><span class="ps-tag">JavaScript</span><span class="ps-tag">CSS Print</span>
          </div>
          <div class="proj-highlights">
            <div class="ph-item">Preview ao vivo do documento oficial DECEA</div>
            <div class="ph-item">Exportação CSV + impressão para PDF</div>
            <div class="ph-item">Waypoints de rota e histórico local</div>
          </div>
        </div>
        <div class="proj-card-footer">
          <button class="btn-proj btn-proj-ghost" onclick="abrirModal('sarpas')">Ver detalhes</button>
          <a href="https://github.com/TheDevOffshore" target="_blank" class="btn-proj btn-proj-primary">GitHub →</a>
        </div>
      </div>

      <!-- CHECKLIST -->
      <div class="proj-card" data-cat="frontend">
        <div class="proj-card-top">
          <div class="proj-icon">✅</div>
          <span class="proj-level pl-init">Iniciante</span>
        </div>
        <div class="proj-card-body">
          <div class="proj-title">Checklist Pré-Voo Interativo</div>
          <p class="proj-desc">App de checklist digital para operações offshore com 41 itens em 6 seções, itens críticos destacados, aprovação digital e histórico persistente.</p>
          <div class="proj-stack">
            <span class="ps-tag">HTML</span><span class="ps-tag">CSS</span><span class="ps-tag">JavaScript</span>
          </div>
          <div class="proj-highlights">
            <div class="ph-item">41 itens baseados em procedimentos reais</div>
            <div class="ph-item">Aprovação com assinatura digital</div>
            <div class="ph-item">Exportação CSV por sessão</div>
          </div>
        </div>
        <div class="proj-card-footer">
          <button class="btn-proj btn-proj-ghost" onclick="abrirModal('checklist')">Ver detalhes</button>
          <a href="https://github.com/TheDevOffshore" target="_blank" class="btn-proj btn-proj-primary">GitHub →</a>
        </div>
      </div>

      <!-- LOG MISSOES -->
      <div class="proj-card" data-cat="frontend">
        <div class="proj-card-top">
          <div class="proj-icon">📋</div>
          <span class="proj-level pl-init">Iniciante</span>
        </div>
        <div class="proj-card-body">
          <div class="proj-title">Log de Missões RPAS</div>
          <p class="proj-desc">App web para registro e visualização de missões de drone offshore com métricas, filtros, busca em tempo real e exportação CSV.</p>
          <div class="proj-stack">
            <span class="ps-tag">HTML</span><span class="ps-tag">CSS</span><span class="ps-tag">JavaScript</span><span class="ps-tag">LocalStorage</span>
          </div>
          <div class="proj-highlights">
            <div class="ph-item">Dashboard com 4 métricas operacionais</div>
            <div class="ph-item">Filtros por status e aeronave</div>
            <div class="ph-item">Sem servidor — roda offline</div>
          </div>
        </div>
        <div class="proj-card-footer">
          <button class="btn-proj btn-proj-ghost" onclick="abrirModal('log')">Ver detalhes</button>
          <a href="https://github.com/TheDevOffshore" target="_blank" class="btn-proj btn-proj-primary">GitHub →</a>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- EXPERIÊNCIA -->
<section id="experiencia">
  <div class="section-wrap">
    <div class="section-label">Trajetória</div>
    <div class="section-title">Experiência profissional</div>
    <div class="exp-grid reveal">
      <div>
        <div class="exp-col-title">Operações RPAS</div>
        <div class="exp-item">
          <div class="exp-company">Empresa Offshore</div>
          <div class="exp-role">Piloto de RPAS Offshore — Técnico de Operações Contínuas</div>
          <div class="exp-period">2022 → Presente</div>
          <ul class="exp-desc">
            <li>Operação de DJI M300 RTK e M30T em plataformas offshore (P-76, P-52, P-66, FPSO)</li>
            <li>Planejamento e execução de missões de inspeção estrutural e termografia</li>
            <li>Gestão de autorizações SARPAS e comunicação com DECEA</li>
            <li>Elaboração de SOPs e documentação operacional</li>
            <li>Conformidade com ANAC RBAC-E 94 e NR-34</li>
          </ul>
        </div>
      </div>
      <div>
        <div class="exp-col-title">Desenvolvimento</div>
        <div class="exp-item">
          <div class="exp-company">Projetos Próprios</div>
          <div class="exp-role">Desenvolvedor — Foco em Oil & Gas / RPAS</div>
          <div class="exp-period">2024 → Presente</div>
          <ul class="exp-desc">
            <li>6 projetos web completos voltados para o setor offshore</li>
            <li>API REST em Python/FastAPI integrada com Open-Meteo</li>
            <li>SaaS de gestão operacional com múltiplos módulos</li>
            <li>Dashboards com mapas interativos (Leaflet.js)</li>
            <li>Sistemas de compliance regulatório ANAC/DECEA</li>
          </ul>
        </div>
        <div class="exp-item">
          <div class="exp-company">Formação Contínua</div>
          <div class="exp-role">Autodidata — Desenvolvimento & Análise de Dados</div>
          <div class="exp-period">2023 → Presente</div>
          <ul class="exp-desc">
            <li>HTML, CSS, JavaScript — projetos aplicados</li>
            <li>Python, FastAPI, APIs REST</li>
            <li>Plano de 12 meses de integração com IA (YOLOv8, Roboflow)</li>
            <li>Roadmap FAA Part 107, EASA e certificações internacionais</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CERTIFICAÇÕES -->
<section id="certificacoes">
  <div class="section-wrap">
    <div class="section-label">Certificações</div>
    <div class="section-title">Qualificações & Certificados</div>
    <div class="certs-grid reveal">
      <div class="cert-card">
        <div class="cert-icon">🏛️</div>
        <div><div class="cert-name">Habilitação ANAC</div><div class="cert-org">Agência Nacional de Aviação Civil</div><div class="cert-status cs-ativo">Ativo</div></div>
      </div>
      <div class="cert-card">
        <div class="cert-icon">📡</div>
        <div><div class="cert-name">Certificado DECEA</div><div class="cert-org">Departamento de Controle do Espaço Aéreo</div><div class="cert-status cs-ativo">Ativo</div></div>
      </div>
      <div class="cert-card">
        <div class="cert-icon">🛸</div>
        <div><div class="cert-name">DJI Enterprise</div><div class="cert-org">DJI — M300 RTK · M30T · M350 RTK</div><div class="cert-status cs-ativo">Ativo</div></div>
      </div>
      <div class="cert-card">
        <div class="cert-icon">🦺</div>
        <div><div class="cert-name">NR-34 Offshore</div><div class="cert-org">Trabalho em embarcações e plataformas</div><div class="cert-status cs-ativo">Ativo</div></div>
      </div>
      <div class="cert-card">
        <div class="cert-icon">🇺🇸</div>
        <div><div class="cert-name">FAA Part 107</div><div class="cert-org">Federal Aviation Administration — EUA</div><div class="cert-status cs-previsto">Previsto 2025</div></div>
      </div>
      <div class="cert-card">
        <div class="cert-icon">🌡️</div>
        <div><div class="cert-name">Termografia RPAS</div><div class="cert-org">Inspeção termográfica com drones</div><div class="cert-status cs-previsto">Em estudo</div></div>
      </div>
      <div class="cert-card">
        <div class="cert-icon">🗺️</div>
        <div><div class="cert-name">Pix4D / DroneDeploy</div><div class="cert-org">Processamento fotogramétrico</div><div class="cert-status cs-previsto">Em estudo</div></div>
      </div>
      <div class="cert-card">
        <div class="cert-icon">🇪🇺</div>
        <div><div class="cert-name">EASA — Open A2</div><div class="cert-org">Agência Europeia de Segurança Aérea</div><div class="cert-status cs-previsto">Roadmap 2026</div></div>
      </div>
    </div>
  </div>
</section>

<!-- CONTATO -->
<section id="contato">
  <div class="section-wrap">
    <div class="contato-wrap reveal">
      <div class="section-label" style="text-align:center;justify-content:center;display:flex">Contato</div>
      <div class="contato-title">Vamos trabalhar juntos?</div>
      <p class="contato-sub">Seja para uma oportunidade em desenvolvimento, análise de dados, operações RPAS ou qualquer interseção entre tecnologia e o setor offshore — estou disponível para conversar.</p>
      <div class="contato-links">
        <a href="https://linkedin.com/in/wmdevoffshore" target="_blank" class="contato-link cl-linkedin">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
          LinkedIn
        </a>
        <a href="https://github.com/TheDevOffshore" target="_blank" class="contato-link cl-github">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 00-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0020 4.77 5.07 5.07 0 0019.91 1S18.73.65 16 2.48a13.38 13.38 0 00-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 005 4.77a5.44 5.44 0 00-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 009 18.13V22"/></svg>
          GitHub
        </a>
        <a href="https://mail.google.com/mail/?view=cm&to=contato@wmdev.offshore" target="_blank" class="contato-link cl-email">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
          E-mail
        </a>
      </div>
      <div class="contato-note">
        <strong>Áreas de interesse:</strong> desenvolvimento front-end ou full-stack, análise de dados, consultor técnico RPAS, e oportunidades no setor de óleo e gás que envolvam tecnologia. Aberto a trabalho remoto e híbrido.
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-left">
    WD.dev — William Oliveira · TheDevOffshore
  </div>
  <div class="footer-right">Feito com HTML, CSS e JS · 2026</div>
</footer>

<!-- MODAL DETALHES PROJETO -->
<div class="proj-modal-overlay" id="proj-modal">
  <div class="proj-modal">
    <div class="pm-header">
      <div class="pm-title" id="pm-title">—</div>
      <button class="pm-close" onclick="fecharModal()">×</button>
    </div>
    <div class="pm-body" id="pm-body"></div>
    <div class="pm-footer" id="pm-footer"></div>
  </div>
</div>

<script>
// ── FILTRO PROJETOS ───────────────────────────────────────────────
document.querySelectorAll('.pf-btn').forEach(btn=>{
  btn.addEventListener('click',()=>{
    document.querySelectorAll('.pf-btn').forEach(b=>b.classList.remove('active'));
    btn.classList.add('active');
    const filter=btn.dataset.filter;
    document.querySelectorAll('.proj-card').forEach(card=>{
      const cat=card.dataset.cat||'';
      const show=filter==='all'||cat.includes(filter);
      card.style.display=show?'flex':'none';
    });
  });
});

// ── SCROLL REVEAL ────────────────────────────────────────────────
const observer=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting)e.target.classList.add('visible')});
},{threshold:.1});
document.querySelectorAll('.reveal').forEach(el=>observer.observe(el));

// ── MODAL PROJETOS ────────────────────────────────────────────────
const PROJ_DATA={
  saas:{
    title:'Plataforma de Gestão RPAS',
    desc:'SaaS completo de gestão operacional para frotas de drones em ambientes offshore. A motivação foi resolver o problema real da gestão fragmentada em planilhas Excel que acontece em operações offshore.',
    problem:'A gestão de frotas RPAS offshore hoje depende de planilhas descentralizadas, sem visibilidade consolidada de status de aeronaves, compliance regulatório, manutenções e missões.',
    solution:'Plataforma web completa com 8 módulos integrados: Dashboard, Missões, Frota, Manutenção, Compliance, Equipe, Tarefas e Relatórios.',
    stack:'HTML5 · CSS3 · JavaScript ES6+ · LocalStorage · Space Grotesk · JetBrains Mono',
    features:['Login com 3 perfis — Piloto, Gerente e Compliance','Dashboard com métricas ao vivo e feed operacional','Gestão de frota com alertas automáticos de manutenção','Compliance com rastreio de vencimentos ANAC/SISANT','Kanban de tarefas operacionais','Exportação CSV de missões, frota e compliance'],
    github:'https://github.com/TheDevOffshore',
  },
  dashboard:{
    title:'Dashboard de Frota RPAS',
    desc:'Painel de gestão e monitoramento de frotas de drones com mapa interativo das plataformas offshore, gráficos de desempenho e alertas de manutenção.',
    problem:'Falta de visibilidade centralizada do status operacional da frota em tempo real.',
    solution:'Dashboard com mapa Leaflet.js mostrando plataformas reais (P-76, P-52, P-66), status de cada aeronave, gráficos de horas por mês e alertas automáticos.',
    stack:'HTML5 · CSS3 · JavaScript · Leaflet.js 1.9.4 · CartoDB Dark Tiles',
    features:['Mapa interativo com 7 locais offshore reais','Status ao vivo: disponível, em voo, manutenção, alerta','Gráfico de horas de voo — 6 meses','Donut chart de distribuição da frota','CRUD completo de aeronaves e missões','Alertas de manutenção com badge de urgência'],
    github:'https://github.com/TheDevOffshore',
  },
  api:{
    title:'API de Condições Meteo para Voo',
    desc:'API REST em Python com FastAPI que consulta dados meteorológicos em tempo real via Open-Meteo e retorna avaliação automática de aptidão para voo RPAS.',
    problem:'A decisão de voar em condições adversas é crítica. Não existe ferramenta que avalie automaticamente as condições com os limites operacionais específicos de cada aeronave.',
    solution:'API com 7 endpoints que consulta Open-Meteo (gratuito, sem API key), aplica limites reais do M300 RTK e M30T e retorna veredicto: APTO, APTO COM ATENÇÃO ou NÃO APTO.',
    stack:'Python 3.10+ · FastAPI · Uvicorn · HTTPX · Pydantic v2 · Open-Meteo API',
    features:['7 endpoints REST com Swagger automático em /docs','Limites operacionais reais por modelo de aeronave','Plataformas offshore pré-configuradas (P-76, P-52...)','Endpoint /relatorio gera relatório formal em JSON','Front-end web com modo demo sem API','Histórico em memória das últimas 50 avaliações'],
    github:'https://github.com/TheDevOffshore',
  },
  sarpas:{
    title:'Gerador de Relatórios SARPAS',
    desc:'App web para preenchimento e geração de relatórios operacionais no formato exigido pelo DECEA/SARPAS, com pré-visualização do documento oficial em tempo real.',
    problem:'O preenchimento de relatórios SARPAS é manual, demorado e sujeito a erros. Cada campo alterado exige re-impressão do documento.',
    solution:'Formulário em 6 seções com preview ao vivo do documento no formato oficial — cada campo atualiza o relatório instantaneamente.',
    stack:'HTML5 · CSS3 · JavaScript · CSS @media print · LocalStorage',
    features:['Preview em tempo real no formato oficial DECEA','6 seções: identificação, piloto, aeronave, área, meteo, ocorrências','Waypoints de rota ilimitados','Impressão limpa para PDF via browser','Histórico de relatórios com edição posterior','Exportação CSV com todos os campos'],
    github:'https://github.com/TheDevOffshore',
  },
  checklist:{
    title:'Checklist Pré-Voo Interativo',
    desc:'Checklist digital de segurança para operações RPAS offshore com 41 itens em 6 seções, itens críticos destacados, aprovação com assinatura e histórico persistente.',
    problem:'Checklists em papel se perdem, não são auditáveis e não têm alertas para itens críticos não verificados.',
    solution:'App digital com progresso em tempo real, itens críticos em destaque, campo de observação por item e aprovação formal com registro histórico.',
    stack:'HTML5 · CSS3 · JavaScript · LocalStorage',
    features:['41 itens baseados em procedimentos reais offshore','6 seções: documentação, aeronave, baterias, software, meteo, EPI','Itens críticos destacados em vermelho','Botão N/A por item para itens não aplicáveis','Aprovação com assinatura digital','Histórico completo de todas as sessões aprovadas'],
    github:'https://github.com/TheDevOffshore',
  },
  log:{
    title:'Log de Missões RPAS',
    desc:'App web para registro e visualização de missões de drone offshore com dashboard de métricas, filtros por status e aeronave, e exportação CSV.',
    problem:'O registro de missões é feito em papel ou planilhas genéricas, sem visualização de dados históricos e sem busca eficiente.',
    solution:'App com tabela, filtros em tempo real, 4 métricas no topo (total, horas, concluídas, mês) e exportação CSV com encoding UTF-8.',
    stack:'HTML5 · CSS3 · JavaScript · LocalStorage',
    features:['Dashboard com 4 métricas operacionais','Busca em tempo real por qualquer campo','Filtros por status e modelo de aeronave','Modal de detalhe de cada missão','Exportação CSV compatível com Excel PT-BR','Funciona 100% offline — sem servidor'],
    github:'https://github.com/TheDevOffshore',
  },
};

function abrirModal(key){
  const d=PROJ_DATA[key];if(!d)return;
  document.getElementById('pm-title').textContent=d.title;
  document.getElementById('pm-body').innerHTML=`
    <div class="pm-section"><div class="pm-lbl">O problema</div><div class="pm-text">${d.problem}</div></div>
    <div class="pm-section"><div class="pm-lbl">A solução</div><div class="pm-text">${d.solution}</div></div>
    <div class="pm-section"><div class="pm-lbl">Stack utilizada</div><div class="pm-text" style="font-family:var(--mono);font-size:12px;color:var(--gold)">${d.stack}</div></div>
    <div class="pm-section"><div class="pm-lbl">Funcionalidades</div><div class="pm-feat-list">${d.features.map(f=>`<div class="pm-feat">${f}</div>`).join('')}</div></div>
  `;
  document.getElementById('pm-footer').innerHTML=`
    <button class="btn-proj btn-proj-ghost" onclick="fecharModal()" style="flex:0 0 auto;padding:8px 16px">Fechar</button>
    <a href="${d.github}" target="_blank" class="btn-proj btn-proj-primary">Ver no GitHub →</a>
  `;
  document.getElementById('proj-modal').classList.add('open');
}

function fecharModal(){
  document.getElementById('proj-modal').classList.remove('open');
}

document.getElementById('proj-modal').addEventListener('click',function(e){
  if(e.target===this)fecharModal();
});

// ── NAV ACTIVE ────────────────────────────────────────────────────
const sections=document.querySelectorAll('section[id]');
const navLinks=document.querySelectorAll('.nav-links a');
window.addEventListener('scroll',()=>{
  let current='';
  sections.forEach(s=>{
    if(window.scrollY>=s.offsetTop-80)current=s.id;
  });
  navLinks.forEach(a=>{
    a.style.color=a.getAttribute('href')==='#'+current?'var(--gold)':'';
  });
});

// ── RADAR ANIMAÇÃO HERO ───────────────────────────────────────────
// já no CSS, sem JS necessário
</script>
</body>
</html>
