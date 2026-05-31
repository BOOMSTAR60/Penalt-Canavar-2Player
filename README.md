# [index.html](https://github.com/user-attachments/files/28442126/index.html)
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Derbi Penaltı Serisi - Resmi Tanıtım ve Maç Alanı</title>
  <style>
    /* GENEL SAYFA TASARIMI */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background-color: #121212;
      color: #ffffff;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      scroll-behavior: smooth;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    /* ÜST MENÜ BAR (NAVBAR) */
    header {
      position: fixed;
      top: 0;
      width: 100%;
      background: rgba(18, 18, 18, 0.95);
      backdrop-filter: blur(10px);
      padding: 20px 50px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      z-index: 100;
      border-bottom: 2px solid #4caf50;
    }

    .logo {
      font-size: 24px;
      font-weight: bold;
      letter-spacing: 1px;
      color: #4caf50;
    }

    .nav-links {
      display: flex;
      list-style: none;
      gap: 25px;
      align-items: center;
    }

    .nav-links a {
      font-size: 15px;
      font-weight: 500;
      transition: color 0.3s;
    }

    .nav-links a:hover {
      color: #4caf50;
    }

    .nav-btn {
      background-color: #4caf50;
      padding: 8px 18px;
      border-radius: 20px;
      font-weight: bold !important;
      transition: background-color 0.3s, transform 0.2s !important;
    }

    .nav-btn:hover {
      background-color: #45a049;
      transform: scale(1.05);
      color: white !important;
    }

    /* ANA GİRİŞ EKRANI (HERO BÖLÜMÜ) */
    .hero {
      height: 100vh;
      background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(18, 18, 18, 1)), 
                  url('https://images.unsplash.com/photo-1508098682722-e99c43a406b2?q=80&w=1920') no-repeat center center/cover;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 0 20px;
    }

    .hero h1 {
      font-size: 56px;
      font-weight: 800;
      margin-bottom: 20px;
      text-transform: uppercase;
      letter-spacing: 2px;
      text-shadow: 3px 3px 10px rgba(0,0,0,0.8);
    }

    .hero h1 span {
      color: #4caf50;
    }

    .hero p {
      font-size: 19px;
      color: #ccc;
      max-width: 700px;
      margin-bottom: 40px;
      line-height: 1.6;
    }

    .hero-btns {
      display: flex;
      gap: 20px;
    }

    .btn {
      color: white;
      padding: 15px 35px;
      font-size: 17px;
      font-weight: bold;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3);
      transition: transform 0.2s, background-color 0.3s;
    }

    .btn-1 { background-color: #4caf50; }
    .btn-1:hover { background-color: #45a049; transform: scale(1.05); }
    
    .btn-2 { background-color: #333; border: 2px solid #555; }
    .btn-2:hover { background-color: #444; transform: scale(1.05); }

    /* ÖZELLİKLER BÖLÜMÜ */
    section {
      padding: 90px 20px;
      max-width: 1200px;
      margin: 0 auto;
    }

    section h2 {
      font-size: 36px;
      text-align: center;
      margin-bottom: 50px;
      text-transform: uppercase;
      position: relative;
    }

    section h2::after {
      content: '';
      position: absolute;
      bottom: -15px;
      left: 50%;
      transform: translateX(-50%);
      width: 80px;
      height: 4px;
      background-color: #4caf50;
    }

    .features-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 30px;
    }

    .feature-card {
      background: #1e1e1e;
      padding: 40px 30px;
      border-radius: 15px;
      text-align: center;
      border: 1px solid #333;
      transition: transform 0.3s, border-color 0.3s;
    }

    .feature-card:hover {
      transform: translateY(-10px);
      border-color: #4caf50;
    }

    .feature-icon {
      font-size: 45px;
      margin-bottom: 20px;
    }

    .feature-card h3 {
      font-size: 21px;
      margin-bottom: 15px;
    }

    .feature-card p {
      color: #aaa;
      font-size: 15px;
      line-height: 1.6;
    }

    /* OYUN ALANLARI ORTAK TASARIMI */
    .game-zone {
      max-width: 100%;
      background: #0d0d0d;
      display: flex;
      flex-direction: column;
      align-items: center;
      border-top: 1px solid #222;
      border-bottom: 1px solid #222;
    }

    .game-wrapper {
      position: relative;
      margin: 20px 0 40px 0;
    }

    canvas {
      display: block;
      background: linear-gradient(#4caf50, #2e8b57);
      border: 4px solid white;
      border-radius: 8px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.7);
    }

    .info-bar {
      position: absolute;
      top: 140px;
      left: 50%;
      transform: translateX(-50%);
      color: white;
      font-size: 24px;
      font-weight: bold;
      text-shadow: 2px 2px 4px black;
      pointer-events: none;
      display: none; 
      text-align: center;
      white-space: nowrap;
    }

    .controls-hint {
      position: absolute;
      bottom: -35px;
      left: 50%;
      transform: translateX(-50%);
      color: #aaa;
      font-size: 14px;
      text-align: center;
      width: 100%;
    }

    /* TAKIM SEÇİM EKRANLARI */
    .team-select-screen {
      position: absolute;
      top: 0;
      left: 0;
      width: 900px;
      height: 600px;
      background: rgba(0, 0, 0, 0.85);
      border: 4px solid white;
      border-radius: 8px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      color: white;
      z-index: 10;
    }

    .team-select-screen h3 {
      font-size: 32px;
      margin-bottom: 40px;
      text-transform: uppercase;
      letter-spacing: 2px;
    }

    .btn-container {
      display: flex;
      gap: 25px;
    }

    .team-btn {
      padding: 15px 35px;
      font-size: 19px;
      font-weight: bold;
      border: 3px solid white;
      border-radius: 10px;
      cursor: pointer;
      transition: transform 0.2s;
    }

    .team-btn:hover { transform: scale(1.1); }
    .gs-btn { background: linear-gradient(45deg, #a90432, #fdb913); color: white; text-shadow: 1px 1px 2px black; }
    .fb-btn { background: linear-gradient(45deg, #002f6c, #fdb913); color: white; text-shadow: 1px 1px 2px black; }
    .bjk-btn { background: linear-gradient(45deg, #000000, #ffffff); color: #000000; border-color: #000; background-color: #fff; }

    /* SİSTEM TABLOSU */
    .specs-table {
      width: 100%;
      max-width: 600px;
      margin: 30px auto 0 auto;
      border-collapse: collapse;
      background: #1e1e1e;
      border-radius: 10px;
      overflow: hidden;
    }

    .specs-table td {
      padding: 15px 20px;
      border-bottom: 1px solid #333;
    }

    .specs-table td:first-child {
      font-weight: bold;
      color: #4caf50;
      width: 40%;
    }

    footer {
      background: #0a0a0a;
      text-align: center;
      padding: 30px 20px;
      color: #555;
      font-size: 14px;
      border-top: 1px solid #222;
    }
  </style>
</head>
<body>

  <header>
    <div class="logo">⚽ ARENA-X</div>
    <ul class="nav-links">
      <li><a href="#">Ana Sayfa</a></li>
      <li><a href="#ozellikler">Özellikler</a></li>
      <li><a href="#single-zone" class="nav-btn">TEK KİŞİLİK</a></li>
      <li><a href="#pvp-zone" class="nav-btn" style="background-color: #002f6c;">2 KİŞİLİK DERBİ</a></li>
    </ul>
  </header>

  <section class="hero">
    <h1>Penaltı Arenasına <span>Hoş Geldin!</span></h1>
    <p>İster yapay zekanın süper hızlı kalecisine meydan oku, ister aynı klavyede arkadaşınla dev bir derbi mücadelesine çık! Takımını seç ve tribünleri coştur.</p>
    <div class="hero-btns">
      <a href="#single-zone" class="btn btn-1">Tek Başınasın (Mod 1)</a>
      <a href="#pvp-zone" class="btn btn-2">Arkadaşınla Kapış (Mod 2)</a>
    </div>
  </section>

  <section id="ozellikler">
    <h2>Gelişmiş Oyun Özellikleri</h2>
    <div class="features-grid">
      <div class="feature-card">
        <div class="feature-icon">🤖</div>
        <h3>Yapay Zeka Kaleci</h3>
        <p>Tek kişilik modda sağa sola durmadan mekik dokuyan, refleksleri üst düzey bir kaleciye karşı şut çek!</p>
      </div>
      <div class="feature-card">
        <div class="feature-icon">👥</div>
        <h3>2 Kişilik PvP Modu</h3>
        <p>Aynı bilgisayarda biriniz fareyle şut yönünü belirlerken, diğeriniz [A] ve [D] tuşlarıyla kaleyi korur.</p>
      </div>
      <div class="feature-card">
        <div class="feature-icon">🔊</div>
        <h3>Dinamik Ses ve Tribün</h3>
        <p>Attığın her golde stadyum hoparlörleri inler, taraftarlar seçtiğin takımın renkleriyle zıplar!</p>
      </div>
    </div>
  </section>

  <section id="single-zone" class="game-zone">
    <h2>🎯 MOD 1: PENALTI CANAVARI (TEK KİŞİLİK)</h2>
    <p style="color: #aaa; margin-bottom: 10px;">Yapay zekanın reflekslerini test etme zamanı!</p>
    
    <div class="game-wrapper">
      <div id="team-select-1" class="team-select-screen">
        <h3>Takımını Seç</h3>
        <div class="btn-container">
          <button class="team-btn gs-btn" onclick="initSingleGame('GS')">Galatasaray</button>
          <button class="team-btn fb-btn" onclick="initSingleGame('FB')">Fenerbahçe</button>
          <button class="team-btn bjk-btn" onclick="initSingleGame('BJK')">Beşiktaş</button>
        </div>
      </div>
      <div id="info-1" class="info-bar">Gol: 0</div>
      <canvas id="gameSingle" width="900" height="600"></canvas>
      <div class="controls-hint">🕹️ <b>Şutör:</b> Fare ile nişan al ve Sol Tıkla! Kaleci otomatik hareket eder.</div>
    </div>
  </section>

  <section id="pvp-zone" class="game-zone" style="background-color: #090909;">
    <h2>🏆 MOD 2: DERBİ KAPIŞMASI (2 KİŞİLİK PvP)</h2>
    <p style="color: #aaa; margin-bottom: 10px;">Arkadaşınla aynı klavyede büyük rekabet!</p>
    
    <div class="game-wrapper">
      <div id="team-select-2" class="team-select-screen">
        <h3>Şutörün Takımını Seç</h3>
        <div class="btn-container">
          <button class="team-btn gs-btn" onclick="initPvPGame('GS')">Galatasaray</button>
          <button class="team-btn fb-btn" onclick="initPvPGame('FB')">Fenerbahçe</button>
          <button class="team-btn bjk-btn" onclick="initPvPGame('BJK')">Beşiktaş</button>
        </div>
      </div>
      <div id="info-2" class="info-bar">Şutör (Gol): 0 &nbsp;|&nbsp; Kaleci (Kurtarış): 0</div>
      <canvas id="gamePvP" width="900" height="600"></canvas>
      <div class="controls-hint">🕹️ <b>Şutör:</b> Fare Sol Tık | 🧤 <b>Kaleci:</b> Klavye [A] ve [D] Tuşları</div>
    </div>
  </section>

  <section id="sistem">
    <h2>Sistem Uyumlulu
