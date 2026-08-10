<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simona Staropoli | Fai brillare la tua Luce</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;0,700;1,400&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-dark: #0f1d15;
            --emerald-deep: #142e23;
            --emerald-light: #2b5443;
            --accent-gold: #d4af37;
            --accent-glow: #70d6a5;
            --text-main: #2c2724;
            --text-muted: #5a534c;
            --parchment-bg: rgba(249, 246, 238, 0.92);
            --glass-bg: rgba(20, 35, 27, 0.65);
            --stone-border: rgba(184, 169, 142, 0.3);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background: #0b1510 url('https://images.unsplash.com/photo-1448375240586-882707db888b?q=80&w=2000&auto=format&fit=crop') center/cover fixed no-repeat;
            color: var(--text-main);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            position: relative;
            overflow-x: hidden;
        }

        /* Ambient overlay */
        body::before {
            content: '';
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            background: radial-gradient(circle at 50% 20%, rgba(30, 60, 45, 0.4) 0%, rgba(5, 12, 8, 0.85) 100%);
            z-index: 0;
            pointer-events: none;
        }

        /* Floating Light Particles */
        .ambient-glow {
            position: fixed;
            top: 10%;
            left: 50%;
            transform: translateX(-50%);
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(162, 217, 187, 0.15) 0%, rgba(0,0,0,0) 70%);
            z-index: 0;
            pointer-events: none;
            animation: pulse 8s infinite alternate ease-in-out;
        }

        @keyframes pulse {
            0% { opacity: 0.5; transform: translateX(-50%) scale(0.9); }
            100% { opacity: 1; transform: translateX(-50%) scale(1.1); }
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px 24px;
            width: 100%;
            position: relative;
            z-index: 1;
        }

        /* Header & Logo */
        header {
            text-align: center;
            padding: 40px 0 20px 0;
        }

        .crystal-symbol {
            width: 70px;
            height: 70px;
            margin: 0 auto 15px auto;
            background: radial-gradient(circle, rgba(212, 175, 55, 0.3) 0%, transparent 70%);
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            border: 1px solid rgba(212, 175, 55, 0.4);
            box-shadow: 0 0 25px rgba(112, 214, 165, 0.3);
            animation: float 5s ease-in-out infinite;
        }

        .crystal-symbol svg {
            width: 36px;
            height: 36px;
            fill: #e6dfc8;
            filter: drop-shadow(0 0 6px rgba(255, 230, 150, 0.8));
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-8px); }
        }

        .site-title {
            font-family: 'Cormorant Garamond', serif;
            font-size: 3rem;
            font-weight: 600;
            letter-spacing: 4px;
            color: #f4efe2;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.7), 0 0 20px rgba(112, 214, 165, 0.3);
            text-transform: uppercase;
        }

        .site-tagline {
            font-family: 'Cormorant Garamond', serif;
            font-style: italic;
            font-size: 1.4rem;
            color: #b8ccbf;
            margin-top: 5px;
            letter-spacing: 1px;
        }

        /* Organic Navigation */
        nav.organic-nav {
            margin: 35px 0 45px 0;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 12px;
        }

        .nav-btn {
            text-decoration: none;
            color: #dce7e1;
            font-size: 0.85rem;
            font-weight: 500;
            letter-spacing: 1px;
            padding: 10px 22px;
            background: rgba(20, 38, 28, 0.65);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(145, 185, 160, 0.25);
            border-radius: 50px;
            transition: all 0.35s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
            position: relative;
            overflow: hidden;
        }

        .nav-btn::before {
            content: '';
            position: absolute;
            top: 0; left: -100%;
            width: 100%; height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.15), transparent);
            transition: left 0.6s ease;
        }

        .nav-btn:hover {
            color: #ffffff;
            background: rgba(35, 70, 50, 0.85);
            border-color: rgba(112, 214, 165, 0.6);
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(112, 214, 165, 0.25);
        }

        .nav-btn:hover::before {
            left: 100%;
        }

        /* Layout Main Grid */
        .main-grid {
            display: grid;
            grid-template-columns: 1fr 300px;
            gap: 35px;
            align-items: start;
        }

        @media (max-width: 900px) {
            .main-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Parchment Content Card */
        .content-card {
            background: var(--parchment-bg);
            backdrop-filter: blur(8px);
            border-radius: 20px;
            padding: 45px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.5), inset 0 0 60px rgba(190, 170, 140, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.6);
            position: relative;
        }

        /* Natural Moss/Stone Decorative Accents */
        .content-card::after {
            content: '🍃';
            position: absolute;
            bottom: -15px;
            right: 20px;
            font-size: 2rem;
            opacity: 0.6;
            filter: drop-shadow(0 2px 5px rgba(0,0,0,0.3));
        }

        .page-title {
            font-family: 'Cormorant Garamond', serif;
            font-size: 1.8rem;
            color: #3b5245;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 5px;
        }

        .welcome-heading {
            font-family: 'Cormorant Garamond', serif;
            font-size: 2.8rem;
            color: #8c4a27;
            margin-bottom: 25px;
            font-weight: 600;
        }

        .content-body p {
            font-size: 1rem;
            line-height: 1.8;
            color: #332e2b;
            margin-bottom: 20px;
        }

        .options-list {
            margin: 25px 0;
            padding-left: 0;
            list-style: none;
        }

        .option-item {
            background: rgba(230, 222, 205, 0.4);
            border-left: 4px solid #6b8e76;
            padding: 18px 22px;
            border-radius: 0 12px 12px 0;
            margin-bottom: 15px;
            line-height: 1.7;
            font-size: 0.98rem;
        }

        .signature {
            font-family: 'Cormorant Garamond', serif;
            font-size: 2rem;
            font-style: italic;
            color: #5c3822;
            margin-top: 30px;
        }

        .contact-box {
            margin-top: 35px;
            padding-top: 25px;
            border-top: 1px solid rgba(140, 120, 100, 0.25);
            font-size: 0.9rem;
            color: var(--text-muted);
        }

        .contact-box strong {
            color: #3b5245;
        }

        /* Sidebar Elements */
        .sidebar {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .sidebar-widget {
            background: var(--glass-bg);
            backdrop-filter: blur(12px);
            border: 1px solid var(--stone-border);
            border-radius: 16px;
            padding: 24px;
            color: #e6dfc8;
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
        }

        .widget-title {
            font-family: 'Cormorant Garamond', serif;
            font-size: 1.4rem;
            letter-spacing: 1px;
            color: #b8ccbf;
            margin-bottom: 15px;
            border-bottom: 1px solid rgba(184, 169, 142, 0.2);
            padding-bottom: 8px;
        }

        /* Search input */
        .search-box {
            display: flex;
            background: rgba(10, 20, 15, 0.6);
            border: 1px solid rgba(184, 169, 142, 0.3);
            border-radius: 30px;
            padding: 4px 6px 4px 16px;
        }

        .search-box input {
            background: transparent;
            border: none;
            outline: none;
            color: #fff;
            width: 100%;
            font-size: 0.9rem;
        }

        .search-box button {
            background: #2b5443;
            border: none;
            color: #fff;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            cursor: pointer;
            transition: background 0.3s;
        }

        .search-box button:hover {
            background: #3e735d;
        }

        /* Social Icons */
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 10px;
        }

        .social-icon {
            width: 42px;
            height: 42px;
            border-radius: 50%;
            background: rgba(255,255,255,0.08);
            border: 1px solid rgba(255,255,255,0.15);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #dce7e1;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .social-icon:hover {
            background: rgba(112, 214, 165, 0.2);
            border-color: rgba(112, 214, 165, 0.6);
            color: #fff;
            transform: scale(1.1);
        }

        /* Footer */
        footer {
            margin-top: 60px;
            padding: 30px 0;
            text-align: center;
            font-size: 0.85rem;
            color: rgba(220, 230, 225, 0.6);
            border-top: 1px solid rgba(255, 255, 255, 0.08);
            position: relative;
            z-index: 1;
        }

        footer a {
            color: rgba(220, 230, 225, 0.8);
            text-decoration: none;
        }

        footer a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>

    <div class="ambient-glow"></div>

    <div class="container">
        <!-- Header -->
        <header>
            <div class="crystal-symbol">
                <!-- Glowing Organic Symbol -->
                <svg viewBox="0 0 24 24">
                    <path d="M12 2L14.5 9.5L22 12L14.5 14.5L12 22L9.5 14.5L2 12L9.5 9.5L12 2Z" />
                </svg>
            </div>
            <h1 class="site-title">Sorgente Interiore</h1>
            <p class="site-tagline">Fai brillare la tua Luce</p>
        </header>

        <!-- Organic Floating Navigation -->
        <nav class="organic-nav">
            <a href="#" class="nav-btn">CHI SONO</a>
            <a href="#" class="nav-btn">COMINCIA DA QUI</a>
            <a href="#" class="nav-btn">COS'È SORGENTE INTERIORE</a>
            <a href="#" class="nav-btn">IL SOGNO DELL'ANIMA</a>
            <a href="#" class="nav-btn">SCIAMANESIMO</a>
            <a href="#" class="nav-btn">IL SENTIERO SCIAMANICO</a>
            <a href="#" class="nav-btn">TRATTAMENTI</a>
            <a href="#" class="nav-btn">EVENTI</a>
        </nav>

        <!-- Main Layout -->
        <div class="main-grid">
            <!-- Content Area -->
            <main class="content-card">
                <div class="page-title">Home</div>
                <h2 class="welcome-heading">Ben Arrivata!</h2>

                <div class="content-body">
                    <p>Ben arrivata o ben arrivato!</p>
                    <p>Non so chi sei e cosa ti abbia portato qui, ma sono sicura che se sei qui non è un caso.</p>
                    <p>Anche se qualcuno ti ha suggerito di guardare questo blog, anche se mi hai trovata in una ricerca, anche se...</p>
                    <p>Non importa il come o il perché, te lo ripeto: se sei qui <strong>NON è un caso</strong>.</p>
                    <p>Se deciderai di addentrarti in questo blog, porta sempre con te questo pensiero: sei arrivata perché era giusto o importante che lo facessi.</p>

                    <p style="margin-top: 25px; font-weight: 500;">Arrivata a questo punto, hai due possibilità:</p>
                    
                    <ul class="options-list">
                        <li class="option-item">
                            <strong>1 -</strong> Chiudere tutto o pensare che è il solito blog new age o di tendenza e continuare con la tua vita così com'è, pensando che è solamente un caso se mi stai leggendo e che hai solo sbagliato la ricerca.
                        </li>
                        <li class="option-item">
                            <strong>2 -</strong> Aprire la tua mente e il tuo cuore e ricevere ciò che queste parole ti diranno, leggere queste pagine come se tu fossi una bambina, come quando a scuola inizi a leggere, non hai barriere mentali, la società non ti ha ancora imposto ciò che è giusto e ciò che è sbagliato, hai solo voglia di scoprire il mondo.
                        </li>
                    </ul>

                    <p>Se opti per la soluzione due ti ringrazio di aver capito che la vita ti sta regalando un'opportunità, ti ringrazio di essere qui, ti ringrazio di essere un'anima che si sta risvegliando dal torpore dei limiti mentali che altri hanno deciso per te.</p>
                    
                    <p>Grazie di essere semplicemente tu!</p>
                    <p style="font-style: italic; color: #4a6654;">Che tu possa far risplendere la tua luce e camminare nella Bellezza ogni giorno.</p>

                    <div class="signature">Simona</div>

                    <div class="contact-box">
                        <p><strong>Contattami qui:</strong></p>
                        <p>SMS o WhatsApp: <strong>349.8615665</strong> | Email: <strong>info@sorgenteinteriore.com</strong></p>
                    </div>
                </div>
            </main>

            <!-- Sidebar -->
            <aside class="sidebar">
                <!-- Search Widget -->
                <div class="sidebar-widget">
                    <h3 class="widget-title">Cerca nel sito</h3>
                    <div class="search-box">
                        <input type="text" placeholder="Cerca un argomento...">
                        <button type="button">🔍</button>
                    </div>
                </div>

                <!-- Social Widget -->
                <div class="sidebar-widget">
                    <h3 class="widget-title">Seguimi</h3>
                    <p style="font-size: 0.85rem; color: #a3b8ac; margin-bottom: 12px;">Rimani in contatto sui social:</p>
                    <div class="social-links">
                        <a href="#" class="social-icon" title="Facebook">f</a>
                        <a href="#" class="social-icon" title="YouTube">▶</a>
                        <a href="#" class="social-icon" title="Instagram">📷</a>
                    </div>
                </div>

                <!-- Archivi Widget -->
                <div class="sidebar-widget">
                    <h3 class="widget-title">Archivi</h3>
                    <ul style="list-style: none; font-size: 0.9rem; line-height: 2;">
                        <li><a href="#" style="color: #cce3d7; text-decoration: none;">✨ Articoli recenti</a></li>
                        <li><a href="#" style="color: #cce3d7; text-decoration: none;">🌿 Percorsi Sciamanici</a></li>
                        <li><a href="#" style="color: #cce3d7; text-decoration: none;">🌸 Meditazioni e Trattamenti</a></li>
                    </ul>
                </div>
            </aside>
        </div>

        <!-- Footer -->
        <footer>
            <p>Copyright 2019/2026 - Simona Staropoli - Gavardo (Bs)</p>
            <p style="margin-top: 6px;">
                <a href="#">Privacy Policy</a> | <a href="#">Cookie Policy</a> | <a href="#">Disclaimer</a>
            </p>
        </footer>
    </div>

</body>
</html>
