[index-v2.html](https://github.com/user-attachments/files/31190573/index-v2.html)
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¡Alendy cumple 26! 🎀🍒</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700&family=Playfair+Display:ital,wght@0,600;1,600;1,700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #ffb6c1;
            --primary-light: #ffe6eb;
            --primary-dark: #c21e56;
            --accent-gold: #ffd700;
            --bg-color: #fff0f5;
            --text-main: #4a4a4a;
            --white: #ffffff;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 10px; }
        ::-webkit-scrollbar-track { background: var(--bg-color); }
        ::-webkit-scrollbar-thumb { background: var(--primary); border-radius: 10px; }
        ::-webkit-scrollbar-thumb:hover { background: var(--primary-dark); }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-main);
            overflow-x: hidden;
            position: relative;
            cursor: default;
        }

        /* === FONDO ANIMADO Y PARTICULAS === */
        .bg-shapes {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: -2;
            overflow: hidden;
            background: radial-gradient(circle at 10% 20%, #fffafb 0%, transparent 50%),
                        radial-gradient(circle at 90% 80%, #ffd1dc 0%, transparent 50%),
                        radial-gradient(circle at 50% 50%, var(--bg-color) 0%, var(--bg-color) 100%);
            animation: bgShift 15s infinite alternate ease-in-out;
        }
        
        .floating-particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            background: rgba(255, 182, 193, 0.4);
            border-radius: 50%;
            animation: float-up infinite linear;
        }

        @keyframes float-up {
            0% { transform: translateY(100vh) scale(0); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-10vh) scale(1.5); opacity: 0; }
        }

        @keyframes bgShift {
            0% { background-position: 0% 0%; transform: scale(1); }
            100% { background-position: 100% 100%; transform: scale(1.05); }
        }

        h1, h2, h3 {
            font-family: 'Playfair Display', serif;
            color: var(--primary-dark);
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* === TARJETAS GLASSMORPHISM MEJORADAS === */
        .glass-card {
            background: rgba(255, 255, 255, 0.75);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 2px solid rgba(255, 255, 255, 0.9);
            border-radius: 40px;
            padding: 60px 40px;
            margin-bottom: 60px;
            box-shadow: 0 20px 50px rgba(194, 30, 86, 0.1),
                        inset 0 0 20px rgba(255, 255, 255, 0.8);
            text-align: center;
            opacity: 0;
            transform: translateY(50px) scale(0.95);
            transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
        }
        
        .glass-card::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(to bottom right, rgba(255,255,255,0.8) 0%, rgba(255,255,255,0) 40%, rgba(255,255,255,0) 100%);
            transform: rotate(30deg);
            pointer-events: none;
        }

        .glass-card.visible {
            opacity: 1;
            transform: translateY(0) scale(1);
        }

        .badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 10px 25px;
            background: linear-gradient(135deg, rgba(255,182,193,0.3), rgba(194,30,86,0.1));
            color: var(--primary-dark);
            border-radius: 50px;
            font-size: 0.9rem;
            font-weight: 700;
            letter-spacing: 2px;
            text-transform: uppercase;
            margin-bottom: 40px;
            box-shadow: 0 5px 15px rgba(194,30,86,0.08);
            border: 1px solid rgba(194,30,86,0.2);
            animation: pulse-badge 2s infinite alternate;
        }

        @keyframes pulse-badge {
            0% { transform: scale(1); box-shadow: 0 5px 15px rgba(194,30,86,0.08); }
            100% { transform: scale(1.05); box-shadow: 0 8px 25px rgba(194,30,86,0.15); }
        }

        /* === CARRUSEL DE FOTOS PROTAGÓNICO === */
        .hero-section {
            position: relative;
            margin: 0 auto 50px;
            width: 100%;
            max-width: 380px;
            height: 480px;
            perspective: 1000px;
        }

        .hero-img-container {
            width: 100%;
            height: 100%;
            border-radius: 30px;
            padding: 12px;
            background: linear-gradient(135deg, var(--primary-light), var(--primary), var(--primary-dark));
            box-shadow: 0 30px 60px rgba(194, 30, 86, 0.3),
                        0 0 40px rgba(255, 182, 193, 0.6);
            animation: float-carousel 6s ease-in-out infinite;
            position: relative;
            z-index: 2;
        }
        
        @keyframes float-carousel {
            0% { transform: translateY(0) rotate(-1deg); }
            50% { transform: translateY(-15px) rotate(1deg); }
            100% { transform: translateY(0) rotate(-1deg); }
        }

        .carousel-inner {
            position: relative;
            width: 100%;
            height: 100%;
            border-radius: 20px;
            overflow: hidden;
            border: 4px solid var(--white);
            background: var(--bg-color);
            box-shadow: inset 0 0 20px rgba(0,0,0,0.2);
        }
        
        .carousel-img {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            opacity: 0;
            transform: scale(1.1) rotate(2deg);
            animation: fadeCarousel 32s infinite;
            filter: contrast(1.05) brightness(1.05);
        }

        /* 8 imágenes - 4 segundos por imagen (32s total) */
        .carousel-img:nth-child(1) { animation-delay: 0s; }
        .carousel-img:nth-child(2) { animation-delay: 4s; }
        .carousel-img:nth-child(3) { animation-delay: 8s; }
        .carousel-img:nth-child(4) { animation-delay: 12s; }
        .carousel-img:nth-child(5) { animation-delay: 16s; }
        .carousel-img:nth-child(6) { animation-delay: 20s; }
        .carousel-img:nth-child(7) { animation-delay: 24s; }
        .carousel-img:nth-child(8) { animation-delay: 28s; }

        @keyframes fadeCarousel {
            0% { opacity: 0; transform: scale(1.1) rotate(2deg); filter: blur(5px); }
            3% { opacity: 1; transform: scale(1) rotate(0deg); filter: blur(0); }
            12.5% { opacity: 1; transform: scale(1) rotate(0deg); filter: blur(0); }
            15.5% { opacity: 0; transform: scale(1.05) rotate(-2deg); filter: blur(5px); }
            100% { opacity: 0; }
        }

        .floating-emoji {
            position: absolute;
            font-size: 3rem;
            filter: drop-shadow(0 10px 15px rgba(0,0,0,0.2));
            z-index: 10;
        }
        .fe-1 { top: -20px; left: -30px; animation: pop-spin 4s infinite alternate; }
        .fe-2 { bottom: 20px; right: -40px; font-size: 3.5rem; animation: pop-spin 5s infinite alternate-reverse; }
        .fe-3 { bottom: -30px; left: 20px; font-size: 2.5rem; animation: pop-float 3s infinite alternate; }

        @keyframes pop-spin {
            0% { transform: scale(1) rotate(-10deg); }
            100% { transform: scale(1.2) rotate(20deg); }
        }
        @keyframes pop-float {
            0% { transform: translateY(0) scale(1); }
            100% { transform: translateY(-20px) scale(1.1); }
        }

        /* === TIPOGRAFÍA === */
        h1 { 
            font-size: 4.5rem; 
            margin-bottom: 10px; 
            background: linear-gradient(to right, var(--primary-dark), #ff6b81, var(--primary-dark));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-size: 200% auto;
            animation: gradient-text 3s linear infinite;
            line-height: 1.2;
        }
        
        @keyframes gradient-text {
            to { background-position: 200% center; }
        }
        
        h2 { 
            font-size: 2.2rem; 
            margin-bottom: 25px; 
            font-style: italic; 
            position: relative;
            display: inline-block;
        }

        p { font-size: 1.15rem; line-height: 1.8; margin-bottom: 20px; }
        .lead { font-size: 1.35rem; font-weight: 700; color: var(--primary-dark); }

        /* === CONTADOR REGRESIVO === */
        .countdown {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 40px 0;
            flex-wrap: wrap;
        }

        .time-box {
            background: linear-gradient(145deg, var(--white), #fff0f5);
            border: 2px solid var(--primary-light);
            color: var(--primary-dark);
            padding: 20px;
            border-radius: 25px;
            min-width: 100px;
            box-shadow: 10px 10px 30px rgba(194, 30, 86, 0.1),
                       -10px -10px 30px rgba(255, 255, 255, 0.8);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
        }
        
        .time-box::before {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 100%; height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--primary-dark));
        }

        .time-box:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 15px 15px 40px rgba(194, 30, 86, 0.15),
                       -15px -15px 40px rgba(255, 255, 255, 1);
        }

        .time-box span {
            font-size: 2.8rem;
            font-weight: 700;
            display: block;
            font-family: 'Playfair Display', serif;
            line-height: 1;
            margin-bottom: 5px;
        }

        .time-box p {
            margin: 0;
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: #888;
            font-weight: 600;
        }

        /* DIVISOR DECORATIVO */
        .divider {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 20px;
            margin: 50px 0;
        }
        .divider::before, .divider::after {
            content: "";
            height: 3px;
            width: 100px;
            background: linear-gradient(to right, transparent, var(--primary), transparent);
            border-radius: 50%;
        }
        .divider span { font-size: 2rem; animation: pulse-glow 2s infinite alternate;}

        /* === GRID DE DETALLES === */
        .details-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
            margin: 40px 0;
        }

        .detail-item {
            background: rgba(255, 255, 255, 0.8);
            padding: 35px 20px;
            border-radius: 30px;
            border: 2px dashed var(--primary);
            transition: all 0.4s ease;
            position: relative;
        }

        .detail-item:hover {
            transform: translateY(-8px);
            border-color: var(--primary-dark);
            border-style: solid;
            background: var(--white);
            box-shadow: 0 15px 30px rgba(194, 30, 86, 0.15);
        }

        .detail-item i { 
            font-style: normal; 
            font-size: 3rem; 
            display: block; 
            margin-bottom: 15px; 
            animation: bounce 2s infinite ease-in-out;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .detail-item strong { 
            color: var(--primary-dark); 
            font-size: 1.3rem; 
            display: block; 
            margin-bottom: 8px;
            font-family: 'Playfair Display', serif;
        }

        /* === BOTÓN ANIMADO === */
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            background: linear-gradient(45deg, var(--primary-dark), #ff6b81, var(--primary-dark));
            background-size: 200% auto;
            color: white;
            padding: 18px 45px;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: 700;
            text-decoration: none;
            box-shadow: 0 10px 30px rgba(194, 30, 86, 0.4);
            transition: all 0.4s ease;
            border: none;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            animation: gradient-text 3s linear infinite;
        }

        .btn:hover {
            transform: translateY(-5px) scale(1.03);
            box-shadow: 0 15px 40px rgba(194, 30, 86, 0.6);
        }
        
        .btn::after {
            content: '';
            position: absolute;
            top: 0; left: -100%;
            width: 50%; height: 100%;
            background: linear-gradient(to right, transparent, rgba(255,255,255,0.4), transparent);
            transform: skewX(-20deg);
            transition: 0.5s;
        }
        .btn:hover::after { left: 150%; }

        /* === DRESS CODE === */
        .palette-container {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 40px;
        }
        
        .color-swatch {
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 110px;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
        }
        
        .color-swatch:hover {
            transform: translateY(-15px) scale(1.1);
        }
        
        .color-box {
            width: 80px;
            height: 100px;
            border-radius: 15px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.15);
            margin-bottom: 15px;
            border: 4px solid white;
            position: relative;
        }
        
        .color-box::after {
            content: '✨';
            position: absolute;
            top: 50%; left: 50%;
            transform: translate(-50%, -50%) scale(0);
            font-size: 1.5rem;
            opacity: 0;
            transition: 0.3s;
        }
        
        .color-swatch:hover .color-box::after {
            transform: translate(-50%, -50%) scale(1);
            opacity: 1;
        }

        .color-name {
            font-size: 0.8rem;
            font-weight: 800;
            color: var(--primary-dark);
            text-align: center;
            margin-bottom: 4px;
        }
        
        .color-hex {
            font-size: 0.7rem;
            color: #888;
            font-weight: 600;
            background: #f0f0f0;
            padding: 3px 8px;
            border-radius: 10px;
        }

        /* === GALERÍA === */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 40px;
        }

        .gallery img {
            width: 100%;
            height: 320px;
            object-fit: cover;
            border-radius: 30px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.15);
            transition: all 0.5s ease;
            cursor: pointer;
            border: 3px solid white;
        }

        .gallery img:hover {
            transform: scale(1.05) rotate(2deg);
            box-shadow: 0 25px 45px rgba(194, 30, 86, 0.3);
        }

        /* === FORMULARIO === */
        .form-box {
            max-width: 550px;
            margin: 0 auto;
            text-align: left;
            background: rgba(255, 255, 255, 0.9);
            padding: 45px;
            border-radius: 35px;
            box-shadow: 0 20px 40px rgba(194, 30, 86, 0.1);
            transition: transform 0.4s ease;
            border: 1px solid var(--primary-light);
        }
        
        .form-box:hover {
            transform: translateY(-8px);
            box-shadow: 0 25px 50px rgba(194, 30, 86, 0.15);
        }

        .input-group { margin-bottom: 30px; }
        .input-group label {
            display: block;
            margin-bottom: 12px;
            font-weight: 700;
            color: var(--primary-dark);
            font-size: 1.1rem;
        }

        .input-group input, .input-group select {
            width: 100%;
            padding: 18px 25px;
            border: 2px solid #ffe6eb;
            border-radius: 20px;
            font-family: inherit;
            font-size: 1.05rem;
            background: #fafafa;
            transition: all 0.3s;
            color: var(--text-main);
        }

        .input-group input:focus, .input-group select:focus {
            outline: none;
            border-color: var(--primary-dark);
            background: var(--white);
            box-shadow: 0 0 0 5px rgba(194, 30, 86, 0.15);
            transform: scale(1.02);
        }

        /* CONTENEDOR CONFETI */
        #confetti {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1000;
        }

        /* RESPONSIVE */
        @media (max-width: 768px) {
            h1 { font-size: 3.2rem; }
            h2 { font-size: 1.8rem; }
            .glass-card { padding: 40px 25px; border-radius: 30px; }
            .hero-section { max-width: 300px; height: 380px; }
            .palette-container { gap: 15px; }
            .color-swatch { width: 90px; }
            .time-box { min-width: 80px; padding: 15px; }
            .time-box span { font-size: 2rem; }
            .form-box { padding: 30px 20px; }
        }
    </style>
</head>
<body>

    <!-- PARTICULAS DEL FONDO -->
    <div class="bg-shapes"></div>
    <div class="floating-particles" id="particles"></div>
    
    <canvas id="confetti"></canvas>

    <div class="container">
        
        <!-- SECCIÓN 1: INICIO -->
        <div class="glass-card visible">
            <div class="badge">🎀 <span>Una celebración especial</span> 🎀</div>
            
            <div class="hero-section">
                <div class="floating-emoji fe-1">🍒</div>
                <div class="floating-emoji fe-2">✨</div>
                <div class="floating-emoji fe-3">🎂</div>
                <div class="hero-img-container">
                    <!-- CARRUSEL DE FOTOS PROTAGÓNICO -->
                    <div class="carousel-inner">
                        <img src="image_75880a.jpg" alt="Alendy 1" class="carousel-img">
                        <img src="image_82bea9.jpg" alt="Alendy 2" class="carousel-img">
                        <img src="image_82bead.jpg" alt="Alendy 3" class="carousel-img">
                        <img src="image_82c152.jpg" alt="Alendy 4" class="carousel-img">
                        <img src="image_82c173.jpg" alt="Alendy 5" class="carousel-img">
                        <img src="image_82c178.jpg" alt="Alendy 6" class="carousel-img">
                        <img src="image_82c193.jpg" alt="Alendy 7" class="carousel-img">
                        <img src="image_82c1b4.jpg" alt="Alendy 8" class="carousel-img">
                    </div>
                </div>
            </div>

            <h2>Acompáñame a celebrar mi cumpleaños</h2>
            <h1>¡Alendy<br>cumple 26!</h1>
            
            <div class="divider">
                <span>🌸</span><span>🍒</span><span>🌸</span>
            </div>

            <p class="lead">Un pequeño detalle para hacer de este día algo aún más especial ✨</p>
            <p>Me encantaría que me acompañes a celebrar mi cumpleaños. Preparé un día hermoso lleno de alegría, sol y buena compañía, y tu presencia es el mejor regalo.</p>

            <div class="countdown" id="countdown">
                <div class="time-box"><span id="days">00</span><p>Días</p></div>
                <div class="time-box"><span id="hours">00</span><p>Horas</p></div>
                <div class="time-box"><span id="mins">00</span><p>Min</p></div>
                <div class="time-box"><span id="secs">00</span><p>Seg</p></div>
            </div>
        </div>

        <!-- SECCIÓN 2: LUGAR Y FECHA -->
        <div class="glass-card scroll-anim">
            <h2>Cuándo y Dónde</h2>
            <p class="lead">¡Prepara tu mejor actitud y tu traje de baño para un día inolvidable!</p>

            <div class="details-grid">
                <div class="detail-item">
                    <i>📅</i>
                    <strong>Fecha</strong>
                    <span>08 de Noviembre</span>
                </div>
                <div class="detail-item">
                    <i>⏰</i>
                    <strong>Hora</strong>
                    <span>10:00 AM</span>
                </div>
                <div class="detail-item">
                    <i>📍</i>
                    <strong>Lugar</strong>
                    <span>Villa Gloria,<br>San Cristóbal</span>
                </div>
            </div>

            <a href="https://maps.app.goo.gl/zQPrrrbGZjWA2Jk99?g_st=aw" target="_blank" class="btn">📍 Abrir en Google Maps</a>

            <div class="gallery">
                <img src="image_759388.jpg" alt="Piscina de la Villa">
                <img src="image_75938f.jpg" alt="Villa Gloria de Noche">
            </div>
        </div>

        <!-- SECCIÓN 3: DRESS CODE -->
        <div class="glass-card scroll-anim">
            <h2>Dress Code</h2>
            <div class="divider"><span>👗</span><span>🤍</span><span>👗</span></div>
            <p class="lead" style="color: var(--primary-dark);">Código de Vestimenta y Paleta de Colores</p>
            <p>Para que nuestras fotos queden hermosas y todos estemos en sintonía, he preparado esta paleta de colores sugerida para la ocasión. ¡Elige tu tono favorito y prepárate para brillar!</p>
            
            <div class="palette-container">
                <div class="color-swatch">
                    <div class="color-box" style="background-color: #F8C8DC;"></div>
                    <span class="color-name">ROSA BEBÉ</span>
                    <span class="color-hex">#F8C8DC</span>
                </div>
                <div class="color-swatch">
                    <div class="color-box" style="background-color: #F4A6C1;"></div>
                    <span class="color-name">ROSA PASTEL</span>
                    <span class="color-hex">#F4A6C1</span>
                </div>
                <div class="color-swatch">
                    <div class="color-box" style="background-color: #E85D8E;"></div>
                    <span class="color-name">ROSA FUERTE</span>
                    <span class="color-hex">#E85D8E</span>
                </div>
                <div class="color-swatch">
                    <div class="color-box" style="background-color: #C9184A;"></div>
                    <span class="color-name">ROJO CEREZA</span>
                    <span class="color-hex">#C9184A</span>
                </div>
                <div class="color-swatch">
                    <div class="color-box" style="background-color: #FFFFFF; border: 2px solid #e1e1e1;"></div>
                    <span class="color-name">BLANCO</span>
                    <span class="color-hex">#FFFFFF</span>
                </div>
                <div class="color-swatch">
                    <div class="color-box" style="background-color: #FFF0F5; border: 2px solid #e1e1e1;"></div>
                    <span class="color-name">ROSA MUY CLARO</span>
                    <span class="color-hex">#FFF0F5</span>
                </div>
            </div>
        </div>

        <!-- SECCIÓN 4: APORTE -->
        <div class="glass-card scroll-anim">
            <h2>Detalles del Aporte</h2>
            <div class="divider"><span>💕</span><span>🏡</span><span>💕</span></div>
            
            <p class="lead">Para disfrutar juntos de la villa y hacer que este cumpleaños sea súper lindo e inolvidable, haremos un pequeño aporte de <strong>RD$1,000 por persona</strong>.</p>
            
            <div style="background: rgba(255,255,255,0.6); border: 3px dashed var(--primary); padding: 30px; border-radius: 30px; margin: 35px 0; transform: rotate(-1deg);">
                <h3 style="margin-bottom: 20px; font-size: 1.8rem;">Fechas de Pago 💳</h3>
                <p style="font-size: 1.3rem; color: var(--primary-dark); margin-bottom: 10px;">💸 <strong>RD$500</strong> - 30 de Septiembre</p>
                <p style="font-size: 1.3rem; color: var(--primary-dark);">💸 <strong>RD$500</strong> - 15 de Octubre</p>
            </div>

            <p><strong>✨ ¿Qué incluye?</strong> Transporte, estadía en la villa, comida y bebida.</p>
            <p style="margin-top: 25px; font-size: 1.2rem;"><em>Gracias por acompañarme, por compartir este día conmigo y por poner su granito de arena para que todo quede precioso. 🥹🎀</em></p>
            <p class="lead" style="color: var(--primary-dark); margin-top: 20px; font-size: 1.5rem;">¡Lo importante es celebrar juntos y crear recuerdos bonitos! 💗✨</p>
        </div>

        <!-- SECCIÓN 5: CONFIRMACIÓN (RSVP) -->
        <div class="glass-card scroll-anim">
            <h2>Confirma tu Asistencia</h2>
            <p style="margin-bottom: 35px; font-size: 1.2rem;">Por favor, regístrate aquí. Al confirmar, serás redirigido automáticamente al grupo oficial de WhatsApp del evento.</p>

            <div class="form-box">
                <form id="rsvp-form">
                    <div class="input-group">
                        <label for="nombre">Nombre</label>
                        <input type="text" id="nombre" placeholder="Ej. María" required>
                    </div>
                    <div class="input-group">
                        <label for="apellido">Apellido</label>
                        <input type="text" id="apellido" placeholder="Ej. Pérez" required>
                    </div>
                    <div class="input-group">
                        <label for="transporte">¿Cómo llegarás a la Villa?</label>
                        <select id="transporte" required>
                            <option value="" disabled selected>Selecciona una opción</option>
                            <option value="incluido">Me iré en el transporte incluido 🚌</option>
                            <option value="independiente">Llegaré de forma independiente 🚗</option>
                        </select>
                    </div>
                    <button type="submit" class="btn" style="width: 100%; font-size: 1.3rem; padding: 20px;">Confirmar y Unirme al Grupo ✨</button>
                </form>
            </div>
        </div>

    </div>

    <script>
        // Generar partículas flotantes para el fondo
        const particlesContainer = document.getElementById('particles');
        const particleCount = 20;

        for (let i = 0; i < particleCount; i++) {
            let particle = document.createElement('div');
            particle.classList.add('particle');
            
            // Tamaños y posiciones aleatorias
            let size = Math.random() * 40 + 10;
            particle.style.width = `${size}px`;
            particle.style.height = `${size}px`;
            particle.style.left = `${Math.random() * 100}vw`;
            particle.style.animationDuration = `${Math.random() * 10 + 10}s`;
            particle.style.animationDelay = `${Math.random() * 5}s`;
            
            particlesContainer.appendChild(particle);
        }

        // Animación al hacer scroll
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.15 });

        document.querySelectorAll('.scroll-anim').forEach(el => observer.observe(el));

        // Contador regresivo
        const countDownDate = new Date("Nov 8, 2026 10:00:00").getTime();

        const x = setInterval(function() {
            const now = new Date().getTime();
            const distance = countDownDate - now;

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("days").innerHTML = days < 10 ? '0'+days : days;
            document.getElementById("hours").innerHTML = hours < 10 ? '0'+hours : hours;
            document.getElementById("mins").innerHTML = minutes < 10 ? '0'+minutes : minutes;
            document.getElementById("secs").innerHTML = seconds < 10 ? '0'+seconds : seconds;

            if (distance < 0) {
                clearInterval(x);
                document.getElementById("countdown").innerHTML = "<h2 style='color:var(--primary-dark); font-size:3rem; animation: pulseText 2s infinite alternate;'>¡Llegó el gran día! 🎉</h2>";
            }
        }, 1000);

        // Confeti avanzado al confirmar
        const canvas = document.getElementById('confetti');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        let confettiParticles = [];

        function fireConfetti() {
            const colors = ['#c21e56', '#ffb6c1', '#ffffff', '#ffd700', '#ff6b81'];
            for (let i = 0; i < 200; i++) {
                confettiParticles.push({
                    x: canvas.width / 2, // Explotan desde el centro
                    y: canvas.height / 2,
                    w: Math.random() * 12 + 5,
                    h: Math.random() * 12 + 5,
                    color: colors[Math.floor(Math.random() * colors.length)],
                    speedY: (Math.random() * 15) - 10,
                    speedX: (Math.random() * 20) - 10,
                    rot: Math.random() * 360,
                    rotSpeed: Math.random() * 15 - 7.5,
                    gravity: 0.2
                });
            }
        }

        function renderConfetti() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            let active = false;

            confettiParticles.forEach((p, index) => {
                p.speedY += p.gravity;
                p.y += p.speedY;
                p.x += p.speedX;
                p.rot += p.rotSpeed;

                ctx.save();
                ctx.translate(p.x, p.y);
                ctx.rotate(p.rot * Math.PI / 180);
                ctx.fillStyle = p.color;
                
                // Formas variadas: cuadrados y círculos
                if (index % 3 === 0) {
                    ctx.beginPath();
                    ctx.arc(0, 0, p.w/2, 0, Math.PI * 2);
                    ctx.fill();
                } else {
                    ctx.fillRect(-p.w/2, -p.h/2, p.w, p.h);
                }
                
                ctx.restore();

                if (p.y < canvas.height) active = true;
            });

            if (active) requestAnimationFrame(renderConfetti);
        }

        document.getElementById('rsvp-form').addEventListener('submit', function(e) {
            e.preventDefault();
            
            fireConfetti();
            renderConfetti();

            const btn = this.querySelector('button');
            btn.innerHTML = "¡Redirigiendo a WhatsApp... ⏳!";
            btn.style.background = "linear-gradient(45deg, #1ebea5, #25D366)";
            btn.style.boxShadow = "0 10px 30px rgba(37, 211, 102, 0.5)";
            btn.style.color = "white";
            btn.style.transform = "scale(1.05)";

            setTimeout(() => {
                window.location.href = "https://chat.whatsapp.com/FyPQrojrnQJKGQoEnh0cGq?s=cl&p=a&ilr=4";
            }, 3000);
        });

        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });
    </script>
</body>
</html>
