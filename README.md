<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Your Name — Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Big+Shoulders+Display:wght@500;700;900&family=IBM+Plex+Sans:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#14120F;
    --paper:#F3EFE7;
    --amber:#C98A3B;
    --muted:#8A8578;
    --line:#2C2A24;
    --max:1180px;
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--bg);
    color:var(--paper);
    font-family:'IBM Plex Sans', sans-serif;
    line-height:1.5;
    -webkit-font-smoothing:antialiased;
    overflow-x:hidden;
    /* subtle grain */
    background-image:
      radial-gradient(circle at 1px 1px, rgba(255,255,255,0.035) 1px, transparent 0);
    background-size:3px 3px;
  }
  a{color:inherit; text-decoration:none;}
  ::selection{background:var(--amber); color:var(--bg);}
  .wrap{max-width:var(--max); margin:0 auto; padding:0 32px;}

  /* header */
  header{
    display:flex; justify-content:space-between; align-items:center;
    padding:30px 0;
  }
  .mark{font-family:'Big Shoulders Display', sans-serif; font-weight:700; font-size:22px; letter-spacing:0.02em;}
  nav{display:flex; gap:26px; font-size:14px; color:var(--muted);}
  nav a:hover{color:var(--paper);}

  /* hero */
  .hero{padding:70px 0 60px; border-bottom:1px solid var(--line);}
  .hero h1{
    font-family:'Big Shoulders Display', sans-serif;
    font-weight:900;
    font-size:clamp(56px, 11vw, 148px);
    line-height:0.86;
    letter-spacing:-0.01em;
    text-transform:uppercase;
  }
  .hero h1 .thin{
    font-weight:500;
    color:var(--amber);
    font-style:normal;
  }
  .hero-sub{
    display:flex; justify-content:space-between; align-items:flex-end;
    margin-top:26px; gap:24px; flex-wrap:wrap;
  }
  .hero-sub p{max-width:42ch; color:#C9C4B6; font-size:16px;}
  .hero-sub .loc{font-size:13px; color:var(--muted); text-align:right; white-space:nowrap;}

  section{padding:70px 0;}
  .section-head{
    display:flex; justify-content:space-between; align-items:baseline;
    margin-bottom:36px;
  }
  .section-head h2{
    font-family:'Big Shoulders Display', sans-serif;
    font-weight:700; text-transform:uppercase;
    font-size:clamp(28px, 4vw, 44px);
    letter-spacing:0.01em;
  }
  .section-head span{font-size:13px; color:var(--muted);}

  /* filmstrip work */
  .filmstrip{
    display:flex; gap:18px;
    overflow-x:auto;
    padding-bottom:20px;
    scroll-snap-type:x proximity;
    margin:0 -32px; padding-left:32px; padding-right:32px;
  }
  .filmstrip::-webkit-scrollbar{height:5px;}
  .filmstrip::-webkit-scrollbar-thumb{background:var(--line); border-radius:4px;}
  .tile{
    flex:0 0 auto;
    scroll-snap-align:start;
    width:340px;
    display:flex; flex-direction:column;
  }
  .tile.wide{width:460px;}
  .tile-img{
    width:100%; height:400px;
    border-radius:2px;
    background:linear-gradient(160deg, var(--tile-a), var(--tile-b));
    transition:transform .35s ease;
  }
  .tile:hover .tile-img{transform:translateY(-6px);}
  .tile-meta{
    display:flex; justify-content:space-between; align-items:baseline;
    margin-top:14px;
  }
  .tile-title{font-family:'Big Shoulders Display', sans-serif; font-weight:700; font-size:20px; text-transform:uppercase;}
  .tile-tag{font-size:12px; color:var(--muted);}

  /* ticker */
  .ticker-wrap{
    border-top:1px solid var(--line);
    border-bottom:1px solid var(--line);
    overflow:hidden;
    padding:22px 0;
  }
  .ticker{
    display:flex; gap:40px; white-space:nowrap;
    width:max-content;
    animation:scroll 26s linear infinite;
    font-family:'Big Shoulders Display', sans-serif;
    font-weight:700; text-transform:uppercase;
    font-size:clamp(20px, 3vw, 30px);
    color:var(--muted);
  }
  .ticker span.dot{color:var(--amber);}
  @keyframes scroll{
    from{transform:translateX(0);}
    to{transform:translateX(-50%);}
  }
  @media (prefers-reduced-motion: reduce){
    .ticker{animation:none;}
  }

  /* about */
  .about-grid{
    display:grid; grid-template-columns:0.9fr 1.1fr; gap:60px;
  }
  .about-grid .big{
    font-family:'Big Shoulders Display', sans-serif;
    font-weight:500; font-size:clamp(24px,3vw,34px);
    line-height:1.25; color:var(--paper);
  }
  .about-grid .big .amber{color:var(--amber);}
  .about-list{list-style:none; font-size:14px;}
  .about-list li{
    display:flex; justify-content:space-between;
    padding:14px 0; border-bottom:1px solid var(--line); color:#C9C4B6;
  }
  .about-list li span{color:var(--muted);}

  /* contact */
  .contact{
    background:var(--amber);
    color:var(--bg);
    margin:0 -0; 
  }
  .contact-inner{padding:90px 0;}
  .contact h2{
    font-family:'Big Shoulders Display', sans-serif;
    font-weight:900; text-transform:uppercase;
    font-size:clamp(48px, 9vw, 110px);
    line-height:0.9;
  }
  .contact a.email{
    display:inline-block; margin-top:24px;
    font-size:clamp(18px,2.4vw,24px);
    font-weight:500;
    border-bottom:2px solid var(--bg);
  }
  .contact a.email:hover{opacity:0.7;}
  .social-row{
    display:flex; gap:24px; margin-top:44px; font-size:13px; font-weight:500;
  }
  .social-row a{border-bottom:1px solid rgba(20,18,15,0.4);}
  .social-row a:hover{border-color:var(--bg);}

  footer{
    background:var(--bg);
    padding:28px 0;
    display:flex; justify-content:space-between;
    font-size:12px; color:var(--muted);
  }

  @media (max-width:640px){
    .about-grid{grid-template-columns:1fr;}
    .tile{width:260px;}
    .tile.wide{width:300px;}
    .tile-img{height:300px;}
  }

  a:focus-visible, button:focus-visible{
    outline:2px solid var(--amber);
    outline-offset:3px;
  }
</style>
</head>
<body>

<div class="wrap">
  <header>
    <div class="mark">YOUR NAME</div>
    <nav>
      <a href="#work">Work</a>
      <a href="#about">About</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <div class="hero">
    <h1>Visual<br>craft<span class="thin">, sharpened.</span></h1>
    <div class="hero-sub">
      <p>Graphic design, branding, video editing and web development — built for brands that want to look like they mean it.</p>
      <div class="loc">Based in Colombo, Sri Lanka<br>Available for freelance — 2026</div>
    </div>
  </div>
</div>

<section id="work">
  <div class="wrap">
    <div class="section-head">
      <h2>Selected Work</h2>
      <span>Scroll →</span>
    </div>
  </div>
  <div class="filmstrip">
    <div class="tile wide" style="--tile-a:#C98A3B; --tile-b:#8A5A22;">
      <div class="tile-img"></div>
      <div class="tile-meta"><span class="tile-title">Fieldnote</span><span class="tile-tag">Branding · 2026</span></div>
    </div>
    <div class="tile" style="--tile-a:#3F4E5C; --tile-b:#1F2731;">
      <div class="tile-img"></div>
      <div class="tile-meta"><span class="tile-title">Lumen Studio</span><span class="tile-tag">Web · 2025</span></div>
    </div>
    <div class="tile wide" style="--tile-a:#6B4C4C; --tile-b:#3A2727;">
      <div class="tile-img"></div>
      <div class="tile-meta"><span class="tile-title">Northbound</span><span class="tile-tag">Video · 2025</span></div>
    </div>
    <div class="tile" style="--tile-a:#556B4A; --tile-b:#2C3925;">
      <div class="tile-img"></div>
      <div class="tile-meta"><span class="tile-title">Kite &amp; Co.</span><span class="tile-tag">Digital · 2024</span></div>
    </div>
    <div class="tile wide" style="--tile-a:#8A5A8A; --tile-b:#452D45;">
      <div class="tile-img"></div>
      <div class="tile-meta"><span class="tile-title">Halo Print</span><span class="tile-tag">Print · 2024</span></div>
    </div>
  </div>
</section>

<div class="ticker-wrap">
  <div class="ticker">
    <span>Branding <span class="dot">•</span></span>
    <span>Motion Design <span class="dot">•</span></span>
    <span>Web Development <span class="dot">•</span></span>
    <span>Art Direction <span class="dot">•</span></span>
    <span>Print Design <span class="dot">•</span></span>
    <span>Branding <span class="dot">•</span></span>
    <span>Motion Design <span class="dot">•</span></span>
    <span>Web Development <span class="dot">•</span></span>
    <span>Art Direction <span class="dot">•</span></span>
    <span>Print Design <span class="dot">•</span></span>
  </div>
</div>

<section id="about">
  <div class="wrap">
    <div class="section-head">
      <h2>About</h2>
      <span>Profile</span>
    </div>
    <div class="about-grid">
      <p class="big">I build identities and interfaces that hold up under scrutiny — <span class="amber">not just first glance.</span></p>
      <ul class="about-list">
        <li><span>Experience</span> 5 years, freelance &amp; studio</li>
        <li><span>Focus</span> Branding, web, motion</li>
        <li><span>Tools</span> Figma, Premiere, After Effects</li>
        <li><span>Clients</span> Startups, creators, small brands</li>
      </ul>
    </div>
  </div>
</section>

<section id="contact" class="contact">
  <div class="wrap contact-inner">
    <h2>Let's build<br>something.</h2>
    <a class="email" href="mailto:hello@yourname.com">hello@yourname.com</a>
    <div class="social-row">
      <a href="#">Instagram</a>
      <a href="#">YouTube</a>
      <a href="#">TikTok</a>
      <a href="#">Facebook</a>
    </div>
  </div>
</section>

<footer>
  <div class="wrap" style="display:flex; justify-content:space-between; width:100%;">
    <span>© 2026 Your Name</span>
    <span>Colombo, Sri Lanka</span>
  </div>
</footer>

</body>
</html>
