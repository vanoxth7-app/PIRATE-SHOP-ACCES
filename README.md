<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PIRATE SHOP | Accès Terminal</title>
  <style>
    /* VARIABLES ET RESET */
    :root {
      --neon-green: #00ff9c;
      --dim-green: #00b368;
      --bg-dark: #020a06;
      --bg-panel: rgba(0, 255, 156, 0.05);
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      background-color: var(--bg-dark);
      color: var(--neon-green);
      font-family: Consolas, "Courier New", monospace;
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* EFFET ÉCRAN CRT (SCANLINES) */
    body::after {
      content: ""; position: fixed; inset: 0; pointer-events: none; z-index: 999;
      background: repeating-linear-gradient(to bottom, transparent 0 2px, rgba(0,0,0,0.2) 3px, transparent 4px),
                  radial-gradient(circle at center, transparent 50%, rgba(0,0,0,0.6) 100%);
    }

    /* HEADER */
    header {
      border-bottom: 1px solid var(--dim-green);
      padding: 15px 30px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: var(--bg-panel);
    }
    .logo { font-size: 24px; font-weight: bold; letter-spacing: 4px; text-shadow: 0 0 10px var(--neon-green); }
    .status { font-size: 14px; animation: blink 1s steps(1) infinite; }
    @keyframes blink { 50% { opacity: 0; } }

    /* CONTENEUR PRINCIPAL */
    .container {
      max-width: 1000px; margin: 0 auto; padding: 40px 20px;
    }

    /* HERO SECTION */
    .hero { text-align: center; margin-bottom: 60px; }
    .hero h1 { font-size: clamp(30px, 5vw, 50px); margin-bottom: 15px; letter-spacing: 5px; }
    .hero p { color: var(--dim-green); font-size: 18px; max-width: 600px; margin: 0 auto; }
    
    /* TERMINAL MOCKUP */
    .terminal-box {
      border: 1px solid var(--neon-green);
      background: rgba(0, 0, 0, 0.5);
      padding: 20px; text-align: left; margin: 30px auto; max-width: 600px;
      box-shadow: inset 0 0 20px rgba(0,255,156,0.1);
    }
    .cmd { color: #fff; }

    /* SECTION PRIX */
    .pricing-title { text-align: center; font-size: 30px; margin-bottom: 40px; letter-spacing: 3px; }
    
    .pricing-grid {
      display: flex; flex-wrap: wrap; justify-content: center; gap: 25px;
    }

    .card {
      flex: 1; min-width: 260px; max-width: 320px;
      border: 1px solid var(--dim-green);
      background: var(--bg-panel);
      padding: 30px; text-align: center;
      transition: 0.3s;
      position: relative;
    }

    .card:hover { border-color: var(--neon-green); box-shadow: 0 0 25px rgba(0,255,156,0.2); transform: translateY(-5px); }
    
    .card.pro { border: 2px solid var(--neon-green); box-shadow: 0 0 15px rgba(0,255,156,0.15); }
    .card.pro::before {
      content: "POPULAIRE"; position: absolute; top: -12px; left: 50%; transform: translateX(-50%);
      background: var(--neon-green); color: var(--bg-dark); padding: 2px 10px; font-weight: bold; font-size: 12px;
    }

    .card h3 { font-size: 22px; margin-bottom: 10px; letter-spacing: 2px; }
    .price { font-size: 40px; font-weight: bold; margin-bottom: 20px; text-shadow: 0 0 10px var(--neon-green); }
    .price span { font-size: 16px; font-weight: normal; color: var(--dim-green); text-shadow: none; }
    
    .features { list-style: none; margin-bottom: 30px; text-align: left; color: #a1ebd0; font-size: 14px; }
    .features li { margin-bottom: 10px; }
    .features li::before { content: "> "; color: var(--neon-green); font-weight: bold; }

    /* BOUTONS */
    .btn {
      display: block; width: 100%; padding: 15px; text-decoration: none;
      background: transparent; border: 1px solid var(--neon-green);
      color: var(--neon-green); font-family: inherit; font-size: 16px; font-weight: bold;
      transition: 0.2s; cursor: pointer; letter-spacing: 2px;
    }
    .btn:hover, .card.pro .btn {
      background: var(--neon-green); color: var(--bg-dark); box-shadow: 0 0 15px var(--neon-green);
    }
    .card.pro .btn:hover { background: transparent; color: var(--neon-green); }

    /* FOOTER */
    footer { text-align: center; padding: 30px; border-top: 1px solid var(--dim-green); margin-top: 60px; font-size: 12px; color: var(--dim-green); }
  </style>
</head>
<body>

  <header>
    <div class="logo">☠ PIRATE_SHOP</div>
    <div class="status">SYS: ONLINE █</div>
  </header>

  <div class="container">
    
    <section class="hero">
      <h1>ACCÈS AU TERMINAL</h1>
      <p>Sélectionne ton niveau d'habilitation pour accéder aux outils et scripts.</p>
      
      <div class="terminal-box">
        <span class="cmd">root@pirate:~#</span> ./check_status.sh<br>
        [OK] Connexion sécurisée établie.<br>
        [OK] Base de données prête.<br>
        <span class="cmd">root@pirate:~#</span> En attente du paiement...
      </div>
    </section>

    <h2 class="pricing-title">/// NIVEAUX D'HABILITATION ///</h2>

    <section class="pricing-grid">
      
      <!-- PALIER 10€ -->
      <div class="card">
        <h3>BASIQUE</h3>
        <div class="price">10€</div>
        <ul class="features">
          <li>Accès aux outils standards</li>
          <li>Pack Visuel & Animation</li>
          <li>Support communautaire</li>
        </ul>
        <a href="https://buy.stripe.com/00w5kw9XdgLI6WH7ML4gg07" class="btn" target="_blank">▶ SÉLECTIONNER</a>
      </div>

      <!-- PALIER 25€ -->
      <div class="card pro">
        <h3>PRO</h3>
        <div class="price">25€</div>
        <ul class="features">
          <li>Tout du pack Basique</li>
          <li>Scripts Avancés</li>
          <li>Mises à jour prioritaires</li>
          <li>Support direct 24/7</li>
        </ul>
        <a href="https://buy.stripe.com/8x200c1qH8fc80L1on4gg06" class="btn" target="_blank">▶ SÉLECTIONNER</a>
      </div>

      <!-- PALIER ULTIME (Abonnement 1 mois) -->
      <div class="card">
        <h3>ULTIME</h3>
        <div class="price">50€ <span>/ 1 mois</span></div>
        <ul class="features">
          <li>Accès TOTAL au serveur</li>
          <li>Outils non censurés</li>
          <li>Accès privé VIP</li>
          <li>Requêtes sur mesure</li>
        </ul>
        <a href="https://buy.stripe.com/6oUbIU5GX5302Gr2sr4gg05" class="btn" target="_blank">▶ SÉLECTIONNER</a>
      </div>

    </section>

  </div>

  <footer>
    <p>© 2024 PIRATE SHOP. Tous droits réservés.</p>
    <p>Outils et animations à but éducatif et de divertissement (vidéos YouTube).</p>
  </footer>

</body>
</html>
