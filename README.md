<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name='impact-site-verification' value='823171f2-d471-4c99-95d5-e3e27491c79c'>
<title>Orbit07 — AI Domain Name Generator</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&family=Space+Grotesk:wght@400;500;600;700&family=DM+Serif+Display&family=Bebas+Neue&family=Montserrat:wght@700;800&family=Poppins:wght@600;700;800&family=Raleway:wght@700;800&family=Nunito:wght@700;800&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#f7f6f3;--white:#fff;--black:#0c0c0c;--ink:#1c1c1e;
  --muted:#737373;--border:#e2dfd9;--chip:#eeecea;
  --accent:#ff4500;--purple:#6d28d9;--green:#059669;
}
html{scroll-behavior:smooth}
body{font-family:'Plus Jakarta Sans',sans-serif;background:var(--bg);color:var(--ink);min-height:100vh;-webkit-font-smoothing:antialiased;overflow-x:hidden}

.mesh{position:fixed;inset:0;pointer-events:none;z-index:0;
  background:radial-gradient(ellipse 55% 45% at 10% 15%,rgba(109,40,217,.11) 0%,transparent 65%),
    radial-gradient(ellipse 50% 55% at 90% 10%,rgba(255,69,0,.09) 0%,transparent 65%),
    radial-gradient(ellipse 60% 35% at 50% 95%,rgba(5,150,105,.07) 0%,transparent 65%),#f7f6f3}

.fe{position:fixed;pointer-events:none;z-index:1;user-select:none;opacity:.4;animation:flt 7s ease-in-out infinite}
@keyframes flt{0%,100%{transform:translateY(0) rotate(0deg)}50%{transform:translateY(-14px) rotate(5deg)}}
.fe1{font-size:24px;top:12%;left:4%;animation-delay:0s}
.fe2{font-size:20px;top:28%;right:6%;animation-delay:1.8s}
.fe3{font-size:18px;top:58%;left:2%;animation-delay:3.2s}
.fe4{font-size:24px;bottom:28%;right:3%;animation-delay:1s}
.fe5{font-size:20px;bottom:14%;left:7%;animation-delay:2.5s}
@media(max-width:640px){.fe{display:none}}

nav{display:flex;justify-content:space-between;align-items:center;padding:0 32px;height:56px;
  background:rgba(247,246,243,.9);backdrop-filter:blur(20px);
  border-bottom:1px solid var(--border);position:sticky;top:0;z-index:100}
.logo{font-family:'Syne',sans-serif;font-size:18px;font-weight:800;color:var(--black);
  display:flex;align-items:center;gap:7px;letter-spacing:-.3px}
.logo-dot{width:7px;height:7px;border-radius:50%;background:var(--accent);
  animation:pulse 2.2s ease-in-out infinite}
@keyframes pulse{0%,100%{transform:scale(1);opacity:1}50%{transform:scale(1.5);opacity:.6}}
.nav-pill{font-size:11px;font-weight:600;color:#fff;letter-spacing:.05em;
  background:linear-gradient(135deg,var(--accent),var(--purple));padding:4px 12px;border-radius:20px}
@media(max-width:480px){nav{padding:0 16px}}

.hero{position:relative;z-index:2;text-align:center;padding:76px 20px 40px;max-width:700px;margin:0 auto}
.hero-tag{display:inline-flex;align-items:center;gap:7px;font-size:11px;font-weight:600;
  color:var(--muted);letter-spacing:.08em;text-transform:uppercase;
  background:rgba(255,255,255,.8);border:1px solid var(--border);border-radius:20px;
  padding:5px 14px;margin-bottom:20px;backdrop-filter:blur(8px)}
.hero-tag span{color:var(--accent)}
h1{font-family:'Syne',sans-serif;font-size:58px;font-weight:800;letter-spacing:-3px;
  line-height:1.0;color:var(--black);margin-bottom:14px}
h1 em{font-style:normal;background:linear-gradient(135deg,var(--accent),var(--purple));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.hero-sub{font-size:16px;color:var(--muted);font-weight:400;line-height:1.65;
  margin-bottom:36px;max-width:460px;margin-left:auto;margin-right:auto}
@media(max-width:640px){h1{font-size:36px;letter-spacing:-1.5px}.hero{padding:56px 16px 28px}.hero-sub{font-size:14px}}

/* ===== SEARCH BOX ===== */
.search-outer{max-width:640px;margin:0 auto 10px;position:relative}
.search-box{
  display:flex;flex-direction:column;
  background:var(--white);
  border-radius:20px;
  border:2px solid transparent;
  background-clip:padding-box;
  box-shadow:0 4px 24px rgba(0,0,0,.08),0 1px 3px rgba(0,0,0,.04);
  transition:all .3s cubic-bezier(.4,0,.2,1);
  position:relative;overflow:hidden;
}
.search-box::before{
  content:'';position:absolute;inset:-2px;border-radius:22px;
  background:linear-gradient(135deg,var(--purple),var(--accent),#06b6d4);
  z-index:-1;opacity:0;transition:opacity .3s;
}
.search-box:focus-within{
  box-shadow:0 8px 36px rgba(109,40,217,.18),0 2px 8px rgba(0,0,0,.06);
}
.search-box:focus-within::before{opacity:1}

/* Top row: input */
.search-top{display:flex;align-items:center;gap:10px;padding:14px 16px 10px 20px}
.search-ai-icon{
  font-size:18px;flex-shrink:0;
  background:linear-gradient(135deg,var(--purple),var(--accent));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  animation:ai-pulse 3s ease-in-out infinite;
}
@keyframes ai-pulse{0%,100%{filter:brightness(1)}50%{filter:brightness(1.3)}}
.search-box input{
  flex:1;border:none;outline:none;font-size:15px;
  font-family:'Plus Jakarta Sans',sans-serif;color:var(--ink);background:transparent;min-width:0;
}
.search-box input::placeholder{color:#c0bdb8}

/* Bottom row: controls + button */
.search-bottom{
  display:flex;align-items:center;gap:8px;
  padding:8px 10px 10px 14px;
  border-top:1px solid var(--border);
}

/* Industry dropdown pill */
.search-pill{
  display:flex;align-items:center;gap:5px;
  background:var(--chip);border:1.5px solid var(--border);
  border-radius:10px;padding:6px 12px;cursor:pointer;
  font-size:12px;font-weight:600;color:var(--ink);
  font-family:'Plus Jakarta Sans',sans-serif;
  transition:all .2s;position:relative;white-space:nowrap;
}
.search-pill:hover{border-color:var(--purple);color:var(--purple);background:#f0ebff}
.search-pill svg{width:12px;height:12px;stroke:currentColor;fill:none;stroke-width:2.5;stroke-linecap:round;stroke-linejoin:round;flex-shrink:0}
.pill-icon{font-size:13px}

/* Domain style pill */
.domain-pill{
  display:flex;align-items:center;gap:5px;
  background:var(--chip);border:1.5px solid var(--border);
  border-radius:10px;padding:6px 12px;cursor:pointer;
  font-size:12px;font-weight:700;color:var(--ink);
  font-family:'Syne',sans-serif;
  transition:all .2s;white-space:nowrap;
}
.domain-pill:hover{border-color:var(--purple);color:var(--purple);background:#f0ebff}
.domain-pill.active{background:var(--black);color:#fff;border-color:var(--black)}

.search-spacer{flex:1}

/* Generate button */
.gen-btn{
  background:linear-gradient(135deg,#0c0c0c 0%,#1a1a2e 50%,#0c0c0c 100%);
  color:#fff;border:none;padding:10px 20px;border-radius:12px;
  font-size:13px;font-weight:700;cursor:pointer;
  font-family:'Plus Jakarta Sans',sans-serif;
  white-space:nowrap;display:flex;align-items:center;gap:7px;
  transition:all .25s cubic-bezier(.4,0,.2,1);flex-shrink:0;
  position:relative;overflow:hidden;
  box-shadow:0 2px 12px rgba(0,0,0,.25);
}
.gen-btn::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,var(--accent),var(--purple));
  opacity:0;transition:opacity .25s;
}
.gen-btn:hover::before{opacity:1}
.gen-btn:hover{transform:scale(.98);box-shadow:0 4px 20px rgba(109,40,217,.35)}
.gen-btn:active{transform:scale(.95)}
.gen-btn-text,.gen-btn-icon{position:relative;z-index:1}
.gen-btn-icon{font-size:14px}

/* Search icon button */
.search-icon-btn{
  width:36px;height:36px;border-radius:10px;background:var(--chip);
  border:1.5px solid var(--border);cursor:pointer;
  display:flex;align-items:center;justify-content:center;
  transition:all .2s;flex-shrink:0;
}
.search-icon-btn:hover{background:#f0ebff;border-color:var(--purple)}
.search-icon-btn svg{width:16px;height:16px;fill:none;stroke:var(--ink);stroke-width:2;stroke-linecap:round;stroke-linejoin:round}

/* Dropdown menus */
.dropdown-wrap{position:relative}
.dropdown-menu{
  position:absolute;top:calc(100% + 8px);left:0;
  background:var(--white);border:1.5px solid var(--border);
  border-radius:16px;padding:8px;min-width:220px;
  box-shadow:0 12px 40px rgba(0,0,0,.12);z-index:200;
  display:none;
}
.dropdown-menu.open{display:block;animation:dd-in .18s cubic-bezier(.34,1.4,.64,1)}
@keyframes dd-in{from{opacity:0;transform:translateY(-6px) scale(.97)}to{opacity:1;transform:none}}
.dd-label{font-size:9px;font-weight:800;color:var(--muted);letter-spacing:.1em;text-transform:uppercase;padding:4px 8px 6px;display:block}
.dd-item{display:flex;align-items:center;gap:8px;padding:8px 10px;border-radius:10px;cursor:pointer;font-size:12px;font-weight:600;color:var(--ink);transition:all .15s}
.dd-item:hover{background:var(--chip)}
.dd-item.selected{background:#f0ebff;color:var(--purple)}
.dd-item-emoji{font-size:16px;width:22px;text-align:center}
.dd-divider{height:1px;background:var(--border);margin:4px 0}

/* Domain dropdown */
.domain-menu{min-width:160px}
.dom-opt{display:flex;align-items:center;gap:8px;padding:8px 10px;border-radius:10px;cursor:pointer;font-size:13px;font-weight:700;color:var(--ink);transition:all .15s;font-family:'Syne',sans-serif}
.dom-opt:hover{background:var(--chip)}
.dom-opt.selected{background:var(--black);color:#fff;border-radius:10px}
.dom-badge{font-size:9px;font-weight:600;background:rgba(109,40,217,.1);color:var(--purple);padding:2px 7px;border-radius:6px;margin-left:auto}
.dom-opt.selected .dom-badge{background:rgba(255,255,255,.15);color:rgba(255,255,255,.7)}

@media(max-width:480px){.gen-btn{padding:9px 14px;font-size:12px}.search-bottom{gap:6px;padding:8px 8px 8px 10px}}

/* ===== STATS — only 2 ===== */
.stats{position:relative;z-index:2;display:flex;justify-content:center;
  gap:48px;flex-wrap:wrap;max-width:400px;margin:0 auto 36px;padding:0 16px}
.stat{text-align:center}
.stat-n{font-family:'Syne',sans-serif;font-size:28px;font-weight:800;
  color:var(--black);letter-spacing:-1px;line-height:1}
.stat-l{font-size:11px;color:var(--muted);margin-top:3px}

/* ===== INDUSTRIES — horizontal scroll pill style ===== */
.industry-wrap{position:relative;z-index:2;max-width:860px;margin:0 auto 14px;padding:0 16px}
.sec-label{font-size:10px;font-weight:700;color:var(--muted);text-transform:uppercase;
  letter-spacing:.1em;margin-bottom:10px;text-align:center}

.ind-scroll{
  display:flex;flex-wrap:wrap;gap:8px;justify-content:center;
}
.ind-pill{
  display:flex;align-items:center;gap:6px;
  background:var(--white);border:1.5px solid var(--border);
  border-radius:100px;padding:7px 16px;cursor:pointer;
  font-size:12px;font-weight:600;color:var(--ink);
  transition:all .2s cubic-bezier(.34,1.4,.64,1);
  white-space:nowrap;
}
.ind-pill:hover{
  transform:translateY(-2px);
  border-color:var(--purple);color:var(--purple);
  background:#f5f0ff;
  box-shadow:0 4px 16px rgba(109,40,217,.12);
}
.ind-pill:active{transform:scale(.96)}
.ind-emoji{font-size:14px;line-height:1}

.liked-bar{position:relative;z-index:2;max-width:900px;margin:20px auto 0;padding:0 20px;display:none}
.liked-inner{background:var(--white);border-radius:12px;padding:12px 16px;border:1px solid var(--border)}
.liked-title{font-size:10px;font-weight:700;color:var(--muted);text-transform:uppercase;letter-spacing:.08em;margin-bottom:8px}
.liked-list{display:flex;flex-wrap:wrap;gap:7px}
.liked-pill{display:flex;align-items:center;gap:5px;background:var(--chip);border-radius:7px;padding:4px 10px;font-size:12px;font-weight:600;color:var(--ink)}
.liked-pill button{background:none;border:none;cursor:pointer;font-size:14px;color:var(--muted);line-height:1;padding:0}
.liked-pill button:hover{color:var(--accent)}

.results{position:relative;z-index:2;max-width:1100px;margin:32px auto 0;padding:0 20px 48px}
.res-label{font-size:11px;font-weight:700;color:var(--muted);letter-spacing:.06em;margin-bottom:20px;text-align:center;text-transform:uppercase}

.logo-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:10px}
@media(max-width:1024px){.logo-grid{grid-template-columns:repeat(4,1fr)}}
@media(max-width:768px){.logo-grid{grid-template-columns:repeat(3,1fr)}}
@media(max-width:480px){.logo-grid{grid-template-columns:repeat(2,1fr)}}

/* Card styles — overlay shown only on hover */
.lc{
  position:relative;border-radius:16px;overflow:hidden;cursor:pointer;
  aspect-ratio:1.4/1;display:flex;flex-direction:column;align-items:center;
  justify-content:center;transition:transform .2s cubic-bezier(.34,1.4,.64,1),box-shadow .2s;
  border:1.5px solid transparent;
}
.lc:hover{transform:scale(1.04);box-shadow:0 8px 28px rgba(0,0,0,.18)}

.lc-top-badge{
  position:absolute;top:8px;left:8px;
  font-size:8px;font-weight:800;letter-spacing:.06em;text-transform:uppercase;
  background:rgba(255,255,255,.22);color:rgba(255,255,255,.95);
  border:1px solid rgba(255,255,255,.3);border-radius:5px;padding:2px 7px;
  z-index:2;backdrop-filter:blur(4px)
}

.lc-like{
  position:absolute;top:8px;right:8px;z-index:4;
  width:28px;height:28px;border-radius:7px;cursor:pointer;font-size:14px;
  border:1.5px solid rgba(255,255,255,.3);background:rgba(255,255,255,.15);
  display:flex;align-items:center;justify-content:center;
  transition:all .15s;backdrop-filter:blur(4px);color:rgba(255,255,255,.8)
}
.lc-like:hover{background:rgba(255,255,255,.3);color:#fff}
.lc-like.liked{background:var(--accent);border-color:var(--accent);color:#fff}

.lc-name{
  font-size:15px;font-weight:700;text-align:center;
  letter-spacing:-.2px;padding:0 10px;line-height:1.2;
  word-break:break-all;z-index:1
}

.avail-dot{
  position:absolute;bottom:8px;right:10px;
  width:8px;height:8px;border-radius:50%;z-index:2
}
.avail-dot.available{background:#4ade80;box-shadow:0 0 6px rgba(74,222,128,.8)}
.avail-dot.checking{background:#fbbf24;animation:blink 1s ease-in-out infinite}
.avail-dot.unavailable{background:#f87171}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.3}}

/* Overlay — ONLY on hover, hidden by default */
.lc-overlay{
  position:absolute;inset:0;background:rgba(0,0,0,.6);
  display:flex;flex-direction:column;align-items:center;justify-content:center;gap:8px;
  opacity:0;transition:opacity .2s;z-index:3;border-radius:16px;
  padding:12px;
}
.lc:hover .lc-overlay{opacity:1}
.lov-btn{
  font-size:12px;font-weight:700;padding:9px 0;border-radius:9px;
  text-decoration:none;text-align:center;font-family:'Plus Jakarta Sans',sans-serif;
  cursor:pointer;border:none;width:140px;transition:opacity .1s;display:block;
}
.lov-buy{background:var(--white);color:var(--black)}
.lov-chk{background:rgba(255,255,255,.18);color:#fff;border:1.5px solid rgba(255,255,255,.4)}
.lov-buy:hover{opacity:.88}
.lov-chk:hover{background:rgba(255,255,255,.28)}

/* Card color schemes — unchanged */
.cs-0{background:#f5a623;color:#7a4f00}
.cs-0 .lc-name{color:#3d2600;font-family:'Syne',sans-serif}
.cs-1{background:#f0f0ed;color:#2c2c2c}
.cs-1 .lc-name{color:#1a1a1a;font-family:'Space Grotesk',sans-serif;font-weight:600}
.cs-2{background:#f8f8f8;color:#111}
.cs-2 .lc-name{color:#111;font-family:'Montserrat',sans-serif;letter-spacing:.5px;font-size:13px}
.cs-3{background:#1a1a2e;color:#e8d5ff}
.cs-3 .lc-name{color:#e8d5ff;font-family:'Syne',sans-serif;font-size:13px}
.cs-4{background:#0a2240;color:#4ab3f4}
.cs-4 .lc-name{color:#fff;font-family:'Bebas Neue',sans-serif;font-size:20px;letter-spacing:2px}
.cs-5{background:#1e3a2f;color:#7dcfb6}
.cs-5 .lc-name{color:#a8edda;font-family:'Poppins',sans-serif;font-size:13px}
.cs-6{background:#2d1b69;color:#c4b5fd}
.cs-6 .lc-name{color:#e9d5ff;font-family:'Raleway',sans-serif;font-size:14px;font-weight:800}
.cs-7{background:#1a1a1a;color:#ff6b35}
.cs-7 .lc-name{color:#ff6b35;font-family:'Space Grotesk',sans-serif;font-weight:700}
.cs-8{background:#fff;color:#111;border:1.5px solid #e0e0e0 !important}
.cs-8 .lc-name{color:#111;font-family:'DM Serif Display',sans-serif;font-size:14px;font-style:italic}
.cs-9{background:#0f172a;color:#38bdf8}
.cs-9 .lc-name{color:#38bdf8;font-family:'Montserrat',sans-serif;font-size:13px;font-weight:800;letter-spacing:1px}
.cs-10{background:#fdf2f8;color:#831843}
.cs-10 .lc-name{color:#9d174d;font-family:'Nunito',sans-serif;font-size:14px;font-weight:800}
.cs-11{background:#f97316;color:#fff}
.cs-11 .lc-name{color:#fff;font-family:'Syne',sans-serif;font-weight:800}
.cs-12{background:#14532d;color:#bbf7d0}
.cs-12 .lc-name{color:#bbf7d0;font-family:'Poppins',sans-serif;font-size:13px}
.cs-13{background:#312e81;color:#c7d2fe}
.cs-13 .lc-name{color:#e0e7ff;font-family:'Raleway',sans-serif;font-size:13px;font-weight:800}
.cs-14{background:#7c3aed;color:#fff}
.cs-14 .lc-name{color:#fff;font-family:'Syne',sans-serif;font-size:14px;font-weight:800}

/* ===== AI LOADING ===== */
.ai-loader{display:flex;flex-direction:column;align-items:center;justify-content:center;padding:80px 20px;gap:28px}
.ai-orb{width:90px;height:90px;position:relative}
.ai-orb-ring{position:absolute;inset:0;border-radius:50%;border:2px solid transparent;background:linear-gradient(var(--bg),var(--bg)) padding-box,linear-gradient(135deg,var(--purple),var(--accent),#06b6d4,var(--purple)) border-box;animation:orb-spin 2s linear infinite}
.ai-orb-ring2{position:absolute;inset:8px;border-radius:50%;border:2px solid transparent;background:linear-gradient(var(--bg),var(--bg)) padding-box,linear-gradient(225deg,var(--accent),var(--purple),#06b6d4,var(--accent)) border-box;animation:orb-spin 1.4s linear infinite reverse}
.ai-orb-core{position:absolute;inset:18px;border-radius:50%;background:linear-gradient(135deg,var(--purple),var(--accent));display:flex;align-items:center;justify-content:center;font-size:22px;animation:core-pulse 2s ease-in-out infinite;box-shadow:0 0 20px rgba(109,40,217,.4)}
@keyframes orb-spin{to{transform:rotate(360deg)}}
@keyframes core-pulse{0%,100%{transform:scale(1);box-shadow:0 0 20px rgba(109,40,217,.4)}50%{transform:scale(1.08);box-shadow:0 0 35px rgba(255,69,0,.5)}}
.ai-loader-text{text-align:center}
.ai-loader-title{font-family:'Syne',sans-serif;font-size:20px;font-weight:800;color:var(--black);letter-spacing:-.5px;margin-bottom:6px}
.ai-loader-sub{font-size:13px;color:var(--muted);font-weight:500;margin-bottom:16px}
.ai-words{display:flex;gap:8px;flex-wrap:wrap;justify-content:center;max-width:400px}
.ai-word{font-size:11px;font-weight:600;padding:4px 12px;border-radius:20px;background:var(--white);border:1.5px solid var(--border);color:var(--muted);animation:word-pop .5s cubic-bezier(.34,1.4,.64,1) both;opacity:0}
@keyframes word-pop{0%{opacity:0;transform:translateY(8px) scale(.9)}100%{opacity:1;transform:none}}
.ai-progress{width:240px;height:3px;background:var(--border);border-radius:3px;overflow:hidden}
.ai-progress-bar{height:100%;width:0%;background:linear-gradient(90deg,var(--purple),var(--accent));border-radius:3px;animation:progress-fill 4s ease-in-out infinite}
@keyframes progress-fill{0%{width:0%}80%{width:88%}100%{width:92%}}

/* SERVICES */
.services{position:relative;z-index:2;max-width:960px;margin:0 auto 40px;padding:0 20px}
.svc-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:14px}
@media(max-width:900px){.svc-grid{grid-template-columns:repeat(2,1fr)}}
@media(max-width:520px){.svc-grid{grid-template-columns:repeat(1,1fr)}}

.svc-card{border-radius:22px;overflow:hidden;text-decoration:none;display:flex;flex-direction:column;position:relative;min-height:340px;cursor:pointer;transition:transform .25s cubic-bezier(.34,1.3,.64,1),box-shadow .25s;border:none}
.svc-card:hover{transform:translateY(-6px) scale(1.025);box-shadow:0 20px 50px rgba(0,0,0,.22)}
.svc-card.card-tm{background:linear-gradient(145deg,#667eea,#764ba2)}
.svc-card.card-domain{background:linear-gradient(145deg,#06b6d4,#0284c7)}
.svc-card.card-logo{background:linear-gradient(145deg,#f59e0b,#ef4444)}
.svc-card.card-web{background:linear-gradient(145deg,#10b981,#059669)}
.svc-emoji{font-size:72px;line-height:1;position:absolute;bottom:70px;right:-10px;opacity:.55;transform:rotate(-8deg);filter:drop-shadow(0 8px 24px rgba(0,0,0,.25));transition:transform .3s,opacity .3s;pointer-events:none}
.svc-card:hover .svc-emoji{transform:rotate(0deg) scale(1.1);opacity:.75}
.svc-content{padding:24px 22px;flex:1;display:flex;flex-direction:column;position:relative;z-index:1}
.svc-tag{font-size:10px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:rgba(255,255,255,.65);margin-bottom:10px}
.svc-title{font-family:'Syne',sans-serif;font-size:20px;font-weight:800;color:#fff;line-height:1.2;margin-bottom:8px;letter-spacing:-.3px}
.svc-desc{font-size:12px;color:rgba(255,255,255,.68);line-height:1.6;flex:1}
.svc-footer{padding:0 22px 22px;position:relative;z-index:1}
.svc-learn{display:inline-flex;align-items:center;gap:7px;background:rgba(255,255,255,.18);backdrop-filter:blur(8px);border:1px solid rgba(255,255,255,.28);color:#fff;font-size:12px;font-weight:700;padding:9px 18px;border-radius:30px;text-decoration:none;font-family:'Plus Jakarta Sans',sans-serif;transition:all .18s}
.svc-learn:hover{background:rgba(255,255,255,.32)}
.svc-learn-arrow{font-size:14px;transition:transform .18s}
.svc-learn:hover .svc-learn-arrow{transform:translateX(4px)}
.tm-card-btns{display:flex;flex-direction:column;gap:8px}
.tm-card-btn{display:flex;align-items:center;justify-content:center;gap:6px;background:rgba(255,255,255,.18);backdrop-filter:blur(8px);border:1px solid rgba(255,255,255,.28);color:#fff;font-size:11px;font-weight:700;padding:9px 14px;border-radius:30px;text-decoration:none;font-family:'Plus Jakarta Sans',sans-serif;transition:all .18s}
.tm-card-btn:hover{background:rgba(255,255,255,.32)}

.how{position:relative;z-index:2;max-width:920px;margin:0 auto 44px;padding:0 20px}
.how-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:12px}
.how-card{background:var(--white);border:1.5px solid var(--border);border-radius:16px;padding:20px;position:relative;overflow:hidden}
.how-num{font-family:'Syne',sans-serif;font-size:36px;font-weight:800;color:var(--border);letter-spacing:-2px;line-height:1;margin-bottom:8px}
.how-icon{font-size:20px;margin-bottom:5px}
.how-h{font-family:'Syne',sans-serif;font-size:14px;font-weight:700;color:var(--black);margin-bottom:4px}
.how-p{font-size:12px;color:var(--muted);line-height:1.6}
@media(max-width:640px){.how-grid{grid-template-columns:1fr}}

.monkb-wrap{position:relative;z-index:2;max-width:920px;margin:0 auto 40px;padding:0 20px}
.monkb{background:linear-gradient(135deg,#0c0c0c 0%,#181830 60%,#0c0c0c 100%);border-radius:20px;padding:32px 34px;display:flex;align-items:center;justify-content:space-between;gap:22px;overflow:hidden;position:relative}
.mb1{position:absolute;top:-50px;left:-50px;width:200px;height:200px;border-radius:50%;background:radial-gradient(circle,rgba(109,40,217,.3),transparent 70%);pointer-events:none}
.mb2{position:absolute;bottom:-50px;right:90px;width:170px;height:170px;border-radius:50%;background:radial-gradient(circle,rgba(255,69,0,.2),transparent 70%);pointer-events:none}
.ml{position:relative;z-index:1;flex:1}
.ml-tag{font-size:10px;font-weight:700;color:rgba(255,255,255,.38);text-transform:uppercase;letter-spacing:.1em;margin-bottom:7px}
.ml-title{font-family:'Syne',sans-serif;font-size:26px;font-weight:800;color:#fff;letter-spacing:-1px;line-height:1.15;margin-bottom:8px}
.ml-title span{background:linear-gradient(135deg,var(--accent),var(--purple));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.ml-desc{font-size:13px;color:rgba(255,255,255,.48);line-height:1.6;max-width:340px}
.ml-btns{display:flex;gap:8px;margin-top:16px;flex-wrap:wrap}
.ml-cta{background:linear-gradient(135deg,var(--accent),#c2410c);color:#fff;border-radius:9px;padding:10px 20px;font-size:13px;font-weight:700;text-decoration:none;font-family:'Plus Jakarta Sans',sans-serif}
.ml-ghost{background:rgba(255,255,255,.08);color:#fff;border:1px solid rgba(255,255,255,.15);border-radius:9px;padding:10px 20px;font-size:13px;font-weight:600;text-decoration:none;font-family:'Plus Jakarta Sans',sans-serif}
.mr{position:relative;z-index:1;text-align:center;flex-shrink:0;display:flex;flex-direction:column;align-items:center;gap:9px}
.mr-emoji{font-size:52px;line-height:1}
.mr-badge{background:rgba(255,255,255,.08);border:1px solid rgba(255,255,255,.12);border-radius:11px;padding:8px 14px}
.mr-name{font-family:'Syne',sans-serif;font-size:18px;font-weight:800;color:#fff;letter-spacing:-.3px}
.mr-sub{font-size:10px;color:rgba(255,255,255,.32);margin-top:2px}
@media(max-width:640px){.monkb{flex-direction:column;padding:22px 18px;align-items:flex-start}.mr{align-self:center}.ml-title{font-size:21px}}

footer{position:relative;z-index:2;border-top:1px solid var(--border);padding:20px 32px;display:flex;justify-content:space-between;align-items:center;background:var(--white);flex-wrap:wrap;gap:10px}
.foot-logo{font-family:'Syne',sans-serif;font-size:15px;font-weight:800;color:var(--black)}
.foot-made{font-size:12px;color:var(--muted)}
.foot-links{display:flex;gap:16px;flex-wrap:wrap}
.foot-link{font-size:12px;color:var(--muted);text-decoration:none;transition:color .15s}
.foot-link:hover{color:var(--black)}
@media(max-width:520px){footer{padding:16px;justify-content:center;text-align:center}}

@media(max-width:640px){
  .results,.services,.how,.industry-wrap,.liked-bar,.monkb-wrap{padding-left:14px;padding-right:14px}
  .svc-grid{grid-template-columns:1fr}
  .stats{gap:24px;padding:0 12px}
}

/* ===== RESULTS PAGE ===== */
#resultsPage{display:none;position:fixed;inset:0;z-index:500;overflow-y:auto;background:var(--bg)}
#resultsPage.open{display:block;animation:rp-in .35s cubic-bezier(.22,1,.36,1)}
@keyframes rp-in{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:none}}
.rp-nav{display:flex;align-items:center;justify-content:space-between;padding:0 24px;height:56px;background:rgba(247,246,243,.95);backdrop-filter:blur(20px);border-bottom:1px solid var(--border);position:sticky;top:0;z-index:10;gap:12px}
.rp-back{display:flex;align-items:center;gap:7px;background:var(--chip);border:1.5px solid var(--border);cursor:pointer;font-size:13px;font-weight:700;color:var(--ink);font-family:'Plus Jakarta Sans',sans-serif;padding:8px 16px;border-radius:10px;transition:all .15s;flex-shrink:0}
.rp-back:hover{background:var(--black);color:#fff;border-color:var(--black)}
.rp-title{font-family:'Syne',sans-serif;font-size:15px;font-weight:800;color:var(--black);overflow:hidden;text-overflow:ellipsis;white-space:nowrap;flex:1;text-align:center}
.rp-count{font-size:11px;font-weight:600;color:var(--muted);background:var(--chip);padding:5px 14px;border-radius:20px;flex-shrink:0}
.rp-saved-wrap{max-width:1100px;margin:20px auto 0;padding:0 20px}
.rp-saved-box{background:var(--white);border-radius:14px;padding:14px 18px;border:1.5px solid var(--accent);display:none}
.rp-saved-box.show{display:block}
.rp-saved-hd{display:flex;align-items:center;justify-content:space-between;margin-bottom:10px}
.rp-saved-hd-left{font-size:11px;font-weight:700;color:var(--accent);text-transform:uppercase;letter-spacing:.08em;display:flex;align-items:center;gap:6px}
.saved-cnt{background:var(--accent);color:#fff;border-radius:10px;padding:2px 8px;font-size:10px;font-weight:800}
.rp-saved-clear{background:none;border:1px solid #fcd9c8;border-radius:6px;cursor:pointer;font-size:11px;font-weight:600;color:#f97316;padding:3px 10px;font-family:'Plus Jakarta Sans',sans-serif}
.rp-saved-list{display:flex;flex-wrap:wrap;gap:7px}
.rp-saved-pill{display:flex;align-items:center;gap:6px;background:#fff3ee;border:1px solid #fcd9c8;border-radius:8px;padding:5px 12px;font-size:12px;font-weight:600;color:#c2410c}
.rp-saved-pill button{background:none;border:none;cursor:pointer;font-size:16px;color:#f97316;line-height:1;padding:0}
.rp-grid-wrap{max-width:1100px;margin:20px auto 60px;padding:0 20px}
.rp-res-label{font-size:11px;font-weight:700;color:var(--muted);letter-spacing:.06em;margin-bottom:18px;text-align:center;text-transform:uppercase}

/* Results page card styles */
.lc{border-radius:16px;overflow:hidden;display:flex;flex-direction:column;border:1.5px solid var(--border);transition:transform .25s cubic-bezier(.34,1.3,.64,1),box-shadow .25s;animation:cardIn .4s ease both}
@keyframes cardIn{from{opacity:0;transform:translateY(14px) scale(.97)}to{opacity:1;transform:none}}
.lc:hover{transform:translateY(-4px) scale(1.02);box-shadow:0 12px 36px rgba(0,0,0,.15)}
.lc-logo{display:flex;align-items:center;justify-content:center;padding:22px 12px 14px;min-height:90px;position:relative;flex:1}
.lc-top-badge{position:absolute;top:8px;left:8px;font-size:7px;font-weight:800;letter-spacing:.08em;text-transform:uppercase;background:rgba(0,0,0,.3);color:#fff;border:1px solid rgba(255,255,255,.3);border-radius:5px;padding:2px 7px}
.lc-avail{position:absolute;top:10px;right:10px;width:8px;height:8px;border-radius:50%}
.lc-avail.av{background:#4ade80;box-shadow:0 0 7px rgba(74,222,128,.9)}
.lc-avail.un{background:#f87171}
.lc-name{font-size:13px;font-weight:700;text-align:center;padding:0 8px;line-height:1.3;word-break:break-all}
/* Actions — hidden by default, show on hover */
.lc-actions{
  padding:8px 10px 10px;display:flex;flex-direction:column;gap:6px;
  max-height:0;overflow:hidden;opacity:0;
  transition:max-height .25s ease,opacity .2s ease,padding .25s ease;
  padding-top:0;padding-bottom:0;
}
.lc:hover .lc-actions{
  max-height:80px;opacity:1;
  padding:8px 10px 10px;
}
.lc-row{display:flex;gap:6px;align-items:center}
.lc-like{width:36px;height:36px;border-radius:9px;cursor:pointer;font-size:17px;border:none;display:flex;align-items:center;justify-content:center;transition:all .2s;flex-shrink:0;background:rgba(255,255,255,.25);color:#fff}
.lc-like:hover{background:rgba(255,107,53,.3);transform:scale(1.1)}
.lc-like.liked{background:var(--accent);color:#fff;box-shadow:0 3px 12px rgba(255,69,0,.5)}
.lov-buy,.lov-chk{flex:1;font-size:10px;font-weight:700;padding:8px 4px;border-radius:9px;text-decoration:none;text-align:center;font-family:'Plus Jakarta Sans',sans-serif;cursor:pointer;border:none;transition:all .15s;display:block}
.lov-buy{background:rgba(255,255,255,.88);color:#111}
.lov-buy:hover{background:#fff}
.lov-chk{background:rgba(255,255,255,.15);color:#fff;border:1px solid rgba(255,255,255,.3)}
.lov-chk:hover{background:rgba(255,255,255,.25)}

/* Card color schemes for results page */
.cs-0 .lc-logo{background:linear-gradient(135deg,#667eea,#764ba2)}.cs-0 .lc-name{color:#fff;font-family:'Syne',sans-serif;font-weight:800}.cs-0 .lc-actions{background:#4c3399}
.cs-1 .lc-logo{background:linear-gradient(135deg,#f093fb,#f5576c)}.cs-1 .lc-name{color:#fff;font-family:'Plus Jakarta Sans',sans-serif;font-weight:800;font-size:12px}.cs-1 .lc-actions{background:#b01055}
.cs-2 .lc-logo{background:linear-gradient(135deg,#0f172a,#1e3a5f)}.cs-2 .lc-name{color:#38bdf8;font-family:'Space Grotesk',sans-serif;font-weight:700;font-size:12px}.cs-2 .lc-actions{background:#0a1420}
.cs-3 .lc-logo{background:linear-gradient(135deg,#064e3b,#065f46)}.cs-3 .lc-name{color:#6ee7b7;font-family:'Plus Jakarta Sans',sans-serif;font-weight:700;font-size:12px}.cs-3 .lc-actions{background:#022c22}
.cs-4 .lc-logo{background:linear-gradient(135deg,#1c1c1c,#2d1515)}.cs-4 .lc-name{color:#ff6b35;font-family:'Bebas Neue',sans-serif;font-size:20px;letter-spacing:2px}.cs-4 .lc-actions{background:#100808}
.cs-5 .lc-logo{background:linear-gradient(135deg,#fce38a,#f9a825)}.cs-5 .lc-name{color:#3d2600;font-family:'Syne',sans-serif;font-weight:900}.cs-5 .lc-actions{background:#b07900}.cs-5 .lc-like{color:#3d2600}.cs-5 .lov-buy{background:rgba(0,0,0,.7);color:#fce38a}.cs-5 .lov-chk{color:#3d2600;border-color:rgba(0,0,0,.3);background:rgba(0,0,0,.15)}
.cs-6 .lc-logo{background:linear-gradient(135deg,#00c6ff,#0072ff)}.cs-6 .lc-name{color:#fff;font-family:'Space Grotesk',sans-serif;font-weight:700;font-size:12px}.cs-6 .lc-actions{background:#004ecc}
.cs-7 .lc-logo{background:linear-gradient(135deg,#c4ff61,#86efac)}.cs-7 .lc-name{color:#14532d;font-family:'Plus Jakarta Sans',sans-serif;font-weight:900}.cs-7 .lc-actions{background:#3d8c28}.cs-7 .lc-like{color:#14532d}.cs-7 .lov-buy{background:rgba(0,0,0,.7);color:#c4ff61}.cs-7 .lov-chk{color:#14532d;border-color:rgba(0,0,0,.2);background:rgba(0,0,0,.1)}
.cs-8 .lc-logo{background:linear-gradient(135deg,#1a1a2e,#16213e)}.cs-8 .lc-name{color:#e8d5ff;font-family:'Syne',sans-serif;font-size:12px;font-weight:700}.cs-8 .lc-actions{background:#0d0d1a}
.cs-9 .lc-logo{background:linear-gradient(135deg,#ff416c,#ff4b2b)}.cs-9 .lc-name{color:#fff;font-family:'Plus Jakarta Sans',sans-serif;font-weight:800;font-size:12px}.cs-9 .lc-actions{background:#b81a1a}
.cs-10 .lc-logo{background:linear-gradient(135deg,#2d1b69,#5b21b6)}.cs-10 .lc-name{color:#c4b5fd;font-family:'Plus Jakarta Sans',sans-serif;font-weight:700;font-size:12px}.cs-10 .lc-actions{background:#1a0e4a}
.cs-11 .lc-logo{background:linear-gradient(135deg,#d0d0d0,#f0f0f0)}.cs-11 .lc-name{color:#111;font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:12px}.cs-11 .lc-actions{background:#aaa}.cs-11 .lc-like{color:#333}.cs-11 .lov-buy{background:#111;color:#fff}.cs-11 .lov-chk{color:#333;border-color:rgba(0,0,0,.25);background:rgba(0,0,0,.08)}
.cs-12 .lc-logo{background:linear-gradient(135deg,#0d0d0d,#1a1a1a)}.cs-12 .lc-name{color:#c4ff61;font-family:'Bebas Neue',sans-serif;font-size:20px;letter-spacing:2px}.cs-12 .lc-actions{background:#060606}
.cs-13 .lc-logo{background:linear-gradient(135deg,#00b4d8,#0077b6)}.cs-13 .lc-name{color:#fff;font-family:'Syne',sans-serif;font-weight:800;font-size:12px}.cs-13 .lc-actions{background:#005577}
.cs-14 .lc-logo{background:linear-gradient(135deg,#f5af19,#f12711)}.cs-14 .lc-name{color:#fff;font-family:'Plus Jakarta Sans',sans-serif;font-weight:900;font-size:12px}.cs-14 .lc-actions{background:#b01a00}

.logo-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:12px}
@media(max-width:1100px){.logo-grid{grid-template-columns:repeat(4,1fr)}}
@media(max-width:800px){.logo-grid{grid-template-columns:repeat(3,1fr)}}
@media(max-width:520px){.logo-grid{grid-template-columns:repeat(2,1fr)}}

/* ===== MULTI-STEP FLOW ===== */
.step-modal{
  position:fixed;inset:0;z-index:600;display:flex;align-items:center;justify-content:center;
  background:rgba(0,0,0,.5);backdrop-filter:blur(6px);
  display:none;
}
.step-modal.open{display:flex;animation:md-in .22s cubic-bezier(.34,1.4,.64,1)}
@keyframes md-in{from{opacity:0;transform:scale(.94)}to{opacity:1;transform:none}}
.step-box{
  background:var(--white);border-radius:24px;padding:32px 28px;
  max-width:520px;width:calc(100% - 32px);
  box-shadow:0 24px 64px rgba(0,0,0,.18);
}
.step-header{margin-bottom:24px}
.step-num{font-size:10px;font-weight:800;color:var(--muted);letter-spacing:.1em;text-transform:uppercase;margin-bottom:6px}
.step-q{font-family:'Syne',sans-serif;font-size:22px;font-weight:800;color:var(--black);letter-spacing:-.5px;line-height:1.25}
.step-sub{font-size:13px;color:var(--muted);margin-top:6px}

.step-options{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:24px}
.step-opt{
  display:flex;align-items:center;gap:8px;
  background:var(--chip);border:1.5px solid var(--border);
  border-radius:12px;padding:10px 16px;cursor:pointer;
  font-size:13px;font-weight:600;color:var(--ink);
  font-family:'Plus Jakarta Sans',sans-serif;
  transition:all .2s;
}
.step-opt:hover{border-color:var(--purple);color:var(--purple);background:#f0ebff}
.step-opt.selected{background:var(--black);color:#fff;border-color:var(--black)}
.step-opt-emoji{font-size:18px}

.step-actions{display:flex;justify-content:space-between;align-items:center;gap:12px}
.step-back-btn{background:none;border:1.5px solid var(--border);border-radius:10px;padding:10px 18px;font-size:13px;font-weight:600;color:var(--muted);cursor:pointer;font-family:'Plus Jakarta Sans',sans-serif;transition:all .15s}
.step-back-btn:hover{border-color:var(--ink);color:var(--ink)}
.step-next-btn{background:var(--black);color:#fff;border:none;border-radius:10px;padding:10px 24px;font-size:13px;font-weight:700;cursor:pointer;font-family:'Plus Jakarta Sans',sans-serif;transition:all .2s;flex:1;max-width:200px}
.step-next-btn:hover{background:var(--purple)}
.step-next-btn:disabled{opacity:.35;cursor:not-allowed}

.step-progress{display:flex;gap:6px;margin-bottom:20px}
.step-dot{width:24px;height:3px;border-radius:3px;background:var(--border);transition:background .2s}
.step-dot.active{background:var(--black)}
.step-dot.done{background:var(--purple)}
</style>
</head>
<body>
<div id="homePage">
<div class="mesh"></div>
<div class="fe fe1">🌐</div>
<div class="fe fe2">✨</div>
<div class="fe fe3">🚀</div>
<div class="fe fe4">💡</div>
<div class="fe fe5">⚡</div>

<nav>
  <div class="logo"><div class="logo-dot"></div>orbit07<span style="color:var(--muted)">.ai</span></div>
  <div class="nav-pill">Orbit07 AI · Free</div>
</nav>

<div class="hero">
  <div class="hero-tag"><span>✦</span> Orbit07 AI · India's Favourite</div>
  <h1>Find your<br><em>perfect domain</em><br>instantly</h1>
  <p class="hero-sub">Describe your business in any language — Orbit07 AI generates unlimited creative domain names in seconds</p>

  <!-- REDESIGNED SEARCH BOX -->
  <div class="search-outer">
    <div class="search-box">
      <!-- Top: text input -->
      <div class="search-top">
        <span class="search-ai-icon">✦</span>
        <input id="bi" type="text" placeholder="e.g. Mumbai restaurant, fashion boutique, yoga studio...">
      </div>
      <!-- Bottom: pills + button -->
      <div class="search-bottom">
        <!-- Industry dropdown -->
        <div class="dropdown-wrap" id="indWrap">
          <div class="search-pill" id="indPill" onclick="toggleDd('indMenu')">
            <span class="pill-icon" id="indPillIcon">🏢</span>
            <span id="indPillText">Industry</span>
            <svg viewBox="0 0 24 24"><polyline points="6 9 12 15 18 9"/></svg>
          </div>
          <div class="dropdown-menu" id="indMenu">
            <span class="dd-label">Select your industry</span>
            <div class="dd-item" onclick="setInd('','🏢','All Industries')"><span class="dd-item-emoji">🏢</span>All Industries</div>
            <div class="dd-divider"></div>
            <div class="dd-item" onclick="setInd('online grocery delivery','🛒','Grocery')"><span class="dd-item-emoji">🛒</span>Grocery</div>
            <div class="dd-item" onclick="setInd('digital marketing agency','📣','Marketing')"><span class="dd-item-emoji">📣</span>Marketing</div>
            <div class="dd-item" onclick="setInd('women fashion boutique','👗','Fashion')"><span class="dd-item-emoji">👗</span>Fashion</div>
            <div class="dd-item" onclick="setInd('CA accounting firm','📊','CA / Finance')"><span class="dd-item-emoji">📊</span>CA / Finance</div>
            <div class="dd-item" onclick="setInd('online coaching education platform','🎓','Education')"><span class="dd-item-emoji">🎓</span>Education</div>
            <div class="dd-item" onclick="setInd('restaurant food delivery','🍽️','Restaurant')"><span class="dd-item-emoji">🍽️</span>Restaurant</div>
            <div class="dd-item" onclick="setInd('real estate property India','🏠','Real Estate')"><span class="dd-item-emoji">🏠</span>Real Estate</div>
            <div class="dd-item" onclick="setInd('healthcare clinic hospital','🏥','Healthcare')"><span class="dd-item-emoji">🏥</span>Healthcare</div>
            <div class="dd-item" onclick="setInd('travel agency tours India','✈️','Travel')"><span class="dd-item-emoji">✈️</span>Travel</div>
            <div class="dd-item" onclick="setInd('software IT company India','💻','IT / Software')"><span class="dd-item-emoji">💻</span>IT / Software</div>
            <div class="dd-item" onclick="setInd('beauty salon spa','💆','Beauty & Spa')"><span class="dd-item-emoji">💆</span>Beauty & Spa</div>
            <div class="dd-item" onclick="setInd('gym fitness center','💪','Fitness')"><span class="dd-item-emoji">💪</span>Fitness</div>
            <div class="dd-item" onclick="setInd('law firm legal services India','⚖️','Legal')"><span class="dd-item-emoji">⚖️</span>Legal</div>
            <div class="dd-item" onclick="setInd('ecommerce online store India','🛍️','E-Commerce')"><span class="dd-item-emoji">🛍️</span>E-Commerce</div>
            <div class="dd-item" onclick="setInd('photography studio','📸','Photography')"><span class="dd-item-emoji">📸</span>Photography</div>
            <div class="dd-item" onclick="setInd('wedding planning event management','💍','Events')"><span class="dd-item-emoji">💍</span>Events</div>
            <div class="dd-item" onclick="setInd('interior design home decor','🛋️','Interior')"><span class="dd-item-emoji">🛋️</span>Interior</div>
            <div class="dd-item" onclick="setInd('automotive car service','🚗','Automotive')"><span class="dd-item-emoji">🚗</span>Automotive</div>
            <div class="dd-item" onclick="setInd('fintech payments startup India','💳','Fintech')"><span class="dd-item-emoji">💳</span>Fintech</div>
            <div class="dd-item" onclick="setInd('startup SaaS B2B product','🚀','SaaS / Startup')"><span class="dd-item-emoji">🚀</span>SaaS / Startup</div>
            <div class="dd-item" onclick="setInd('agriculture farming rural India','🌾','Agriculture')"><span class="dd-item-emoji">🌾</span>Agriculture</div>
            <div class="dd-item" onclick="setInd('logistics courier delivery service','📦','Logistics')"><span class="dd-item-emoji">📦</span>Logistics</div>
            <div class="dd-item" onclick="setInd('gaming esports platform India','🎮','Gaming')"><span class="dd-item-emoji">🎮</span>Gaming</div>
            <div class="dd-item" onclick="setInd('solar energy green environment startup','🌱','Green / Energy')"><span class="dd-item-emoji">🌱</span>Green / Energy</div>
          </div>
        </div>

        <!-- Domain style dropdown -->
        <div class="dropdown-wrap" id="domWrap">
          <div class="search-pill domain-pill" id="domPill" onclick="toggleDd('domMenu')">
            <span id="domPillText">.com</span>
            <svg viewBox="0 0 24 24"><polyline points="6 9 12 15 18 9"/></svg>
          </div>
          <div class="dropdown-menu domain-menu" id="domMenu">
            <span class="dd-label">Domain extension</span>
            <div class="dom-opt selected" onclick="setDom('.com',this)">.com <span class="dom-badge">Most trusted</span></div>
            <div class="dom-opt" onclick="setDom('.in',this)">.in <span class="dom-badge">India</span></div>
            <div class="dom-opt" onclick="setDom('.co.in',this)">.co.in <span class="dom-badge">India biz</span></div>
            <div class="dom-opt" onclick="setDom('.ai',this)">.ai <span class="dom-badge">Tech / AI</span></div>
            <div class="dom-opt" onclick="setDom('.tv',this)">.tv <span class="dom-badge">Media</span></div>
            <div class="dom-opt" onclick="setDom('mix',this)">✦ Mix All <span class="dom-badge">All types</span></div>
          </div>
        </div>

        <div class="search-spacer"></div>

        <!-- Search icon button -->
        <button class="search-icon-btn" onclick="go()" title="Search">
          <svg viewBox="0 0 24 24"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
        </button>

        <!-- Generate button -->
        <button class="gen-btn" onclick="go()">
          <span class="gen-btn-icon">✦</span>
          <span class="gen-btn-text">Generate</span>
        </button>
      </div>
    </div>
  </div>
</div>



<!-- INDUSTRIES — pill style -->
<div class="industry-wrap">
  <div class="sec-label">Popular Industries — tap to search instantly</div>
  <div class="ind-scroll">
    <div class="ind-pill" onclick="sx('online grocery delivery','grocery')"><span class="ind-emoji">🛒</span>Grocery</div>
    <div class="ind-pill" onclick="sx('digital marketing agency','marketing')"><span class="ind-emoji">📣</span>Marketing</div>
    <div class="ind-pill" onclick="sx('women fashion boutique','fashion')"><span class="ind-emoji">👗</span>Fashion</div>
    <div class="ind-pill" onclick="sx('CA accounting firm','finance')"><span class="ind-emoji">📊</span>CA / Finance</div>
    <div class="ind-pill" onclick="sx('online coaching education platform','education')"><span class="ind-emoji">🎓</span>Education</div>
    <div class="ind-pill" onclick="sx('restaurant food delivery','restaurant')"><span class="ind-emoji">🍽️</span>Restaurant</div>
    <div class="ind-pill" onclick="sx('real estate property India','realestate')"><span class="ind-emoji">🏠</span>Real Estate</div>
    <div class="ind-pill" onclick="sx('healthcare clinic hospital','healthcare')"><span class="ind-emoji">🏥</span>Healthcare</div>
    <div class="ind-pill" onclick="sx('travel agency tours India','travel')"><span class="ind-emoji">✈️</span>Travel</div>
    <div class="ind-pill" onclick="sx('software IT company India','tech')"><span class="ind-emoji">💻</span>IT / Software</div>
    <div class="ind-pill" onclick="sx('beauty salon spa','beauty')"><span class="ind-emoji">💆</span>Beauty & Spa</div>
    <div class="ind-pill" onclick="sx('gym fitness center','fitness')"><span class="ind-emoji">💪</span>Fitness</div>
    <div class="ind-pill" onclick="sx('law firm legal services India','legal')"><span class="ind-emoji">⚖️</span>Legal</div>
    <div class="ind-pill" onclick="sx('ecommerce online store India','ecommerce')"><span class="ind-emoji">🛍️</span>E-Commerce</div>
    <div class="ind-pill" onclick="sx('photography studio','photography')"><span class="ind-emoji">📸</span>Photography</div>
    <div class="ind-pill" onclick="sx('wedding planning event management','events')"><span class="ind-emoji">💍</span>Events</div>
    <div class="ind-pill" onclick="sx('interior design home decor','interior')"><span class="ind-emoji">🛋️</span>Interior</div>
    <div class="ind-pill" onclick="sx('automotive car service','auto')"><span class="ind-emoji">🚗</span>Automotive</div>
    <div class="ind-pill" onclick="sx('fintech payments startup India','fintech')"><span class="ind-emoji">💳</span>Fintech</div>
    <div class="ind-pill" onclick="sx('online pharmacy medicine delivery','pharma')"><span class="ind-emoji">💊</span>Pharma</div>
    <div class="ind-pill" onclick="sx('pet care grooming veterinary','pets')"><span class="ind-emoji">🐾</span>Pet Care</div>
    <div class="ind-pill" onclick="sx('cloud kitchen tiffin service','tiffin')"><span class="ind-emoji">🍱</span>Cloud Kitchen</div>
    <div class="ind-pill" onclick="sx('news media blog portal India','media')"><span class="ind-emoji">📰</span>News / Media</div>
    <div class="ind-pill" onclick="sx('gaming esports platform India','gaming')"><span class="ind-emoji">🎮</span>Gaming</div>
    <div class="ind-pill" onclick="sx('startup SaaS B2B product','saas')"><span class="ind-emoji">🚀</span>SaaS / Startup</div>
    <div class="ind-pill" onclick="sx('kids toys children products','kids')"><span class="ind-emoji">🧸</span>Kids & Toys</div>
    <div class="ind-pill" onclick="sx('agriculture farming rural India','agri')"><span class="ind-emoji">🌾</span>Agriculture</div>
    <div class="ind-pill" onclick="sx('logistics courier delivery service','logistics')"><span class="ind-emoji">📦</span>Logistics</div>
    <div class="ind-pill" onclick="sx('music streaming artist platform','music')"><span class="ind-emoji">🎵</span>Music</div>
    <div class="ind-pill" onclick="sx('solar energy green environment startup','green')"><span class="ind-emoji">🌱</span>Green / Energy</div>
  </div>
</div>

</div><!-- end homePage -->

<div class="services">
  <div class="sec-label" style="margin-bottom:20px;">Our Services</div>
  <div class="svc-grid">
    <div class="svc-card card-tm">
      <div class="svc-emoji">⚖️</div>
      <div class="svc-content">
        <div class="svc-tag">Trademark</div>
        <div class="svc-title">Protect Your Brand</div>
        <div class="svc-desc">Secure your brand name legally. Trademark search is free — registration from ₹1,499.</div>
      </div>
      <div class="svc-footer">
        <div class="tm-card-btns">
          <a href="https://www.legaldocs.co.in/trademark-search" target="_blank" class="tm-card-btn">🔎 Free TM Check →</a>
          <a href="https://www.legaldocs.co.in/trademark-registration" target="_blank" class="tm-card-btn">✅ Register Now →</a>
        </div>
      </div>
    </div>
    <a class="svc-card card-domain" href="https://www.namecheap.com/domains/" target="_blank">
      <div class="svc-emoji">🌐</div>
      <div class="svc-content">
        <div class="svc-tag">Domain Registration</div>
        <div class="svc-title">Buy Your Domain</div>
        <div class="svc-desc">Register your domain at the best price. .in from ₹599/yr. .com from ₹899/yr.</div>
      </div>
      <div class="svc-footer">
        <span class="svc-learn">Buy Domain <span class="svc-learn-arrow">→</span></span>
      </div>
    </a>
    <a class="svc-card card-logo" href="https://looka.com" target="_blank">
      <div class="svc-emoji">🎨</div>
      <div class="svc-content">
        <div class="svc-tag">Business Logo</div>
        <div class="svc-title">Create Free Logo</div>
        <div class="svc-desc">AI-powered professional logo, instantly ready. No designer needed.</div>
      </div>
      <div class="svc-footer">
        <span class="svc-learn">Generate Free <span class="svc-learn-arrow">→</span></span>
      </div>
    </a>
    <div class="svc-card card-web">
      <div class="svc-emoji">💻</div>
      <div class="svc-content">
        <div class="svc-tag">Website · ₹199/month</div>
        <div class="svc-title">Get a Website</div>
        <div class="svc-desc">Professional website for just ₹199/month. Perfect for Indian entrepreneurs.</div>
      </div>
      <div class="svc-footer">
        <span class="svc-learn">Get Started <span class="svc-learn-arrow">→</span></span>
      </div>
    </div>
  </div>
</div>

<div class="how" id="how">
  <div class="sec-label" style="margin-bottom:14px;">How It Works</div>
  <div class="how-grid">
    <div class="how-card">
      <div class="how-icon">✍️</div>
      <div class="how-num">01</div>
      <div class="how-h">Describe your business</div>
      <div class="how-p">Type in English, Hindi, or Hinglish. More detail = better names.</div>
    </div>
    <div class="how-card">
      <div class="how-icon">✨</div>
      <div class="how-num">02</div>
      <div class="how-h">Orbit07 generates names</div>
      <div class="how-p">Orbit07 AI instantly generates unlimited creative, brandable domain names.</div>
    </div>
    <div class="how-card">
      <div class="how-icon">🚀</div>
      <div class="how-num">03</div>
      <div class="how-h">Save, buy & launch</div>
      <div class="how-p">Heart your favourites, check availability, buy instantly.</div>
    </div>
  </div>
</div>

<div class="monkb-wrap">
  <div class="monkb">
    <div class="mb1"></div><div class="mb2"></div>
    <div class="ml">
      <div class="ml-tag">Powered by Orbit07</div>
      <div class="ml-title">Sell more on Instagram<br>with <span>MONKB</span></div>
      <div class="ml-desc">Link in Bio + Auto DM + Order Management — everything an Instagram seller needs.</div>
      <div class="ml-btns">
        <a href="#" class="ml-cta">🚀 Try MONKB Free</a>
        <a href="#" class="ml-ghost">Learn More →</a>
      </div>
    </div>
    <div class="mr">
      <div class="mr-emoji">🐒</div>
      <div class="mr-badge">
        <div class="mr-name">MONKB</div>
        <div class="mr-sub">by Orbit07</div>
      </div>
    </div>
  </div>
</div>

<footer>
  <div class="foot-logo">orbit07.ai</div>
  <div class="foot-made">Made with ❤️ in India</div>
  <div class="foot-links">
    <a class="foot-link" href="#">Privacy</a>
    <a class="foot-link" href="#">Terms</a>
  </div>
</footer>

<!-- RESULTS PAGE -->
<div id="resultsPage">
  <div class="rp-nav">
    <button class="rp-back" onclick="goHome()">← Back</button>
    <div class="rp-title" id="rpTitle">Results</div>
    <div class="rp-count" id="rpCount">Loading...</div>
  </div>
  <div class="rp-saved-wrap">
    <div class="rp-saved-box" id="rpSavedBox">
      <div class="rp-saved-hd">
        <div class="rp-saved-hd-left">❤️ Saved Domains <span class="saved-cnt" id="savedCnt">0</span></div>
        <button class="rp-saved-clear" onclick="clearAllLiked()">Clear All</button>
      </div>
      <div class="rp-saved-list" id="rpSavedList"></div>
    </div>
  </div>
  <div class="rp-grid-wrap">
    <div class="rp-res-label" id="rpResLabel"></div>
    <div class="logo-grid" id="rpGrid"></div>
  </div>
</div>

<!-- MULTI-STEP MODAL -->
<div class="step-modal" id="stepModal">
  <div class="step-box">
    <div class="step-progress">
      <div class="step-dot active" id="sdot1"></div>
      <div class="step-dot" id="sdot2"></div>
      <div class="step-dot" id="sdot3"></div>
    </div>
    <div id="stepContent"></div>
  </div>
</div>

<script>
const GROQ_KEY='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';
let tl='.com';
let liked=JSON.parse(localStorage.getItem('o7_liked')||'[]');
const CS=15;

// State for multi-step
let stepState={industry:'',nameLength:'mix',tld:'.com'};
let currentStep=1;

/* ===== DROPDOWN LOGIC ===== */
function toggleDd(id){
  const menu=document.getElementById(id);
  const isOpen=menu.classList.contains('open');
  // close all
  document.querySelectorAll('.dropdown-menu').forEach(m=>m.classList.remove('open'));
  if(!isOpen)menu.classList.add('open');
}
document.addEventListener('click',function(e){
  if(!e.target.closest('.dropdown-wrap'))
    document.querySelectorAll('.dropdown-menu').forEach(m=>m.classList.remove('open'));
});

function setInd(query,emoji,label){
  document.getElementById('indPillIcon').textContent=emoji;
  document.getElementById('indPillText').textContent=label;
  document.getElementById('indMenu').classList.remove('open');
  // mark selected
  document.querySelectorAll('#indMenu .dd-item').forEach(i=>i.classList.remove('selected'));
  event.currentTarget.classList.add('selected');
  // pre-fill input if field is empty
  const bi=document.getElementById('bi');
  if(query && !bi.value.trim()) bi.value=query;
}

function setDom(val,el){
  tl=val;
  document.getElementById('domPillText').textContent=val==='mix'?'✦ Mix':val;
  document.getElementById('domMenu').classList.remove('open');
  document.querySelectorAll('.dom-opt').forEach(o=>o.classList.remove('selected'));
  el.classList.add('selected');
}

/* ===== INDUSTRY QUICK PILL CLICK ===== */
function sx(query,indKey){
  const bi=document.getElementById('bi');
  const existing=bi.value.trim();
  if(existing && existing.length>2){
    bi.value=existing+', '+query;
  } else {
    bi.value=query;
  }
  go();
}

/* ===== RESULTS PAGE ===== */
function openResults(){
  document.getElementById('homePage').style.display='none';
  const rp=document.getElementById('resultsPage');
  rp.classList.add('open');rp.scrollTop=0;
}
function goHome(){
  document.getElementById('homePage').style.display='block';
  document.getElementById('resultsPage').classList.remove('open');
}

/* ===== LIKED ===== */
function saveLiked(){localStorage.setItem('o7_liked',JSON.stringify(liked));renderSaved()}
function renderSaved(){
  const box=document.getElementById('rpSavedBox');
  const list=document.getElementById('rpSavedList');
  const cnt=document.getElementById('savedCnt');
  if(!liked.length){box.classList.remove('show');return}
  box.classList.add('show');
  if(cnt)cnt.textContent=liked.length;
  list.innerHTML=liked.map(d=>`<div class="rp-saved-pill"><span>${d}</span><button onclick="removeLiked('${d.replace(/'/g,"\'")}')">×</button></div>`).join('');
}
function removeLiked(d){
  liked=liked.filter(x=>x!==d);saveLiked();
  document.querySelectorAll('.lc-like').forEach(b=>{if(b.dataset.domain===d){b.classList.remove('liked');b.innerHTML='♡'}});
}
function clearAllLiked(){
  liked=[];saveLiked();
  document.querySelectorAll('.lc-like').forEach(b=>{b.classList.remove('liked');b.innerHTML='♡'});
}
function toggleLike(domain,btn){
  if(liked.includes(domain)){liked=liked.filter(x=>x!==domain);btn.classList.remove('liked');btn.innerHTML='♡'}
  else{liked.push(domain);btn.classList.add('liked');btn.innerHTML='♥'}
  saveLiked();
}

/* ===== LOADER ===== */
const loadingWords=[
  ['✦ Analyzing','🔍 Industry','💡 Brainstorming','🌐 Domains'],
  ['🚀 Generating','✨ Creative','🎯 Brandable','💎 Names'],
  ['⚡ AI Working','🧠 Processing','🌟 Crafting','🎨 Ideas'],
];
function showLoader(){
  const wordSet=loadingWords[Math.floor(Math.random()*loadingWords.length)];
  const wordsHTML=wordSet.map((w,i)=>`<div class="ai-word" style="animation-delay:${i*0.15}s">${w}</div>`).join('');
  return`<div class="ai-loader">
    <div class="ai-orb">
      <div class="ai-orb-ring"></div>
      <div class="ai-orb-ring2"></div>
      <div class="ai-orb-core">✦</div>
    </div>
    <div class="ai-loader-text">
      <div class="ai-loader-title">Orbit07 AI is working...</div>
      <div class="ai-loader-sub">Generating unlimited brand names for you</div>
      <div class="ai-words">${wordsHTML}</div>
    </div>
    <div class="ai-progress"><div class="ai-progress-bar"></div></div>
  </div>`;
}

/* ===== GENERATE ===== */
async function go(){
  const biz=document.getElementById('bi').value.trim();
  if(!biz)return;

  document.getElementById('rpTitle').textContent='"'+biz+'"';
  document.getElementById('rpCount').textContent='Loading...';
  document.getElementById('rpResLabel').textContent='';
  document.getElementById('rpGrid').innerHTML=showLoader();
  openResults();
  renderSaved();

  const prompt=`You are Orbit07, world-class domain branding AI. Generate exactly 100 unique creative brandable domain names for: "${biz}".
TLD: ${tl==='mix'?'mix of .com .in .co.in .ai .tv':tl}.
Rules: short memorable professional, mix compound/portmanteau/suffix(-ify-ly-hub-go-now-hq)/prefix(get-my-try-), no duplicates, include keyword-match names.
First 8: top:true, rest top:false. likely_available:true if made-up word, false if common phrase.
Respond ONLY raw JSON array no markdown no backticks:
[{"domain":"x.com","reason":"why","top":true,"likely_available":true}]
All 100 required.`;

  try{
    const r=await fetch('https://api.groq.com/openai/v1/chat/completions',{
      method:'POST',
      headers:{'Content-Type':'application/json','Authorization':'Bearer '+GROQ_KEY},
      body:JSON.stringify({model:'llama-3.3-70b-versatile',max_tokens:8000,temperature:0.93,messages:[{role:'user',content:prompt}]})
    });
    const d=await r.json();
    const raw=d.choices[0].message.content.replace(/```json|```/g,'').trim();
    const doms=JSON.parse(raw);
    document.getElementById('rpCount').textContent=doms.length+' names';
    document.getElementById('rpResLabel').textContent='✦ '+doms.length+' brand names for "'+biz+'"';
    document.getElementById('rpGrid').innerHTML=doms.map((x,i)=>{
      const iL=liked.includes(x.domain);
      const safe=x.domain.replace(/\\/g,'\\\\').replace(/'/g,"\\'");
      return`<div class="lc cs-${i%CS}" title="${(x.reason||'').replace(/"/g,'&quot;')}" style="animation-delay:${Math.min(i*.025,1.2)}s">
        <div class="lc-logo">
          ${x.top?'<div class="lc-top-badge">✦ TOP PICK</div>':''}
          <div class="lc-avail ${x.likely_available?'av':'un'}" title="${x.likely_available?'Likely available':'Possibly taken'}"></div>
          <div class="lc-name">${x.domain}</div>
        </div>
        <div class="lc-actions">
          <div class="lc-row">
            <button class="lc-like${iL?' liked':''}" data-domain="${x.domain}" onclick="toggleLike('${safe}',this)">${iL?'♥':'♡'}</button>
            <a class="lov-buy" href="https://www.namecheap.com/domains/registration/results/?domain=${encodeURIComponent(x.domain)}" target="_blank">Buy Now</a>
            <a class="lov-chk" href="https://www.godaddy.com/domainsearch/find?checkAvail=1&domainToCheck=${encodeURIComponent(x.domain)}" target="_blank">Check</a>
          </div>
        </div>
      </div>`;
    }).join('');
    renderSaved();
  }catch(e){
    document.getElementById('rpGrid').innerHTML='<div style="text-align:center;padding:60px 20px"><div style="font-size:40px;margin-bottom:12px">😕</div><div style="font-size:14px;color:#ef4444;font-weight:600">Something went wrong. Please try again.</div></div>';
    console.error(e);
  }
}
document.getElementById('bi').addEventListener('keydown',e=>{if(e.key==='Enter')go()});
</script>
</body>
</html>
