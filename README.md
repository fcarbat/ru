<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>ФК «АРБАТ» — официальный сайт</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800;900&family=Oswald:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #00a862;
      --primary-dark: #007a47;
      --accent: #ffd200;
      --accent-dark: #e6b800;
      --dark: #0d1117;
      --dark-2: #161b22;
      --dark-3: #1f2630;
      --light: #f0f4f0;
      --gray: #8b949e;
      --white: #ffffff;
      --radius: 14px;
      --shadow: 0 8px 30px rgba(0,0,0,0.12);
      --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }
    * { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body {
      font-family: 'Montserrat', sans-serif;
      background: var(--dark);
      color: var(--light);
      line-height: 1.7;
      overflow-x: hidden;
    }
    h1, h2, h3, .display { font-family: 'Oswald', sans-serif; letter-spacing: 0.5px; }
    a { text-decoration: none; color: inherit; }
    img { max-width: 100%; display: block; }

    /* ===== HEADER ===== */
    header {
      position: fixed; top: 0; left: 0; right: 0; z-index: 1000;
      background: rgba(13,17,23,0.85); backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(255,255,255,0.06);
      padding: 0.8rem 2rem;
      display: flex; justify-content: space-between; align-items: center;
      transition: var(--transition);
    }
    .logo {
      display: flex; align-items: center; gap: 0.6rem;
      font-family: 'Oswald', sans-serif; font-size: 1.4rem; font-weight: 700;
      color: var(--white); text-transform: uppercase; letter-spacing: 1px;
    }
    .logo .crest {
      width: 38px; height: 38px; border-radius: 50%;
      background: linear-gradient(135deg, var(--primary), var(--primary-dark));
      display: flex; align-items: center; justify-content: center;
      font-size: 1.1rem; color: var(--white); border: 2px solid var(--accent);
      box-shadow: 0 0 12px rgba(0,168,98,0.4);
    }
    .logo span { color: var(--primary); }
    nav ul { list-style: none; display: flex; gap: 2rem; }
    nav a {
      color: var(--gray); font-weight: 600; font-size: 0.95rem;
      text-transform: uppercase; letter-spacing: 0.5px;
      transition: var(--transition); position: relative;
    }
    nav a:hover, nav a.active { color: var(--white); }
    nav a::after {
      content: ''; position: absolute; bottom: -4px; left: 0; width: 0; height: 2px;
      background: var(--primary); transition: var(--transition);
    }
    nav a:hover::after { width: 100%; }
    .burger { display: none; flex-direction: column; gap: 5px; cursor: pointer; background: none; border: none; }
    .burger span { width: 25px; height: 3px; background: var(--white); border-radius: 2px; transition: var(--transition); }

    /* ===== HERO ===== */
    .hero {
      position: relative; min-height: 100vh; display: flex; align-items: center; justify-content: center;
      text-align: center; overflow: hidden;
      background:
        radial-gradient(ellipse at 50% 100%, rgba(0,168,98,0.15), transparent 60%),
        linear-gradient(180deg, rgba(13,17,23,0.6), rgba(13,17,23,0.95)),
        url('https://images.unsplash.com/photo-1574629810360-7efbbe195018?w=1920&q=80') center/cover no-repeat;
    }
    .hero::before {
      content: ''; position: absolute; inset: 0;
      background: repeating-linear-gradient(90deg, transparent, transparent 50%, rgba(255,255,255,0.015) 50%, rgba(255,255,255,0.015) 100%);
      background-size: 60px 100%;
    }
    .hero-content { position: relative; z-index: 2; padding: 0 2rem; max-width: 800px; }
    .hero-tag {
      display: inline-block; padding: 0.4rem 1.2rem; border-radius: 30px;
      background: rgba(0,168,98,0.15); border: 1px solid rgba(0,168,98,0.3);
      color: var(--primary); font-size: 0.85rem; font-weight: 600;
      text-transform: uppercase; letter-spacing: 2px; margin-bottom: 1.5rem;
    }
    .hero h1 {
      font-size: clamp(3rem, 8vw, 5.5rem); font-weight: 900;
      color: var(--white); text-transform: uppercase; line-height: 1.05;
      margin-bottom: 0.5rem; letter-spacing: 2px;
    }
    .hero h1 .accent { color: var(--accent); }
    .hero p {
      font-size: 1.15rem; color: var(--gray); margin-bottom: 2rem;
    }
    .btn {
      display: inline-flex; align-items: center; gap: 0.5rem;
      padding: 0.85rem 2.2rem; border-radius: 50px; font-weight: 700;
      text-transform: uppercase; letter-spacing: 1px; font-size: 0.9rem;
      transition: var(--transition); cursor: pointer; border: none;
    }
    .btn-primary { background: var(--primary); color: var(--white); }
    .btn-primary:hover { background: var(--primary-dark); transform: translateY(-2px); box-shadow: 0 6px 20px rgba(0,168,98,0.35); }
    .btn-outline { background: transparent; color: var(--white); border: 2px solid rgba(255,255,255,0.2); }
    .btn-outline:hover { border-color: var(--accent); color: var(--accent); }
    .scroll-down {
      position: absolute; bottom: 2rem; left: 50%; transform: translateX(-50%);
      color: var(--gray); font-size: 1.5rem; animation: bounce 2s infinite;
    }
    @keyframes bounce { 0%,100% { transform: translateX(-50%) translateY(0); } 50% { transform: translateX(-50%) translateY(10px); } }

    /* ===== SECTIONS ===== */
    section { padding: 5rem 2rem; max-width: 1200px; margin: 0 auto; }
    .section-title {
      text-align: center; margin-bottom: 3rem;
    }
    .section-title h2 {
      font-size: clamp(2rem, 5vw, 3rem); font-weight: 700; color: var(--white);
      text-transform: uppercase; letter-spacing: 2px;
    }
    .section-title .underline {
      width: 60px; height: 4px; background: var(--primary); margin: 1rem auto 0; border-radius: 2px;
    }
    .section-title p { color: var(--gray); margin-top: 0.8rem; font-size: 1rem; }

    /* ===== ABOUT ===== */
    .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: center; }
    .about-text p { color: var(--gray); margin-bottom: 1.2rem; font-size: 1.05rem; }
    .achievements {
      list-style: none; display: flex; flex-wrap: wrap; gap: 0.6rem; margin-top: 1.5rem;
    }
    .achievements li {
      display: flex; align-items: center; gap: 0.5rem;
      padding: 0.5rem 1rem; border-radius: 30px;
      background: var(--dark-2); border: 1px solid rgba(0,168,98,0.2);
      font-size: 0.9rem; font-weight: 600; color: var(--light);
    }
    .achievements li .trophy { font-size: 1.1rem; }

    /* ===== STATS BAR ===== */
    .stats-bar {
      display: grid; grid-template-columns: repeat(4, 1fr); gap: 1rem;
      max-width: 1000px; margin: 0 auto 4rem;
    }
    .stat-item {
      text-align: center; padding: 1.5rem 1rem;
      background: var(--dark-2); border-radius: var(--radius);
      border: 1px solid rgba(255,255,255,0.05);
      transition: var(--transition);
    }
    .stat-item:hover { transform: translateY(-4px); border-color: rgba(0,168,98,0.3); }
    .stat-number { font-family: 'Oswald', sans-serif; font-size: 2.5rem; font-weight: 700; color: var(--primary); }
    .stat-label { color: var(--gray); font-size: 0.85rem; text-transform: uppercase; letter-spacing: 1px; }

    /* ===== COACH ===== */
    .coach-card {
      max-width: 500px; margin: 0 auto;
      background: var(--dark-2); border-radius: var(--radius); overflow: hidden;
      border: 1px solid rgba(255,255,255,0.06);
      transition: var(--transition);
    }
    .coach-card:hover { box-shadow: var(--shadow); border-color: rgba(0,168,98,0.3); }
    .coach-top {
      background: linear-gradient(135deg, var(--primary-dark), var(--primary));
      padding: 2.5rem 2rem; text-align: center;
    }
    .coach-avatar {
      width: 90px; height: 90px; border-radius: 50%;
      background: rgba(255,255,255,0.15); border: 3px solid var(--accent);
      display: flex; align-items: center; justify-content: center;
      font-size: 2.2rem; margin: 0 auto 1rem;
    }
    .coach-top h3 { font-size: 1.5rem; color: var(--white); }
    .coach-top .role { color: rgba(255,255,255,0.8); font-size: 0.95rem; }
    .coach-body { padding: 1.5rem 2rem; }
    .coach-info { display: flex; justify-content: space-between; padding: 0.5rem 0; border-bottom: 1px solid rgba(255,255,255,0.05); }
    .coach-info:last-child { border-bottom: none; }
    .coach-info .label { color: var(--gray); font-size: 0.9rem; }
    .coach-info .value { color: var(--white); font-weight: 600; font-size: 0.9rem; }
    .coach-desc { color: var(--gray); font-size: 0.95rem; margin-top: 1rem; font-style: italic; }

    /* ===== ROSTER ===== */
    .roster-grid {
      display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 1.5rem;
    }
    .player-card {
      background: var(--dark-2); border-radius: var(--radius); overflow: hidden;
      border: 1px solid rgba(255,255,255,0.06);
      transition: var(--transition); position: relative;
    }
    .player-card:hover { transform: translateY(-6px); box-shadow: 0 12px 40px rgba(0,168,98,0.15); border-color: rgba(0,168,98,0.3); }
    .player-number {
      position: absolute; top: 0.8rem; right: 0.8rem; z-index: 3;
      width: 40px; height: 40px; border-radius: 50%;
      background: rgba(0,168,98,0.9); color: var(--white);
      display: flex; align-items: center; justify-content: center;
      font-family: 'Oswald', sans-serif; font-size: 1.2rem; font-weight: 700;
    }
    .player-photo {
      height: 180px; display: flex; align-items: center; justify-content: center;
      font-size: 4rem; position: relative;
    }
    .player-photo.gk { background: linear-gradient(135deg, #1a3a5c, #2c5f8f); }
    .player-photo.df { background: linear-gradient(135deg, #3a1a1a, #8f2c2c); }
    .player-photo.mf { background: linear-gradient(135deg, #1a3a1a, #2c8f2c); }
    .player-photo.fw { background: linear-gradient(135deg, #3a2c1a, #8f6f2c); }
    .player-info { padding: 1.2rem; text-align: center; }
    .player-info h3 { font-size: 1.15rem; color: var(--white); margin-bottom: 0.3rem; }
    .player-position {
      display: inline-block; padding: 0.25rem 0.8rem; border-radius: 20px;
      font-size: 0.8rem; font-weight: 600; text-transform: uppercase; letter-spacing: 1px;
      margin-bottom: 0.6rem;
    }
    .pos-gk { background: rgba(44,95,143,0.2); color: #6ba8e0; }
    .pos-df { background: rgba(143,44,44,0.2); color: #e06b6b; }
    .pos-mf { background: rgba(44,143,44,0.2); color: #6be06b; }
    .pos-fw { background: rgba(143,111,44,0.2); color: #e0b86b; }
    .player-meta { color: var(--gray); font-size: 0.85rem; margin-top: 0.3rem; }
    .player-desc { color: var(--gray); font-size: 0.85rem; margin-top: 0.6rem; font-style: italic; line-height: 1.5; }

    /* ===== MATCHES ===== */
    .matches-list { display: flex; flex-direction: column; gap: 1rem; }
    .match-card {
      display: grid; grid-template-columns: auto 1fr auto; align-items: center; gap: 1.5rem;
      background: var(--dark-2); border-radius: var(--radius); padding: 1.2rem 1.5rem;
      border: 1px solid rgba(255,255,255,0.06);
      transition: var(--transition);
    }
    .match-card:hover { border-color: rgba(0,168,98,0.2); }
    .match-date {
      text-align: center; min-width: 70px;
    }
    .match-date .day { font-family: 'Oswald', sans-serif; font-size: 1.6rem; font-weight: 700; color: var(--white); }
    .match-date .month { color: var(--gray); font-size: 0.8rem; text-transform: uppercase; }
    .match-teams { text-align: center; }
    .match-teams .vs { display: flex; align-items: center; justify-content: center; gap: 1rem; font-size: 1.1rem; }
    .match-teams .team { font-weight: 700; color: var(--white); }
    .match-teams .score { font-family: 'Oswald', sans-serif; font-size: 1.3rem; color: var(--accent); font-weight: 700; }
    .match-teams .comp { color: var(--gray); font-size: 0.8rem; margin-top: 0.3rem; }
    .match-status {
      padding: 0.35rem 1rem; border-radius: 20px; font-size: 0.78rem; font-weight: 600;
      text-transform: uppercase; letter-spacing: 1px; white-space: nowrap;
    }
    .status-past { background: rgba(139,148,158,0.15); color: var(--gray); }
    .status-upcoming { background: rgba(0,168,98,0.15); color: var(--primary); }
    .match-card .btn-small {
      padding: 0.4rem 1rem; font-size: 0.8rem; border-radius: 20px;
      background: var(--primary); color: var(--white); font-weight: 600;
      border: none; cursor: pointer; transition: var(--transition);
    }
    .match-card .btn-small:hover { background: var(--primary-dark); }
    .match-actions { display: flex; gap: 0.5rem; }

    /* ===== CONTACTS ===== */
    .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; }
    .contact-info { display: flex; flex-direction: column; gap: 1rem; }
    .contact-item {
      display: flex; align-items: center; gap: 1rem;
      padding: 1rem 1.2rem; background: var(--dark-2); border-radius: var(--radius);
      border: 1px solid rgba(255,255,255,0.06);
    }
    .contact-icon {
      width: 44px; height: 44px; border-radius: 50%;
      background: rgba(0,168,98,0.12); display: flex; align-items: center; justify-content: center;
      font-size: 1.2rem; flex-shrink: 0;
    }
    .contact-item .label { color: var(--gray); font-size: 0.8rem; text-transform: uppercase; letter-spacing: 1px; }
    .contact-item .value { color: var(--white); font-weight: 600; }
    .social-links { display: flex; gap: 0.8rem; margin-top: 0.5rem; }
    .social-link {
      width: 44px; height: 44px; border-radius: 50%;
      background: var(--dark-2); border: 1px solid rgba(255,255,255,0.08);
      display: flex; align-items: center; justify-content: center;
      font-size: 1.1rem; transition: var(--transition);
    }
    .social-link:hover { background: var(--primary); transform: translateY(-3px); }

    .contact-form {
      background: var(--dark-2); border-radius: var(--radius); padding: 2rem;
      border: 1px solid rgba(255,255,255,0.06);
    }
    .form-group { margin-bottom: 1.2rem; }
    .form-group label { display: block; color: var(--gray); font-size: 0.85rem; margin-bottom: 0.4rem; text-transform: uppercase; letter-spacing: 1px; }
    .form-group input, .form-group textarea {
      width: 100%; padding: 0.8rem 1rem; border-radius: 8px;
      background: var(--dark-3); border: 1px solid rgba(255,255,255,0.08);
      color: var(--white); font-family: 'Montserrat', sans-serif; font-size: 0.95rem;
      transition: var(--transition);
    }
    .form-group input:focus, .form-group textarea:focus {
      outline: none; border-color: var(--primary); box-shadow: 0 0 0 3px rgba(0,168,98,0.15);
    }
    .form-group textarea { resize: vertical; min-height: 100px; }

    /* ===== FOOTER ===== */
    footer {
      background: var(--dark-2); border-top: 1px solid rgba(255,255,255,0.06);
      padding: 2rem; text-align: center; color: var(--gray);
    }
    footer p { font-size: 0.9rem; }

    /* ===== ANIMATIONS ===== */
    .fade-in { opacity: 0; transform: translateY(30px); transition: opacity 0.8s, transform 0.8s; }
    .fade-in.visible { opacity: 1; transform: translateY(0); }

    /* ===== RESPONSIVE ===== */
    @media (max-width: 768px) {
      nav ul { display: none; position: fixed; top: 60px; left: 0; right: 0; flex-direction: column; background: var(--dark-2); padding: 1rem 2rem; gap: 1rem; }
      nav ul.open { display: flex; }
      .burger { display: flex; }
      .about-grid, .contact-grid { grid-template-columns: 1fr; }
      .stats-bar { grid-template-columns: repeat(2, 1fr); }
      .match-card { grid-template-columns: 1fr; text-align: center; }
      .match-date, .match-status, .match-actions { justify-self: center; }
      section { padding: 3rem 1rem; }
    }
  </style>
</head>
<body>

  <!-- HEADER -->
  <header id="header">
    <a href="фк.jpg" class="logo">
      <div class="crest"><img src="фк.jpg" alt="" width="30" height="3">
</div>
      ФК <span>АРБАТ</span>
    </a>
    <nav>
      <ul id="nav-menu">
         <li><a href="#about">О команде</a></li>
        <li><a href="#roster">Состав</a></li>
        <li><a href="#matches">Матчи</a></li>
        <li><a href="#contacts">Контакты</a></li>
      </ul>
    </nav>
    <button class="burger" onclick="toggleMenu()"><span></span><span></span><span></span></button>
  </header>

  <!-- HERO -->
  <section class="hero" id="hero" style="padding-top:0; padding-bottom:0; max-width:none;">
    <div class="hero-content">
      <span class="hero-tag">Основан в 2024 году</span>
      <h1>ФК <span class="accent">АРБАТ</span></h1>
      <p>Сила, скорость, характер, переулок — играем сердцем.</p>
      <div style="display:flex; gap:1rem; justify-content:center; flex-wrap:wrap;">
        <a href="#matches" class="btn btn-primary">Календарь игр</a>
        <a href="#roster" class="btn btn-outline">Наш состав</a>
      </div>
    </div>
    <a href="#about" class="scroll-down">⌄</a>
  </section>

  <!-- ABOUT -->
  <section id="about" class="fade-in">
    <div class="section-title">
      <h2>О команде</h2>
      <div class="underline"></div>
      <p>Районная футбольная команда из Краснодара</p>
    </div>
    <div class="about-grid">
      <div class="about-text">
        <p>«ФК АРБАТ» — районная футбольная команда, основанная в 2024 году. Наша философия: дисциплина, уважение к сопернику и максимальная самоотдача на поле.</p>
        <p>Мы развиваем молодёжь и стремимся к стабильным результатам в школьных турнирах. Каждый игрок — часть семьи, каждый матч — шаг к победе.</p>
        <ul class="achievements">
          <li><span class="trophy">🏆</span> Чемпион лиги района 2024</li>
          <li><span class="trophy">🏆</span> Чемпион Лиги ФАПА 2024</li>
          <li><span class="trophy">🏆</span> Кубок дружбы 2024</li>
          <li><span class="trophy">🏆</span> Чемпион лиги района 2025</li>
          <li><span class="trophy">🏆</span> Чемпион Лиги Арбат 2025</li>
          <li><span class="trophy">🏆</span> Кубок Района 2026</li>
          <li><span class="trophy">⚽</span> Бронза Кубка СОШ 103, май 2026</li>
          <li><span class="trophy">⚽</span> 1/4 финала Кубка СОШ 103, сен 2026</li>
        </ul>
      </div>
      <div class="stats-bar" style="margin:0; grid-template-columns: repeat(2,1fr);">
        <div class="stat-item">
          <div class="stat-number">2024</div>
          <div class="stat-label">Год основания</div>
        </div>
        <div class="stat-item">
          <div class="stat-number">8</div>
          <div class="stat-label">Трофеев</div>
        </div>
        <div class="stat-item">
          <div class="stat-number">5</div>
          <div class="stat-label">Игроков</div>
        </div>
        <div class="stat-item">
          <div class="stat-number">34</div>
          <div class="stat-label">Гола лидера</div>
        </div>
      </div>
    </div>
  </section>

  <!-- COACH -->
  <section id="coach" class="fade-in" style="background: var(--dark-2); max-width:none; padding-left:2rem; padding-right:2rem;">
    <div style="max-width:1200px; margin:0 auto;">
      <div class="section-title">
        <h2>Тренерский штаб</h2>
        <div class="underline"></div>
      </div>
      <div class="coach-card">
        <div class="coach-top">
          <div class="coach-avatar">📋</div>
          <h3>Соловьёв М.Л.</h3>
          <div class="role">Главный тренер</div>
        </div>
        <div class="coach-body">
          <div class="coach-info"><span class="label">Номер</span><span class="value">0</span></div>
          <div class="coach-info"><span class="label">Год рождения</span><span class="value">2010</span></div>
          <p class="coach-desc">Глава команды, опыт игры с 2014 года.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ROSTER -->
  <section id="roster" class="fade-in">
    <div class="section-title">
      <h2>Текущий состав</h2>
      <div class="underline"></div>
      <p>Игроки, которые делают результат</p>
    </div>
    <div class="roster-grid">
      <!-- Гефтов Фёдор -->
      <div class="player-card">
        <div class="player-number">1</div>
        <div class="player-photo gk">⚽</div>
        <div class="player-info">
          <h3>Гефтов Фёдор</h3>
          <span class="player-position pos-gk">Вратарь</span>
          <p class="player-meta">21.01.2014</p>
          <p class="player-desc">Опыт игры с 2017 года. Надёжная опора ворот.</p>
        </div>
      </div>
      <!-- Кондакчян Даниэль -->
      <div class="player-card">
        <div class="player-number">4</div>
        <div class="player-photo df">⚽</div>
        <div class="player-info">
          <h3>Кондакчян Даниэль</h3>
          <span class="player-position pos-df">Защитник</span>
          <p class="player-meta">2014 г.р.</p>
          <p class="player-desc">Лидер обороны, лучший по отборам. Опыт 10 лет.</p>
        </div>
      </div>
      <!-- Тетов Богдан -->
      <div class="player-card">
        <div class="player-number">3</div>
        <div class="player-photo df">⚽</div>
        <div class="player-info">
          <h3>Тетов Богдан</h3>
          <span class="player-position pos-df">Защитник</span>
          <p class="player-meta">2018 г.р.</p>
          <p class="player-desc">Хорош в обороне, лучший по отборам. Опыт с 2022 года.</p>
        </div>
      </div>
      <!-- Климов Демьян -->
      <div class="player-card">
        <div class="player-number">10</div>
        <div class="player-photo mf">⚡</div>
        <div class="player-info">
          <h3>Климов Демьян</h3>
          <span class="player-position pos-mf">Полузащитник</span>
          <p class="player-meta">2015 г.р.</p>
          <p class="player-desc">Главный диспетчер команды, отвечает за темп. Опыт с 2018.</p>
        </div>
      </div>
      <!-- Романов Александр -->
      <div class="player-card">
        <div class="player-number">1</div>
        <div class="player-photo fw">⚽</div>
        <div class="player-info">
          <h3>Романов Александр</h3>
          <span class="player-position pos-fw">Нападающий</span>
          <p class="player-meta">2014 г.р.</p>
          <p class="player-desc">Лучший бомбардир, 34 гола. Опыт с 2016 года.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- MATCHES -->
  <section id="matches" class="fade-in" style="background: var(--dark-2); max-width:none; padding-left:2rem; padding-right:2rem;">
    <div style="max-width:1200px; margin:0 auto;">
      <div class="section-title">
        <h2>Матчи</h2>
        <div class="underline"></div>
        <p>Ближайшие и прошедшие игры</p>
      </div>
      <div class="matches-list">
        <!-- Past 1 -->
        <div class="match-card">
          <div class="match-date"><div class="day">31</div><div class="month">авг</div></div>
          <div class="match-teams">
            <div class="vs"><span class="team">ФК АРБАТ</span> <span class="score">6 : 2</span> <span class="team">ЖК ЛУЧШИЙ</span></div>
            <div class="comp">Лига Района · ЖК ЛУЧШИЙ</div>
          </div>
          <span class="match-status status-past">Прошедший</span>
        </div>
        <!-- Past 2 -->
        <div class="match-card">
          <div class="match-date"><div class="day">05</div><div class="month">сен</div></div>
          <div class="match-teams">
            <div class="vs"><span class="team">Краснодар-Ф</span> <span class="score">4 : 4</span> <span class="team">ФК АРБАТ</span></div>
            <div class="comp">Товарищеский · переулок Арбатский</div>
          </div>
          <span class="match-status status-past">Прошедший</span>
        </div>
        <!-- Upcoming 1 -->
        <div class="match-card">
          <div class="match-date"><div class="day">04</div><div class="month">окт</div></div>
          <div class="match-teams">
            <div class="vs"><span class="team">ФК АРБАТ</span> <span style="color:var(--gray)">vs</span> <span class="team">ЖК ЛУЧШИЙ</span></div>
            <div class="comp">Товарищеский · ЖК ЛУЧШИЙ</div>
          </div>
          <div class="match-actions">
            <button class="btn-small">Напомнить</button>
          </div>
        </div>
        <!-- Upcoming 2 -->
        <div class="match-card">
          <div class="match-date"><div class="day">04</div><div class="month">окт</div></div>
          <div class="match-teams">
            <div class="vs"><span class="team">ФК АРБАТ-2</span> <span style="color:var(--gray)">vs</span> <span class="team">ФК АРБАТ</span></div>
            <div class="comp">Товарищеский · переулок Утренний</div>
          </div>
          <div class="match-actions">
            <button class="btn-small">Билет</button>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACTS -->
  <section id="contacts" class="fade-in">
    <div class="section-title">
      <h2>Контакты</h2>
      <div class="underline"></div>
      <p>Свяжитесь с нами</p>
    </div>
    <div class="contact-grid">
      <div class="contact-info">
        <div class="contact-item">
          <div class="contact-icon">✉️</div>
          <div><div class="label">Email</div><div class="value">maksim.solovyev10@mail.ru</div></div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">📞</div>
          <div><div class="label">Телефон</div><div class="value">+7 (999) 123-45-67</div></div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">📍</div>
          <div><div class="label">Адрес</div><div class="value">г. Краснодар, пер. Арбатский<br>ЖК ЛУЧШИЙ</div></div>
        </div>
        <div class="social-links">
          <a href="https://vk.ru/club230043117" class="social-link" title="VK">VK</a>
          <a href="https://t.me/fcarbat" class="social-link" title="Telegram">TG</a>
          <a href="https://max.ru/join/ATvpgYbFyND0RALpBRNCsaS8Bw5d0ArXqv7Y1RQqZgI" class="social-link" title="YouTube">MAX</a>
        </div>
      </div>
      <form class="contact-form" onsubmit="event.preventDefault(); alert('Сообщение отправлено!'); this.reset();" action="https://formspree.io/f/mqpadwab"
  method="POST">
        <div class="form-group">
          <label>Ваше имя</label>
          <input type="text" placeholder="Иван Иванов" required />
        </div>
        <div class="form-group">
          <label>Сообщение</label>
          <textarea placeholder="Напишите нам..." required></textarea>
        </div>
        <button type="submit" class="btn btn-primary" style="width:100%; justify-content:center;">Отправить</button>
      </form>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <p>© 2024–2026 ФК «АРБАТ». Все права защищены.</p>
    <p style="margin-top:0.5rem;">Сделано с ⚽ в Краснодаре</p>
  </footer>

  <script>
    // Mobile menu
    function toggleMenu() {
      document.getElementById('nav-menu').classList.toggle('open');
    }
    // Close menu on link click
    document.querySelectorAll('#nav-menu a').forEach(a => a.addEventListener('click', () => {
      document.getElementById('nav-menu').classList.remove('open');
    }));
    // Scroll animation
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
    }, { threshold: 0.15 });
    document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));
    // Header shadow on scroll
    window.addEventListener('scroll', () => {
      const h = document.getElementById('header');
      if (window.scrollY > 10) h.style.background = 'rgba(13,17,23,0.95)';
      else h.style.background = 'rgba(13,17,23,0.85)';
    });
  </script>
</body>
</html>
