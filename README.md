# Tooro-Buns-website
TOORO BUNS-flame grilled Burgers Website with online ordering 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes">
  <title>TOORO BUNS · Burgers with a Tooro Soul</title>
  <!-- Primary fonts: bold headlines (Bebas Neue) + clean body (Inter) -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background-color: #0A0A0A; /* deep charcoal black */
      color: #F5F5F5;
      font-family: 'Inter', sans-serif;
      line-height: 1.5;
      -webkit-font-smoothing: antialiased;
    }

    h1, h2, h3, .display-font {
      font-family: 'Bebas Neue', cursive;
      font-weight: 400;
      letter-spacing: 1.5px;
      text-transform: uppercase;
    }

    /* accent colors */
    :root {
      --flame: #FF4C13;
      --gold: #FFD700;
      --dark-bg: #0A0A0A;
      --card-bg: #141414;
      --border-glow: rgba(255, 76, 19, 0.3);
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 20px;
    }

    /* flame / grill texture hint */
    .bg-texture {
      background-image: radial-gradient(circle at 30% 40%, rgba(255, 76, 19, 0.08) 0%, transparent 30%);
    }

    /* Buttons & CTAs */
    .btn {
      display: inline-block;
      font-family: 'Inter', sans-serif;
      font-weight: 700;
      text-decoration: none;
      padding: 16px 28px;
      border-radius: 60px;
      transition: all 0.2s ease;
      text-align: center;
      border: none;
      cursor: pointer;
      font-size: 1.1rem;
      letter-spacing: 0.5px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.5);
    }

    .btn-primary {
      background: var(--flame);
      color: #0A0A0A;
      border: 2px solid var(--flame);
    }

    .btn-primary:hover {
      background: #e03e0a;
      border-color: #e03e0a;
      transform: scale(1.02);
      box-shadow: 0 0 15px #FF4C13aa;
    }

    .btn-outline {
      background: transparent;
      color: white;
      border: 2px solid var(--flame);
    }

    .btn-outline:hover {
      background: var(--flame);
      color: #0A0A0A;
    }

    .btn-wa {
      background: #25D366;
      color: #0A0A0A;
      border: none;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
    }

    .btn-wa:hover {
      background: #20b859;
      box-shadow: 0 0 20px #25D366;
    }

    /* Sticky WhatsApp button (mobile) */
    .sticky-wa {
      position: fixed;
      bottom: 24px;
      right: 24px;
      z-index: 1000;
      background: #25D366;
      color: #0A0A0A;
      width: 65px;
      height: 65px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 6px 20px rgba(0,0,0,0.6), 0 0 0 3px var(--gold);
      transition: transform 0.2s;
      text-decoration: none;
    }

    .sticky-wa:hover {
      transform: scale(1.1);
    }

    .sticky-wa svg {
      width: 38px;
      height: 38px;
      fill: #0A0A0A;
    }

    /* Logo style */
    .logo {
      font-family: 'Bebas Neue', cursive;
      font-size: 2.4rem;
      letter-spacing: 3px;
      color: white;
      display: inline-block;
      line-height: 1;
    }

    .logo .flame-o {
      display: inline-block;
      position: relative;
      color: var(--flame);
      text-shadow: 0 0 12px var(--flame);
    }

    /* Sections */
    section {
      padding: 70px 0;
      border-bottom: 1px solid rgba(255, 76, 19, 0.15);
    }

    .section-title {
      font-size: 3.5rem;
      margin-bottom: 30px;
      color: white;
      position: relative;
      display: inline-block;
    }

    .section-title::after {
      content: "🔥";
      font-size: 2.2rem;
      margin-left: 12px;
      color: var(--flame);
    }

    /* Hero */
    .hero {
      padding: 20px 0 60px;
      min-height: 90vh;
      display: flex;
      align-items: center;
      background: radial-gradient(circle at 80% 30%, #2a1508 0%, #0A0A0A 80%);
    }

    .hero-grid {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 30px;
    }

    .hero-content {
      flex: 1 1 350px;
    }

    .hero-visual {
      flex: 1 1 350px;
      text-align: center;
      position: relative;
    }

    .hero h1 {
      font-size: clamp(3.2rem, 12vw, 5.5rem);
      line-height: 1.1;
      margin-bottom: 20px;
    }

    .hero .highlight {
      color: var(--flame);
      text-shadow: 0 0 8px #FF4C13;
    }

    .trust-badge {
      display: inline-block;
      background: #1f1f1f;
      padding: 8px 20px;
      border-radius: 40px;
      border-left: 6px solid var(--flame);
      margin: 20px 0 30px;
      font-weight: 600;
    }

    /* burger visual placeholder */
    .flame-burger {
      max-width: 100%;
      height: auto;
      filter: drop-shadow(0 0 30px #FF4C1340);
      border-radius: 40px;
    }

    /* Testimonials */
    .testimonial-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 24px;
    }

    .testimonial-card {
      background: var(--card-bg);
      padding: 24px;
      border-radius: 24px;
      border: 1px solid #2a2a2a;
      box-shadow: 0 10px 20px -5px rgba(0,0,0,0.7);
    }

    .stars {
      color: var(--gold);
      font-size: 1.3rem;
      margin-bottom: 12px;
    }

    .testimonial-card p {
      font-style: italic;
      font-size: 1.05rem;
    }

    /* Menu cards */
    .menu-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 24px;
    }

    .menu-item {
      background: #121212;
      border-radius: 28px;
      padding: 24px;
      border: 1px solid #2c2c2c;
      transition: border 0.2s;
      display: flex;
      flex-direction: column;
    }

    .menu-item:hover {
      border-color: var(--flame);
    }

    .menu-title {
      font-family: 'Bebas Neue', cursive;
      font-size: 2rem;
      letter-spacing: 1px;
      color: white;
    }

    .price {
      font-size: 1.8rem;
      font-weight: 700;
      color: var(--gold);
      margin: 10px 0 8px;
    }

    .desc {
      color: #bbb;
      margin-bottom: 20px;
      flex-grow: 1;
    }

    .badge {
      background: var(--flame);
      color: #0A0A0A;
      padding: 4px 12px;
      border-radius: 40px;
      font-weight: 700;
      font-size: 0.8rem;
      display: inline-block;
      margin-left: 8px;
    }

    .menu-footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 12px;
    }

    .btn-small {
      padding: 10px 20px;
      font-size: 0.95rem;
      background: transparent;
      border: 1.5px solid var(--flame);
      color: white;
      border-radius: 40px;
      text-decoration: none;
      font-weight: 600;
    }

    .btn-small:hover {
      background: var(--flame);
      color: black;
    }

    /* How to order steps */
    .steps {
      display: flex;
      flex-wrap: wrap;
      gap: 20px;
      margin-top: 30px;
    }

    .step {
      flex: 1 1 180px;
      background: #151515;
      padding: 30px 20px;
      border-radius: 30px;
      text-align: center;
      border-bottom: 6px solid var(--flame);
    }

    .step-number {
      font-size: 4rem;
      font-family: 'Bebas Neue', cursive;
      color: var(--flame);
      opacity: 0.5;
      line-height: 1;
    }

    /* urgency strip */
    .urgency {
      background: #1C0E08;
      border-top: 2px solid var(--flame);
      border-bottom: 2px solid var(--flame);
      text-align: center;
    }

    /* Map placeholder */
    .location-flex {
      display: flex;
      flex-wrap: wrap;
      gap: 30px;
    }

    .map-placeholder {
      background: #1e1e1e;
      border-radius: 30px;
      padding: 20px;
      border: 1px solid #444;
      flex: 1 1 280px;
    }

    .map-image {
      width: 100%;
      height: 220px;
      background: #2a2a2a;
      border-radius: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 200 120" width="100%" height="100%"><rect width="200" height="120" fill="%23333"/><text x="20" y="60" fill="%23FF4C13" font-size="14" font-family="monospace">📍 SAM'S PLACE</text><circle cx="100" cy="50" r="8" fill="%23FF4C13"/><path d="M90 70 L110 70 L105 90 L95 90 Z" fill="%23FFD700"/></svg>');
      background-size: cover;
    }

    .footer {
      padding: 40px 0;
      text-align: center;
      background: #050505;
      color: #aaa;
    }

    .footer-logo {
      font-size: 2.5rem;
    }

    /* responsiveness */
    @media (max-width: 600px) {
      .section-title { font-size: 2.8rem; }
      .hero { min-height: auto; }
      .btn { padding: 14px 20px; font-size: 1rem; }
    }

    /* inline wa icon */
    .wa-icon {
      margin-right: 6px;
    }

    /* gold for differentiation */
    .gold-text { color: var(--gold); }
  </style>
</head>
<body>

<!-- Sticky WhatsApp CTA -->
<a href="https://wa.me/256768775079?text=I'm%20ready%20to%20order%20🔥%20TOORO%20BUNS" class="sticky-wa" aria-label="Order on WhatsApp">
  <svg viewBox="0 0 24 24" width="36" height="36"><path d="M12 2C6.48 2 2 6.48 2 12c0 1.86.5 3.61 1.38 5.12L2.05 22l4.96-1.3A9.94 9.94 0 0 0 12 22c5.52 0 10-4.48 10-10S17.52 2 12 2zm0 18c-1.64 0-3.21-.44-4.56-1.21l-.33-.19-2.94.77.79-2.86-.2-.35A8.01 8.01 0 0 1 4 12c0-4.41 3.59-8 8-8s8 3.59 8 8-3.59 8-8 8z"/><path d="M17.5 14.5c-.2 0-1-.5-1.2-.6-.2-.1-.3-.2-.5.2-.2.4-.7 1.2-.8 1.4-.1.2-.3.3-.5.1-1.2-.6-2-1-3.5-2.4-.3-.3-.6-.7-.8-1 .1-.1.2-.3.4-.5.2-.2.3-.4.5-.6.1-.2.2-.3 0-.5-.1-.2-.6-1.3-.8-1.8-.2-.4-.4-.4-.6-.4h-.5c-.2 0-.5.1-.8.4-.3.3-1 .9-1 2.2s1 2.6 1.2 2.8c.2.2 2 3.1 4.8 4.3.6.3 1.2.4 1.6.5.7.1 1.3 0 1.8-.2.5-.2 1.5-.6 1.7-1.2.2-.6.2-1.1.1-1.2-.1-.1-.3-.2-.5-.3z"/></svg>
</a>

<!-- HERO SECTION -->
<section class="hero bg-texture">
  <div class="container hero-grid">
    <div class="hero-content">
      <div class="logo" style="margin-bottom: 15px;">
        TOOR<span class="flame-o">O</span> BUNS
      </div>
      <h1>
        FORGET EVERYTHING <br>
        YOU KNOW ABOUT BURGERS.<br>
        <span class="highlight">THIS IS THE NYAMWIRU FEAST.</span>
      </h1>
      <p style="font-size: 1.4rem; margin-bottom: 10px; font-weight: 600;">Flame‑Grilled. Overloaded. Dripping with Bachwezi Secret Sauce.</p>
      <p style="margin-bottom: 20px;">📍 Mugurusi Road, Sam’s Place, Fort Portal</p>
      <div class="trust-badge">
        🔥 FRESH OFF THE GRILL 🔥
      </div>
      <div style="display: flex; gap: 15px; flex-wrap: wrap;">
        <a href="https://wa.me/256768775079?text=I%20want%20to%20order%20🔥%20TOORO%20BUNS" class="btn btn-primary">👉 ORDER NOW ON WHATSAPP</a>
        <a href="#location" class="btn btn-outline">📍 FIND US</a>
      </div>
    </div>
    <div class="hero-visual">
      <!-- flame burger visual with SVG overlay -->
      <div style="position: relative;">
        <svg viewBox="0 0 400 300" style="width: 100%; max-width: 450px;" class="flame-burger">
          <rect width="400" height="300" rx="40" fill="#1A0E07" />
          <!-- burger illustration -->
          <circle cx="200" cy="130" r="90" fill="#8B4513" opacity="0.5"/>
          <rect x="110" y="120" width="180" height="25" fill="#D2691E" rx="8"/>
          <rect x="120" y="110" width="160" height="20" fill="#FF6347" rx="6"/>
          <rect x="130" y="100" width="140" height="18" fill="#F4A460" rx="6"/>
          <rect x="115" y="140" width="170" height="22" fill="#CD853F" rx="8"/>
          <rect x="125" y="155" width="150" height="20" fill="#8B0000" rx="6"/>
          <!-- flame accents -->
          <path d="M280 70 Q300 30 310 70 Q320 30 330 70" stroke="#FF4C13" stroke-width="6" fill="none" stroke-linecap="round"/>
          <path d="M80 180 Q60 140 70 180 Q50 140 60 180" stroke="#FFD700" stroke-width="5" fill="none"/>
          <text x="140" y="240" fill="#FFD700" font-family="Bebas Neue" font-size="22">TOORO SOUL</text>
        </svg>
      </div>
    </div>
  </div>
</section>

<!-- SOCIAL PROOF -->
<section>
  <div class="container">
    <h2 class="section-title">THE STREETS ARE TALKING</h2>
    <div class="testimonial-grid">
      <div class="testimonial-card">
        <div class="stars">⭐⭐⭐⭐⭐</div>
        <p>“Best burger in Fort Portal. The Bachwezi Secret is on another level. Juicy, smoky, perfect.”</p>
        <p style="margin-top: 15px; font-weight: 700;">— Brenda K.</p>
      </div>
      <div class="testimonial-card">
        <div class="stars">⭐⭐⭐⭐⭐</div>
        <p>“Worth every shilling. Nyamwiru Feast Double is MASSIVE. Finally a place that doesn't skimp.”</p>
        <p style="margin-top: 15px; font-weight: 700;">— James O.</p>
      </div>
      <div class="testimonial-card">
        <div class="stars">⭐⭐⭐⭐⭐</div>
        <p>“That Pit Secret is addictive. Smoky BBQ wings with a local twist. Get extra napkins.”</p>
        <p style="margin-top: 15px; font-weight: 700;">— Sarah M.</p>
      </div>
      <div class="testimonial-card">
        <div class="stars">⭐⭐⭐⭐⭐</div>
        <p>“Night food vibe unmatched. The grill glow hits different. Fast service too.”</p>
        <p style="margin-top: 15px; font-weight: 700;">— @EastAfricaEats</p>
      </div>
    </div>
  </div>
</section>

<!-- MENU SHOWCASE -->
<section>
  <div class="container">
    <h2 class="section-title">FLAME MENU · TOORO PRIDE</h2>
    <div class="menu-grid">
      <!-- Royal Classic -->
      <div class="menu-item">
        <div class="menu-title">ROYAL CLASSIC <span style="color:var(--gold);">with CHEESE</span></div>
        <div class="price">15,000 UGX</div>
        <div class="desc">Premium beef patty, melted cheese, fresh lettuce, tomato, onions, house sauce. Smooth. Rich. Classic. ⭐ Served with Chwezi Fries</div>
        <div class="menu-footer"><span>🔥 classic</span> <a href="https://wa.me/256768775079?text=I'd%20like%20Royal%20Classic%20with%20Cheese%20🍔" class="btn-small">👉 ORDER</a></div>
      </div>
      <!-- Street King -->
      <div class="menu-item">
        <div class="menu-title">STREET KING <span style="font-size:1.2rem;">(NO CHEESE)</span></div>
        <div class="price">10,000 UGX</div>
        <div class="desc">Juicy beef patty, lettuce, tomato, onions, signature house sauce. Budget-friendly, flavor-packed. ⭐ Served with Chwezi Fries</div>
        <div class="menu-footer"><span>💪 budget beast</span> <a href="https://wa.me/256768775079?text=I'll%20take%20Street%20King%20Burger%20🔥" class="btn-small">👉 ORDER</a></div>
      </div>
      <!-- Bachwezi Secret -->
      <div class="menu-item" style="border: 2px solid #FFD70033;">
        <div class="menu-title">BACHWEZI SECRET <span class="badge">PREMIUM</span></div>
        <div class="price">25,000 UGX</div>
        <div class="desc">Beef patty, melted cheese, crispy bacon, caramelized onions, pickles, Bachwezi Secret Sauce. ⭐ Includes Chwezi Fries</div>
        <div class="menu-footer"><span>👑 heritage</span> <a href="https://wa.me/256768775079?text=One%20Bachwezi%20Secret%20please!%20🔥" class="btn-small">👉 ORDER</a></div>
      </div>
      <!-- Nyamwiru Feast Double -->
      <div class="menu-item" style="background: #1A0E07;">
        <div class="menu-title">NYAMWIRU FEAST DOUBLE <span class="badge">BEAST</span></div>
        <div class="price">35,000 UGX</div>
        <div class="desc">Two flame-grilled patties, double cheese, bacon, fresh veg, pickles, premium house sauce. Built for serious appetites. ⭐ Served with Chwezi Fries</div>
        <div class="menu-footer"><span>🍖 double trouble</span> <a href="https://wa.me/256768775079?text=Nyamwiru%20Feast%20Double%20–%20I'm%20hungry!" class="btn-small">👉 ORDER</a></div>
      </div>
      <!-- Royal Chicken Burger -->
      <div class="menu-item">
        <div class="menu-title">ROYAL CHICKEN BURGER</div>
        <div class="price">25,000 UGX</div>
        <div class="desc">Grilled chicken fillet, lettuce, tomato, house sauce. Bold premium chicken option. ⭐ Served with Chwezi Fries</div>
        <div class="menu-footer"><span>🐔 grilled</span> <a href="https://wa.me/256768775079?text=Royal%20Chicken%20Burger%20please%20🍗" class="btn-small">👉 ORDER</a></div>
      </div>
      <!-- THE PIT SECRET (highlight) -->
      <div class="menu-item" style="background: #1f140e; border-left: 8px solid var(--flame);">
        <div class="menu-title">THE PIT SECRET 🔥</div>
        <div class="price">15,000 UGX</div>
        <div class="desc">Smoky BBQ glazed chicken wings. Signature item — highlight heavily. ⭐ Served with Chwezi Fries</div>
        <div class="menu-footer"><span>CROWD FAVORITE</span> <a href="https://wa.me/256768775079?text=I%20need%20The%20Pit%20Secret%20Wings%20🔥" class="btn-small">👉 ORDER</a></div>
      </div>
      <!-- Sides and drinks (compact) -->
    </div>
    <!-- extra sides/add-ons row -->
    <div style="display: flex; flex-wrap: wrap; gap: 20px; margin-top: 30px; justify-content: center;">
      <div style="background:#151515; padding:16px 25px; border-radius:50px;"><strong>Extra Chwezi Fries</strong> 5,000 UGX <a href="#" class="btn-small" style="margin-left:12px;">ADD</a></div>
      <div style="background:#151515; padding:16px 25px; border-radius:50px;"><strong>Loaded Chwezi Fries</strong> 12,000 UGX <a href="#" class="btn-small" style="margin-left:12px;">ADD</a></div>
      <div style="background:#151515; padding:16px 25px; border-radius:50px;"><strong>Soft Drinks</strong> 3,000 UGX</div>
      <div style="background:#151515; padding:16px 25px; border-radius:50px;"><strong>Water</strong> 2,000 UGX</div>
    </div>
    <div style="text-align: center; margin: 40px 0 20px;">
      <a href="https://wa.me/256768775079?text=I'm%20ready%20to%20order%20from%20TOORO%20BUNS" class="btn btn-primary">👉 ORDER NOW – FULL MENU ON WHATSAPP</a>
    </div>
  </div>
</section>

<!-- WHY TOORO BUNS -->
<section>
  <div class="container">
    <h2 class="section-title">WHY THE FLAME?</h2>
    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(180px,1fr)); gap: 30px;">
      <div><span style="font-size:2.5rem;">🔥</span><h3>FLAME GRILLED</h3><p>Real fire. Real flavor. No shortcuts.</p></div>
      <div><span style="font-size:2.5rem;">👑</span><h3>TOORO SOUL</h3><p>Signature Pit Secret & Bachwezi sauces – exclusive.</p></div>
      <div><span style="font-size:2.5rem;">⚖️</span><h3>BIG ENERGY</h3><p>Massive portions. You leave full or not at all.</p></div>
      <div><span style="font-size:2.5rem;">⚡</span><h3>FAST & FRESH</h3><p>From grill to box in minutes. No waiting.</p></div>
    </div>
  </div>
</section>

<!-- HOW TO ORDER -->
<section>
  <div class="container">
    <h2 class="section-title">3 STEPS TO FLAVOR</h2>
    <div class="steps">
      <div class="step"><div class="step-number">01</div><h3>TAP WHATSAPP</h3><p>Green button. Chat opens.</p></div>
      <div class="step"><div class="step-number">02</div><h3>SEND ORDER</h3><p>"1 Nyamwiru Feast & Pit Secret Wings"</p></div>
      <div class="step"><div class="step-number">03</div><h3>PICK UP HOT</h3><p>📍 Sam's Place, Mugurusi Road.</p></div>
    </div>
  </div>
</section>

<!-- LOCATION + URGENCY -->
<section id="location">
  <div class="container">
    <div class="location-flex">
      <div style="flex:1;">
        <h2 class="section-title" style="margin-bottom:10px;">FIND THE FLAME</h2>
        <p style="font-size:1.8rem; font-weight:700;">📍 Mugurusi Road, Sam’s Place, Fort Portal</p>
        <p style="margin:20px 0;"><em>Landmark: Look for the crowd and the smell of smoke near the main junction.</em></p>
        <a href="#" class="btn btn-outline" style="margin-top:10px;">📍 GET DI
