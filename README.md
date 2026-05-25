<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>TradeLink Africa — Buy. Sell. Connect.</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;1,400&display=swap" rel="stylesheet"/>
<style>
:root{
  --g:#0a6638;--gl:#0d8a4a;--gd:#074d2b;
  --ac:#f5a623;--acl:#ffc04d;
  --bg:#0d1117;--bg2:#161b22;--bg3:#21262d;
  --tx:#e6edf3;--txm:#8b949e;--txl:#c9d1d9;
  --br:#30363d;--danger:#f85149;--ok:#3fb950;--warn:#d29922;
  --r:12px;--rl:20px;--ff:'Syne',sans-serif;--fb:'DM Sans',sans-serif;
  --tr:all .25s cubic-bezier(.4,0,.2,1);
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:var(--fb);background:var(--bg);color:var(--tx);line-height:1.6;-webkit-font-smoothing:antialiased;overflow-x:hidden}
h1,h2,h3,h4{font-family:var(--ff);font-weight:700;line-height:1.2}
a{color:inherit;text-decoration:none}
img{max-width:100%;display:block}
button{cursor:pointer;font-family:var(--fb)}
input,textarea,select{font-family:var(--fb)}
::-webkit-scrollbar{width:6px}::-webkit-scrollbar-track{background:var(--bg2)}::-webkit-scrollbar-thumb{background:var(--br);border-radius:3px}

/* LAYOUT */
.wrap{max-width:1200px;margin:0 auto;padding:0 20px}
.wrap-sm{max-width:620px;margin:0 auto;padding:0 20px}

/* BUTTONS */
.btn{display:inline-flex;align-items:center;gap:8px;padding:12px 28px;border-radius:var(--r);font-weight:600;font-size:.95rem;border:none;outline:none;transition:var(--tr);white-space:nowrap;cursor:pointer;text-decoration:none}
.btn-p{background:var(--g);color:#fff;box-shadow:0 0 20px rgba(10,102,56,.3)}
.btn-p:hover{background:var(--gl);transform:translateY(-2px);box-shadow:0 0 30px rgba(10,102,56,.5)}
.btn-a{background:var(--ac);color:#0d1117}
.btn-a:hover{background:var(--acl);transform:translateY(-2px)}
.btn-o{background:transparent;color:var(--tx);border:1.5px solid var(--br)}
.btn-o:hover{border-color:var(--g);color:var(--gl);transform:translateY(-2px)}
.btn-gh{background:transparent;color:var(--txm);padding:10px 16px}
.btn-gh:hover{color:var(--tx);background:var(--bg3);border-radius:var(--r)}
.btn-sm{padding:8px 18px;font-size:.85rem}
.btn-lg{padding:16px 36px;font-size:1.05rem}
.btn-full{width:100%;justify-content:center}
.btn:disabled{opacity:.5;cursor:not-allowed;transform:none!important}

/* FORMS */
.fg{display:flex;flex-direction:column;gap:6px;margin-bottom:18px}
.fl{font-size:.875rem;font-weight:500;color:var(--txl)}
.fi{background:var(--bg);border:1.5px solid var(--br);color:var(--tx);padding:12px 16px;border-radius:var(--r);font-size:.95rem;transition:var(--tr);width:100%;outline:none}
.fi:focus{border-color:var(--g);box-shadow:0 0 0 3px rgba(10,102,56,.15)}
.fi::placeholder{color:var(--txm)}
.fi.err{border-color:var(--danger)}
.ferr{font-size:.8rem;color:var(--danger);min-height:16px}
.fhint{font-size:.8rem;color:var(--txm)}
textarea.fi{resize:vertical;min-height:100px}
select.fi{appearance:none;cursor:pointer}
.fgrid{display:grid;grid-template-columns:1fr 1fr;gap:0 16px}

/* CARDS */
.card{background:var(--bg2);border:1px solid var(--br);border-radius:var(--rl);padding:24px;transition:var(--tr)}

/* BADGES */
.badge{display:inline-flex;align-items:center;gap:4px;padding:3px 10px;border-radius:20px;font-size:.75rem;font-weight:600}
.b-ok{background:rgba(63,185,80,.15);color:var(--ok);border:1px solid rgba(63,185,80,.3)}
.b-warn{background:rgba(210,153,34,.15);color:var(--warn);border:1px solid rgba(210,153,34,.3)}
.b-err{background:rgba(248,81,73,.15);color:var(--danger);border:1px solid rgba(248,81,73,.3)}
.b-p{background:rgba(10,102,56,.15);color:var(--gl);border:1px solid rgba(10,102,56,.3)}
.b-a{background:rgba(245,166,35,.15);color:var(--ac);border:1px solid rgba(245,166,35,.3)}

/* SECTION */
.sec{padding:96px 0}
.sh{text-align:center;margin-bottom:56px}
.st{font-size:clamp(1.8rem,4vw,2.6rem);font-weight:800;margin-bottom:12px}
.ss{color:var(--txm);font-size:1.05rem;max-width:520px;margin:0 auto}

/* UTILITIES */
.spinner{width:36px;height:36px;border:3px solid var(--br);border-top-color:var(--g);border-radius:50%;animation:spin .8s linear infinite;margin:0 auto}
@keyframes spin{to{transform:rotate(360deg)}}
.empty{text-align:center;padding:60px 24px;color:var(--txm)}
.empty-ico{font-size:3rem;margin-bottom:16px;opacity:.4}
.empty h3{color:var(--txl);margin-bottom:8px}
.fade{animation:fadeUp .4s ease forwards}
@keyframes fadeUp{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:translateY(0)}}
.grad{background:linear-gradient(135deg,var(--gl),var(--ac));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}

/* ═══════ NAVBAR ═══════ */
#nav{position:fixed;top:0;left:0;right:0;z-index:1000;padding:16px 0;transition:all .3s ease}
#nav.sc{background:rgba(13,17,23,.96);backdrop-filter:blur(20px);border-bottom:1px solid var(--br);padding:12px 0;box-shadow:0 4px 24px rgba(0,0,0,.4)}
.nav-in{display:flex;align-items:center;justify-content:space-between}
.nav-logo{display:flex;align-items:center;gap:10px;font-family:var(--ff);font-size:1.2rem;font-weight:800}
.nav-logo span{color:var(--gl)}
.nav-links{display:flex;align-items:center;gap:8px}
.nav-link{padding:8px 14px;border-radius:8px;font-size:.9rem;font-weight:500;color:var(--txm);transition:var(--tr)}
.nav-link:hover{color:var(--tx);background:var(--bg3)}
.ham{display:none;flex-direction:column;gap:5px;background:none;border:none;padding:6px;cursor:pointer}
.ham span{display:block;width:22px;height:2px;background:var(--tx);border-radius:2px;transition:var(--tr)}

/* nav user dropdown */
.nav-user{position:relative;margin-left:8px}
.nav-avt{display:flex;align-items:center;gap:8px;background:var(--bg3);border:1px solid var(--br);border-radius:30px;padding:4px 12px 4px 4px;cursor:pointer;transition:var(--tr);font-size:.875rem;font-weight:500}
.nav-avt:hover{border-color:var(--g)}
.nav-dd{position:absolute;top:calc(100% + 8px);right:0;background:var(--bg2);border:1px solid var(--br);border-radius:var(--r);min-width:180px;box-shadow:0 8px 40px rgba(0,0,0,.5);overflow:hidden;display:none}
.nav-dd.open{display:block;animation:fadeUp .15s ease}
.dd-item{display:flex;align-items:center;gap:10px;padding:10px 16px;font-size:.875rem;color:var(--txl);transition:var(--tr);background:none;border:none;width:100%;text-align:left;cursor:pointer}
.dd-item:hover{background:var(--bg3);color:var(--tx)}
.dd-item.red:hover{background:rgba(248,81,73,.1);color:var(--danger)}
.dd-div{border-top:1px solid var(--br);margin:4px 0}
.ava{border-radius:50%;object-fit:cover;background:var(--bg3);border:2px solid var(--br);display:flex;align-items:center;justify-content:center;overflow:hidden;flex-shrink:0;font-weight:700}
.ava-s{width:32px;height:32px;font-size:.8rem}
.ava-m{width:52px;height:52px;font-size:1.1rem}
.ava-l{width:80px;height:80px;font-size:1.8rem}
.ava-p{background:var(--g);color:#fff}

/* ═══════ PAGES ═══════ */
.page{display:none;min-height:100vh;padding-top:64px}
.page.act{display:block}

/* ═══════ HOME ═══════ */
#p-home.act{display:block}

/* HERO */
.hero{position:relative;min-height:100vh;display:flex;align-items:center;padding:120px 0 80px;overflow:hidden}
.hero-bg{position:absolute;inset:0;z-index:0}
.orb{position:absolute;border-radius:50%;filter:blur(80px);opacity:.15;pointer-events:none}
.orb1{width:600px;height:600px;background:var(--g);top:-100px;left:-100px;animation:fl1 8s ease-in-out infinite}
.orb2{width:400px;height:400px;background:var(--ac);bottom:0;right:100px;animation:fl2 10s ease-in-out infinite}
@keyframes fl1{0%,100%{transform:translate(0,0)}50%{transform:translate(40px,30px)}}
@keyframes fl2{0%,100%{transform:translate(0,0)}50%{transform:translate(-30px,-40px)}}
.hero-grid{position:absolute;inset:0;background-image:linear-gradient(var(--br) 1px,transparent 1px),linear-gradient(90deg,var(--br) 1px,transparent 1px);background-size:60px 60px;opacity:.12;mask-image:radial-gradient(ellipse at center,black 30%,transparent 80%);-webkit-mask-image:radial-gradient(ellipse at center,black 30%,transparent 80%)}
.hero-c{position:relative;z-index:1;max-width:820px}
.hero-badge{display:flex;align-items:center;gap:10px;color:var(--txm);font-size:.875rem;margin-bottom:24px}
.hero-h{font-size:clamp(2.4rem,6vw,4rem);font-weight:800;line-height:1.1;margin-bottom:20px}
.hero-sub{color:var(--txm);font-size:1.1rem;max-width:560px;margin-bottom:36px;line-height:1.7}
.hero-btns{display:flex;gap:14px;margin-bottom:32px;flex-wrap:wrap}
.hero-search{display:flex;align-items:center;gap:8px;background:var(--bg2);border:1px solid var(--br);border-radius:var(--rl);padding:6px 6px 6px 16px;max-width:560px;margin-bottom:56px;transition:var(--tr)}
.hero-search:focus-within{border-color:var(--g);box-shadow:0 0 0 3px rgba(10,102,56,.15)}
.hero-search input{background:none;border:none;outline:none;color:var(--tx);flex:1;padding:8px 10px;font-size:.95rem}
.hero-search input::placeholder{color:var(--txm)}
.hero-stats{display:flex;gap:40px;flex-wrap:wrap}
.hs-val{font-family:var(--ff);font-size:1.8rem;font-weight:800}
.hs-lbl{font-size:.8rem;color:var(--txm)}

/* CATEGORIES */
.cats-sec{background:var(--bg2);border-top:1px solid var(--br);border-bottom:1px solid var(--br)}
.cats-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(190px,1fr));gap:12px}
.cat-card{background:var(--bg2);border:1px solid var(--br);border-radius:var(--rl);padding:18px 20px;display:flex;align-items:center;gap:12px;transition:var(--tr);color:var(--txl);font-weight:500;cursor:pointer;font-size:.9rem}
.cat-card:hover{border-color:var(--g);transform:translateY(-2px);box-shadow:0 8px 24px rgba(0,0,0,.3)}

/* PRODUCTS GRID */
.pgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));gap:20px}
.mkt-filters{display:flex;align-items:center;justify-content:space-between;margin-bottom:28px;gap:12px;flex-wrap:wrap}
.fl-left{display:flex;gap:10px;flex-wrap:wrap}
.fsel{background:var(--bg2);border:1px solid var(--br);color:var(--tx);padding:8px 14px;border-radius:var(--r);font-size:.875rem;outline:none;cursor:pointer}
.fsel:focus{border-color:var(--g)}
.pc-wrap{background:var(--bg2);border:1px solid var(--br);border-radius:var(--rl);overflow:hidden;transition:var(--tr);display:flex;flex-direction:column;cursor:pointer}
.pc-wrap:hover{border-color:rgba(10,102,56,.5);transform:translateY(-4px);box-shadow:0 12px 40px rgba(0,0,0,.4)}
.pc-img{aspect-ratio:4/3;background:var(--bg3);display:flex;align-items:center;justify-content:center;font-size:5rem;position:relative;overflow:hidden}
.pc-cat{position:absolute;top:10px;left:10px;background:rgba(13,17,23,.85);border:1px solid var(--br);color:var(--txm);padding:3px 8px;border-radius:6px;font-size:.72rem;backdrop-filter:blur(8px)}
.pc-body{padding:16px;display:flex;flex-direction:column;gap:8px;flex:1}
.pc-title{font-family:var(--ff);font-size:.95rem;font-weight:600;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden}
.pc-price{font-size:1.15rem;font-weight:800;color:var(--gl);font-family:var(--ff)}
.pc-meta{display:flex;justify-content:space-between;font-size:.78rem;color:var(--txm)}
.pc-seller{display:flex;align-items:center;gap:8px;padding-top:8px;border-top:1px solid var(--br);font-size:.8rem;color:var(--txm);margin-top:auto}
.mini-ava{width:24px;height:24px;border-radius:50%;background:var(--g);display:flex;align-items:center;justify-content:center;font-size:.7rem;font-weight:700;color:#fff;flex-shrink:0}

/* HOW IT WORKS */
.how-sec{background:var(--bg2);border-top:1px solid var(--br);border-bottom:1px solid var(--br)}
.how-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:24px;margin-bottom:48px}
.how-card{background:var(--bg2);border:1px solid var(--br);border-radius:var(--rl);padding:28px;position:relative;overflow:hidden;transition:var(--tr)}
.how-card:hover{border-color:var(--g);transform:translateY(-4px)}
.how-n{font-family:var(--ff);font-size:3rem;font-weight:800;color:var(--br);position:absolute;top:12px;right:16px;line-height:1}
.how-ico{font-size:1.5rem;background:rgba(10,102,56,.1);border:1px solid rgba(10,102,56,.2);width:48px;height:48px;border-radius:12px;display:flex;align-items:center;justify-content:center;margin-bottom:16px}
.how-card h3{font-size:1rem;font-weight:700;margin-bottom:10px}
.how-card p{font-size:.875rem;color:var(--txm);line-height:1.6}

/* TESTIMONIALS */
.test-sec{background:var(--bg2);border-top:1px solid var(--br);border-bottom:1px solid var(--br)}
.tgrid{display:grid;grid-template-columns:repeat(3,1fr);gap:24px}
.tcard{background:var(--bg2);border:1px solid var(--br);border-radius:var(--rl);padding:28px;transition:var(--tr)}
.tcard:hover{border-color:rgba(245,166,35,.3);transform:translateY(-4px)}
.t-stars{color:var(--ac);margin-bottom:16px;font-size:1rem;letter-spacing:2px}
.t-text{color:var(--txm);font-size:.9rem;line-height:1.7;margin-bottom:20px;font-style:italic}
.t-auth{display:flex;align-items:center;gap:12px}
.t-ava{width:40px;height:40px;border-radius:50%;background:var(--g);display:flex;align-items:center;justify-content:center;font-weight:700;color:#fff;font-size:1.1rem;flex-shrink:0}
.t-name{font-weight:600;font-size:.9rem}
.t-role{font-size:.78rem;color:var(--txm)}

/* PERKS */
.perks-in{display:grid;grid-template-columns:1fr 1fr;gap:80px;align-items:center}
.plist{list-style:none;display:flex;flex-direction:column;gap:14px;margin-top:24px}
.plist li{display:flex;align-items:flex-start;gap:12px;font-size:.95rem;color:var(--txl)}
.pck{color:var(--gl);flex-shrink:0;font-weight:700}

/* CONTACT */
.contact-in{display:grid;grid-template-columns:1fr 1fr;gap:80px;align-items:start}
.c-details{display:flex;flex-direction:column;gap:16px}
.c-item{display:flex;align-items:center;gap:12px;color:var(--txm);font-size:.9rem}
.c-form{background:var(--bg2);border:1px solid var(--br);border-radius:var(--rl);padding:32px}

/* FOOTER */
footer{background:var(--bg2);border-top:1px solid var(--br);padding:80px 0 0;position:relative;overflow:hidden}
.f-glow{position:absolute;top:0;left:50%;transform:translateX(-50%);width:600px;height:2px;background:linear-gradient(90deg,transparent,var(--g),transparent)}
.f-in{display:grid;grid-template-columns:2fr 1fr 1fr 1.5fr;gap:48px;padding-bottom:56px}
.f-logo{font-family:var(--ff);font-size:1.3rem;font-weight:800;display:flex;align-items:center;gap:8px;margin-bottom:8px}
.f-tag{font-size:.8rem;letter-spacing:2px;text-transform:uppercase;color:var(--gl);font-weight:600;margin-bottom:12px}
.f-desc{color:var(--txm);font-size:.9rem;line-height:1.7;margin-bottom:20px}
.f-soc{display:flex;gap:12px}
.f-soc a{width:36px;height:36px;background:var(--bg3);border:1px solid var(--br);border-radius:8px;display:flex;align-items:center;justify-content:center;color:var(--txm);transition:var(--tr)}
.f-soc a:hover{background:var(--g);color:#fff;border-color:var(--g)}
.f-col{display:flex;flex-direction:column;gap:10px}
.f-col h4{font-size:.75rem;font-weight:700;letter-spacing:1.5px;text-transform:uppercase;color:var(--tx);margin-bottom:4px}
.f-col a{color:var(--txm);font-size:.9rem;transition:var(--tr)}
.f-col a:hover{color:var(--gl);padding-left:4px}
.f-bot{border-top:1px solid var(--br);padding:20px 0}
.f-bot-in{display:flex;justify-content:space-between;font-size:.8rem;color:var(--txm)}

/* ═══════ AUTH PAGES ═══════ */
.auth-wrap{min-height:100vh;padding:100px 0 60px;position:relative;overflow:hidden}
.auth-orb{position:fixed;width:600px;height:600px;background:radial-gradient(circle,rgba(10,102,56,.2),transparent 70%);top:-100px;right:-200px;border-radius:50%;pointer-events:none;z-index:0}
.auth-hdr{text-align:center;margin-bottom:32px;position:relative;z-index:1}
.auth-brand{display:inline-block;font-family:var(--ff);font-size:1.2rem;font-weight:800;margin-bottom:20px;color:var(--tx)}
.auth-hdr h2{font-size:1.8rem;margin-bottom:8px}
.auth-hdr p{color:var(--txm);font-size:.95rem}
.auth-form{padding:36px;position:relative;z-index:1}
.auth-sw{text-align:center;font-size:.9rem;color:var(--txm);margin-top:20px}
.auth-sw a{color:var(--gl);font-weight:600}
.demo-box{background:rgba(10,102,56,.1);border:1px solid rgba(10,102,56,.25);border-radius:var(--r);padding:12px 16px;font-size:.82rem;color:var(--txm);margin-bottom:8px;line-height:1.6}
.photo-row{display:flex;align-items:center;gap:16px;margin-bottom:24px;padding-bottom:24px;border-bottom:1px solid var(--br)}
.photo-prev{width:72px;height:72px;border-radius:50%;background:var(--bg3);border:2px dashed var(--br);display:flex;align-items:center;justify-content:center;color:var(--txm);overflow:hidden;position:relative}
.photo-prev img{width:100%;height:100%;object-fit:cover}
.photo-btn{position:absolute;bottom:0;right:0;width:24px;height:24px;border-radius:50%;background:var(--g);display:flex;align-items:center;justify-content:center;cursor:pointer;border:2px solid var(--bg2);font-size:.7rem}
.iw{position:relative}
.eye-btn{position:absolute;right:12px;top:50%;transform:translateY(-50%);background:none;border:none;cursor:pointer;color:var(--txm);font-size:.9rem}

/* ═══════ DASHBOARD ═══════ */
.dash-wrap{display:flex;min-height:100vh;padding-top:64px}
.dash-side{width:260px;flex-shrink:0;background:var(--bg2);border-right:1px solid var(--br);padding:24px 14px;position:sticky;top:64px;height:calc(100vh - 64px);overflow-y:auto;display:flex;flex-direction:column}
.side-user{display:flex;align-items:center;gap:12px;padding:14px;margin-bottom:8px;background:var(--bg3);border-radius:var(--r)}
.side-info{display:flex;flex-direction:column;min-width:0}
.side-info strong{font-size:.875rem;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.side-nav{display:flex;flex-direction:column;gap:2px;margin-top:12px;flex:1}
.snav-btn{display:flex;align-items:center;gap:10px;padding:11px 14px;border-radius:var(--r);background:none;border:none;color:var(--txm);font-size:.875rem;font-weight:500;text-align:left;transition:var(--tr);cursor:pointer;width:100%}
.snav-btn:hover{background:var(--bg3);color:var(--tx)}
.snav-btn.on{background:rgba(10,102,56,.15);color:var(--gl);border:1px solid rgba(10,102,56,.25)}
.snav-btn.out{color:var(--danger);margin-top:auto}
.snav-btn.out:hover{background:rgba(248,81,73,.1)}
.dash-main{flex:1;padding:32px;overflow-y:auto}
.d-sec{max-width:900px;display:none}
.d-sec.on{display:block}
.d-title{font-size:1.5rem;font-weight:800;margin-bottom:24px}
.d-hdr{display:flex;align-items:center;justify-content:space-between;margin-bottom:24px}
.d-hdr .d-title{margin-bottom:0}
.srow{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;margin-bottom:28px}
.scard{background:var(--bg2);border:1px solid var(--br);border-radius:var(--rl);padding:20px 24px;display:flex;flex-direction:column;gap:8px}
.sval{font-size:2rem;font-weight:800;font-family:var(--ff)}
.slbl{font-size:.85rem;color:var(--txm)}
.link-card{margin-bottom:24px}
.link-hdr{display:flex;align-items:center;gap:8px;font-weight:700;margin-bottom:12px}
.link-row{display:flex;align-items:center;gap:10px;background:var(--bg3);border:1px solid var(--br);border-radius:var(--r);padding:10px 14px;margin-bottom:6px}
.link-txt{flex:1;font-size:.85rem;color:var(--gl);overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.act-prompt{text-align:center;padding:48px 32px}
.act-prompt h3{font-size:1.2rem;margin-bottom:8px}
.act-prompt p{color:var(--txm);font-size:.9rem;max-width:400px;margin:0 auto}
/* table */
.tbl-wrap{overflow-x:auto;border:1px solid var(--br);border-radius:var(--rl)}
table{width:100%;border-collapse:collapse;font-size:.875rem}
th{text-align:left;padding:10px 14px;border-bottom:1px solid var(--br);color:var(--txm);font-weight:600;font-size:.72rem;text-transform:uppercase;background:var(--bg2)}
td{padding:12px 14px;border-bottom:1px solid rgba(48,54,61,.5);vertical-align:middle}
tr:last-child td{border-bottom:none}
tr:hover td{background:var(--bg3)}
.tp{display:flex;align-items:center;gap:10px}
.tt{width:40px;height:40px;border-radius:8px;background:var(--bg3);display:flex;align-items:center;justify-content:center;font-size:1.2rem;flex-shrink:0}
/* product form */
.pform{padding:32px}
.img-zone{border:2px dashed var(--br);border-radius:var(--rl);padding:32px;cursor:pointer;transition:var(--tr);min-height:180px;display:flex;align-items:center;justify-content:center}
.img-zone:hover{border-color:var(--g);background:rgba(10,102,56,.05)}
.up-ph{text-align:center;color:var(--txm)}
.up-ph p{font-weight:500;color:var(--txl);margin:8px 0 4px}
.up-ph span{font-size:.8rem}
.img-prevs{display:flex;gap:10px;flex-wrap:wrap;width:100%}
.ipi{width:80px;height:80px;border-radius:8px;overflow:hidden;border:2px solid var(--br);flex-shrink:0}
.ipi img{width:100%;height:100%;object-fit:cover}

/* ═══════ ACTIVATION PAGE ═══════ */
.act-layout{display:grid;grid-template-columns:1fr 1fr;gap:28px;align-items:start}
.act-perks{list-style:none;display:flex;flex-direction:column;gap:12px}
.act-perks li{display:flex;align-items:flex-start;gap:10px;font-size:.9rem;color:var(--txl)}

/* ═══════ ADMIN ═══════ */
.adm-hdr{background:var(--bg2);border-bottom:1px solid var(--br);padding:32px 0 0}
.adm-tabs{display:flex;gap:2px;overflow-x:auto}
.adm-tab{display:flex;align-items:center;gap:8px;padding:12px 20px;background:none;border:none;color:var(--txm);font-size:.875rem;font-weight:500;cursor:pointer;border-bottom:2px solid transparent;transition:var(--tr);white-space:nowrap}
.adm-tab:hover{color:var(--tx)}
.adm-tab.on{color:var(--gl);border-bottom-color:var(--g)}
.adm-body{padding:36px 0 80px}
.adm-sgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(180px,1fr));gap:16px;margin-bottom:40px}
.adm-sec{display:none}
.adm-sec.on{display:block}
.adm-title{font-size:1.3rem;font-weight:800;margin-bottom:20px}

/* ═══════ MODAL ═══════ */
.modal{position:fixed;inset:0;z-index:2000;background:rgba(0,0,0,.78);backdrop-filter:blur(6px);display:none;align-items:center;justify-content:center;padding:20px}
.modal.open{display:flex}
.modal-box{background:var(--bg2);border:1px solid var(--br);border-radius:var(--rl);padding:32px;max-width:640px;width:100%;max-height:90vh;overflow-y:auto;animation:fadeUp .2s ease}

/* ═══════ TOAST ═══════ */
#toast{position:fixed;bottom:24px;right:24px;z-index:9999;background:var(--bg2);border:1px solid var(--br);color:var(--tx);padding:14px 20px;border-radius:var(--r);font-size:.9rem;font-weight:500;box-shadow:0 8px 40px rgba(0,0,0,.5);transform:translateY(100px);opacity:0;transition:all .3s ease;max-width:340px;pointer-events:none}
#toast.show{transform:translateY(0);opacity:1}
#toast.ok{border-color:rgba(63,185,80,.4)}
#toast.er{border-color:rgba(248,81,73,.4)}

/* ═══════ RESPONSIVE ═══════ */
@media(max-width:1024px){
  .how-grid{grid-template-columns:1fr 1fr}
  .perks-in{grid-template-columns:1fr}
  .f-in{grid-template-columns:1fr 1fr;gap:32px}
  .f-brand{grid-column:1/-1}
}
@media(max-width:768px){
  .sec{padding:64px 0}
  .hero{min-height:auto;padding:100px 0 60px}
  .hero-stats{gap:24px}
  .hero-btns{flex-direction:column}
  .hero-search{max-width:100%}
  .how-grid{grid-template-columns:1fr}
  .tgrid{grid-template-columns:1fr}
  .contact-in{grid-template-columns:1fr;gap:40px}
  .fgrid{grid-template-columns:1fr}
  .cats-grid{grid-template-columns:1fr 1fr}
  .pgrid{grid-template-columns:1fr 1fr}
  .act-layout{grid-template-columns:1fr}
  .mkt-filters{flex-direction:column;align-items:flex-start}
  .f-in{grid-template-columns:1fr}
  .f-bot-in{flex-direction:column;gap:6px;text-align:center}
  .ham{display:flex}
  .nav-links{display:none;flex-direction:column;align-items:stretch;position:fixed;top:64px;left:0;right:0;background:var(--bg2);border-bottom:1px solid var(--br);padding:16px;gap:4px}
  .nav-links.open{display:flex}
  .nav-links .btn{justify-content:center}
  .dash-wrap{flex-direction:column}
  .dash-side{width:100%;height:auto;position:static;overflow-x:auto;padding:12px;flex-direction:row}
  .side-user{display:none}
  .side-nav{flex-direction:row;margin-top:0}
  .snav-btn{white-space:nowrap;padding:8px 12px;font-size:.8rem}
  .dash-main{padding:20px 16px}
  .srow{grid-template-columns:1fr}
  .adm-sgrid{grid-template-columns:1fr 1fr}
}
@media(max-width:480px){
  .pgrid{grid-template-columns:1fr}
  .cats-grid{grid-template-columns:1fr}
}
</style>
</head>
<body>

<!-- ══════════════════════════════ NAVBAR -->
<nav id="nav">
  <div class="wrap nav-in">
    <a href="#" class="nav-logo" onclick="showPage('home')">🌍 TradeLink <span>Africa</span></a>
    <div class="nav-links" id="navLinks">
      <a class="nav-link" onclick="showPage('home');scrollTo('mkt')">Marketplace</a>
      <a class="nav-link" onclick="showPage('home');scrollTo('how')">How It Works</a>
      <a class="nav-link" onclick="showPage('home');scrollTo('contact')">Contact</a>
      <div id="navGuest" style="display:flex;gap:8px;align-items:center;">
        <button class="btn btn-o btn-sm" onclick="showPage('login')">Login</button>
        <button class="btn btn-p btn-sm" onclick="showPage('register')">Get Started</button>
      </div>
      <div id="navUser" style="display:none;" class="nav-user">
        <div class="nav-avt" id="navAvtBtn">
          <div class="ava ava-s ava-p" id="navIco">U</div>
          <span id="navName">User</span>
        </div>
        <div class="nav-dd" id="navDd">
          <button class="dd-item" onclick="showPage('dashboard');closeDd()">📊 Dashboard</button>
          <button class="dd-item" id="adminNavBtn" onclick="showPage('admin');closeDd()" style="display:none;">🛡 Admin Panel</button>
          <div class="dd-div"></div>
          <button class="dd-item red" onclick="doLogout()">🚪 Sign Out</button>
        </div>
      </div>
    </div>
    <button class="ham" id="ham"><span></span><span></span><span></span></button>
  </div>
</nav>

<!-- ══════════════════════════════ HOME PAGE -->
<div id="p-home" class="page act">

  <!-- HERO -->
  <section class="hero">
    <div class="hero-bg">
      <div class="orb orb1"></div>
      <div class="orb orb2"></div>
      <div class="hero-grid"></div>
    </div>
    <div class="wrap hero-c">
      <div class="hero-badge"><span class="badge b-ok">🚀 Live Platform</span> Africa's fastest-growing marketplace</div>
      <h1 class="hero-h">Sell your products and<br><span class="grad">connect with buyers</span><br>across locations.</h1>
      <p class="hero-sub">Join thousands of sellers building their businesses on TradeLink Africa. Create your store, list products, and reach buyers in every state.</p>
      <div class="hero-btns">
        <button class="btn btn-p btn-lg" onclick="showPage('register')">Start Selling →</button>
        <button class="btn btn-o btn-lg" onclick="scrollTo('mkt')">Explore Market</button>
      </div>
      <form class="hero-search" onsubmit="doHeroSearch(event)">
        <span style="color:var(--txm)">🔍</span>
        <input id="heroQ" placeholder="Search products, sellers, locations..."/>
        <button type="submit" class="btn btn-p btn-sm">Search</button>
      </form>
      <div class="hero-stats">
        <div><div class="hs-val">2,400+</div><div class="hs-lbl">Active Sellers</div></div>
        <div><div class="hs-val">18,000+</div><div class="hs-lbl">Products Listed</div></div>
        <div><div class="hs-val">36</div><div class="hs-lbl">Nigerian States</div></div>
        <div><div class="hs-val">50,000+</div><div class="hs-lbl">Registered Buyers</div></div>
      </div>
    </div>
  </section>

  <!-- CATEGORIES -->
  <section class="sec cats-sec" id="cats">
    <div class="wrap">
      <div class="sh"><h2 class="st">Browse by Category</h2><p class="ss">Find exactly what you need across all product categories</p></div>
      <div class="cats-grid" id="catsGrid"></div>
    </div>
  </section>

  <!-- MARKETPLACE -->
  <section class="sec" id="mkt">
    <div class="wrap">
      <div class="sh"><h2 class="st">Latest Listings</h2><p class="ss">Fresh products from verified sellers across Africa</p></div>
      <div class="mkt-filters">
        <div class="fl-left">
          <select class="fsel" id="fCat" onchange="applyFilters()"><option value="">All Categories</option></select>
          <select class="fsel" id="fState" onchange="applyFilters()"><option value="">All States</option></select>
          <select class="fsel" id="fSort" onchange="applyFilters()">
            <option value="new">Newest First</option>
            <option value="asc">Price: Low→High</option>
            <option value="desc">Price: High→Low</option>
          </select>
        </div>
        <span id="pCount" style="font-size:.85rem;color:var(--txm)"></span>
      </div>
      <div class="pgrid" id="prodGrid"></div>
      <div style="text-align:center;margin-top:40px"><button class="btn btn-o btn-lg" id="loadMoreBtn" onclick="loadMore()">Load More</button></div>
    </div>
  </section>

  <!-- HOW IT WORKS -->
  <section class="sec how-sec" id="how">
    <div class="wrap">
      <div class="sh"><h2 class="st">How It Works</h2><p class="ss">Getting started takes less than 5 minutes</p></div>
      <div class="how-grid">
        <div class="how-card"><div class="how-n">01</div><div class="how-ico">👥</div><h3>Create Your Account</h3><p>Register in minutes with your name, email, and location. Your profile is ready instantly.</p></div>
        <div class="how-card"><div class="how-n">02</div><div class="how-ico">🔒</div><h3>Activate Seller Profile</h3><p>Pay a one-time ₦1,000 activation fee to unlock your full seller dashboard and public profile.</p></div>
        <div class="how-card"><div class="how-n">03</div><div class="how-ico">📦</div><h3>List Your Products</h3><p>Upload photos, set prices, and add descriptions. Your listings go live in the marketplace immediately.</p></div>
        <div class="how-card"><div class="how-n">04</div><div class="how-ico">📈</div><h3>Connect &amp; Sell</h3><p>Share your unique seller link. Buyers find you, contact you directly, and deals get done.</p></div>
      </div>
      <div style="text-align:center"><button class="btn btn-a btn-lg" onclick="showPage('register')">Get Started Free →</button></div>
    </div>
  </section>

  <!-- PERKS -->
  <section class="sec">
    <div class="wrap perks-in">
      <div>
        <span class="badge b-a" style="margin-bottom:16px">For Sellers</span>
        <h2 class="st" style="text-align:left">Everything you need to sell online</h2>
        <ul class="plist">
          <li><span class="pck">✓</span> Your own public seller profile with a unique link</li>
          <li><span class="pck">✓</span> Upload up to 5 images per product listing</li>
          <li><span class="pck">✓</span> Real-time dashboard to track views and products</li>
          <li><span class="pck">✓</span> Buyers can contact you directly — no middleman</li>
          <li><span class="pck">✓</span> Location-based discovery by city and state</li>
          <li><span class="pck">✓</span> One-time activation fee, no monthly charges</li>
        </ul>
        <button class="btn btn-p btn-lg" style="margin-top:32px" onclick="showPage('register')">Activate Seller Account — ₦1,000 →</button>
      </div>
      <div style="background:var(--bg2);border:1px solid var(--br);border-radius:var(--rl);padding:28px">
        <div style="background:var(--bg3);border-radius:12px;padding:20px;margin-bottom:16px">
          <div style="display:flex;gap:10px;align-items:center;margin-bottom:12px"><div style="width:36px;height:36px;border-radius:50%;background:var(--g);opacity:.7"></div><div><div style="height:10px;background:var(--br);border-radius:4px;width:80px;margin-bottom:4px"></div><div style="height:8px;background:var(--bg2);border-radius:4px;width:60px"></div></div></div>
          <div style="height:120px;background:var(--bg2);border-radius:10px;margin-bottom:12px;display:flex;align-items:center;justify-content:center;font-size:3rem">📱</div>
          <div style="display:flex;justify-content:space-between"><div style="height:12px;background:var(--g);opacity:.5;border-radius:4px;width:80px"></div><div style="height:10px;background:var(--br);border-radius:4px;width:60px"></div></div>
        </div>
        <div style="display:flex;gap:12px;justify-content:center">
          <div style="text-align:center"><div style="font-size:1.4rem;font-weight:800;font-family:var(--ff);color:var(--gl)">24</div><div style="font-size:.75rem;color:var(--txm)">Products</div></div>
          <div style="text-align:center"><div style="font-size:1.4rem;font-weight:800;font-family:var(--ff);color:var(--ac)">1,280</div><div style="font-size:.75rem;color:var(--txm)">Views</div></div>
          <div style="text-align:center"><div style="font-size:1.4rem;font-weight:800;font-family:var(--ff);color:var(--ok)">₦240k</div><div style="font-size:.75rem;color:var(--txm)">Earned</div></div>
        </div>
      </div>
    </div>
  </section>

  <!-- TESTIMONIALS -->
  <section class="sec test-sec">
    <div class="wrap">
      <div class="sh"><h2 class="st">Sellers Love TradeLink Africa</h2><p class="ss">Real stories from real sellers growing their business</p></div>
      <div class="tgrid" id="testGrid"></div>
    </div>
  </section>

  <!-- CONTACT -->
  <section class="sec" id="contact">
    <div class="wrap contact-in">
      <div>
        <span class="badge b-p" style="margin-bottom:16px">Contact Us</span>
        <h2 class="st" style="text-align:left">Get in touch</h2>
        <p style="color:var(--txm);margin-bottom:32px">Have questions? We're here 7 days a week.</p>
        <div class="c-details">
          <div class="c-item">📧 support@tradelinkafrica.com</div>
          <div class="c-item">📞 +234 800 000 0000</div>
          <div class="c-item">📍 Available across all 36 states in Nigeria</div>
        </div>
      </div>
      <div class="c-form">
        <h3 style="margin-bottom:20px">Send a Message</h3>
        <form onsubmit="submitContact(event)">
          <div class="fg"><label class="fl">Your Name</label><input class="fi" placeholder="John Doe" required/></div>
          <div class="fg"><label class="fl">Email</label><input type="email" class="fi" placeholder="john@example.com" required/></div>
          <div class="fg"><label class="fl">Message</label><textarea class="fi" rows="4" placeholder="How can we help?" required></textarea></div>
          <button type="submit" class="btn btn-p btn-full">Send Message</button>
        </form>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="f-glow"></div>
    <div class="wrap f-in">
      <div class="f-brand">
        <div class="f-logo">🌍 TradeLink Africa</div>
        <div class="f-tag">Buy. Sell. Connect.</div>
        <p class="f-desc">Africa's modern marketplace connecting buyers and sellers across every state and city.</p>
        <div class="f-soc"><a href="#">𝕏</a><a href="#">📸</a><a href="#">👤</a></div>
      </div>
      <div class="f-col"><h4>Platform</h4><a href="#" onclick="scrollTo('mkt')">Marketplace</a><a href="#" onclick="showPage('register')">Become a Seller</a><a href="#" onclick="showPage('login')">Login</a></div>
      <div class="f-col"><h4>Company</h4><a href="#" onclick="scrollTo('how')">How It Works</a><a href="#">About Us</a><a href="#">Privacy Policy</a><a href="#">Terms</a></div>
      <div class="f-col"><h4>Contact</h4><a href="mailto:support@tradelinkafrica.com">📧 support@tradelinkafrica.com</a><a href="tel:+2348000000000">📞 +234 800 000 0000</a></div>
    </div>
    <div class="f-bot"><div class="wrap f-bot-in"><p>© <span id="yr"></span> TradeLink Africa. All rights reserved.</p><p>Payments by <strong>Paystack</strong> · Images by <strong>Cloudinary</strong></p></div></div>
  </footer>
</div>

<!-- ══════════════════════════════ LOGIN PAGE -->
<div id="p-login" class="page">
  <div class="auth-wrap">
    <div class="auth-orb"></div>
    <div class="wrap-sm">
      <div class="auth-hdr">
        <a class="auth-brand" onclick="showPage('home')">🌍 TradeLink Africa</a>
        <h2>Welcome back</h2>
        <p>Sign in to your TradeLink Africa account</p>
      </div>
      <div class="auth-form card">
        <div class="demo-box"><strong>Demo accounts:</strong><br>Seller: seller@demo.com / password123<br>Admin: admin@demo.com / admin123</div>
        <form onsubmit="doLogin(event)" novalidate>
          <div class="fg"><label class="fl">Email Address</label><input type="email" class="fi" id="lEmail" placeholder="john@example.com" required/><span class="ferr" id="lEErr"></span></div>
          <div class="fg">
            <div style="display:flex;justify-content:space-between"><label class="fl">Password</label><a href="#" style="font-size:.8rem;color:var(--gl)">Forgot password?</a></div>
            <div class="iw" style="margin-top:6px"><input type="password" class="fi" id="lPass" placeholder="Enter your password" required/><button type="button" class="eye-btn" onclick="toggleEye('lPass',this)">👁</button></div>
            <span class="ferr" id="lPErr"></span>
          </div>
          <button type="submit" class="btn btn-p btn-full btn-lg" style="margin-top:8px" id="loginBtn">Sign In</button>
        </form>
        <p class="auth-sw">Don't have an account? <a onclick="showPage('register')">Create one free</a></p>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════ REGISTER PAGE -->
<div id="p-register" class="page">
  <div class="auth-wrap">
    <div class="auth-orb"></div>
    <div class="wrap-sm">
      <div class="auth-hdr">
        <a class="auth-brand" onclick="showPage('home')">🌍 TradeLink Africa</a>
        <h2>Create your account</h2>
        <p>Join thousands of sellers on Africa's growing marketplace</p>
      </div>
      <div class="auth-form card">
        <form onsubmit="doRegister(event)" novalidate>
          <div class="photo-row">
            <div style="position:relative;flex-shrink:0">
              <div class="photo-prev" id="photoPrev">👤</div>
              <label for="photoInp" class="photo-btn" title="Upload photo">📷</label>
              <input type="file" id="photoInp" accept="image/*" hidden onchange="previewPhoto(this)"/>
            </div>
            <div><p style="font-weight:600;font-size:.9rem;margin-bottom:4px">Profile Photo</p><p class="fhint">Optional — max 5MB</p></div>
          </div>
          <div class="fgrid">
            <div class="fg"><label class="fl">Full Name *</label><input class="fi" id="rName" placeholder="John Doe" required/><span class="ferr" id="rNErr"></span></div>
            <div class="fg"><label class="fl">Phone Number *</label><input type="tel" class="fi" id="rPhone" placeholder="+234 800 000 0000" required/><span class="ferr" id="rPhErr"></span></div>
          </div>
          <div class="fg"><label class="fl">Email Address *</label><input type="email" class="fi" id="rEmail" placeholder="john@example.com" required/><span class="ferr" id="rEErr"></span></div>
          <div class="fgrid">
            <div class="fg"><label class="fl">City *</label><input class="fi" id="rCity" placeholder="Lagos" required/><span class="ferr" id="rCErr"></span></div>
            <div class="fg"><label class="fl">State *</label><select class="fi" id="rState" required><option value="">Select state</option></select><span class="ferr" id="rStErr"></span></div>
          </div>
          <div class="fgrid">
            <div class="fg"><label class="fl">Password *</label><div class="iw"><input type="password" class="fi" id="rPass" placeholder="Min. 8 characters" required/><button type="button" class="eye-btn" onclick="toggleEye('rPass',this)">👁</button></div><span class="ferr" id="rPErr"></span></div>
            <div class="fg"><label class="fl">Confirm Password *</label><div class="iw"><input type="password" class="fi" id="rConf" placeholder="Repeat password" required/></div><span class="ferr" id="rCfErr"></span></div>
          </div>
          <button type="submit" class="btn btn-p btn-full btn-lg" id="regBtn">Create Account</button>
        </form>
        <p class="auth-sw">Already have an account? <a onclick="showPage('login')">Sign in</a></p>
        <p style="text-align:center;font-size:.78rem;color:var(--txm);margin-top:12px">By registering, you agree to our <a href="#" style="color:var(--txm);text-decoration:underline">Terms</a> &amp; <a href="#" style="color:var(--txm);text-decoration:underline">Privacy Policy</a>.</p>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════ ACTIVATION PAGE -->
<div id="p-activate" class="page">
  <div class="auth-wrap">
    <div class="auth-orb"></div>
    <div class="wrap" style="max-width:900px">
      <div class="auth-hdr">
        <a class="auth-brand" onclick="showPage('home')">🌍 TradeLink Africa</a>
        <h2>Activate Your Seller Account</h2>
        <p>Unlock the full power of TradeLink Africa and start selling to buyers across every state.</p>
      </div>
      <div class="act-layout">
        <div class="card" style="padding:32px">
          <div style="display:flex;align-items:center;gap:12px;margin-bottom:24px;padding-bottom:20px;border-bottom:1px solid var(--br)">
            <span style="font-size:1.4rem">⭐</span>
            <div><h3 style="font-size:1.1rem;margin-bottom:2px">Seller Membership</h3><p style="font-size:.85rem;color:var(--txm)">Everything you need to sell online</p></div>
          </div>
          <ul class="act-perks">
            <li><span class="pck">✓</span> Public seller profile with unique link</li>
            <li><span class="pck">✓</span> Unlimited product listings</li>
            <li><span class="pck">✓</span> Up to 5 images per product</li>
            <li><span class="pck">✓</span> Dashboard with analytics</li>
            <li><span class="pck">✓</span> Direct buyer-to-seller contact</li>
            <li><span class="pck">✓</span> Location-based discovery</li>
            <li><span class="pck">✓</span> One-time fee — no recurring charges</li>
            <li><span class="pck">✓</span> Verified seller badge</li>
          </ul>
        </div>
        <div>
          <div class="card" style="padding:32px">
            <div style="font-family:var(--ff);font-size:3rem;font-weight:800;margin-bottom:4px">₦1,000</div>
            <div style="font-size:.85rem;color:var(--txm);margin-bottom:24px;padding-bottom:24px;border-bottom:1px solid var(--br)">one-time fee — pay once, sell forever</div>
            <div style="margin-bottom:24px;display:flex;flex-direction:column;gap:10px">
              <div style="display:flex;justify-content:space-between;font-size:.875rem"><span style="color:var(--txm)">Amount</span><strong>₦1,000</strong></div>
              <div style="display:flex;justify-content:space-between;font-size:.875rem"><span style="color:var(--txm)">Payment</span><span>Card / Bank / USSD</span></div>
            </div>
            <button class="btn btn-p btn-full btn-lg" id="actBtn" onclick="doActivate()">🔒 Pay ₦1,000 &amp; Activate Now</button>
            <p style="text-align:center;font-size:.75rem;color:var(--txm);margin-top:12px">Secured by Paystack</p>
          </div>
          <p style="text-align:center;font-size:.85rem;color:var(--txm);margin-top:12px">Not ready? <a onclick="showPage('dashboard')" style="color:var(--gl);cursor:pointer">Go to dashboard</a></p>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════ DASHBOARD PAGE -->
<div id="p-dashboard" class="page">
  <div class="dash-wrap">
    <aside class="dash-side">
      <div class="side-user" id="sideUser"></div>
      <nav class="side-nav">
        <button class="snav-btn on" onclick="dTab('overview',this)">📊 Overview</button>
        <button class="snav-btn" onclick="dTab('products',this)">📦 My Products</button>
        <button class="snav-btn" id="addTabBtn" onclick="dTab('add',this)">➕ Add Product</button>
        <button class="snav-btn" onclick="dTab('profile',this)">👤 Profile</button>
        <button class="snav-btn out" onclick="doLogout()">🚪 Sign Out</button>
      </nav>
    </aside>
    <main class="dash-main">
      <!-- Overview -->
      <div class="d-sec on" id="d-overview">
        <h2 class="d-title">Dashboard Overview</h2>
        <div class="srow" id="dStats"></div>
        <div class="link-card card" id="dLinkCard" style="display:none">
          <div class="link-hdr">🔗 Your Public Seller Link</div>
          <div class="link-row"><span class="link-txt" id="dLinkTxt"></span><button class="btn btn-o btn-sm" onclick="copySellerLink()">📋 Copy</button></div>
          <p class="fhint">Share this link so buyers can visit your profile and products.</p>
        </div>
        <div class="act-prompt card" id="dActPrompt" style="display:none">
          <div style="font-size:2.5rem;margin-bottom:16px">🚀</div>
          <h3>Activate Your Seller Account</h3>
          <p>Pay a one-time ₦1,000 fee to unlock your seller dashboard and list products.</p>
          <button class="btn btn-p btn-lg" style="margin-top:16px" onclick="showPage('activate')">Activate for ₦1,000</button>
        </div>
      </div>
      <!-- My Products -->
      <div class="d-sec" id="d-products">
        <div class="d-hdr"><h2 class="d-title">My Products</h2><button class="btn btn-p btn-sm" onclick="dTab('add',null)">➕ Add Product</button></div>
        <div id="dMyProducts"></div>
      </div>
      <!-- Add/Edit Product -->
      <div class="d-sec" id="d-add">
        <div class="d-hdr"><h2 class="d-title" id="addTitle">Add New Product</h2><button class="btn btn-gh btn-sm" id="cancelEdit" style="display:none" onclick="cancelEditProduct()">✕ Cancel</button></div>
        <div id="dAddGate"></div>
        <form class="pform card" id="pForm" onsubmit="submitProduct(event)" style="display:none">
          <div class="fg">
            <label class="fl">Product Images *</label>
            <div class="img-zone" id="imgZone" onclick="document.getElementById('pImages').click()">
              <div class="up-ph" id="upPh"><div style="font-size:2rem;margin-bottom:8px">📤</div><p>Click or drag images here</p><span>PNG, JPG, WebP</span></div>
              <div class="img-prevs" id="imgPrevs" style="display:none"></div>
            </div>
            <input type="file" id="pImages" accept="image/*" multiple hidden onchange="previewProdImages(this)"/>
          </div>
          <div class="fg"><label class="fl">Product Title *</label><input class="fi" id="pTitle" placeholder="e.g. iPhone 14 Pro Max 256GB" required/></div>
          <div class="fg"><label class="fl">Description *</label><textarea class="fi" id="pDesc" rows="5" placeholder="Describe your product in detail..." required></textarea></div>
          <div class="fgrid">
            <div class="fg"><label class="fl">Price (₦) *</label><input type="number" class="fi" id="pPrice" placeholder="e.g. 50000" min="0" required/></div>
            <div class="fg"><label class="fl">Category *</label><select class="fi" id="pCat" required><option value="">Select category</option></select></div>
          </div>
          <div class="fg" style="max-width:300px"><label class="fl">Condition</label><select class="fi" id="pCond"><option>New</option><option>Used - Like New</option><option>Used - Good</option><option>Used - Fair</option></select></div>
          <div style="display:flex;gap:12px">
            <button type="submit" class="btn btn-p btn-lg" id="pSubmitBtn">List Product</button>
            <button type="button" class="btn btn-o btn-lg" id="pCancelBtn" style="display:none" onclick="cancelEditProduct()">Cancel</button>
          </div>
        </form>
      </div>
      <!-- Profile -->
      <div class="d-sec" id="d-profile">
        <h2 class="d-title">My Profile</h2>
        <form class="pform card" onsubmit="saveProfile(event)">
          <div class="fgrid">
            <div class="fg"><label class="fl">Full Name</label><input class="fi" id="prName"/></div>
            <div class="fg"><label class="fl">Phone</label><input class="fi" id="prPhone"/></div>
            <div class="fg"><label class="fl">City</label><input class="fi" id="prCity"/></div>
            <div class="fg"><label class="fl">State</label><input class="fi" id="prState"/></div>
          </div>
          <div class="fg"><label class="fl">Seller Bio</label><textarea class="fi" id="prBio" rows="4" placeholder="Tell buyers about yourself..."></textarea></div>
          <button type="submit" class="btn btn-p">Save Profile</button>
        </form>
      </div>
    </main>
  </div>
  <!-- Delete modal -->
  <div class="modal" id="delModal">
    <div class="modal-box">
      <h3>Delete Product?</h3>
      <p style="color:var(--txm);margin:10px 0 24px">This action cannot be undone.</p>
      <div style="display:flex;gap:10px">
        <button class="btn btn-p" style="background:var(--danger)" onclick="confirmDelete()">Yes, Delete</button>
        <button class="btn btn-o" onclick="document.getElementById('delModal').classList.remove('open')">Cancel</button>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════ ADMIN PAGE -->
<div id="p-admin" class="page">
  <div class="adm-hdr">
    <div class="wrap">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:24px">
        <div><h1 style="display:flex;align-items:center;gap:10px;font-size:1.6rem">🛡 Admin Panel</h1><p style="color:var(--txm);font-size:.875rem;margin-top:4px">TradeLink Africa management</p></div>
        <span class="badge b-warn">Admin Access</span>
      </div>
      <div class="adm-tabs">
        <button class="adm-tab on" onclick="aTab('stats',this)">📊 Overview</button>
        <button class="adm-tab" onclick="aTab('users',this)">👥 Users</button>
        <button class="adm-tab" onclick="aTab('products',this)">📦 Products</button>
        <button class="adm-tab" onclick="aTab('payments',this)">💳 Payments</button>
      </div>
    </div>
  </div>
  <div class="adm-body wrap">
    <div class="adm-sec on" id="a-stats"></div>
    <div class="adm-sec" id="a-users"></div>
    <div class="adm-sec" id="a-products"></div>
    <div class="adm-sec" id="a-payments"></div>
  </div>
</div>

<!-- ══════════════════════════════ PRODUCT MODAL -->
<div class="modal" id="prodModal">
  <div class="modal-box" id="prodModalBox"></div>
</div>

<!-- ══════════════════════════════ TOAST -->
<div id="toast"></div>

<script>
'use strict';

/* ═══════════════════════════ DATA ═══════════════════════════ */
const CATS=[
  {n:'Electronics',e:'💻'},{n:'Fashion',e:'👗'},{n:'Food & Agriculture',e:'🌾'},
  {n:'Health & Beauty',e:'💊'},{n:'Home & Garden',e:'🏡'},{n:'Vehicles',e:'🚗'},
  {n:'Services',e:'🔧'},{n:'Real Estate',e:'🏢'},{n:'Books & Education',e:'📚'},
  {n:'Sports',e:'⚽'},{n:'Baby & Kids',e:'🧸'},{n:'Art & Crafts',e:'🎨'}
];
const STATES=['Abia','Adamawa','Akwa Ibom','Anambra','Bauchi','Bayelsa','Benue','Borno','Cross River','Delta','Ebonyi','Edo','Ekiti','Enugu','FCT','Gombe','Imo','Jigawa','Kaduna','Kano','Katsina','Kebbi','Kogi','Kwara','Lagos','Nasarawa','Niger','Ogun','Ondo','Osun','Oyo','Plateau','Rivers','Sokoto','Taraba','Yobe','Zamfara'];
const EMO={Electronics:'💻',Fashion:'👗','Food & Agriculture':'🌾','Health & Beauty':'💊','Home & Garden':'🏡',Vehicles:'🚗',Services:'🔧','Real Estate':'🏢','Books & Education':'📚',Sports:'⚽','Baby & Kids':'🧸','Art & Crafts':'🎨',Other:'📦'};
const SELLERS=[
  {id:'s1',name:'Amaka Okafor',username:'amaka_styles',city:'Lagos',state:'Lagos',bio:'Fashion seller with 5+ years experience.'},
  {id:'s2',name:'Emeka Nwosu',username:'emeka_tech',city:'Abuja',state:'FCT',bio:'Certified electronics dealer. All products with warranty.'},
  {id:'s3',name:'Fatima Bello',username:'fatima_farm',city:'Kano',state:'Kano',bio:'Farm fresh produce delivered to your door.'},
  {id:'s4',name:'Chidi Obi',username:'chidi_motors',city:'Port Harcourt',state:'Rivers',bio:'Verified vehicle dealer.'},
  {id:'s5',name:'Ngozi Eze',username:'ngozi_beauty',city:'Enugu',state:'Enugu',bio:'Natural beauty products made in Nigeria.'},
];
const DEMO_PRODUCTS=[
  {id:'p1',title:'iPhone 14 Pro Max 256GB',price:850000,category:'Electronics',condition:'Used - Like New',city:'Lagos',state:'Lagos',sellerId:'s2',e:'📱',views:234,createdAt:'2025-05-10'},
  {id:'p2',title:'Ankara Midi Dress Collection',price:12500,category:'Fashion',condition:'New',city:'Lagos',state:'Lagos',sellerId:'s1',e:'👗',views:187,createdAt:'2025-05-12'},
  {id:'p3',title:'Fresh Organic Tomatoes (25kg)',price:8500,category:'Food & Agriculture',condition:'New',city:'Kano',state:'Kano',sellerId:'s3',e:'🍅',views:94,createdAt:'2025-05-14'},
  {id:'p4',title:'Samsung 55" 4K Smart TV',price:420000,category:'Electronics',condition:'New',city:'Abuja',state:'FCT',sellerId:'s2',e:'📺',views:312,createdAt:'2025-05-08'},
  {id:'p5',title:'2020 Toyota Camry XLE',price:14500000,category:'Vehicles',condition:'Used - Good',city:'Port Harcourt',state:'Rivers',sellerId:'s4',e:'🚗',views:543,createdAt:'2025-05-06'},
  {id:'p6',title:'Natural Shea Butter Set (6pcs)',price:7800,category:'Health & Beauty',condition:'New',city:'Enugu',state:'Enugu',sellerId:'s5',e:'🧴',views:128,createdAt:'2025-05-15'},
  {id:'p7',title:'3 Bedroom Flat to Let — Lekki',price:3500000,category:'Real Estate',condition:'New',city:'Lagos',state:'Lagos',sellerId:'s1',e:'🏠',views:891,createdAt:'2025-05-04'},
  {id:'p8',title:'HP Laptop 16GB / 512GB SSD',price:520000,category:'Electronics',condition:'New',city:'Ibadan',state:'Oyo',sellerId:'s2',e:'💻',views:276,createdAt:'2025-05-11'},
  {id:'p9',title:"Men's Agbada (Custom Sewn)",price:45000,category:'Fashion',condition:'New',city:'Kano',state:'Kano',sellerId:'s1',e:'👘',views:153,createdAt:'2025-05-13'},
  {id:'p10',title:'Fresh Catfish (Live) — 5kg',price:4500,category:'Food & Agriculture',condition:'New',city:'Lagos',state:'Lagos',sellerId:'s3',e:'🐟',views:67,createdAt:'2025-05-16'},
  {id:'p11',title:'Generator 5KVA Elemax',price:380000,category:'Home & Garden',condition:'New',city:'Abuja',state:'FCT',sellerId:'s2',e:'⚡',views:198,createdAt:'2025-05-09'},
  {id:'p12',title:"Children's Study Desk & Chair",price:28000,category:'Baby & Kids',condition:'New',city:'Enugu',state:'Enugu',sellerId:'s5',e:'🪑',views:82,createdAt:'2025-05-17'},
  {id:'p13',title:'Professional Photography Service',price:75000,category:'Services',condition:'New',city:'Lagos',state:'Lagos',sellerId:'s1',e:'📸',views:345,createdAt:'2025-05-07'},
  {id:'p14',title:'Brand New Tecno Camon 20 Pro',price:185000,category:'Electronics',condition:'New',city:'Port Harcourt',state:'Rivers',sellerId:'s2',e:'📱',views:421,createdAt:'2025-05-05'},
  {id:'p15',title:'Handmade Woven Bag Collection',price:9500,category:'Art & Crafts',condition:'New',city:'Ibadan',state:'Oyo',sellerId:'s1',e:'👜',views:110,createdAt:'2025-05-18'},
  {id:'p16',title:'2018 Honda Civic Sedan',price:8200000,category:'Vehicles',condition:'Used - Good',city:'Lagos',state:'Lagos',sellerId:'s4',e:'🚘',views:674,createdAt:'2025-05-03'},
];
const DEMO_USERS=[
  {id:'u1',fullName:'Demo Seller',email:'seller@demo.com',password:'password123',username:'demoseller',city:'Lagos',state:'Lagos',role:'seller',isSellerActivated:true},
  {id:'u2',fullName:'Admin User',email:'admin@demo.com',password:'admin123',username:'adminuser',city:'Abuja',state:'FCT',role:'admin',isSellerActivated:true},
];
const TESTS=[
  {name:'Amaka Okafor',city:'Lagos',role:'Fashion Seller',stars:5,text:'TradeLink Africa changed my business completely. Within 2 weeks of activating my seller account, I had 30+ orders from buyers in different states!'},
  {name:'Emeka Nwosu',city:'Abuja',role:'Electronics Dealer',stars:5,text:'The platform is clean and professional. My customers trust buying from me here. The seller profile link is gold — I share it everywhere.'},
  {name:'Fatima Bello',city:'Kano',role:'Food Vendor',stars:5,text:'I sell farm produce and now reach buyers across the north easily. TradeLink Africa is truly built for us Africans.'},
];

/* ═══════════════════════════ STORAGE ═══════════════════════════ */
const S={
  getUser:()=>JSON.parse(localStorage.getItem('tla_u')||'null'),
  setUser:u=>localStorage.setItem('tla_u',JSON.stringify(u)),
  clearUser:()=>{localStorage.removeItem('tla_u');localStorage.removeItem('tla_tok')},
  getProds:()=>JSON.parse(localStorage.getItem('tla_p')||'null')||DEMO_PRODUCTS,
  setProds:a=>localStorage.setItem('tla_p',JSON.stringify(a)),
  getUsers:()=>JSON.parse(localStorage.getItem('tla_us')||'null')||[...DEMO_USERS],
  setUsers:a=>localStorage.setItem('tla_us',JSON.stringify(a)),
  getPays:()=>JSON.parse(localStorage.getItem('tla_pays')||'[]'),
  addPay:p=>{const a=S.getPays();a.unshift(p);localStorage.setItem('tla_pays',JSON.stringify(a))},
  fmt:n=>'₦'+Number(n).toLocaleString(),
  ago:d=>{const days=Math.floor((Date.now()-new Date(d))/86400000);return days===0?'Today':days===1?'Yesterday':days+'d ago'},
};

/* ═══════════════════════════ TOAST ═══════════════════════════ */
function toast(msg,type=''){
  const t=document.getElementById('toast');
  t.textContent=msg; t.className='toast show '+type;
  clearTimeout(t._t); t._t=setTimeout(()=>t.className='toast',3200);
}

/* ═══════════════════════════ NAVBAR ═══════════════════════════ */
document.getElementById('yr').textContent=new Date().getFullYear();
window.addEventListener('scroll',()=>document.getElementById('nav').classList.toggle('sc',scrollY>20),{passive:true});
document.getElementById('nav').classList.toggle('sc',scrollY>20);
const ham=document.getElementById('ham'),nl=document.getElementById('navLinks');
ham.addEventListener('click',()=>nl.classList.toggle('open'));
document.addEventListener('click',e=>{if(!document.getElementById('nav').contains(e.target))nl.classList.remove('open')});
const navAvtBtn=document.getElementById('navAvtBtn'),navDd=document.getElementById('navDd');
navAvtBtn&&navAvtBtn.addEventListener('click',e=>{e.stopPropagation();navDd.classList.toggle('open')});
document.addEventListener('click',()=>navDd&&navDd.classList.remove('open'));
function closeDd(){navDd&&navDd.classList.remove('open')}
function updateNav(){
  const u=S.getUser();
  document.getElementById('navGuest').style.display=u?'none':'flex';
  document.getElementById('navUser').style.display=u?'block':'none';
  if(u){
    document.getElementById('navIco').textContent=u.fullName[0];
    document.getElementById('navName').textContent=u.fullName.split(' ')[0];
    document.getElementById('adminNavBtn').style.display=u.role==='admin'?'flex':'none';
  }
}
updateNav();

/* ═══════════════════════════ PAGE ROUTING ═══════════════════════════ */
function showPage(name){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('act'));
  const el=document.getElementById('p-'+name);
  if(!el)return;
  el.classList.add('act');
  window.scrollTo(0,0);
  if(name==='dashboard') initDashboard();
  if(name==='admin') initAdmin();
  if(name==='activate'&&!S.getUser()){showPage('login');return}
}
function scrollTo(id){
  const el=document.getElementById(id);
  if(el)el.scrollIntoView({behavior:'smooth'});
}

/* ═══════════════════════════ HOME ═══════════════════════════ */
// Categories
(function(){
  const g=document.getElementById('catsGrid');
  if(!g)return;
  g.innerHTML=CATS.map(c=>`<div class="cat-card" onclick="filterCat('${c.n}')"><span style="font-size:1.5rem">${c.e}</span><span style="flex:1">${c.n}</span><span style="color:var(--txm)">→</span></div>`).join('');
})();

// Populate selects
(function(){
  const fc=document.getElementById('fCat'),fs=document.getElementById('fState');
  CATS.forEach(c=>{const o=document.createElement('option');o.value=c.n;o.textContent=c.e+' '+c.n;fc.appendChild(o)});
  STATES.forEach(s=>{const o=document.createElement('option');o.value=s;o.textContent=s;fs.appendChild(o)});
})();

let filtered=[],shown=8;
function applyFilters(){
  const cat=document.getElementById('fCat').value,
        st=document.getElementById('fState').value,
        sort=document.getElementById('fSort').value,
        q=(document.getElementById('heroQ')||{}).value||'';
  let arr=S.getProds().filter(p=>{
    if(cat&&p.category!==cat)return false;
    if(st&&p.state!==st)return false;
    if(q&&!p.title.toLowerCase().includes(q.toLowerCase())&&!p.category.toLowerCase().includes(q.toLowerCase()))return false;
    return true;
  });
  if(sort==='asc')arr.sort((a,b)=>a.price-b.price);
  else if(sort==='desc')arr.sort((a,b)=>b.price-a.price);
  else arr.sort((a,b)=>new Date(b.createdAt)-new Date(a.createdAt));
  filtered=arr; shown=8; renderProds();
}
function filterCat(c){document.getElementById('fCat').value=c;applyFilters();scrollTo('mkt')}
function loadMore(){shown+=8;renderProds()}
function renderProds(){
  const g=document.getElementById('prodGrid'),pc=document.getElementById('pCount'),lb=document.getElementById('loadMoreBtn');
  const slice=filtered.slice(0,shown);
  g.innerHTML=slice.length?slice.map(p=>{
    const seller=SELLERS.find(s=>s.id===p.sellerId)||{name:'Seller',username:'seller'};
    return`<div class="pc-wrap" onclick="openProdModal('${p.id}')">
      <div class="pc-img"><span>${p.e||'📦'}</span><span class="pc-cat">${p.category}</span></div>
      <div class="pc-body">
        <div class="pc-title">${p.title}</div>
        <div class="pc-price">${S.fmt(p.price)}</div>
        <div class="pc-meta"><span>📍 ${p.city}, ${p.state}</span><span>👁 ${p.views||0}</span></div>
        <div class="pc-seller"><div class="mini-ava">${seller.name[0]}</div><span>${seller.name}</span></div>
      </div>
    </div>`;
  }).join(''):`<div class="empty" style="grid-column:1/-1"><div class="empty-ico">🔍</div><h3>No products found</h3><p>Try adjusting your filters</p></div>`;
  pc.textContent=filtered.length+' products';
  lb.style.display=filtered.length>shown?'inline-flex':'none';
}
applyFilters();

// Testimonials
(function(){
  const g=document.getElementById('testGrid');
  g.innerHTML=TESTS.map(t=>`<div class="tcard"><div class="t-stars">${'★'.repeat(t.stars)}</div><p class="t-text">"${t.text}"</p><div class="t-auth"><div class="t-ava">${t.name[0]}</div><div><div class="t-name">${t.name}</div><div class="t-role">${t.role} · ${t.city}</div></div></div></div>`).join('');
})();

function doHeroSearch(e){e.preventDefault();applyFilters();scrollTo('mkt')}
function submitContact(e){e.preventDefault();toast('✅ Message sent! We\'ll reply within 24hrs.','ok');e.target.reset()}

/* ═══════════════════════════ PRODUCT MODAL ═══════════════════════════ */
function openProdModal(id){
  const p=S.getProds().find(x=>x.id===id);if(!p)return;
  const seller=SELLERS.find(s=>s.id===p.sellerId)||{name:'Seller',bio:'',city:'',state:''};
  document.getElementById('prodModalBox').innerHTML=`
    <div style="display:flex;justify-content:flex-end;margin-bottom:16px"><button onclick="document.getElementById('prodModal').classList.remove('open')" style="background:none;border:none;color:var(--txm);font-size:1.4rem;cursor:pointer">✕</button></div>
    <div style="font-size:6rem;text-align:center;background:var(--bg3);border-radius:12px;padding:32px;margin-bottom:20px">${p.e||'📦'}</div>
    <div style="display:flex;gap:8px;flex-wrap:wrap;margin-bottom:12px"><span class="badge b-p">${p.category}</span>${p.condition!=='New'?`<span class="badge b-a">${p.condition}</span>`:''}</div>
    <h2 style="font-size:1.5rem;margin-bottom:10px">${p.title}</h2>
    <div style="font-size:1.8rem;font-weight:800;color:var(--gl);font-family:var(--ff);margin-bottom:16px">${S.fmt(p.price)}</div>
    <div style="display:flex;gap:16px;flex-wrap:wrap;font-size:.82rem;color:var(--txm);margin-bottom:20px;padding-bottom:20px;border-bottom:1px solid var(--br)">
      <span>📍 ${p.city}, ${p.state}</span><span>👁 ${p.views||0} views</span><span>🗓 ${S.ago(p.createdAt)}</span>
    </div>
    <div style="background:var(--bg3);border:1px solid var(--br);border-radius:12px;padding:16px;margin-bottom:16px">
      <div style="display:flex;align-items:center;gap:12px;margin-bottom:12px">
        <div class="ava ava-m ava-p">${seller.name[0]}</div>
        <div><div style="font-weight:700">${seller.name}</div><div style="font-size:.8rem;color:var(--txm)">📍 ${seller.city}, ${seller.state}</div></div>
      </div>
      <p style="font-size:.85rem;color:var(--txm);margin-bottom:12px">${seller.bio||'Verified seller on TradeLink Africa.'}</p>
      <button class="btn btn-p btn-full" onclick="contactSeller('${seller.name}')">📞 Contact Seller</button>
    </div>
    <button class="btn btn-o btn-full" onclick="document.getElementById('prodModal').classList.remove('open')">Close</button>`;
  document.getElementById('prodModal').classList.add('open');
}
function contactSeller(name){toast('📞 Contact request sent to '+name+'!','ok');document.getElementById('prodModal').classList.remove('open')}
document.getElementById('prodModal').addEventListener('click',e=>{if(e.target.id==='prodModal')document.getElementById('prodModal').classList.remove('open')});

/* ═══════════════════════════ AUTH ═══════════════════════════ */
// Populate state select
STATES.forEach(s=>{const o=document.createElement('option');o.value=s;o.textContent=s;document.getElementById('rState').appendChild(o)});

function toggleEye(id,btn){const i=document.getElementById(id);i.type=i.type==='password'?'text':'password';btn.textContent=i.type==='password'?'👁':'🙈'}
function previewPhoto(inp){
  const f=inp.files[0];if(!f)return;
  if(f.size>5*1024*1024){toast('Photo must be under 5MB','er');return}
  const r=new FileReader();r.onload=e=>{document.getElementById('photoPrev').innerHTML=`<img src="${e.target.result}"/>`};r.readAsDataURL(f);
}

function doLogin(e){
  e.preventDefault();
  const em=document.getElementById('lEmail').value.trim().toLowerCase(),
        pw=document.getElementById('lPass').value;
  document.getElementById('lEErr').textContent='';
  document.getElementById('lPErr').textContent='';
  if(!em){document.getElementById('lEErr').textContent='Email is required';return}
  if(!pw){document.getElementById('lPErr').textContent='Password is required';return}
  const btn=document.getElementById('loginBtn');btn.disabled=true;btn.textContent='Signing in...';
  setTimeout(()=>{
    let user=DEMO_USERS.find(u=>u.email===em&&u.password===pw)||S.getUsers().find(u=>u.email===em);
    if(!user){document.getElementById('lEErr').textContent='Invalid email or password';btn.disabled=false;btn.textContent='Sign In';return}
    S.setUser(user);localStorage.setItem('tla_tok','demo_'+Date.now());
    updateNav();toast('👋 Welcome back, '+user.fullName.split(' ')[0]+'!','ok');
    setTimeout(()=>showPage(user.role==='admin'?'admin':'dashboard'),900);
  },900);
}

function doRegister(e){
  e.preventDefault();
  const nm=document.getElementById('rName').value.trim(),
        ph=document.getElementById('rPhone').value.trim(),
        em=document.getElementById('rEmail').value.trim().toLowerCase(),
        cy=document.getElementById('rCity').value.trim(),
        st=document.getElementById('rState').value,
        pw=document.getElementById('rPass').value,
        cf=document.getElementById('rConf').value;
  ['rNErr','rPhErr','rEErr','rCErr','rStErr','rPErr','rCfErr'].forEach(id=>document.getElementById(id).textContent='');
  let ok=true;
  const err=(id,msg)=>{document.getElementById(id).textContent=msg;ok=false};
  if(!nm)err('rNErr','Full name required');
  if(!ph)err('rPhErr','Phone required');
  if(!/^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(em))err('rEErr','Valid email required');
  if(!cy)err('rCErr','City required');
  if(!st)err('rStErr','Select a state');
  if(pw.length<8)err('rPErr','Min. 8 characters');
  if(pw!==cf)err('rCfErr','Passwords do not match');
  if(!ok)return;
  const users=S.getUsers();
  if(users.find(u=>u.email===em)){err('rEErr','Email already registered');return}
  const btn=document.getElementById('regBtn');btn.disabled=true;btn.textContent='Creating Account...';
  setTimeout(()=>{
    const newUser={id:'u'+Date.now(),fullName:nm,email:em,phone:ph,city:cy,state:st,username:nm.toLowerCase().replace(/\s+/g,'')+Math.floor(Math.random()*999),role:'buyer',isSellerActivated:false,createdAt:new Date().toISOString()};
    users.push(newUser);S.setUsers(users);S.setUser(newUser);localStorage.setItem('tla_tok','demo_'+Date.now());
    updateNav();toast('🎉 Account created! Welcome to TradeLink Africa!','ok');
    btn.disabled=false;btn.textContent='Create Account';
    setTimeout(()=>showPage('activate'),1000);
  },1000);
}

function doLogout(){S.clearUser();updateNav();showPage('home');toast('Signed out successfully.')}

/* ═══════════════════════════ ACTIVATION ═══════════════════════════ */
function doActivate(){
  if(!S.getUser()){showPage('login');return}
  const btn=document.getElementById('actBtn');btn.disabled=true;btn.textContent='Processing...';
  setTimeout(()=>{
    const u=S.getUser();u.isSellerActivated=true;u.role='seller';S.setUser(u);
    S.addPay({id:'pay'+Date.now(),userId:u.id,userName:u.fullName,userEmail:u.email,amount:1000,status:'success',purpose:'Seller Activation',receiptNumber:'TLA-'+Date.now(),createdAt:new Date().toISOString()});
    updateNav();toast('🎉 Seller account activated! You can now list products.','ok');
    btn.disabled=false;btn.textContent='🔒 Pay ₦1,000 & Activate Now';
    setTimeout(()=>showPage('dashboard'),1200);
  },2000);
}

/* ═══════════════════════════ DASHBOARD ═══════════════════════════ */
let editId=null,delId=null;

function initDashboard(){
  const u=S.getUser();if(!u){showPage('login');return}
  // Sidebar
  document.getElementById('sideUser').innerHTML=`<div class="ava ava-m ava-p" style="font-size:1.3rem;flex-shrink:0">${u.fullName[0]}</div><div class="side-info"><strong>${u.fullName}</strong><span style="font-size:.75rem;color:var(--txm)">@${u.username}</span><span class="badge ${u.isSellerActivated?'b-ok':'b-warn'}" style="margin-top:4px;font-size:.7rem">${u.isSellerActivated?'✓ Active Seller':'Buyer'}</span></div>`;
  // Populate category select
  const cs=document.getElementById('pCat');
  if(cs.options.length<=1)CATS.forEach(c=>{const o=document.createElement('option');o.value=c.n;o.textContent=c.e+' '+c.n;cs.appendChild(o)});
  renderDOverview();
}

function dTab(name,btn){
  document.querySelectorAll('.snav-btn').forEach(b=>b.classList.remove('on'));
  if(btn)btn.classList.add('on');
  document.querySelectorAll('.d-sec').forEach(s=>s.classList.remove('on'));
  document.getElementById('d-'+name).classList.add('on');
  if(name==='overview')renderDOverview();
  if(name==='products')renderDProds();
  if(name==='add'){editId=null;renderDAdd()}
  if(name==='profile')renderDProfile();
}

function renderDOverview(){
  const u=S.getUser();if(!u)return;
  const prods=S.getProds().filter(p=>p.sellerId===u.id||p.sellerId===u.username);
  const views=prods.reduce((s,p)=>s+(p.views||0),0);
  document.getElementById('dStats').innerHTML=`
    <div class="scard"><div style="font-size:1.5rem">📦</div><div class="sval">${prods.length}</div><div class="slbl">Total Products</div></div>
    <div class="scard"><div style="font-size:1.5rem">🟢</div><div class="sval">${prods.filter(p=>p.isAvailable!==false).length}</div><div class="slbl">Active Listings</div></div>
    <div class="scard"><div style="font-size:1.5rem">👁️</div><div class="sval">${views}</div><div class="slbl">Total Views</div></div>`;
  if(u.isSellerActivated){
    document.getElementById('dLinkCard').style.display='block';
    document.getElementById('dActPrompt').style.display='none';
    document.getElementById('dLinkTxt').textContent=`tradelinkafrica.com/seller/${u.username}`;
  }else{
    document.getElementById('dLinkCard').style.display='none';
    document.getElementById('dActPrompt').style.display='block';
  }
}

function copySellerLink(){
  const u=S.getUser();if(!u)return;
  navigator.clipboard&&navigator.clipboard.writeText(`https://tradelinkafrica.com/seller/${u.username}`).catch(()=>{});
  toast('📋 Seller link copied!','ok');
}

function renderDProds(){
  const u=S.getUser();if(!u)return;
  const prods=S.getProds().filter(p=>p.sellerId===u.id||p.sellerId===u.username);
  const wrap=document.getElementById('dMyProducts');
  if(!prods.length){wrap.innerHTML=`<div class="empty"><div class="empty-ico">📦</div><h3>No products yet</h3><p>Start listing products to reach buyers across Africa</p>${u.isSellerActivated?`<button class="btn btn-p" style="margin-top:16px" onclick="dTab('add',null)">➕ Add Product</button>`:''}</div>`;return}
  wrap.innerHTML=`<div class="tbl-wrap"><table><thead><tr><th>Product</th><th>Price</th><th>Category</th><th>Views</th><th>Status</th><th>Actions</th></tr></thead><tbody>${prods.map(p=>`<tr><td><div class="tp"><div class="tt">${p.e||'📦'}</div><span>${p.title}</span></div></td><td style="font-weight:700;color:var(--gl)">${S.fmt(p.price)}</td><td><span class="badge b-p" style="font-size:.72rem">${p.category}</span></td><td>${p.views||0}</td><td><span class="badge ${p.isAvailable!==false?'b-ok':'b-warn'}">${p.isAvailable!==false?'Active':'Paused'}</span></td><td><div style="display:flex;gap:6px"><button class="btn btn-gh btn-sm" onclick="editProduct('${p.id}')">✏️</button><button class="btn btn-gh btn-sm" style="color:var(--danger)" onclick="openDel('${p.id}')">🗑️</button></div></td></tr>`).join('')}</tbody></table></div>`;
}

function renderDAdd(){
  const u=S.getUser();if(!u)return;
  const gate=document.getElementById('dAddGate'),form=document.getElementById('pForm');
  if(!u.isSellerActivated){
    gate.innerHTML=`<div class="act-prompt card"><div style="font-size:2.5rem;margin-bottom:16px">🔒</div><h3>Seller Account Required</h3><p>Activate your seller account to start listing products.</p><button class="btn btn-p btn-lg" style="margin-top:16px" onclick="showPage('activate')">Activate for ₦1,000</button></div>`;
    gate.style.display='block';form.style.display='none';return;
  }
  gate.style.display='none';form.style.display='block';
  const atitle=document.getElementById('addTitle'),subBtn=document.getElementById('pSubmitBtn'),cBtn=document.getElementById('cancelEdit'),cBtnF=document.getElementById('pCancelBtn');
  if(editId){
    const p=S.getProds().find(x=>x.id===editId);if(!p)return;
    atitle.textContent='Edit Product';subBtn.textContent='Update Product';cBtn.style.display='inline-flex';cBtnF.style.display='inline-flex';
    document.getElementById('pTitle').value=p.title;document.getElementById('pDesc').value=p.description||'';document.getElementById('pPrice').value=p.price;document.getElementById('pCat').value=p.category;document.getElementById('pCond').value=p.condition||'New';
    document.getElementById('imgPrevs').innerHTML=`<div style="font-size:5rem;text-align:center;padding:16px;width:100%">${p.e||'📦'}</div>`;
    document.getElementById('imgPrevs').style.display='flex';document.getElementById('upPh').style.display='none';
  }else{
    atitle.textContent='Add New Product';subBtn.textContent='List Product';cBtn.style.display='none';cBtnF.style.display='none';
    document.getElementById('pForm').reset();document.getElementById('imgPrevs').style.display='none';document.getElementById('upPh').style.display='block';
  }
}

function previewProdImages(inp){
  const files=Array.from(inp.files);if(!files.length)return;
  document.getElementById('imgPrevs').innerHTML=files.map(f=>`<div class="ipi"><img src="${URL.createObjectURL(f)}"/></div>`).join('');
  document.getElementById('imgPrevs').style.display='flex';document.getElementById('upPh').style.display='none';
}

function submitProduct(e){
  e.preventDefault();
  const title=document.getElementById('pTitle').value.trim(),desc=document.getElementById('pDesc').value.trim(),price=parseFloat(document.getElementById('pPrice').value),cat=document.getElementById('pCat').value,cond=document.getElementById('pCond').value;
  if(!title||!desc||!price||!cat){toast('Please fill all required fields','er');return}
  const u=S.getUser();const btn=document.getElementById('pSubmitBtn');btn.disabled=true;btn.textContent='Saving...';
  setTimeout(()=>{
    const prods=S.getProds();
    if(editId){
      const idx=prods.findIndex(p=>p.id===editId);
      if(idx!==-1)prods[idx]={...prods[idx],title,description:desc,price,category:cat,condition:cond,e:EMO[cat]||'📦'};
      S.setProds(prods);toast('✅ Product updated!','ok');editId=null;
    }else{
      prods.unshift({id:'p'+Date.now(),title,description:desc,price,category:cat,condition:cond,e:EMO[cat]||'📦',city:u.city,state:u.state,sellerId:u.id,views:0,isAvailable:true,createdAt:new Date().toISOString()});
      S.setProds(prods);toast('🎉 Product listed!','ok');
    }
    btn.disabled=false;btn.textContent='List Product';
    applyFilters();dTab('products',document.querySelector('[onclick*="products"]'));
  },900);
}

function editProduct(id){editId=id;dTab('add',null)}
function cancelEditProduct(){editId=null;dTab('products',null)}
function openDel(id){delId=id;document.getElementById('delModal').classList.add('open')}
function confirmDelete(){
  if(!delId)return;
  S.setProds(S.getProds().filter(p=>p.id!==delId));
  document.getElementById('delModal').classList.remove('open');
  delId=null;toast('🗑️ Product deleted','ok');applyFilters();renderDProds();
}

function renderDProfile(){
  const u=S.getUser();if(!u)return;
  document.getElementById('prName').value=u.fullName||'';document.getElementById('prPhone').value=u.phone||'';
  document.getElementById('prCity').value=u.city||'';document.getElementById('prState').value=u.state||'';
  document.getElementById('prBio').value=u.sellerBio||'';
}
function saveProfile(e){
  e.preventDefault();const u=S.getUser();if(!u)return;
  u.fullName=document.getElementById('prName').value.trim()||u.fullName;
  u.phone=document.getElementById('prPhone').value.trim();
  u.city=document.getElementById('prCity').value.trim();
  u.state=document.getElementById('prState').value.trim();
  u.sellerBio=document.getElementById('prBio').value.trim();
  S.setUser(u);updateNav();toast('✅ Profile updated!','ok');
}

/* ═══════════════════════════ ADMIN ═══════════════════════════ */
function initAdmin(){
  const u=S.getUser();if(!u||u.role!=='admin'){showPage('login');return}
  renderAStats();
}
function aTab(name,btn){
  document.querySelectorAll('.adm-tab').forEach(b=>b.classList.remove('on'));if(btn)btn.classList.add('on');
  document.querySelectorAll('.adm-sec').forEach(s=>s.classList.remove('on'));
  document.getElementById('a-'+name).classList.add('on');
  if(name==='stats')renderAStats();if(name==='users')renderAUsers();if(name==='products')renderAProducts();if(name==='payments')renderAPayments();
}
function renderAStats(){
  const users=S.getUsers(),prods=S.getProds(),pays=S.getPays();
  const rev=pays.filter(p=>p.status==='success').reduce((s,p)=>s+(p.amount||0),0);
  document.getElementById('a-stats').innerHTML=`<h2 class="adm-title">Platform Overview</h2><div class="adm-sgrid">
    <div class="scard"><div style="font-size:1.5rem">👥</div><div class="sval">${users.length}</div><div class="slbl">Total Users</div></div>
    <div class="scard"><div style="font-size:1.5rem">🏪</div><div class="sval">${users.filter(u=>u.isSellerActivated).length}</div><div class="slbl">Active Sellers</div></div>
    <div class="scard"><div style="font-size:1.5rem">📦</div><div class="sval">${prods.length}</div><div class="slbl">Total Products</div></div>
    <div class="scard"><div style="font-size:1.5rem">💰</div><div class="sval">${S.fmt(rev)}</div><div class="slbl">Total Revenue</div></div>
    <div class="scard"><div style="font-size:1.5rem">💳</div><div class="sval">${pays.filter(p=>p.status==='success').length}</div><div class="slbl">Payments</div></div>
  </div>`;
}
function renderAUsers(){
  const users=S.getUsers();
  document.getElementById('a-users').innerHTML=`<h2 class="adm-title">Manage Users (${users.length})</h2><div class="tbl-wrap"><table><thead><tr><th>User</th><th>Email</th><th>Location</th><th>Role</th><th>Status</th><th>Actions</th></tr></thead><tbody>${users.map(u=>`<tr><td><div style="display:flex;align-items:center;gap:10px"><div class="ava ava-s ava-p">${u.fullName[0]}</div><div><div style="font-weight:600;font-size:.875rem">${u.fullName}</div><div style="font-size:.75rem;color:var(--txm)">@${u.username||'—'}</div></div></div></td><td style="font-size:.82rem;color:var(--txm)">${u.email}</td><td style="font-size:.82rem">${u.city||'—'}, ${u.state||'—'}</td><td><span class="badge ${u.role==='admin'?'b-a':u.role==='seller'?'b-ok':'b-p'}">${u.role||'buyer'}</span></td><td><span class="badge ${u.isSuspended?'b-err':u.isSellerActivated?'b-ok':'b-warn'}">${u.isSuspended?'Suspended':u.isSellerActivated?'Active':'Buyer'}</span></td><td><div style="display:flex;gap:6px">${u.role!=='admin'?`<button class="btn btn-sm ${u.isSuspended?'btn-o':''}" style="${u.isSuspended?'':'background:var(--danger);color:#fff'}" onclick="suspendUser('${u.id}')">${u.isSuspended?'✓ Unsuspend':'🚫 Suspend'}</button>`:''}</div></td></tr>`).join('')}</tbody></table></div>`;
}
function suspendUser(id){const users=S.getUsers(),idx=users.findIndex(u=>u.id===id);if(idx<0)return;users[idx].isSuspended=!users[idx].isSuspended;S.setUsers(users);toast(users[idx].isSuspended?'🚫 User suspended':'✅ User unsuspended','ok');renderAUsers()}
function renderAProducts(){
  const prods=S.getProds();
  document.getElementById('a-products').innerHTML=`<h2 class="adm-title">Manage Products (${prods.length})</h2><div class="tbl-wrap"><table><thead><tr><th>Product</th><th>Price</th><th>Category</th><th>Views</th><th>Actions</th></tr></thead><tbody>${prods.map(p=>`<tr><td><div style="display:flex;align-items:center;gap:10px"><div style="width:40px;height:40px;border-radius:8px;background:var(--bg3);display:flex;align-items:center;justify-content:center;font-size:1.3rem;flex-shrink:0">${p.e||'📦'}</div><span style="font-size:.875rem;font-weight:500">${p.title.substring(0,40)}${p.title.length>40?'…':''}</span></div></td><td style="font-weight:700;color:var(--gl)">${S.fmt(p.price)}</td><td><span class="badge b-p" style="font-size:.72rem">${p.category}</span></td><td>${p.views||0}</td><td><button class="btn btn-sm" style="background:var(--danger);color:#fff" onclick="adminDelProd('${p.id}')">🗑️ Remove</button></td></tr>`).join('')}</tbody></table></div>`;
}
function adminDelProd(id){if(!confirm('Remove this product permanently?'))return;S.setProds(S.getProds().filter(p=>p.id!==id));toast('🗑️ Product removed','ok');applyFilters();renderAProducts()}
function renderAPayments(){
  let pays=S.getPays();
  if(!pays.length){DEMO_USERS.filter(u=>u.isSellerActivated).forEach((u,i)=>S.addPay({id:'pay'+i,userId:u.id,userName:u.fullName,userEmail:u.email,amount:1000,status:'success',purpose:'Seller Activation',receiptNumber:'TLA-'+Date.now()+'-'+i,createdAt:new Date(Date.now()-i*86400000).toISOString()}));pays=S.getPays()}
  document.getElementById('a-payments').innerHTML=`<h2 class="adm-title">Payment Records (${pays.length})</h2><div class="tbl-wrap"><table><thead><tr><th>Receipt</th><th>User</th><th>Amount</th><th>Purpose</th><th>Status</th><th>Date</th></tr></thead><tbody>${pays.map(p=>`<tr><td style="font-size:.78rem;color:var(--txm);font-family:monospace">${p.receiptNumber||p.id||'—'}</td><td style="font-size:.82rem"><div>${p.userName||'—'}</div><div style="font-size:.75rem;color:var(--txm)">${p.userEmail||'—'}</div></td><td style="font-weight:700;color:var(--gl)">${S.fmt(p.amount||0)}</td><td style="font-size:.82rem">${p.purpose||'Seller Activation'}</td><td><span class="badge ${p.status==='success'?'b-ok':p.status==='failed'?'b-err':'b-warn'}">${p.status||'success'}</span></td><td style="font-size:.78rem;color:var(--txm)">${new Date(p.createdAt).toLocaleDateString('en-NG')}</td></tr>`).join('')}</tbody></table></div>`;
}
</script>
</body>
</html>
