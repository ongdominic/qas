# qas_homepage_prototype.html

```text
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Quality Air Solution — Your air, our responsibility</title>

<!--
  ============================================================
  QAS WEBSITE — HOMEPAGE PROTOTYPE (handoff to designer)
  This file is the layout + design-system reference. Notes:
   - Design tokens live in :root below. They ARE the spec
     (colours, type scale, spacing, radii). Reuse everywhere.
   - Replace the logo URL with the final asset.
   - Text in [SQUARE BRACKETS] = placeholder content to supply.
   - Every section is labelled. Product / segment / contact
     pages reuse these same components.
  ============================================================
-->

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Schibsted+Grotesk:wght@400;500;600;700&family=Hanken+Grotesk:wght@400;500;600&display=swap" rel="stylesheet">

<style>
:root{
  /* Brand colours (sampled from the QAS logo) */
  --navy:#0A1B3D;       /* anchor / dark sections / headings */
  --blue:#1439F4;       /* primary action */
  --cyan:#00B0F0;       /* accent */
  --slate:#48566B;      /* body text */
  --mist:#F5F8FC;       /* tinted section background */
  --line:#E6EDF5;       /* hairline borders */
  --white:#FFFFFF;
  --navy-soft:#16294d;  /* hover on navy */

  /* Type */
  --font-display:'Schibsted Grotesk',sans-serif;
  --font-body:'Hanken Grotesk',sans-serif;
  --h1:clamp(2.1rem,5vw,3.4rem);
  --h2:clamp(1.5rem,3vw,2.1rem);
  --h3:1.15rem;
  --lead:clamp(1rem,1.6vw,1.18rem);

  /* Spacing + shape */
  --container:1180px;
  --gutter:clamp(1.2rem,4vw,2.5rem);
  --section-y:clamp(3.5rem,7vw,6rem);
  --r:16px;
  --r-sm:10px;
  --r-pill:999px;
  --shadow:0 12px 40px -18px rgba(10,27,61,.28);
}

*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:var(--font-body);color:var(--navy);background:var(--white);line-height:1.65;-webkit-font-smoothing:antialiased}
h1,h2,h3{font-family:var(--font-display);font-weight:600;line-height:1.1;letter-spacing:-.02em}
p{color:var(--slate)}
a{color:inherit;text-decoration:none}
img{max-width:100%;display:block}
.container{max-width:var(--container);margin:0 auto;padding-inline:var(--gutter)}
.eyebrow{font-family:var(--font-display);font-size:.8rem;font-weight:600;letter-spacing:.12em;text-transform:uppercase;color:var(--cyan)}

/* ---------- Buttons ---------- */
.btn{display:inline-flex;align-items:center;gap:.55rem;font-family:var(--font-display);font-weight:600;font-size:.98rem;padding:.85rem 1.5rem;border-radius:var(--r-pill);border:1.5px solid transparent;cursor:pointer;transition:.18s ease}
.btn svg{width:18px;height:18px}
.btn-primary{background:var(--blue);color:#fff}
.btn-primary:hover{background:#0d2bc9;transform:translateY(-1px)}
.btn-ghost{background:transparent;color:#fff;border-color:rgba(255,255,255,.4)}
.btn-ghost:hover{border-color:#fff;background:rgba(255,255,255,.08)}
.btn-light{background:#fff;color:var(--blue)}
.btn-light:hover{transform:translateY(-1px)}
.btn-outline{background:transparent;color:var(--navy);border-color:var(--line)}
.btn-outline:hover{border-color:var(--blue);color:var(--blue)}

/* ---------- Header ---------- */
header{position:sticky;top:0;z-index:50;background:rgba(255,255,255,.92);backdrop-filter:blur(10px);border-bottom:1px solid var(--line)}
.nav{display:flex;align-items:center;justify-content:space-between;height:74px}
.brand{display:flex;align-items:center;gap:.6rem;font-family:var(--font-display);font-weight:700;font-size:1.1rem;letter-spacing:-.01em}
.brand img{width:38px;height:38px}
.nav-links{display:flex;align-items:center;gap:2rem}
.nav-links a{font-weight:500;font-size:.95rem;color:var(--navy);transition:.15s}
.nav-links a:hover{color:var(--blue)}
.nav-cta{display:flex;align-items:center;gap:1rem}
.menu-btn{display:none;background:none;border:0;cursor:pointer}

/* ---------- Hero ---------- */
.hero{position:relative;background:var(--navy);color:#fff;overflow:hidden}
.hero::before{content:"";position:absolute;inset:0;background:radial-gradient(60% 80% at 85% 0%,rgba(0,176,240,.22),transparent 60%);pointer-events:none}
.hero-inner{position:relative;padding-block:clamp(4rem,9vw,7rem)}
.hero .eyebrow{display:inline-block;border:1px solid rgba(255,255,255,.18);border-radius:var(--r-pill);padding:.4rem 1rem;margin-bottom:1.6rem}
.hero h1{font-size:var(--h1);max-width:13ch;margin-bottom:.4rem}
.hero h1 .accent{color:var(--cyan)}
.hero .rule{width:64px;height:4px;background:var(--cyan);border-radius:2px;margin:1.4rem 0}
.hero p.lead{font-size:var(--lead);color:#C2CDE2;max-width:46ch;margin-bottom:2.2rem}
.hero-actions{display:flex;gap:1rem;flex-wrap:wrap}
.hero-stats{display:flex;gap:2.5rem;flex-wrap:wrap;margin-top:3.2rem;padding-top:2rem;border-top:1px solid rgba(255,255,255,.12)}
.stat .n{font-family:var(--font-display);font-weight:700;font-size:1.8rem;color:#fff}
.stat .l{font-size:.82rem;color:#9FB0CC}

/* ---------- Trust band ---------- */
.trust{background:var(--mist);border-bottom:1px solid var(--line)}
.trust-inner{display:flex;flex-wrap:wrap;gap:1.2rem 2.4rem;align-items:center;justify-content:center;padding-block:1.1rem;font-size:.88rem;color:var(--slate)}
.trust-inner span{display:inline-flex;align-items:center;gap:.5rem;font-weight:500}
.trust-inner svg{width:18px;height:18px;color:var(--blue)}

/* ---------- Section header ---------- */
.section{padding-block:var(--section-y)}
.section-head{text-align:center;max-width:60ch;margin:0 auto clamp(2.2rem,5vw,3.2rem)}
.section-head h2{font-size:var(--h2);margin:.5rem 0 .6rem}
.section-head p{font-size:1.02rem}

/* ---------- Solutions cards ---------- */
.grid-3{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:1.4rem}
.card{background:#fff;border:1px solid var(--line);border-radius:var(--r);padding:1.8rem;transition:.2s ease}
.card:hover{transform:translateY(-4px);box-shadow:var(--shadow);border-color:#d4def0}
.card .ico{width:56px;height:56px;border-radius:14px;display:flex;align-items:center;justify-content:center;background:#EAF0FB;margin-bottom:1.2rem}
.card .ico svg{width:28px;height:28px;color:var(--blue)}
.card .ico.cyan{background:#E4F6FC}
.card .ico.cyan svg{color:var(--cyan)}
.card .kicker{font-family:var(--font-display);font-weight:600;font-size:.78rem;letter-spacing:.08em;text-transform:uppercase;color:var(--cyan);margin-bottom:.35rem}
.card h3{font-size:1.25rem;margin-bottom:.6rem}
.card p{font-size:.95rem;margin-bottom:1rem}
.card .tags{font-size:.82rem;color:#8693A6;border-top:1px solid var(--line);padding-top:.9rem;margin-bottom:1rem}
.card .more{font-family:var(--font-display);font-weight:600;font-size:.92rem;color:var(--blue);display:inline-flex;align-items:center;gap:.4rem}
.card .more svg{width:16px;height:16px;transition:.15s}
.card:hover .more svg{transform:translateX(3px)}

/* ---------- Why lease ---------- */
.lease{background:var(--mist)}
.lease .grid-3{gap:1rem}
.feat{padding:1.6rem;background:#fff;border:1px solid var(--line);border-radius:var(--r)}
.feat .ico{width:48px;height:48px;border-radius:12px;background:#EAF0FB;display:flex;align-items:center;justify-content:center;margin-bottom:1rem}
.feat .ico svg{width:24px;height:24px;color:var(--blue)}
.feat h3{font-size:1.08rem;margin-bottom:.4rem}
.feat p{font-size:.92rem}

/* ---------- Industries ---------- */
.tiles{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:1rem}
.tile{position:relative;border:1px solid var(--line);border-radius:var(--r);padding:1.5rem;background:#fff;transition:.2s}
.tile:hover{border-color:var(--blue);background:var(--mist)}
.tile h3{font-size:1.02rem;margin-bottom:.3rem}
.tile p{font-size:.85rem;margin-bottom:.8rem}
.tile .pill{font-size:.72rem;font-weight:600;font-family:var(--font-display);color:var(--blue);background:#EAF0FB;padding:.25rem .7rem;border-radius:var(--r-pill)}

/* ---------- How it works ---------- */
.steps{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:1.4rem;counter-reset:step}
.step{position:relative;padding-top:1rem}
.step .num{counter-increment:step;font-family:var(--font-display);font-weight:700;font-size:2.2rem;color:#D7E0F2;line-height:1}
.step .num::before{content:"0" counter(step)}
.step h3{font-size:1.05rem;margin:.6rem 0 .4rem}
.step p{font-size:.9rem}

/* ---------- Proof placeholder ---------- */
.proof{background:var(--mist);border-top:1px solid var(--line);border-bottom:1px solid var(--line)}
.proof-box{border:1px dashed #BCCBE4;border-radius:var(--r);padding:2.4rem;text-align:center;color:#7E8CA3;background:#fff}

/* ---------- Final CTA ---------- */
.cta{background:var(--blue);color:#fff;text-align:center}
.cta h2{font-size:var(--h2);color:#fff;margin-bottom:.7rem}
.cta p{color:#D5DEFB;max-width:48ch;margin:0 auto 2rem}
.cta-actions{display:flex;gap:1rem;justify-content:center;flex-wrap:wrap}

/* ---------- Footer ---------- */
footer{background:var(--navy);color:#A9B7D0;padding-block:3rem 2rem;font-size:.9rem}
.foot-grid{display:grid;grid-template-columns:1.4fr 1fr 1fr;gap:2rem;padding-bottom:2rem;border-bottom:1px solid rgba(255,255,255,.1)}
.foot-grid h4{font-family:var(--font-display);color:#fff;font-size:.95rem;margin-bottom:.9rem;font-weight:600}
.foot-grid a{display:block;padding:.25rem 0;color:#A9B7D0}
.foot-grid a:hover{color:#fff}
.foot-brand .brand{color:#fff;margin-bottom:.8rem}
.foot-bottom{display:flex;justify-content:space-between;flex-wrap:wrap;gap:1rem;padding-top:1.4rem;font-size:.8rem;color:#7E8CA3}

/* ---------- Sticky WhatsApp ---------- */
.wa{position:fixed;right:20px;bottom:20px;z-index:60;width:58px;height:58px;border-radius:50%;background:#25D366;display:flex;align-items:center;justify-content:center;box-shadow:0 10px 30px -8px rgba(0,0,0,.4)}
.wa svg{width:30px;height:30px;color:#fff}

/* ---------- Reveal animation ---------- */
.fade{opacity:0;transform:translateY(16px);animation:up .7s ease forwards}
@keyframes up{to{opacity:1;transform:none}}
.d1{animation-delay:.05s}.d2{animation-delay:.15s}.d3{animation-delay:.25s}.d4{animation-delay:.35s}

/* ---------- Responsive ---------- */
@media(max-width:860px){
  .nav-links{display:none}
  .menu-btn{display:block}
  .foot-grid{grid-template-columns:1fr 1fr}
}
@media(max-width:560px){
  .hero-stats{gap:1.5rem}
  .foot-grid{grid-template-columns:1fr}
  .nav-cta .btn{padding:.7rem 1.1rem;font-size:.9rem}
}
</style>
</head>
<body>

<!-- ============ HEADER ============ -->
<header>
  <div class="container nav">
    <a class="brand" href="#">
      <img src="https://qas.sg/wp-content/uploads/2024/09/QAS-LOGO.png" alt="Quality Air Solution logo">
      Quality Air Solution
    </a>
    <nav class="nav-links">
      <a href="#solutions">Solutions</a>
      <a href="#why">Why lease</a>
      <a href="#industries">For your space</a>
      <a href="#how">How it works</a>
      <a href="#">About</a>
    </nav>
    <div class="nav-cta">
      <a href="#contact" class="btn btn-primary"><span>Get a quote</span></a>
      <button class="menu-btn" aria-label="Menu">
        <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 6h16M4 12h16M4 18h16"/></svg>
      </button>
    </div>
  </div>
</header>

<!-- ============ HERO ============ -->
<section class="hero">
  <div class="container hero-inner">
    <span class="eyebrow fade d1">Managed air solutions · rental only</span>
    <h1 class="fade d1">Your air, <span class="accent">our responsibility.</span></h1>
    <div class="rule fade d2"></div>
    <p class="lead fade d2">Clean it, cool it, or clear the grease from it — we supply and fully maintain the right equipment on a simple lease. No upfront cost, no servicing to manage.</p>
    <div class="hero-actions fade d3">
      <a href="#contact" class="btn btn-primary">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="4" width="18" height="18" rx="2"/><path d="M16 2v4M8 2v4M3 10h18M9 16l2 2 4-4"/></svg>
        Book a free site assessment
      </a>
      <a href="https://wa.me/6566651808" class="btn btn-ghost">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2a10 10 0 0 0-8.6 15l-1.4 5 5.1-1.3A10 10 0 1 0 12 2zm0 18a8 8 0 0 1-4.1-1.1l-.3-.2-3 .8.8-2.9-.2-.3A8 8 0 1 1 12 20zm4.5-5.9c-.2-.1-1.4-.7-1.7-.8s-.4-.1-.5.1-.6.8-.8 1-.3.2-.5.1a6.6 6.6 0 0 1-3.3-2.9c-.2-.4.2-.4.6-1.2a.5.5 0 0 0 0-.5l-.8-1.8c-.2-.5-.4-.4-.5-.4h-.5a1 1 0 0 0-.7.3 3 3 0 0 0-.9 2.2c0 1.3 1 2.6 1.1 2.8a10 10 0 0 0 3.9 3.4c1.4.6 1.9.6 2.6.5.5 0 1.4-.6 1.6-1.1s.2-1 .1-1.1-.2-.1-.4-.2z"/></svg>
        WhatsApp us
      </a>
    </div>
    <div class="hero-stats fade d4">
      <div class="stat"><div class="n">0.01μm</div><div class="l">Particles filtered (AS-150)</div></div>
      <div class="stat"><div class="n">~80%</div><div class="l">Less energy than aircon (Airsonic)</div></div>
      <div class="stat"><div class="n">~95%</div><div class="l">Oil mist removed (KOMC)</div></div>
    </div>
  </div>
</section>

<!-- ============ TRUST BAND ============ -->
<div class="trust">
  <div class="container trust-inner">
    <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9 12l2 2 4-4"/><circle cx="12" cy="12" r="9"/></svg>SGS certified</span>
    <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2l8 4v6c0 5-3.5 8-8 10-4.5-2-8-5-8-10V6z"/></svg>CE certified</span>
    <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 21s-7-5-7-11a7 7 0 0 1 14 0c0 6-7 11-7 11z"/><circle cx="12" cy="10" r="2.5"/></svg>Made in Taiwan &amp; Singapore</span>
    <span><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="9"/><path d="M3 12h18M12 3c3 3 3 15 0 18M12 3c-3 3-3 15 0 18"/></svg>Exclusive distributor · SG · MY · ID</span>
  </div>
</div>

<!-- ============ SOLUTIONS ============ -->
<section class="section" id="solutions">
  <div class="container">
    <div class="section-head">
      <span class="eyebrow">One promise, three solutions</span>
      <h2>The right equipment for your air problem</h2>
      <p>Whatever your space needs — cleaner, cooler, or grease-free air — we lease it to you fully maintained.</p>
    </div>
    <div class="grid-3">
      <article class="card">
        <div class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 8h11a3 3 0 1 0-3-3M3 12h15a3 3 0 1 1-3 3M3 16h9a3 3 0 1 1-3 3"/></svg></div>
        <div class="kicker">Air purifier</div>
        <h3>Airsmeg AS-150</h3>
        <p>Clean indoor air for homes and workplaces. Captures PM2.5 and ultra-fine particles down to 0.01μm, with washable electrostatic plates.</p>
        <div class="tags">Homes · offices · clinics · salons</div>
        <a class="more" href="#">View details <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M5 12h14M13 6l6 6-6 6"/></svg></a>
      </article>
      <article class="card">
        <div class="ico cyan"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2v20M2 12h20M5 5l14 14M19 5L5 19"/></svg></div>
        <div class="kicker">Air cooler</div>
        <h3>Airsonic-QAS</h3>
        <p>Cools large, open and semi-open spaces for around 80% less energy than air-conditioning — up to 20,000 m³/h, covering 800 sq ft.</p>
        <div class="tags">Factories · warehouses · events · farms</div>
        <a class="more" href="#">View details <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M5 12h14M13 6l6 6-6 6"/></svg></a>
      </article>
      <article class="card">
        <div class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 22c4-2 6-5 6-9 0-3-2-5-2-5s-1 2-3 2c0-3-3-6-3-6S8 3 8 7c-2 0-3-2-3-2S3 8 3 11c0 4 2 7 6 9"/></svg></div>
        <div class="kicker">Kitchen oil mist collector</div>
        <h3>KOMC</h3>
        <p>Removes about 95% of oil mist and odour before discharge — eliminating pollution and neighbour complaints. Just 8 minutes to service.</p>
        <div class="tags">Restaurants · hawker stalls · central kitchens</div>
        <a class="more" href="#">View details <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M5 12h14M13 6l6 6-6 6"/></svg></a>
      </article>
    </div>
  </div>
</section>

<!-- ============ WHY LEASE ============ -->
<section class="section lease" id="why">
  <div class="container">
    <div class="section-head">
      <span class="eyebrow">Why lease, not buy</span>
      <h2>Clean air, without owning a thing</h2>
      <p>Owning equipment means buying filters and arranging servicing — forever. Leasing means we keep it running.</p>
    </div>
    <div class="grid-3">
      <div class="feat">
        <div class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 1v22M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"/></svg></div>
        <h3>Zero upfront cost</h3>
        <p>A predictable monthly fee instead of a capital purchase. Easy to budget, easy to start.</p>
      </div>
      <div class="feat">
        <div class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14.7 6.3a4 4 0 0 1-5 5L4 17v3h3l5.7-5.7a4 4 0 0 0 5-5z"/></svg></div>
        <h3>Maintenance included</h3>
        <p>We service every unit on a schedule, free of charge. You never buy a filter or arrange a repair.</p>
      </div>
      <div class="feat">
        <div class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 12a9 9 0 0 1 15-6.7L21 8M21 3v5h-5M21 12a9 9 0 0 1-15 6.7L3 16M3 21v-5h5"/></svg></div>
        <h3>Swap or scale anytime</h3>
        <p>Change the unit or add more as your home or business grows. No equipment to resell.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============ INDUSTRIES ============ -->
<section class="section" id="industries">
  <div class="container">
    <div class="section-head">
      <span class="eyebrow">For your space</span>
      <h2>Made for where you work and live</h2>
    </div>
    <div class="tiles">
      <a class="tile" href="#"><h3>Homes &amp; offices</h3><p>Cleaner indoor air, fully maintained.</p><span class="pill">AS-150</span></a>
      <a class="tile" href="#"><h3>Factories &amp; warehouses</h3><p>Wide-area cooling at a fraction of aircon cost.</p><span class="pill">Airsonic</span></a>
      <a class="tile" href="#"><h3>Events &amp; public spaces</h3><p>Deployable cooling, anywhere.</p><span class="pill">Airsonic</span></a>
      <a class="tile" href="#"><h3>F&amp;B &amp; commercial kitchens</h3><p>Pass inspections, keep neighbours happy.</p><span class="pill">KOMC</span></a>
      <a class="tile" href="#"><h3>HIP upgrades</h3><p>Add cleaner air to your flat's upgrade.</p><span class="pill">AS-150</span></a>
    </div>
  </div>
</section>

<!-- ============ HOW IT WORKS ============ -->
<section class="section lease" id="how">
  <div class="container">
    <div class="section-head">
      <span class="eyebrow">How it works</span>
      <h2>From enquiry to clean air in four steps</h2>
    </div>
    <div class="steps">
      <div class="step"><div class="num"></div><h3>Enquire</h3><p>Message us on WhatsApp or request a quote. Tell us about your space.</p></div>
      <div class="step"><div class="num"></div><h3>Free site assessment</h3><p>We visit, assess the space and recommend the right solution. No obligation.</p></div>
      <div class="step"><div class="num"></div><h3>Install</h3><p>We deliver and set up your unit. <em>[Lead time to confirm]</em></p></div>
      <div class="step"><div class="num"></div><h3>We maintain</h3><p>Scheduled servicing is included for as long as you lease.</p></div>
    </div>
  </div>
</section>

<!-- ============ SOCIAL PROOF (placeholder) ============ -->
<section class="section proof">
  <div class="container">
    <div class="section-head" style="margin-bottom:1.6rem">
      <span class="eyebrow">Trusted across Singapore</span>
      <h2>What our clients say</h2>
    </div>
    <div class="proof-box">[Testimonials, client logos, or before / after air-quality readings to be added here — a 3-up layout reusing the card component.]</div>
  </div>
</section>

<!-- ============ FINAL CTA ============ -->
<section class="section cta" id="contact">
  <div class="container">
    <h2>Tell us about your space</h2>
    <p>Book a free, no-obligation assessment. We'll measure your space and recommend the right solution for your home or business.</p>
    <div class="cta-actions">
      <a href="#" class="btn btn-light">Book an assessment</a>
      <a href="https://wa.me/6566651808" class="btn btn-ghost">WhatsApp +65 6665 1808</a>
    </div>
  </div>
</section>

<!-- ============ FOOTER ============ -->
<footer>
  <div class="container">
    <div class="foot-grid">
      <div class="foot-brand">
        <div class="brand"><img src="https://qas.sg/wp-content/uploads/2024/09/QAS-LOGO.png" alt="" style="width:34px;height:34px">Quality Air Solution</div>
        <p style="color:#8FA0BC;max-width:34ch">Commercial-grade air purifiers, coolers and kitchen oil mist collectors — on rental, fully maintained. Exclusive Airsmeg distributor for SG · MY · ID.</p>
      </div>
      <div>
        <h4>Solutions</h4>
        <a href="#">Airsmeg AS-150 — purifier</a>
        <a href="#">Airsonic-QAS — cooler</a>
        <a href="#">KOMC — oil mist collector</a>
        <a href="#why">Why lease</a>
      </div>
      <div>
        <h4>Contact</h4>
        <a href="https://wa.me/6566651808">WhatsApp +65 6665 1808</a>
        <a href="mailto:sales@qas.sg">sales@qas.sg</a>
        <a href="#">Facebook</a>
        <a href="#">Instagram</a>
      </div>
    </div>
    <div class="foot-bottom">
      <span>© 2026 Quality Air Solution Pte Ltd. All rights reserved.</span>
      <span>SGS certified · CE certified</span>
    </div>
  </div>
</footer>

<!-- ============ STICKY WHATSAPP ============ -->
<a class="wa" href="https://wa.me/6566651808" aria-label="WhatsApp us">
  <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2a10 10 0 0 0-8.6 15l-1.4 5 5.1-1.3A10 10 0 1 0 12 2zm0 18a8 8 0 0 1-4.1-1.1l-.3-.2-3 .8.8-2.9-.2-.3A8 8 0 1 1 12 20zm4.5-5.9c-.2-.1-1.4-.7-1.7-.8s-.4-.1-.5.1-.6.8-.8 1-.3.2-.5.1a6.6 6.6 0 0 1-3.3-2.9c-.2-.4.2-.4.6-1.2a.5.5 0 0 0 0-.5l-.8-1.8c-.2-.5-.4-.4-.5-.4h-.5a1 1 0 0 0-.7.3 3 3 0 0 0-.9 2.2c0 1.3 1 2.6 1.1 2.8a10 10 0 0 0 3.9 3.4c1.4.6 1.9.6 2.6.5.5 0 1.4-.6 1.6-1.1s.2-1 .1-1.1-.2-.1-.4-.2z"/></svg>
</a>

<script>
  document.querySelector('.menu-btn').addEventListener('click',function(){
    var n=document.querySelector('.nav-links');
    var open=n.style.display==='flex';
    n.style.display=open?'':'flex';
    if(!open){n.style.position='absolute';n.style.flexDirection='column';n.style.top='74px';n.style.left='0';n.style.right='0';n.style.background='#fff';n.style.padding='1.2rem var(--gutter)';n.style.borderBottom='1px solid var(--line)';n.style.gap='1rem'}
  });
</script>
</body>
</html>

```
