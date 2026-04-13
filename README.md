<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Muskan Shaikh — Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:ital,wght@0,700;1,400&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{font-family:'Inter',sans-serif;background:#0a0a0f;color:#e8e8f0;line-height:1.6;overflow-x:hidden;}
button{font-family:'Inter',sans-serif;cursor:pointer;border:none;background:none;}
::-webkit-scrollbar{width:3px;}
::-webkit-scrollbar-track{background:#0a0a0f;}
::-webkit-scrollbar-thumb{background:#2ec4b6;border-radius:3px;}

:root{
  --teal:#2ec4b6;--teal-g:#1aa99d;
  --violet:#7c6ff7;--amber:#f4a932;--rose:#f25c7e;--green:#3dd68c;
  --bg:#0a0a0f;--surface:#111118;--card:#16161f;
  --border:#1e1e2e;--border2:#252535;
  --t1:#e8e8f0;--t2:#9090a8;--t3:#555568;
  --nav-h:60px;
}

/* LOADER */
#loader{position:fixed;inset:0;background:var(--bg);z-index:9999;display:flex;align-items:center;justify-content:center;flex-direction:column;gap:1.2rem;transition:opacity .7s,visibility .7s;}
#loader.out{opacity:0;visibility:hidden;}
.ld-logo{font-family:'Playfair Display',serif;font-size:2.2rem;font-weight:700;background:linear-gradient(135deg,var(--teal),var(--violet));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
.ld-bar{width:140px;height:2px;background:var(--border2);border-radius:2px;overflow:hidden;}
.ld-fill{height:100%;background:linear-gradient(to right,var(--teal),var(--violet),var(--amber));animation:ldFill 1s .2s ease forwards;width:0;}
@keyframes ldFill{to{width:100%}}

/* PROGRESS */
#pgbar{position:fixed;top:0;left:0;height:2px;background:linear-gradient(to right,var(--teal),var(--violet));z-index:1001;width:0;pointer-events:none;transition:width .08s;}

/* NAV */
#nav{position:fixed;top:0;left:0;right:0;height:var(--nav-h);z-index:500;display:flex;align-items:center;justify-content:space-between;padding:0 clamp(1.2rem,5vw,4rem);background:rgba(10,10,15,.93);backdrop-filter:blur(18px);border-bottom:1px solid transparent;transition:border-color .3s;}
#nav.scrolled{border-bottom-color:var(--border);}
.logo{font-family:'Playfair Display',serif;font-size:1.25rem;font-weight:700;background:linear-gradient(90deg,var(--teal),var(--violet));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;cursor:pointer;}
.nav-links{display:flex;align-items:center;gap:.15rem;}
.nav-links button{font-size:.68rem;font-weight:500;letter-spacing:.1em;text-transform:uppercase;color:var(--t3);padding:.35rem .65rem;border-radius:.25rem;transition:all .2s;}
.nav-links button:hover,.nav-links button.active{color:var(--teal);background:rgba(46,196,182,.07);}
.nav-hire{font-size:.68rem;font-weight:600;color:var(--teal);border:1px solid rgba(46,196,182,.4);padding:.35rem 1rem;border-radius:2rem;transition:all .22s;margin-left:.5rem;white-space:nowrap;}
.nav-hire:hover{background:var(--teal);color:#0a0a0f;border-color:var(--teal);}

/* HAMBURGER */
.hbg{display:none;flex-direction:column;gap:5px;cursor:pointer;padding:.3rem;}
.hbg span{display:block;width:20px;height:2px;background:var(--t2);border-radius:2px;transition:all .28s;}
.hbg.open span:nth-child(1){transform:rotate(45deg) translate(5px,5px);}
.hbg.open span:nth-child(2){opacity:0;transform:translateX(-6px);}
.hbg.open span:nth-child(3){transform:rotate(-45deg) translate(5px,-5px);}

/* MOBILE MENU */
#mMenu{display:none;position:fixed;top:var(--nav-h);left:0;right:0;background:rgba(10,10,15,.97);backdrop-filter:blur(20px);border-bottom:1px solid var(--border);z-index:490;transform:translateY(-105%);transition:transform .32s cubic-bezier(.16,1,.3,1);}
#mMenu.open{transform:translateY(0);}
#mMenu li{list-style:none;}
#mMenu button{display:block;width:100%;text-align:left;padding:.8rem clamp(1.2rem,5vw,4rem);font-size:.82rem;font-weight:500;color:var(--t2);background:none;border:none;cursor:pointer;letter-spacing:.08em;text-transform:uppercase;transition:color .2s;}
#mMenu button:hover{color:var(--teal);}
.mob-cta{display:block;margin:1rem clamp(1.2rem,5vw,4rem);text-align:center;font-size:.78rem;font-weight:600;color:var(--teal);border:1px solid rgba(46,196,182,.35);padding:.6rem;border-radius:2rem;background:none;cursor:pointer;width:calc(100% - clamp(2.4rem,10vw,8rem));transition:all .22s;}
.mob-cta:hover{background:var(--teal);color:#0a0a0f;}

/* SECTIONS */
section{padding:clamp(3.5rem,7vw,6.5rem) clamp(1.2rem,5vw,4rem);}
.wrap{max-width:1080px;margin:0 auto;}
.lbl{display:inline-flex;align-items:center;gap:.55rem;font-size:.62rem;font-weight:600;letter-spacing:.2em;text-transform:uppercase;color:var(--t3);margin-bottom:.9rem;}
.lbl::before{content:'';width:16px;height:1px;}
.lbl.t::before{background:var(--teal);}
.lbl.v::before{background:var(--violet);}
.lbl.a::before{background:var(--amber);}
.stitle{font-family:'Playfair Display',serif;font-size:clamp(1.9rem,5vw,3.2rem);font-weight:700;line-height:1.1;letter-spacing:-.02em;margin-bottom:clamp(1.8rem,3.5vw,3rem);}
.stitle em{font-style:italic;font-weight:400;}
.stitle .tc{color:var(--teal);}
.stitle .vc{color:var(--violet);}
.stitle .ac{color:var(--amber);}

/* REVEAL */
[data-r]{opacity:0;transform:translateY(24px);transition:opacity .68s cubic-bezier(.16,1,.3,1),transform .68s cubic-bezier(.16,1,.3,1);}
[data-r=l]{transform:translateX(-24px);}
[data-r=r]{transform:translateX(24px);}
[data-r=s]{transform:scale(.96);}
[data-r].on{opacity:1;transform:none;}
[data-d="1"]{transition-delay:.1s;}[data-d="2"]{transition-delay:.18s;}[data-d="3"]{transition-delay:.26s;}[data-d="4"]{transition-delay:.34s;}

/* ── HERO ── */
.hero{min-height:100svh;display:flex;align-items:center;position:relative;overflow:hidden;padding-top:calc(var(--nav-h) + 1.5rem);}
.hero-bg{position:absolute;inset:0;pointer-events:none;}
.hgrid{position:absolute;inset:0;background-image:linear-gradient(rgba(46,196,182,.03) 1px,transparent 1px),linear-gradient(90deg,rgba(46,196,182,.03) 1px,transparent 1px);background-size:55px 55px;animation:gMove 22s linear infinite;}
@keyframes gMove{to{background-position:55px 55px;}}
.orb{position:absolute;border-radius:50%;filter:blur(85px);pointer-events:none;animation:oFloat 13s ease-in-out infinite;}
.ob1{width:min(480px,75vw);height:min(480px,75vw);background:radial-gradient(circle,rgba(46,196,182,.12),transparent 70%);top:-15%;right:-8%;animation-duration:15s;}
.ob2{width:min(320px,55vw);height:min(320px,55vw);background:radial-gradient(circle,rgba(124,111,247,.09),transparent 70%);bottom:-10%;left:-5%;animation-duration:19s;animation-direction:reverse;}
.ob3{width:min(180px,35vw);height:min(180px,35vw);background:radial-gradient(circle,rgba(244,169,50,.06),transparent 70%);top:40%;right:20%;animation-duration:11s;animation-delay:2s;}
@keyframes oFloat{0%,100%{transform:translateY(0)}50%{transform:translateY(-20px)}}

.hcon{position:relative;z-index:2;width:100%;max-width:1080px;margin:0 auto;}
.hbadge{display:inline-flex;align-items:center;gap:.5rem;background:rgba(46,196,182,.07);border:1px solid rgba(46,196,182,.18);color:var(--teal);font-size:.6rem;font-weight:600;letter-spacing:.18em;text-transform:uppercase;padding:.32rem .85rem;border-radius:2rem;margin-bottom:1.4rem;animation:fu .6s 1.3s both;}
.ldot{width:5px;height:5px;border-radius:50%;background:var(--green);position:relative;flex-shrink:0;}
.ldot::after{content:'';position:absolute;inset:-3px;border:1px solid var(--green);border-radius:50%;animation:lp 2s ease infinite;}
@keyframes lp{0%{opacity:1;transform:scale(1)}100%{opacity:0;transform:scale(2.2)}}

.hname{font-family:'Playfair Display',serif;font-size:clamp(3.2rem,10vw,7.5rem);font-weight:700;line-height:.92;letter-spacing:-.03em;margin-bottom:.3rem;animation:fu .8s 1.45s cubic-bezier(.16,1,.3,1) both;}
.hname .gr{background:linear-gradient(135deg,var(--teal),var(--violet) 50%,var(--amber));background-size:200% 200%;-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;animation:gm 6s ease infinite;}
@keyframes gm{0%,100%{background-position:0 50%}50%{background-position:100% 50%}}

.hrole{font-family:'Playfair Display',serif;font-size:clamp(1rem,3vw,1.7rem);font-style:italic;color:var(--t2);margin-bottom:1.4rem;min-height:2rem;animation:fu .6s 1.6s both;}
#tw{border-right:2px solid var(--teal);animation:bc .7s step-end infinite;}
@keyframes bc{0%,100%{border-color:var(--teal)}50%{border-color:transparent}}
.hdesc{font-size:clamp(.83rem,2.2vw,.95rem);color:var(--t2);line-height:1.9;max-width:540px;margin-bottom:1.8rem;animation:fu .6s 1.75s both;}
.hbtns{display:flex;gap:.65rem;flex-wrap:wrap;margin-bottom:2rem;animation:fu .6s 1.9s both;}
.btn{display:inline-flex;align-items:center;gap:.4rem;padding:.65rem 1.4rem;border-radius:.3rem;font-size:.75rem;font-weight:600;letter-spacing:.06em;cursor:pointer;font-family:'Inter',sans-serif;transition:all .22s;white-space:nowrap;}
.bp{background:linear-gradient(135deg,var(--teal),var(--teal-g));color:#0a0a0f;border:none;}
.bp:hover{transform:translateY(-2px);box-shadow:0 8px 22px rgba(46,196,182,.28);}
.bg{background:transparent;color:var(--t1);border:1px solid var(--border2);}
.bg:hover{border-color:var(--violet);color:var(--violet);transform:translateY(-2px);}

/* Hero contact strip */
.hstrip{display:flex;flex-wrap:wrap;gap:.6rem 1.2rem;animation:fu .6s 2.05s both;}
.hci{display:flex;align-items:center;gap:.4rem;cursor:pointer;transition:all .2s;}
.hci-ic{width:26px;height:26px;border-radius:.28rem;background:var(--card);border:1px solid var(--border);display:flex;align-items:center;justify-content:center;font-size:.7rem;transition:border-color .2s;flex-shrink:0;}
.hci span{font-size:.68rem;color:var(--t2);transition:color .2s;}
.hci:hover span{color:var(--t1);}
.hci.t:hover .hci-ic{border-color:var(--teal);}
.hci.v:hover .hci-ic{border-color:var(--violet);}
.hci.a:hover .hci-ic{border-color:var(--amber);}
.hci.r:hover .hci-ic{border-color:var(--rose);}

/* Hero stats */
.hstats{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;background:var(--border);border:1px solid var(--border);border-radius:.5rem;overflow:hidden;margin-top:2.5rem;max-width:500px;animation:fu .6s 2.2s both;}
.hs{background:var(--card);padding:1rem .8rem;text-align:center;}
.hs-v{font-family:'Playfair Display',serif;font-size:1.7rem;font-weight:700;line-height:1;display:block;}
.hs-v.t{color:var(--teal);}
.hs-v.v{color:var(--violet);}
.hs-v.a{color:var(--amber);}
.hs-v.r{color:var(--rose);font-size:1.1rem;margin-top:.2rem;}
.hs-k{font-size:.52rem;color:var(--t3);text-transform:uppercase;letter-spacing:.12em;display:block;margin-top:.25rem;}

@keyframes fu{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:translateY(0)}}

.scue{position:absolute;bottom:1.8rem;left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:.35rem;opacity:0;animation:fu .5s 2.5s forwards;}
.scue span{font-size:.55rem;letter-spacing:.2em;text-transform:uppercase;color:var(--t3);}
.sline{width:1px;height:26px;background:linear-gradient(to bottom,var(--t3),transparent);animation:sl 2.2s 3s ease infinite;}
@keyframes sl{0%{transform:scaleY(0);transform-origin:top}50%{transform:scaleY(1);transform-origin:top}51%{transform-origin:bottom}100%{transform:scaleY(0);transform-origin:bottom}}

/* ── ABOUT ── */
.about{background:var(--surface);}
.ag{display:grid;grid-template-columns:3fr 2fr;gap:clamp(2rem,5vw,4.5rem);align-items:start;}
.at p{font-size:.88rem;color:var(--t2);line-height:2;margin-bottom:1.1rem;}
.at strong{color:var(--t1);font-weight:600;}
.hl{background:linear-gradient(transparent 62%,rgba(46,196,182,.15) 62%);}
.ebox{background:var(--card);border:1px solid var(--border);border-left:3px solid var(--teal);border-radius:.5rem;padding:1.3rem 1.5rem;margin-top:1.4rem;}
.ebox-h{display:flex;justify-content:space-between;flex-wrap:wrap;gap:.4rem;margin-bottom:.35rem;}
.eorg{font-size:.8rem;font-weight:600;color:var(--teal);}
.eperiod{font-size:.6rem;color:var(--t3);font-family:monospace;}
.erole{font-size:.76rem;color:var(--t2);margin-bottom:.65rem;}
.eul{list-style:none;}
.eul li{font-size:.74rem;color:var(--t2);line-height:1.7;padding-left:.9rem;position:relative;margin-bottom:.25rem;}
.eul li::before{content:'›';position:absolute;left:0;color:var(--teal);}
.sg{display:grid;grid-template-columns:1fr 1fr;gap:1px;background:var(--border);border:1px solid var(--border);border-radius:.5rem;overflow:hidden;margin-bottom:1.4rem;}
.sv{background:var(--surface);padding:1.3rem 1.1rem;transition:background .2s;}
.sv:hover{background:var(--card);}
.sv-n{font-family:'Playfair Display',serif;font-size:2rem;font-weight:700;line-height:1;margin-bottom:.25rem;}
.sv-k{font-size:.56rem;letter-spacing:.12em;text-transform:uppercase;color:var(--t3);}
.tags{display:flex;flex-wrap:wrap;gap:.38rem;margin-top:.9rem;}
.tag{font-size:.63rem;padding:.28rem .7rem;border-radius:2rem;border:1px solid var(--border2);color:var(--t2);background:var(--card);cursor:default;transition:all .2s;}
.tag:hover{border-color:var(--teal);color:var(--teal);}

/* ── SKILLS — text only, no icons/visuals ── */
.skills{background:var(--bg);}
.sk-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.2rem;}
.skc{background:var(--card);border:1px solid var(--border);border-radius:.6rem;padding:1.5rem;transition:transform .28s,box-shadow .28s;}
.skc:hover{transform:translateY(-4px);}
.skc.c1:hover{box-shadow:0 14px 36px rgba(46,196,182,.1);}
.skc.c2:hover{box-shadow:0 14px 36px rgba(124,111,247,.1);}
.skc.c3:hover{box-shadow:0 14px 36px rgba(244,169,50,.08);}
.sk-head{font-size:.65rem;font-weight:700;letter-spacing:.16em;text-transform:uppercase;padding-bottom:.8rem;border-bottom:1px solid var(--border);margin-bottom:.9rem;}
.skc.c1 .sk-head{color:var(--teal);}
.skc.c2 .sk-head{color:var(--violet);}
.skc.c3 .sk-head{color:var(--amber);}
.sk-list{list-style:none;display:flex;flex-direction:column;gap:.1rem;}
.sk-list li{font-size:.8rem;color:var(--t2);padding:.32rem 0;border-bottom:1px solid rgba(255,255,255,.03);display:flex;align-items:center;gap:.5rem;}
.sk-list li::before{content:'';width:4px;height:4px;border-radius:50%;flex-shrink:0;}
.skc.c1 .sk-list li::before{background:var(--teal);}
.skc.c2 .sk-list li::before{background:var(--violet);}
.skc.c3 .sk-list li::before{background:var(--amber);}
.sk-list li:last-child{border-bottom:none;}
.exp-row{display:flex;flex-wrap:wrap;gap:.35rem;margin-top:1rem;padding-top:.9rem;border-top:1px solid var(--border);}
.etag{font-size:.58rem;padding:.2rem .55rem;border-radius:.2rem;background:rgba(124,111,247,.07);border:1px solid rgba(124,111,247,.18);color:var(--violet);}

/* ── PROJECTS ── */
.projects{background:var(--surface);}
.pj-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.2rem;}
.pj{background:var(--card);border:1px solid var(--border);border-radius:.6rem;padding:1.4rem;display:flex;flex-direction:column;cursor:pointer;position:relative;overflow:hidden;transition:transform .28s,border-color .28s,box-shadow .28s;}
.pj-bar{height:2px;width:32px;border-radius:2px;margin-bottom:.9rem;transition:width .35s cubic-bezier(.16,1,.3,1);}
.pj:hover .pj-bar{width:100%;}
.pj.ct .pj-bar{background:var(--teal);}
.pj.cv .pj-bar{background:var(--violet);}
.pj.ca .pj-bar{background:var(--amber);}
.pj.cr .pj-bar{background:var(--rose);}
.pj.wide{grid-column:span 2;}
.pj:hover{transform:translateY(-4px);}
.pj.ct:hover{border-color:rgba(46,196,182,.22);box-shadow:0 14px 36px rgba(0,0,0,.28);}
.pj.cv:hover{border-color:rgba(124,111,247,.22);box-shadow:0 14px 36px rgba(0,0,0,.28);}
.pj.ca:hover{border-color:rgba(244,169,50,.22);box-shadow:0 14px 36px rgba(0,0,0,.28);}
.pj.cr:hover{border-color:rgba(242,92,126,.22);box-shadow:0 14px 36px rgba(0,0,0,.28);}
.pj-cat{font-size:.56rem;font-weight:700;letter-spacing:.14em;text-transform:uppercase;margin-bottom:.5rem;}
.pj.ct .pj-cat{color:var(--teal);}
.pj.cv .pj-cat{color:var(--violet);}
.pj.ca .pj-cat{color:var(--amber);}
.pj.cr .pj-cat{color:var(--rose);}
.pj-name{font-family:'Playfair Display',serif;font-size:1.1rem;font-weight:700;color:var(--t1);margin-bottom:.5rem;line-height:1.3;}
.pj-desc{font-size:.74rem;color:var(--t2);line-height:1.8;flex:1;margin-bottom:1.1rem;}
.pj-tags{display:flex;flex-wrap:wrap;gap:.3rem;margin-bottom:1.1rem;}
.ptag{font-size:.56rem;padding:.18rem .48rem;background:rgba(255,255,255,.03);border:1px solid var(--border2);border-radius:.2rem;color:var(--t3);}
.pj-foot{display:flex;align-items:center;justify-content:space-between;padding-top:.7rem;border-top:1px solid var(--border);}
.pj-meta{font-size:.58rem;color:var(--t3);}
.pj-gh{font-size:.6rem;font-weight:600;display:flex;align-items:center;gap:.22rem;transition:gap .2s;}
.pj.ct .pj-gh{color:var(--teal);}
.pj.cv .pj-gh{color:var(--violet);}
.pj.ca .pj-gh{color:var(--amber);}
.pj.cr .pj-gh{color:var(--rose);}
.pj:hover .pj-gh{gap:.4rem;}

/* ── RESEARCH ── */
.research{background:var(--bg);}
.rc{background:var(--card);border:1px solid var(--border);border-radius:.6rem;padding:clamp(1.4rem,4vw,2.2rem);display:grid;grid-template-columns:1fr auto;gap:2rem;align-items:start;animation:rpulse 4s ease-in-out infinite;}
@keyframes rpulse{0%,100%{box-shadow:none}50%{box-shadow:0 0 18px rgba(244,169,50,.1)}}
.rc:hover{border-color:rgba(244,169,50,.22);}
.rbadge{display:inline-flex;align-items:center;gap:.4rem;background:rgba(244,169,50,.07);border:1px solid rgba(244,169,50,.2);color:var(--amber);font-size:.58rem;letter-spacing:.14em;text-transform:uppercase;padding:.26rem .7rem;border-radius:2rem;margin-bottom:.8rem;}
.rtit{font-family:'Playfair Display',serif;font-size:clamp(1.2rem,3vw,1.6rem);font-weight:700;color:var(--t1);margin-bottom:.65rem;line-height:1.3;}
.rdesc{font-size:.78rem;color:var(--t2);line-height:1.85;}
.rven{background:rgba(255,255,255,.03);border:1px solid var(--border2);border-radius:.4rem;padding:.85rem 1.1rem;text-align:right;flex-shrink:0;}
.rven-l{font-size:.55rem;color:var(--t3);letter-spacing:.14em;text-transform:uppercase;display:block;margin-bottom:.22rem;}
.rven-n{font-size:.86rem;font-weight:600;color:var(--amber);display:block;}
.rdate{font-size:.6rem;color:var(--t3);display:block;margin-top:.35rem;font-family:monospace;}

/* ── CERTIFICATIONS — real org logos ── */
.certs{background:var(--surface);}
.cert-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.2rem;}
.cc{background:var(--card);border:1px solid var(--border);border-radius:.6rem;padding:1.4rem;display:flex;flex-direction:column;gap:.9rem;cursor:pointer;transition:transform .28s,border-color .28s,box-shadow .28s;}
.cc:hover{transform:translateY(-3px);box-shadow:0 12px 30px rgba(0,0,0,.28);}
.cc.oc:hover{border-color:rgba(200,60,50,.3);}
.cc.nc:hover{border-color:rgba(30,120,200,.3);}
.cc.ic:hover{border-color:rgba(0,120,215,.3);}
.cc.sc:hover{border-color:rgba(0,180,140,.3);}
.cc.dlc:hover{border-color:rgba(255,100,60,.3);}
.cc.pc:hover{border-color:rgba(243,112,33,.3);}

/* Org logo container */
.cc-logo{height:36px;display:flex;align-items:center;}
.cc-logo svg{max-height:36px;width:auto;}

.cc-body{flex:1;}
.cc-name{font-size:.84rem;font-weight:600;color:var(--t1);margin-bottom:.2rem;line-height:1.35;}
.cc-issuer{font-size:.7rem;font-weight:500;}
.cc.oc .cc-issuer{color:#e04030;}
.cc.nc .cc-issuer{color:#1e78c8;}
.cc.ic .cc-issuer{color:#0078d7;}
.cc.sc .cc-issuer{color:#00b48c;}
.cc.dlc .cc-issuer{color:#ff643c;}
.cc.pc .cc-issuer{color:#f37021;}
.cc-foot{display:flex;align-items:center;justify-content:space-between;padding-top:.8rem;border-top:1px solid var(--border);}
.cc-date{font-size:.6rem;color:var(--t3);font-family:monospace;}
.cc-cta{font-size:.62rem;font-weight:600;color:var(--violet);display:flex;align-items:center;gap:.22rem;transition:gap .2s;}
.cc:hover .cc-cta{gap:.38rem;}

/* ── EDUCATION ── */
.edu{background:var(--bg);}
.edu-grid{display:grid;grid-template-columns:1fr 1fr;gap:clamp(2rem,4vw,3.5rem);}
.tl{position:relative;padding-left:1.4rem;}
.tl::before{content:'';position:absolute;left:0;top:0;bottom:0;width:1px;background:var(--border);}
.tli{position:relative;padding-bottom:1.8rem;padding-left:1.4rem;}
.tli::before{content:'';position:absolute;left:-1.4rem;top:5px;width:7px;height:7px;border-radius:50%;background:var(--teal);border:2px solid var(--bg);box-shadow:0 0 0 1px var(--teal);}
.tl-p{font-size:.58rem;color:var(--t3);font-family:monospace;margin-bottom:.3rem;}
.tl-d{font-size:.88rem;font-weight:600;color:var(--t1);margin-bottom:.12rem;}
.tl-i{font-size:.74rem;color:var(--t2);}
.cpr{display:flex;gap:.65rem;flex-wrap:wrap;margin-top:1.4rem;}

/* Coding profile pills with real logos */
.cpill{display:inline-flex;align-items:center;gap:.5rem;padding:.45rem 1rem;background:var(--card);border:1px solid var(--border);border-radius:2rem;cursor:pointer;transition:all .22s;font-size:.7rem;font-weight:500;color:var(--t2);}
.cpill:hover{transform:translateY(-2px);}
.cpill.hr:hover{border-color:rgba(0,234,100,.3);color:#00ea64;}
.cpill.lc:hover{border-color:rgba(255,161,22,.3);color:#ffa116;}
.cpill svg{flex-shrink:0;}

/* ── CONTACT ── */
.contact{background:var(--surface);position:relative;overflow:hidden;}
.cg{display:grid;grid-template-columns:1fr 1fr;gap:clamp(2rem,5vw,4.5rem);align-items:center;}
.ct-title{font-family:'Playfair Display',serif;font-size:clamp(2rem,5vw,3.5rem);font-weight:700;line-height:1.1;letter-spacing:-.02em;margin-bottom:1rem;}
.ct-title em{font-style:italic;color:var(--teal);}
.ct-sub{font-size:.86rem;color:var(--t2);line-height:1.9;margin-bottom:1.6rem;}
.clinks{display:flex;flex-direction:column;gap:.65rem;}
.cl{display:flex;align-items:center;gap:.9rem;padding:.95rem 1.1rem;background:var(--card);border:1px solid var(--border);border-radius:.45rem;cursor:pointer;transition:all .24s;}
.cl:hover{transform:translateX(4px);}
.cl.tc:hover{border-color:rgba(46,196,182,.25);background:rgba(46,196,182,.04);}
.cl.vc:hover{border-color:rgba(124,111,247,.25);background:rgba(124,111,247,.04);}
.cl.ac:hover{border-color:rgba(244,169,50,.25);background:rgba(244,169,50,.04);}
.cl.rc:hover{border-color:rgba(242,92,126,.25);background:rgba(242,92,126,.04);}
.cl-ic{width:34px;height:34px;border-radius:.3rem;display:flex;align-items:center;justify-content:center;font-size:.82rem;flex-shrink:0;}
.cl.tc .cl-ic{background:rgba(46,196,182,.08);}
.cl.vc .cl-ic{background:rgba(124,111,247,.08);}
.cl.ac .cl-ic{background:rgba(244,169,50,.08);}
.cl.rc .cl-ic{background:rgba(242,92,126,.08);}
.cl-l{font-size:.56rem;color:var(--t3);letter-spacing:.14em;text-transform:uppercase;display:block;}
.cl-v{font-size:.78rem;color:var(--t1);display:block;margin-top:.08rem;}
.cl-arr{margin-left:auto;color:var(--t3);font-size:.7rem;transition:all .22s;}
.cl:hover .cl-arr{transform:translate(3px,-3px);}
.cl.tc:hover .cl-arr{color:var(--teal);}
.cl.vc:hover .cl-arr{color:var(--violet);}
.cl.ac:hover .cl-arr{color:var(--amber);}
.cl.rc:hover .cl-arr{color:var(--rose);}

/* FOOTER */
footer{background:var(--bg);border-top:1px solid var(--border);padding:1.3rem clamp(1.2rem,5vw,4rem);display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:.6rem;font-size:.6rem;color:var(--t3);}
.fe{color:var(--teal);cursor:pointer;transition:opacity .2s;}
.fe:hover{opacity:.7;}

/* DOCK */
.dock{position:fixed;bottom:1.4rem;left:50%;transform:translateX(-50%);z-index:400;display:flex;gap:.3rem;background:rgba(10,10,15,.93);backdrop-filter:blur(18px);border:1px solid var(--border);border-radius:3rem;padding:.45rem .6rem;opacity:0;pointer-events:none;transition:opacity .28s;white-space:nowrap;}
.dock.show{opacity:1;pointer-events:all;}
.dk{display:flex;align-items:center;gap:.32rem;padding:.38rem .68rem;border-radius:2rem;font-size:.6rem;font-weight:500;color:var(--t3);cursor:pointer;transition:all .2s;}
.dk:hover{background:var(--card);}
.dk.t:hover{color:var(--teal);}
.dk.v:hover{color:var(--violet);}
.dk.a:hover{color:var(--amber);}
.dk.r:hover{color:var(--rose);}
.dkd{width:4px;height:4px;border-radius:50%;}
.dk.t .dkd{background:var(--teal);}
.dk.v .dkd{background:var(--violet);}
.dk.a .dkd{background:var(--amber);}
.dk.r .dkd{background:var(--rose);}
.dsep{width:1px;background:var(--border);align-self:stretch;margin:.12rem 0;}

#particles{position:fixed;inset:0;pointer-events:none;z-index:0;opacity:.28;}

/* ═══ RESPONSIVE ═══ */
@media(max-width:900px){
  .hbg{display:flex;}
  .nav-links,.nav-hire{display:none;}
  #mMenu{display:block;}
  .ag{grid-template-columns:1fr;}
  .sk-grid{grid-template-columns:1fr 1fr;}
  .pj-grid{grid-template-columns:1fr 1fr;}
  .pj.wide{grid-column:span 1;}
  .cert-grid{grid-template-columns:1fr 1fr;}
  .edu-grid{grid-template-columns:1fr;}
  .cg{grid-template-columns:1fr;}
  .rc{grid-template-columns:1fr;}
  .hstats{grid-template-columns:repeat(2,1fr);}
}
@media(max-width:560px){
  .sk-grid,.pj-grid,.cert-grid{grid-template-columns:1fr;}
  .hstats{grid-template-columns:repeat(2,1fr);}
  .hstrip{gap:.45rem .8rem;}
  .hci span{display:none;}
  .dock{bottom:.9rem;padding:.38rem .5rem;}
  .dk{padding:.32rem .5rem;font-size:.56rem;}
  footer{flex-direction:column;text-align:center;}
  .sg{grid-template-columns:1fr 1fr;}
}
</style>
</head>
<body>

<canvas id="particles"></canvas>
<div id="pgbar"></div>

<!-- LOADER -->
<div id="loader">
  <div class="ld-logo">MS</div>
  <div class="ld-bar"><div class="ld-fill"></div></div>
</div>

<!-- DOCK -->
<div class="dock" id="dock">
  <button class="dk a" onclick="go('mailto:2003shaikhmuskan@gmail.com')"><div class="dkd"></div>Email</button>
  <div class="dsep"></div>
  <button class="dk t" onclick="go('tel:+917000261170')"><div class="dkd"></div>Call</button>
  <div class="dsep"></div>
  <button class="dk v" onclick="go('https://linkedin.com/in/muskan-shaikh786')"><div class="dkd"></div>LinkedIn</button>
  <div class="dsep"></div>
  <button class="dk r" onclick="go('https://github.com/mus-shaikh')"><div class="dkd"></div>GitHub</button>
</div>

<!-- NAV -->
<nav id="nav">
  <button class="logo" onclick="ss('home')">Muskan Shaikh</button>
  <ul class="nav-links">
    <li><button onclick="ss('about')">About</button></li>
    <li><button onclick="ss('skills')">Skills</button></li>
    <li><button onclick="ss('projects')">Projects</button></li>
    <li><button onclick="ss('research')">Research</button></li>
    <li><button onclick="ss('certifications')">Certs</button></li>
    <li><button onclick="ss('education')">Education</button></li>
    <li><button onclick="ss('contact')">Contact</button></li>
  </ul>
  <button class="nav-hire" onclick="go('mailto:2003shaikhmuskan@gmail.com')">Hire Me</button>
  <button class="hbg" id="hbg" onclick="toggleMenu()" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- MOBILE MENU -->
<div id="mMenu">
  <ul>
    <li><button onclick="ss('about');cm()">About</button></li>
    <li><button onclick="ss('skills');cm()">Skills</button></li>
    <li><button onclick="ss('projects');cm()">Projects</button></li>
    <li><button onclick="ss('research');cm()">Research</button></li>
    <li><button onclick="ss('certifications');cm()">Certifications</button></li>
    <li><button onclick="ss('education');cm()">Education</button></li>
    <li><button onclick="ss('contact');cm()">Contact</button></li>
  </ul>
  <button class="mob-cta" onclick="go('mailto:2003shaikhmuskan@gmail.com');cm()">Hire Me →</button>
</div>

<!-- ═══ HERO ═══ -->
<section class="hero" id="home">
  <div class="hero-bg">
    <div class="hgrid"></div>
    <div class="orb ob1"></div><div class="orb ob2"></div><div class="orb ob3"></div>
  </div>
  <div class="hcon">
    <div class="hbadge"><div class="ldot"></div>Open to Opportunities · Bhopal, India</div>
    <div class="hname"><span class="gr">Muskan</span><br>Shaikh</div>
    <div class="hrole"><span id="tw"></span></div>
    <p class="hdesc">Passionate about building impactful AI &amp; ML applications. Translating complex problems into scalable, data-driven solutions — from predictive models to LLM-powered systems.</p>
    <div class="hbtns">
      <button class="btn bp" onclick="ss('projects')">Explore Projects →</button>
      <button class="btn bg" onclick="go('https://github.com/mus-shaikh')">GitHub ↗</button>
      <button class="btn bg" onclick="go('https://linkedin.com/in/muskan-shaikh786')">LinkedIn ↗</button>
    </div>
    <div class="hstrip">
      <div class="hci a" onclick="go('mailto:2003shaikhmuskan@gmail.com')"><div class="hci-ic">✉️</div><span>2003shaikhmuskan@gmail.com</span></div>
      <div class="hci t" onclick="go('tel:+917000261170')"><div class="hci-ic">📞</div><span>+91 7000 261 170</span></div>
      <div class="hci v" onclick="go('https://linkedin.com/in/muskan-shaikh786')"><div class="hci-ic" style="font-size:.58rem;font-weight:700;">in</div><span>muskan-shaikh786</span></div>
      <div class="hci r" onclick="go('https://github.com/mus-shaikh')"><div class="hci-ic">⚡</div><span>mus-shaikh</span></div>
    </div>
    <div class="hstats">
      <div class="hs"><span class="hs-v t" data-count="12">0</span><span class="hs-k">Projects</span></div>
      <div class="hs"><span class="hs-v v">98.4%</span><span class="hs-k">Accuracy</span></div>
      <div class="hs"><span class="hs-v a">IIM</span><span class="hs-k">Research</span></div>
      <div class="hs"><span class="hs-v r">Oracle<br>Certified</span><span class="hs-k">GenAI</span></div>
    </div>
  </div>
  <div class="scue"><span>Scroll</span><div class="sline"></div></div>
</section>

<!-- ═══ ABOUT ═══ -->
<section id="about" class="about">
  <div class="wrap">
    <div class="lbl t" data-r>About</div>
    <h2 class="stitle" data-r>About <em class="tc">me</em></h2>
    <div class="ag">
      <div data-r="l">
        <div class="at">
          <p>I'm a <strong>passionate developer</strong> with a strong interest in <strong>Artificial Intelligence and Machine Learning</strong>, focused on building impactful, real-world applications. I enjoy translating complex problems into efficient, scalable solutions using data-driven approaches.</p>
          <p>I have hands-on experience with <strong class="hl">Python, SQL, Pandas, and data visualization</strong>, along with practical exposure through projects involving <strong>predictive modeling</strong> and AI-powered insights — with exposure to NLP, deep learning (CNN), and generative AI (LLMs, RAG).</p>
          <p>I'm a <strong>quick learner</strong> who values <strong>clean code, intuitive design, and scalable architecture</strong>. I thrive in collaborative environments and actively participate in technical and creative activities — including painting and singing.</p>
        </div>
        <div class="ebox">
          <div class="ebox-h"><span class="eorg">Infosys Springboard</span><span class="eperiod">Feb 2026 – Apr 2026</span></div>
          <div class="erole">Data Visualization Intern</div>
          <ul class="eul">
            <li>Cleaned and analyzed tourism data using Power BI to extract trends and patterns</li>
            <li>Created interactive dashboards and maps to visualize location-based insights</li>
            <li>Developed a Streamlit web app with authentication and AI insights</li>
          </ul>
        </div>
      </div>
      <div data-r="r">
        <div class="sg">
          <div class="sv"><div class="sv-n" style="color:var(--teal)">12+</div><div class="sv-k">Projects</div></div>
          <div class="sv"><div class="sv-n" style="color:var(--violet)">98.4%</div><div class="sv-k">Accuracy</div></div>
          <div class="sv"><div class="sv-n" style="color:var(--amber)">IIM</div><div class="sv-k">Research</div></div>
          <div class="sv"><div class="sv-n" style="color:var(--rose)">3</div><div class="sv-k">Certs</div></div>
        </div>
        <p class="lbl" style="margin-bottom:.8rem;">Interests</p>
        <div class="tags">
          <span class="tag">🎨 Painting</span><span class="tag">🎵 Singing</span>
          <span class="tag">🤖 AI & ML</span><span class="tag">📊 Data Viz</span>
          <span class="tag">💡 DSA</span><span class="tag">🔬 Research</span>
          <span class="tag">🧠 NLP</span><span class="tag">🌱 Open Source</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ SKILLS — text only ═══ -->
<section id="skills" class="skills">
  <div class="wrap">
    <div class="lbl v" data-r>Technical Stack</div>
    <h2 class="stitle" data-r>Skills &amp; <em class="vc">Stack</em></h2>
    <div class="sk-grid">
      <div class="skc c1" data-r>
        <div class="sk-head">Data &amp; Analytics</div>
        <ul class="sk-list">
          <li>Python</li><li>SQL / MySQL</li><li>Pandas / NumPy</li>
          <li>Matplotlib / Seaborn</li><li>Power BI</li><li>EDA &amp; Feature Engineering</li>
        </ul>
      </div>
      <div class="skc c2" data-r data-d="1">
        <div class="sk-head">AI &amp; Machine Learning</div>
        <ul class="sk-list">
          <li>Classification / Regression</li><li>Clustering / PCA</li>
          <li>NLP / TF-IDF / NLTK</li><li>CNN / Deep Learning</li>
          <li>Scikit-learn</li><li>TensorFlow / Keras</li>
        </ul>
        <div class="exp-row">
          <span class="etag">LLM</span><span class="etag">RAG</span><span class="etag">Transformer</span><span class="etag">Embeddings</span><span class="etag">VectorDB</span>
        </div>
      </div>
      <div class="skc c3" data-r data-d="2">
        <div class="sk-head">Tools &amp; Deployment</div>
        <ul class="sk-list">
          <li>Jupyter Notebook</li><li>Streamlit</li><li>FastAPI</li>
          <li>Git &amp; GitHub</li><li>VS Code</li><li>DSA (C++)</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- ═══ PROJECTS ═══ -->
<section id="projects" class="projects">
  <div class="wrap">
    <div class="lbl t" data-r>Work</div>
    <h2 class="stitle" data-r>Featured <em class="tc">Projects</em></h2>
    <div class="pj-grid">
      <div class="pj ct wide" data-r onclick="go('https://github.com/mus-shaikh')">
        <div class="pj-bar"></div><div class="pj-cat">AI · Clustering · GenAI</div>
        <div class="pj-name">AI-Driven Heart Disease Clustering &amp; Insights</div>
        <p class="pj-desc">Built an AI app combining <strong style="color:var(--t1)">KMeans, PCA, and a Llama-based LLM</strong> to generate natural-language explanations for clustering results. End-to-end workflow: preprocessing, training, serialization, and Streamlit deployment.</p>
        <div class="pj-tags"><span class="ptag">Python</span><span class="ptag">KMeans</span><span class="ptag">PCA</span><span class="ptag">Streamlit</span><span class="ptag">Llama LLM</span><span class="ptag">Pandas</span></div>
        <div class="pj-foot"><span class="pj-meta">End-to-end AI workflow</span><span class="pj-gh">GitHub ↗</span></div>
      </div>
      <div class="pj cv" data-r data-d="1" onclick="go('https://github.com/mus-shaikh')">
        <div class="pj-bar"></div><div class="pj-cat">NLP · Emotion AI</div>
        <div class="pj-name">Emotion Detection System</div>
        <p class="pj-desc">NLP-based emotion detection using TF-IDF, tokenization, Naive Bayes and Logistic Regression classifiers.</p>
        <div class="pj-tags"><span class="ptag">Python</span><span class="ptag">NLTK</span><span class="ptag">TF-IDF</span><span class="ptag">Naive Bayes</span></div>
        <div class="pj-foot"><span class="pj-meta">Text Classification</span><span class="pj-gh">GitHub ↗</span></div>
      </div>
      <div class="pj cr" data-r onclick="go('https://github.com/mus-shaikh')">
        <div class="pj-bar"></div><div class="pj-cat">Deep Learning · CNN</div>
        <div class="pj-name">Brain Tumor Detection</div>
        <p class="pj-desc">CNN model for brain tumor image classification achieving <strong style="color:var(--t1)">87.8% accuracy</strong>. Evaluated Custom CNN, AlexNet, LeNet, ResNet.</p>
        <div class="pj-tags"><span class="ptag">Python</span><span class="ptag">TensorFlow</span><span class="ptag">Keras</span><span class="ptag">ResNet</span></div>
        <div class="pj-foot"><span class="pj-meta">87.8% accuracy · Medical AI</span><span class="pj-gh">GitHub ↗</span></div>
      </div>
      <div class="pj ca" data-r data-d="1" onclick="go('https://github.com/mus-shaikh')">
        <div class="pj-bar"></div><div class="pj-cat">ML · Healthcare</div>
        <div class="pj-name">Diabetes Prediction System</div>
        <p class="pj-desc">Classification models on healthcare datasets with FastAPI-deployed real-time inference and interactive dashboards.</p>
        <div class="pj-tags"><span class="ptag">Python</span><span class="ptag">Scikit-learn</span><span class="ptag">FastAPI</span><span class="ptag">Pandas</span></div>
        <div class="pj-foot"><span class="pj-meta">FastAPI deployment</span><span class="pj-gh">GitHub ↗</span></div>
      </div>
      <div class="pj ct" data-r data-d="2" onclick="go('https://github.com/mus-shaikh/Anomoly-Detection')">
        <div class="pj-bar"></div><div class="pj-cat">ML · Anomaly Detection</div>
        <div class="pj-name">Anomaly Detection System</div>
        <p class="pj-desc">XGBoost app detecting abnormal sensor behaviour using lag values and rolling statistics. Achieves <strong style="color:var(--t1)">98.4% accuracy</strong>.</p>
        <div class="pj-tags"><span class="ptag">XGBoost</span><span class="ptag">Streamlit</span><span class="ptag">Pandas</span><span class="ptag">Parquet</span></div>
        <div class="pj-foot"><span class="pj-meta">⭐ 1 · 98.4% accuracy</span><span class="pj-gh">GitHub ↗</span></div>
      </div>
      <div class="pj cv" data-r data-d="3" onclick="go('https://github.com/mus-shaikh/Mobile-Sales-Dashboard')">
        <div class="pj-bar"></div><div class="pj-cat">Analytics · Dashboard</div>
        <div class="pj-name">Mobile Sales Dashboard</div>
        <p class="pj-desc">Interactive BI dashboard for mobile sales KPIs, trend analysis, and visual storytelling for data-driven business decisions.</p>
        <div class="pj-tags"><span class="ptag">Power BI</span><span class="ptag">SQL</span><span class="ptag">Data Viz</span></div>
        <div class="pj-foot"><span class="pj-meta">Business Intelligence</span><span class="pj-gh">GitHub ↗</span></div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ RESEARCH ═══ -->
<section id="research" class="research">
  <div class="wrap">
    <div class="lbl a" data-r>Publication</div>
    <h2 class="stitle" data-r>Research <em class="ac">Work</em></h2>
    <div class="rc" data-r="s">
      <div>
        <div class="rbadge">📄 Accepted · Conference Paper</div>
        <div class="rtit">GNN–LLM Model for Financial Forecasting</div>
        <p class="rdesc">This study introduces a conceptual GNN–LLM hybrid framework for financial forecasting, grounded in comprehensive literature analysis and architectural planning. Combines Graph Neural Networks with Large Language Models to enable intelligent, context-aware market predictions.</p>
      </div>
      <div class="rven">
        <span class="rven-l">Conference</span>
        <span class="rven-n">IIM Nagpur</span>
        <span class="rdate">February 2026</span>
      </div>
    </div>
  </div>
</section>

<!-- ═══ CERTIFICATIONS — real logos ═══ -->
<section id="certifications" class="certs">
  <div class="wrap">
    <div class="lbl v" data-r>Credentials</div>
    <h2 class="stitle" data-r>Certifi<em class="vc">cations</em></h2>
    <div class="cert-grid">

      <!-- Oracle -->
      <div class="cc oc" data-r onclick="go('https://catalog-education.oracle.com/pls/apex/f?p=1010:26:0::::FSP_ORG_ID:41')">
        <div class="cc-logo">
          <!-- Oracle wordmark SVG -->
          <svg viewBox="0 0 120 28" fill="none" xmlns="http://www.w3.org/2000/svg" height="28">
            <text x="0" y="22" font-family="Arial,sans-serif" font-size="22" font-weight="700" fill="#C74634">Oracle</text>
          </svg>
        </div>
        <div class="cc-body">
          <div class="cc-name">Oracle Cloud Infrastructure Generative AI Professional</div>
          <div class="cc-issuer">Oracle University</div>
        </div>
        <div class="cc-foot"><span class="cc-date">Oct 2025</span><span class="cc-cta">View ↗</span></div>
      </div>

      <!-- NPTEL -->
      <div class="cc nc" data-r data-d="1" onclick="go('https://nptel.ac.in/noc/Ecertificate/')">
        <div class="cc-logo">
          <svg viewBox="0 0 100 28" fill="none" xmlns="http://www.w3.org/2000/svg" height="28">
            <rect width="28" height="28" rx="4" fill="#1e78c8"/>
            <text x="5" y="20" font-family="Arial,sans-serif" font-size="13" font-weight="700" fill="white">np</text>
            <text x="32" y="20" font-family="Arial,sans-serif" font-size="15" font-weight="700" fill="#1e78c8">NPTEL</text>
          </svg>
        </div>
        <div class="cc-body">
          <div class="cc-name">Python For Data Science</div>
          <div class="cc-issuer">NPTEL — IIT Madras</div>
        </div>
        <div class="cc-foot"><span class="cc-date">Mar 2025</span><span class="cc-cta">View ↗</span></div>
      </div>

      <!-- Infosys Springboard — Power BI -->
      <div class="cc ic" data-r data-d="2" onclick="go('https://infyspringboard.onwingspan.com/')">
        <div class="cc-logo">
          <svg viewBox="0 0 130 28" fill="none" xmlns="http://www.w3.org/2000/svg" height="28">
            <text x="0" y="20" font-family="Arial,sans-serif" font-size="14" font-weight="700" fill="#0078d7">Infosys</text>
            <text x="65" y="20" font-family="Arial,sans-serif" font-size="11" font-weight="500" fill="#555568">Springboard</text>
          </svg>
        </div>
        <div class="cc-body">
          <div class="cc-name">Power BI — Data Visualization</div>
          <div class="cc-issuer">Infosys Springboard</div>
        </div>
        <div class="cc-foot"><span class="cc-date">Sep 2024</span><span class="cc-cta">View ↗</span></div>
      </div>

      <!-- Simplilearn — Machine Learning -->
      <div class="cc sc" data-r data-d="1" onclick="go('https://www.simplilearn.com/skillup-certificate-landing')">
        <div class="cc-logo">
          <svg viewBox="0 0 140 28" fill="none" xmlns="http://www.w3.org/2000/svg" height="28">
            <circle cx="12" cy="14" r="10" fill="#00b48c"/>
            <text x="8" y="19" font-family="Arial,sans-serif" font-size="12" font-weight="700" fill="white">S</text>
            <text x="28" y="20" font-family="Arial,sans-serif" font-size="14" font-weight="700" fill="#00b48c">Simplilearn</text>
          </svg>
        </div>
        <div class="cc-body">
          <div class="cc-name">Machine Learning Certificate</div>
          <div class="cc-issuer">Simplilearn</div>
        </div>
        <div class="cc-foot"><span class="cc-date">2024</span><span class="cc-cta">View ↗</span></div>
      </div>

      <!-- Scaler — Deep Learning -->
      <div class="cc dlc" data-r data-d="2" onclick="go('https://www.scaler.com/topics/deep-learning/')">
        <div class="cc-logo">
          <svg viewBox="0 0 110 28" fill="none" xmlns="http://www.w3.org/2000/svg" height="28">
            <rect width="24" height="24" rx="5" y="2" fill="#ff643c"/>
            <text x="5" y="19" font-family="Arial,sans-serif" font-size="13" font-weight="700" fill="white">S</text>
            <text x="30" y="20" font-family="Arial,sans-serif" font-size="15" font-weight="700" fill="#ff643c">Scaler</text>
          </svg>
        </div>
        <div class="cc-body">
          <div class="cc-name">Deep Learning Certificate</div>
          <div class="cc-issuer">Scaler</div>
        </div>
        <div class="cc-foot"><span class="cc-date">2024</span><span class="cc-cta">View ↗</span></div>
      </div>

      <!-- Infosys DB cert -->
      <div class="cc ic" data-r data-d="3" onclick="go('https://infyspringboard.onwingspan.com/')">
        <div class="cc-logo">
          <svg viewBox="0 0 130 28" fill="none" xmlns="http://www.w3.org/2000/svg" height="28">
            <text x="0" y="20" font-family="Arial,sans-serif" font-size="14" font-weight="700" fill="#0078d7">Infosys</text>
            <text x="65" y="20" font-family="Arial,sans-serif" font-size="11" font-weight="500" fill="#555568">Springboard</text>
          </svg>
        </div>
        <div class="cc-body">
          <div class="cc-name">Database Management System</div>
          <div class="cc-issuer">Infosys Springboard</div>
        </div>
        <div class="cc-foot"><span class="cc-date">Sep 2024</span><span class="cc-cta">View ↗</span></div>
      </div>

    </div>
  </div>
</section>

<!-- ═══ EDUCATION ═══ -->
<section id="education" class="edu">
  <div class="wrap">
    <div class="lbl t" data-r>Background</div>
    <h2 class="stitle" data-r>Education &amp; <em class="tc">Journey</em></h2>
    <div class="edu-grid">
      <div data-r="l">
        <p class="lbl" style="margin-bottom:1.1rem;">Academic</p>
        <div class="tl">
          <div class="tli"><div class="tl-p">2022 – 2026</div><div class="tl-d">B.Tech — Computer Science &amp; Business Systems</div><div class="tl-i">Sagar Institute of Research &amp; Technology, Bhopal</div></div>
          <div class="tli"><div class="tl-p">2021 – 2022</div><div class="tl-d">CBSE Class 12th</div><div class="tl-i">Anand Vihar School</div></div>
          <div class="tli"><div class="tl-p">2019 – 2020</div><div class="tl-d">CBSE Class 10th</div><div class="tl-i">Anand Vihar School</div></div>
        </div>
        <p class="lbl" style="margin:1.4rem 0 .9rem;">Coding Profiles</p>
        <div class="cpr">
          <!-- HackerRank exact logo -->
          <button class="cpill hr" onclick="go('https://www.hackerrank.com/')">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none">
              <path d="M12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0z" fill="#00EA64"/>
              <path d="M8.5 7.5h1.8v3.7h3.4V7.5h1.8v9h-1.8v-3.7H10.3v3.7H8.5v-9z" fill="#333"/>
            </svg>
            HackerRank
          </button>
          <!-- LeetCode exact logo -->
          <button class="cpill lc" onclick="go('https://leetcode.com/')">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none">
              <path d="M13.483 0a1.374 1.374 0 0 0-.961.438L7.116 6.226l-3.854 4.126a5.266 5.266 0 0 0-1.209 2.104 5.35 5.35 0 0 0-.125.513 5.527 5.527 0 0 0 .062 2.362 5.83 5.83 0 0 0 .349 1.017 5.938 5.938 0 0 0 1.271 1.818l4.277 4.193.039.038c2.248 2.165 5.852 2.133 8.063-.074l2.396-2.392c.54-.54.54-1.414.003-1.955a1.378 1.378 0 0 0-1.951-.003l-2.396 2.392a3.021 3.021 0 0 1-4.205.038l-.02-.019-4.276-4.193c-.652-.64-.972-1.469-.948-2.263a2.68 2.68 0 0 1 .066-.523 2.545 2.545 0 0 1 .619-1.164L9.13 8.114c1.058-1.134 3.204-1.27 4.43-.278l3.501 2.831c.593.48 1.461.387 1.94-.207a1.384 1.384 0 0 0-.207-1.943l-3.5-2.831c-.8-.647-1.766-1.045-2.774-1.202l2.015-2.158A1.384 1.384 0 0 0 13.483 0zm-2.866 12.815a1.38 1.38 0 0 0-1.38 1.382 1.38 1.38 0 0 0 1.38 1.382H20.79a1.38 1.38 0 0 0 1.38-1.382 1.38 1.38 0 0 0-1.38-1.382z" fill="#FFA116"/>
            </svg>
            LeetCode
          </button>
        </div>
      </div>
      <div data-r="r">
        <p class="lbl" style="margin-bottom:1.1rem;">Experience &amp; Highlights</p>
        <div class="tl">
          <div class="tli"><div class="tl-p">Feb 2026 – Apr 2026</div><div class="tl-d">Data Visualization Intern</div><div class="tl-i">Infosys Springboard</div></div>
          <div class="tli"><div class="tl-p">February 2026</div><div class="tl-d">Research Paper — GNN–LLM Financial Forecasting</div><div class="tl-i">Accepted · IIM Nagpur Conference</div></div>
          <div class="tli"><div class="tl-p">Ongoing</div><div class="tl-d">Independent AI &amp; ML Projects</div><div class="tl-i">CNN, NLP, LLM, XGBoost, FastAPI, Streamlit</div></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ CONTACT ═══ -->
<section id="contact" class="contact">
  <div class="orb ob1" style="position:absolute;top:-15%;right:-8%;pointer-events:none;z-index:0;"></div>
  <div class="orb ob2" style="position:absolute;bottom:-10%;left:-5%;pointer-events:none;z-index:0;"></div>
  <div class="wrap" style="position:relative;z-index:1;">
    <div class="lbl t" data-r>Get in Touch</div>
    <div class="cg">
      <div data-r="l">
        <h2 class="ct-title">Let's build something <em>remarkable.</em></h2>
        <p class="ct-sub">Open to internships, research collaborations, and full-time roles in Data Analytics, AI/ML, and related fields. Have a project idea? Let's connect!</p>
        <button class="btn bp" onclick="go('https://github.com/mus-shaikh')">All Projects on GitHub →</button>
      </div>
      <div class="clinks" data-r="r">
        <div class="cl ac" onclick="go('mailto:2003shaikhmuskan@gmail.com')"><div class="cl-ic">✉️</div><div><span class="cl-l">Email</span><span class="cl-v">2003shaikhmuskan@gmail.com</span></div><span class="cl-arr">↗</span></div>
        <div class="cl tc" onclick="go('tel:+917000261170')"><div class="cl-ic">📞</div><div><span class="cl-l">Phone</span><span class="cl-v">+91 7000 261 170</span></div><span class="cl-arr">↗</span></div>
        <div class="cl vc" onclick="go('https://linkedin.com/in/muskan-shaikh786')"><div class="cl-ic" style="font-size:.7rem;font-weight:700;">in</div><div><span class="cl-l">LinkedIn</span><span class="cl-v">muskan-shaikh786</span></div><span class="cl-arr">↗</span></div>
        <div class="cl rc" onclick="go('https://github.com/mus-shaikh')"><div class="cl-ic">⚡</div><div><span class="cl-l">GitHub</span><span class="cl-v">github.com/mus-shaikh</span></div><span class="cl-arr">↗</span></div>
      </div>
    </div>
  </div>
</section>

<footer>
  <span>© 2026 Muskan Shaikh · <span class="fe" onclick="go('mailto:2003shaikhmuskan@gmail.com')">2003shaikhmuskan@gmail.com</span> · Bhopal, India</span>
  <span>CSBS · Data Analyst · AI Developer · Researcher</span>
</footer>

<script>
/* open link without sandbox interception */
function go(url){
  const a=document.createElement('a');
  a.href=url;a.target='_blank';a.rel='noopener noreferrer';
  document.body.appendChild(a);a.click();document.body.removeChild(a);
}

/* smooth scroll — offset by nav height */
function ss(id){
  const el=document.getElementById(id);if(!el)return;
  const nh=document.getElementById('nav').offsetHeight;
  window.scrollTo({top:el.getBoundingClientRect().top+window.scrollY-nh-6,behavior:'smooth'});
}

/* mobile menu */
function toggleMenu(){document.getElementById('hbg').classList.toggle('open');document.getElementById('mMenu').classList.toggle('open');}
function cm(){document.getElementById('hbg').classList.remove('open');document.getElementById('mMenu').classList.remove('open');}

/* close mobile menu on outside click */
document.addEventListener('click',function(e){
  const m=document.getElementById('mMenu');
  const h=document.getElementById('hbg');
  if(m.classList.contains('open')&&!m.contains(e.target)&&!h.contains(e.target))cm();
});

/* loader */
window.addEventListener('load',()=>setTimeout(()=>document.getElementById('loader').classList.add('out'),950));

/* typewriter */
(function(){
  const roles=['Data Analyst','AI & ML Developer','Researcher','Problem Solver'];
  const el=document.getElementById('tw');
  let ri=0,ci=0,del=false;
  setTimeout(function tick(){
    const w=roles[ri];
    if(!del){el.textContent=w.slice(0,++ci);if(ci===w.length){del=true;setTimeout(tick,1700);return;}}
    else{el.textContent=w.slice(0,--ci);if(ci===0){del=false;ri=(ri+1)%roles.length;setTimeout(tick,350);return;}}
    setTimeout(tick,del?60:90);
  },2000);
})();

/* progress + nav scroll + active + dock */
const navEl=document.getElementById('nav');
const dockEl=document.getElementById('dock');
const allSecs=[...document.querySelectorAll('section[id]')];
const nBtns=[...document.querySelectorAll('.nav-links button')];

window.addEventListener('scroll',()=>{
  const sy=window.scrollY;
  document.getElementById('pgbar').style.width=(sy/(document.body.scrollHeight-window.innerHeight)*100)+'%';
  navEl.classList.toggle('scrolled',sy>40);
  dockEl.classList.toggle('show',sy>window.innerHeight*0.55);
  let cur='';
  allSecs.forEach(s=>{if(sy>=s.offsetTop-130)cur=s.id;});
  nBtns.forEach(b=>{const fn=b.getAttribute('onclick')||'';b.classList.toggle('active',fn.includes("'"+cur+"'"));});
},{passive:true});

/* scroll reveal */
const revObs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting){e.target.classList.add('on');revObs.unobserve(e.target);}});
},{threshold:.09,rootMargin:'0px 0px -36px 0px'});
document.querySelectorAll('[data-r]').forEach(el=>revObs.observe(el));

/* counter animation */
const cntObs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(!e.isIntersecting)return;
    const el=e.target,t=+el.dataset.count;
    if(!t)return;
    let s=null;
    (function step(ts){if(!s)s=ts;const p=Math.min((ts-s)/1200,1);el.textContent=Math.floor(p*t)+'+';if(p<1)requestAnimationFrame(step);})(performance.now());
    cntObs.unobserve(el);
  });
},{threshold:.5});
document.querySelectorAll('[data-count]').forEach(el=>cntObs.observe(el));

/* particles */
(function(){
  const c=document.getElementById('particles'),ctx=c.getContext('2d');
  let W,H;
  const rsz=()=>{W=c.width=window.innerWidth;H=c.height=window.innerHeight;};
  rsz();window.addEventListener('resize',rsz,{passive:true});
  const COLS=['rgba(46,196,182,','rgba(124,111,247,','rgba(244,169,50,'];
  const dots=Array.from({length:45},()=>({x:Math.random()*1400,y:Math.random()*900,r:Math.random()*1.3+.3,vx:(Math.random()-.5)*.22,vy:(Math.random()-.5)*.22,c:COLS[Math.floor(Math.random()*3)],a:Math.random()*.38+.1}));
  (function draw(){
    ctx.clearRect(0,0,W,H);
    dots.forEach(d=>{d.x+=d.vx;d.y+=d.vy;if(d.x<0||d.x>W)d.vx*=-1;if(d.y<0||d.y>H)d.vy*=-1;ctx.beginPath();ctx.arc(d.x,d.y,d.r,0,Math.PI*2);ctx.fillStyle=d.c+d.a+')';ctx.fill();});
    requestAnimationFrame(draw);
  })();
})();
</script>
</body>
</html>
