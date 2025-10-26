# guiria-turismo
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Descubre Güiria - Donde el Atlántico Abraza al Caribe</title>
    <meta name="description" content="Descubre Güiria, el único puerto venezolano en el Océano Atlántico. Playas paradisíacas, cultura única, historia viva y gastronomía exclusiva te esperan.">
    <meta name="keywords" content="Güiria, Venezuela, turismo, playas, Atlántico, Caribe, turismo Venezuela, Estado Sucre">
    
    <!-- Fuentes -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    
    <style>
        :root {
            --ocean-blue: #0e4c92;
            --turquoise: #18a3c5;
            --warm-orange: #ff6b35;
            --golden: #ffd700;
            --white: #ffffff;
            --light-gray: #f8f9fa;
            --dark-gray: #333333;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: var(--dark-gray);
            overflow-x: hidden;
        }

        /* Navegación */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            transition: all 0.3s ease;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--ocean-blue);
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-link {
            text-decoration: none;
            color: var(--dark-gray);
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-link:hover {
            color: var(--turquoise);
        }

        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .hamburger span {
            width: 25px;
            height: 3px;
            background: var(--ocean-blue);
            margin: 3px 0;
            transition: 0.3s;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(135deg, var(--ocean-blue), var(--turquoise)),
                        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 800"><rect fill="%230e4c92" width="1200" height="800"/><path fill="%2318a3c5" d="M0 400L50 383.3C100 366.7 200 333.3 300 316.7C400 300 500 300 600 316.7C700 333.3 800 366.7 900 383.3C1000 400 1100 400 1150 400L1200 400L1200 800L1150 800C1100 800 1000 800 900 800C800 800 700 800 600 800C500 800 400 800 300 800C200 800 100 800 50 800L0 800Z"/></svg>');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--white);
            position: relative;
        }

        .hero-content h1 {
            font-size: 4rem;
            font-weight: 700;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease 0.3s both;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2rem;
            background: var(--warm-orange);
            color: var(--white);
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease 0.6s both;
        }

        .cta-button:hover {
            background: #e55a2b;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }

        /* Secciones */
        section {
            padding: 5rem 0;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--ocean-blue);
        }

        /* ¿Por qué Güiria? */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .feature-card {
            background: var(--white);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        /* Eventos */
        .events-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 3rem;
        }

        .event-card {
            background: var(--white);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .event-card:hover {
            transform: scale(1.05);
        }

        .event-header {
            padding: 1rem;
            color: var(--white);
            font-weight: 600;
        }

        .event-content {
            padding: 1.5rem;
        }

        /* Lugares */
        .places-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .place-card {
            background: var(--white);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .place-card:hover {
            transform: scale(1.05);
        }

        .place-image {
            height: 200px;
            background: linear-gradient(45deg, var(--turquoise), var(--golden));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
        }

        .place-content {
            padding: 1.5rem;
        }

        /* Gastronomía */
        .food-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .food-item {
            text-align: center;
            transition: all 0.3s ease;
        }

        .food-item:hover {
            transform: scale(1.1);
        }

        .food-circle {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--warm-orange), var(--golden));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            margin: 0 auto 1rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        /* Galería */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1rem;
            margin-top: 3rem;
        }

        .gallery-item {
            height: 250px;
            background: linear-gradient(135deg, var(--turquoise), var(--ocean-blue));
            border-radius: 10px;
            overflow: hidden;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: var(--white);
        }

        .gallery-item:hover {
            transform: scale(1.05);
        }

        /* Cómo Llegar */
        .transport-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .transport-card {
            background: var(--white);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        /* Testimonios */
        .testimonials-carousel {
            max-width: 800px;
            margin: 3rem auto;
            position: relative;
        }

        .testimonial {
            background: var(--white);
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            text-align: center;
        }

        .stars {
            color: var(--golden);
            font-size: 1.2rem;
            margin-bottom: 1rem;
        }

        /* Paquetes */
        .packages-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .package-card {
            background: var(--white);
            border-radius: 15px;
            padding: 2rem;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            position: relative;
        }

        .package-card.featured {
            border: 3px solid var(--warm-orange);
            transform: scale(1.05);
        }

        .package-price {
            font-size: 2.5rem;
            color: var(--warm-orange);
            font-weight: 700;
            margin: 1rem 0;
        }

        /* Formulario */
        .contact-form {
            max-width: 600px;
            margin: 3rem auto;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-family: inherit;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--turquoise);
        }

        /* Footer */
        footer {
            background: var(--ocean-blue);
            color: var(--white);
            padding: 3rem 0 1rem;
            text-align: center;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            color: var(--white);
            font-size: 1.5rem;
            transition: color 0.3s ease;
        }

        .social-links a:hover {
            color: var(--golden);
        }

        /* WhatsApp Float */
        .whatsapp-float {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 60px;
            height: 60px;
            background-color: #25d366;
            color: var(--white);
            border-radius: 50px;
            text-align: center;
            font-size: 30px;
            box-shadow: 2px 2px 10px rgba(0,0,0,0.3);
            z-index: 100;
            transition: all 0.3s ease;
        }

        .whatsapp-float:hover {
            transform: scale(1.1);
        }

        /* Animaciones */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-menu {
                position: fixed;
                left: -100%;
                top: 70px;
                flex-direction: column;
                background-color: var(--white);
                width: 100%;
                text-align: center;
                transition: 0.3s;
                box-shadow: 0 10px 27px rgba(0,0,0,0.05);
                padding: 2rem 0;
            }

            .nav-menu.active {
                left: 0;
            }

            .hamburger {
                display: flex;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .hero-content p {
                font-size: 1.2rem;
            }

            section {
                padding: 3rem 0;
            }
        }

        /* Contador Regresivo */
        .countdown {
            background: linear-gradient(135deg, var(--warm-orange), var(--golden));
            color: var(--white);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            margin: 2rem 0;
        }

        .countdown-timer {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 1rem;
        }

        .countdown-item {
            text-align: center;
        }

        .countdown-number {
            font-size: 2.5rem;
            font-weight: 700;
            display: block;
        }

        .countdown-label {
            font-size: 0.9rem;
            text-transform: uppercase;
        }
    </style>
</head>
<body>
    <!-- Navegación -->
    <nav class="navbar">
        <div class="nav-container">
            <div class="logo">🏝️ Descubre Güiria</div>
            <ul class="nav-menu">
                <li><a href="#inicio" class="nav-link">Inicio</a></li>
                <li><a href="#eventos" class="nav-link">Eventos</a></li>
                <li><a href="#lugares" class="nav-link">Lugares</a></li>
                <li><a href="#gastronomia" class="nav-link">Gastronomía</a></li>
                <li><a href="#como-llegar" class="nav-link">Cómo Llegar</a></li>
                <li><a href="#reservar" class="nav-link">Reservar</a></li>
                <li><a href="#contacto" class="nav-link">Contacto</a></li>
            </ul>
            <div class="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="inicio" class="hero">
        <div class="hero-content">
            <h1>Descubre Güiria</h1>
            <p>Donde el Atlántico Abraza al Caribe</p>
            <a href="#reservar" class="cta-button">Planifica tu Viaje</a>
        </div>
    </section>

    <!-- Contador Regresivo -->
    <section style="background: var(--light-gray); padding: 2rem 0;">
        <div class="container">
            <div class="countdown fade-in">
                <h3>🎭 Próximo Evento: Carnavales de Güiria</h3>
                <div class="countdown-timer">
                    <div class="countdown-item">
                        <span class="countdown-number" id="days">45</span>
                        <span class="countdown-label">Días</span>
                    </div>
                    <div class="countdown-item">
                        <span class="countdown-number" id="hours">12</span>
                        <span class="countdown-label">Horas</span>
                    </div>
                    <div class="countdown-item">
                        <span class="countdown-number" id="minutes">34</span>
                        <span class="countdown-label">Minutos</span>
                    </div>
                    <div class="countdown-item">
                        <span class="countdown-number" id="seconds">56</span>
                        <span class="countdown-label">Segundos</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ¿Por qué Güiria? -->
    <section id="por-que-guiria">
        <div class="container">
            <h2 class="section-title fade-in">¿Por Qué Güiria?</h2>
            <div class="features-grid">
                <div class="feature-card fade-in">
                    <div class="feature-icon">🏖️</div>
                    <h3>Playas Paradisíacas</h3>
                    <p>Playa Medina, considerada entre las Top 10 de Sudamérica con sus aguas cristalinas y arena blanca.</p>
                </div>
                <div class="feature-card fade-in">
                    <div class="feature-icon">🎭</div>
                    <h3>Cultura Única</h3>
                    <p>Fusión afro-caribeña auténtica con steelpan, cricket y tradiciones que te transportan a otro mundo.</p>
                </div>
                <div class="feature-card fade-in">
                    <div class="feature-icon">🏛️</div>
                    <h3>Historia Viva</h3>
                    <p>El primer lugar visitado por Cristóbal Colón en Venezuela en 1498, con sitios históricos por descubrir.</p>
                </div>
                <div class="feature-card fade-in">
                    <div class="feature-icon">🍽️</div>
                    <h3>Gastronomía Exclusiva</h3>
                    <p>Sabores únicos como el Kalalu, pelau y souse que fusionan lo mejor del Caribe y Venezuela.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Eventos -->
    <section id="eventos" style="background: var(--light-gray);">
        <div class="container">
            <h2 class="section-title fade-in">Eventos Anuales</h2>
            <div class="events-grid">
                <div class="event-card fade-in">
                    <div class="event-header" style="background: linear-gradient(135deg, #ff6b35, #feca57);">
                        FEBRERO-MARZO: Carnavales de Güiria 🎭
                    </div>
                    <div class="event-content">
                        <p>Desfiles con steelpan, comparsas vibrantes y carnaval en la playa. La celebración más colorida del año.</p>
                    </div>
                </div>
                <div class="event-card fade-in">
                    <div class="event-header" style="background: linear-gradient(135deg, #0e4c92, #18a3c5);">
                        MARZO: Festival del Pescado 🐟
                    </div>
                    <div class="event-content">
                        <p>Feria gastronómica marina con torneo de pesca y degustación de platos frescos del Atlántico.</p>
                    </div>
                </div>
                <div class="event-card fade-in">
                    <div class="event-header" style="background: linear-gradient(135deg, #ffd700, #ff9ff3);">
                        ABRIL: Semana Santa Playera 🏖️
                    </div>
                    <div class="event-content">
                        <p>Paquetes especiales a playas vírgenes y festival del coco con actividades familiares.</p>
                    </div>
                </div>
                <div class="event-card fade-in">
                    <div class="event-header" style="background: linear-gradient(135deg, #54a0ff, #5f27cd);">
                        MAYO: Güiria Emprende 💼
                    </div>
                    <div class="event-content">
                        <p>Exposición de más de 100 emprendimientos locales. Apoya la economía regional.</p>
                    </div>
                </div>
                <div class="event-card fade-in">
                    <div class="event-header" style="background: linear-gradient(135deg, #00d2d3, #54a0ff);">
                        JUNIO: Festival Ecológico "Salvemos Paria" 🌿
                    </div>
                    <div class="event-content">
                        <p>Liberación de tortugas marinas y limpieza de playas. Turismo responsable y sostenible.</p>
                    </div>
                </div>
                <div class="event-card fade-in">
                    <div class="event-header" style="background: linear-gradient(135deg, #ff6348, #ff9ff3);">
                        JULIO: Festival de la Juventud 🎮
                    </div>
                    <div class="event-content">
                        <p>Torneos deportivos, conciertos y batalla de freestyle. La energía de la juventud güireña.</p>
                    </div>
                </div>
                <div class="event-card fade-in">
                    <div class="event-header" style="background: linear-gradient(135deg, #feca57, #ff6348);">
                        AGOSTO: Ruta de Colón ⛵
                    </div>
                    <div class="event-content">
                        <p>Recreación histórica y tours guiados a Macuro, siguiendo los pasos de Colón.</p>
                    </div>
                </div>
                <div class="event-card fade-in">
                    <div class="event-header" style="background: linear-gradient(135deg, #48dbfb, #0abde3);">
                        SEPTIEMBRE: Raíces Afro-Caribeñas 🥁
                    </div>
                    <div class="event-content">
                        <p>Festival de tambores y danzas tradicionales que celebran nuestras raíces africanas.</p>
                    </div>
                </div>
                <div class="event-card fade-in">
                    <div class="event-header" style="background: linear-gradient(135deg, #ff6b35, #feca57);">
                        OCTUBRE: Halloween Tropical 🎃
                    </div>
                    <div class="event-content">
                        <p>Concurso de disfraces y fiesta en la playa con temática tropical única.</p>
                    </div>
                </div>
                <div class="event-card fade-in">
                    <div class="event-header" style="background: linear-gradient(135deg, #5f27cd, #00d2d3);">
                        NOVIEMBRE: Maratón del Atlántico 🏃
                    </div>
                    <div class="event-content">
                        <p>Carreras de 5K, 10K y 21K frente al mar Atlántico. Desafía tus límites.</p>
                    </div>
                </div>
                <div class="event-card fade-in">
                    <div class="event-header" style="background: linear-gradient(135deg, #00d84a, #00d2d3);">
                        DICIEMBRE: Navidad Güireña 🎄
                    </div>
                    <div class="event-content">
                        <p>Árbol gigante, feria navideña y año nuevo en la playa con fuegos artificiales.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Lugares Turísticos -->
    <section id="lugares">
        <div class="container">
            <h2 class="section-title fade-in">Lugares Turísticos</h2>
            <div class="places-grid">
                <div class="place-card fade-in">
                    <div class="place-image">🏖️</div>
                    <div class="place-content">
                        <h3>Playa Medina</h3>
                        <p>Considerada entre las Top 10 playas de Sudamérica. Aguas cristalinas y arena blanca como el azúcar.</p>
                        <p><strong>Distancia:</strong> 30 min desde Güiria</p>
                        <a href="#" class="cta-button" style="margin-top: 1rem; padding: 0.5rem 1rem; font-size: 0.9rem;">Ver más</a>
                    </div>
                </div>
                <div class="place-card fade-in">
                    <div class="place-image">🏝️</div>
                    <div class="place-content">
                        <h3>Playa Pui-Puy</h3>
                        <p>Aguas cristalinas y ambiente tranquilo. Perfecta para snorkeling y descanso total.</p>
                        <p><strong>Distancia:</strong> 45 min desde Güiria</p>
                        <a href="#" class="cta-button" style="margin-top: 1rem; padding: 0.5rem 1rem; font-size: 0.9rem;">Ver más</a>
                    </div>
                </div>
                <div class="place-card fade-in">
                    <div class="place-image">⚓</div>
                    <div class="place-content">
                        <h3>Macuro</h3>
                        <p>Sitio histórico donde desembarcó Colón en 1498. Playas vírgenes y historia viva.</p>
                        <p><strong>Distancia:</strong> 1 hora desde Güiria</p>
                        <a href="#" class="cta-button" style="margin-top: 1rem; padding: 0.5rem 1rem; font-size: 0.9rem;">Ver más</a>
                    </div>
                </div>
                <div class="place-card fade-in">
                    <div class="place-image">🌊</div>
                    <div class="place-content">
                        <h3>San Juan de las Galdonas</h3>
                        <p>Playa virgen y salvaje. Para los amantes de la naturaleza y la aventura auténtica.</p>
                        <p><strong>Distancia:</strong> 1.5 horas desde Güiria</p>
                        <a href="#" class="cta-button" style="margin-top: 1rem; padding: 0.5rem 1rem; font-size: 0.9rem;">Ver más</a>
                    </div>
                </div>
                <div class="place-card fade-in">
                    <div class="place-image">🚢</div>
                    <div class="place-content">
                        <h3>Puerto de Güiria</h3>
                        <p>El único puerto venezolano en el Atlántico. Ver la pesca artesanal y los barcos llegar.</p>
                        <p><strong>Distancia:</strong> En el centro de Güiria</p>
                        <a href="#" class="cta-button" style="margin-top: 1rem; padding: 0.5rem 1rem; font-size: 0.9rem;">Ver más</a>
                    </div>
                </div>
                <div class="place-card fade-in">
                    <div class="place-image">🌅</div>
                    <div class="place-content">
                        <h3>Malecón de Güiria</h3>
                        <p>Paseo costero con vista al Atlántico. Atardeceres mágicos y ambiente familiar.</p>
                        <p><strong>Distancia:</strong> En el centro de Güiria</p>
                        <a href="#" class="cta-button" style="margin-top: 1rem; padding: 0.5rem 1rem; font-size: 0.9rem;">Ver más</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Gastronomía -->
    <section id="gastronomia" style="background: var(--light-gray);">
        <div class="container">
            <h2 class="section-title fade-in">Gastronomía</h2>
            <div class="food-grid">
                <div class="food-item fade-in">
                    <div class="food-circle">🍲</div>
                    <h4>Kalalu</h4>
                    <p>Sopa de hojas de dasheen, única en Venezuela</p>
                </div>
                <div class="food-item fade-in">
                    <div class="food-circle">🍚</div>
                    <h4>Pelau</h4>
                    <p>Arroz con pollo estilo trinitario, exquisito</p>
                </div>
                <div class="food-item fade-in">
                    <div class="food-circle">🥩</div>
                    <h4>Souse</h4>
                    <p>Cerdo marinado en limón, tradicional</p>
                </div>
                <div class="food-item fade-in">
                    <div class="food-circle">🥟</div>
                    <h4>Domplina</h4>
                    <p>Bollitos hervidos, acompañamiento perfecto</p>
                </div>
                <div class="food-item fade-in">
                    <div class="food-circle">🍛</div>
                    <h4>Talkari de Chivo</h4>
                    <p>Curry caribeño de chivo, explosión de sabor</p>
                </div>
                <div class="food-item fade-in">
                    <div class="food-circle">🐟</div>
                    <h4>Pescado Frito</h4>
                    <p>Fresco del Puerto, del Atlántico a tu plato</p>
                </div>
                <div class="food-item fade-in">
                    <div class="food-circle">🥥</div>
                    <h4>Dulce de Coco</h4>
                    <p>Postre tradicional, dulzura tropical</p>
                </div>
                <div class="food-item fade-in">
                    <div class="food-circle">🦐</div>
                    <h4>Mariscos Frescos</h4>
                    <p>Del Atlántico, la mejor calidad y sabor</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Galería -->
    <section id="galeria">
        <div class="container">
            <h2 class="section-title fade-in">Galería de Fotos</h2>
            <div class="gallery-grid">
                <div class="gallery-item fade-in">🏖️ Playas</div>
                <div class="gallery-item fade-in">🎭 Eventos</div>
                <div class="gallery-item fade-in">🍽️ Gastronomía</div>
                <div class="gallery-item fade-in">🥁 Cultura</div>
                <div class="gallery-item fade-in">🌅 Atardeceres</div>
                <div class="gallery-item fade-in">⚓ Puerto</div>
                <div class="gallery-item fade-in">🏝️ Naturaleza</div>
                <div class="gallery-item fade-in">🎉 Celebraciones</div>
            </div>
        </div>
    </section>

    <!-- Cómo Llegar -->
    <section id="como-llegar" style="background: var(--light-gray);">
        <div class="container">
            <h2 class="section-title fade-in">Cómo Llegar</h2>
            <div class="transport-options">
                <div class="transport-card fade-in">
                    <i class="fas fa-bus" style="font-size: 3rem; color: var(--ocean-blue); margin-bottom: 1rem;"></i>
                    <h3>Desde Caracas</h3>
                    <p><strong>7 horas</strong> en autobús</p>
                    <p>Salidas diarias desde la Terminal de Oriente</p>
                </div>
                <div class="transport-card fade-in">
                    <i class="fas fa-car" style="font-size: 3rem; color: var(--turquoise); margin-bottom: 1rem;"></i>
                    <h3>Desde Cumaná</h3>
                    <p><strong>3 horas</strong> en carro</p>
                    <p>Ruta costera con vistas espectaculares</p>
                </div>
                <div class="transport-card fade-in">
                    <i class="fas fa-ship" style="font-size: 3rem; color: var(--warm-orange); margin-bottom: 1rem;"></i>
                    <h3>Desde Carúpano</h3>
                    <p><strong>1.5 horas</strong> en carro</p>
                    <p>La ruta más corta y directa</p>
                </div>
                <div class="transport-card fade-in">
                    <i class="fas fa-anchor" style="font-size: 3rem; color: var(--golden); margin-bottom: 1rem;"></i>
                    <h3>Desde Trinidad</h3>
                    <p><strong>3 horas</strong> en ferry</p>
                    <p>Próximamente - Conexión directa</p>
                </div>
            </div>
            <div style="margin-top: 3rem; text-align: center;">
                <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d198563.53783453985!2d-62.50000000000001!3d10.5833333!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8c0bb6d15f9e8c3b%3A0x2e4b8b0a4d8e8c3b!2sG%C3%BCiria%2C%20Sucre%2C%20Venezuela!5e0!3m2!1ses!2sus!4v1635360000000" width="100%" height="450" style="border:0; border-radius: 15px;" allowfullscreen="" loading="lazy"></iframe>
            </div>
        </div>
    </section>

    <!-- Testimonios -->
    <section id="testimonios">
        <div class="container">
            <h2 class="section-title fade-in">Testimonios</h2>
            <div class="testimonials-carousel">
                <div class="testimonial fade-in">
                    <div class="stars">★★★★★</div>
                    <p>"Güiria superó todas mis expectativas. Las playas son increíbles, la gente es cálida y la comida es excepcional. ¡Volveré pronto!"</p>
                    <strong>- María González</strong>
                    <p>Caracas, Venezuela</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Paquetes Turísticos -->
    <section id="paquetes" style="background: var(--light-gray);">
        <div class="container">
            <h2 class="section-title fade-in">Paquetes Turísticos</h2>
            <div class="packages-grid">
                <div class="package-card fade-in">
                    <h3>BÁSICO</h3>
                    <div class="package-price">$150</div>
                    <ul style="list-style: none; padding: 0;">
                        <li>✅ 2 días / 1 noche</li>
                        <li>✅ Hospedaje en posada</li>
                        <li>✅ Desayuno incluido</li>
                        <li>✅ Tour a 1 playa</li>
                    </ul>
                    <a href="#reservar" class="cta-button" style="margin-top: 1.5rem; display: block;">Reservar</a>
                </div>
                <div class="package-card featured fade-in">
                    <h3>COMPLETO</h3>
                    <div class="package-price">$400</div>
                    <ul style="list-style: none; padding: 0;">
                        <li>✅ 4 días / 3 noches</li>
                        <li>✅ Posada frente al mar</li>
                        <li>✅ Todas las comidas</li>
                        <li>✅ Tours a 3 playas</li>
                        <li>✅ Actividades acuáticas</li>
                    </ul>
                    <a href="#reservar" class="cta-button" style="margin-top: 1.5rem; display: block;">Reservar</a>
                </div>
                <div class="package-card fade-in">
                    <h3>PREMIUM</h3>
                    <div class="package-price">$650</div>
                    <ul style="list-style: none; padding: 0;">
                        <li>✅ 5 días / 4 noches</li>
                        <li>✅ Hotel boutique</li>
                        <li>✅ All inclusive</li>
                        <li>✅ Tours privados</li>
                        <li>✅ Experiencias gastronómicas</li>
                        <li>✅ Guía personalizado</li>
                    </ul>
                    <a href="#reservar" class="cta-button" style="margin-top: 1.5rem; display: block;">Reservar</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Formulario de Reserva -->
    <section id="reservar">
        <div class="container">
            <h2 class="section-title fade-in">Reserva tu Viaje</h2>
            <form class="contact-form" action="https://formspree.io/f/your-form-id" method="POST">
                <div class="form-group">
                    <label for="name">Nombre completo</label>
                    <input type="text" id="name" name="name" required>
                </div>
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="phone">Teléfono</label>
                    <input type="tel" id="phone" name="phone" required>
                </div>
                <div class="form-group">
                    <label for="date">Fecha de viaje deseada</label>
                    <input type="date" id="date" name="date" required>
                </div>
                <div class="form-group">
                    <label for="people">Número de personas</label>
                    <input type="number" id="people" name="people" min="1" required>
                </div>
                <div class="form-group">
                    <label for="package">Tipo de paquete</label>
                    <select id="package" name="package" required>
                        <option value="">Selecciona un paquete</option>
                        <option value="basico">Básico - $150</option>
                        <option value="completo">Completo - $400</option>
                        <option value="premium">Premium - $650</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="message">Mensaje adicional</label>
                    <textarea id="message" name="message" rows="4"></textarea>
                </div>
                <button type="submit" class="cta-button" style="width: 100%; border: none; font-size: 1.1rem;">Enviar Solicitud</button>
            </form>
        </div>
    </section>

    <!-- Newsletter -->
    <section style="background: var(--ocean-blue); color: var(--white);">
        <div class="container" style="text-align: center;">
            <h2 class="fade-in">Recibe Ofertas Exclusivas</h2>
            <p class="fade-in">Suscríbete y entérate primero de nuestros descuentos y eventos especiales</p>
            <form style="max-width: 500px; margin: 2rem auto; display: flex; gap: 1rem;" class="fade-in">
                <input type="email" placeholder="Tu email" style="flex: 1; padding: 1rem; border: none; border-radius: 50px;">
                <button type="submit" class="cta-button" style="border: none;">Suscribirse</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contacto">
        <div class="container">
            <div class="footer-content">
                <div>
                    <h3>Contacto</h3>
                    <p>📍 Plaza Bolívar, Güiria, Estado Sucre</p>
                    <p>📧 info@descubreguiria.com</p>
                    <p>📱 +58 414-1234567</p>
                </div>
                <div>
                    <h3>Síguenos</h3>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-facebook"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                    <p style="margin-top: 1rem;">@descubreguiria</p>
                </div>
                <div>
                    <h3>Enlaces Rápidos</h3>
                    <p><a href="#eventos" style="color: var(--white); text-decoration: none;">Próximos Eventos</a></p>
                    <p><a href="#paquetes" style="color: var(--white); text-decoration: none;">Paquetes</a></p>
                    <p><a href="#como-llegar" style="color: var(--white); text-decoration: none;">Cómo Llegar</a></p>
                </div>
            </div>
            <hr style="margin: 2rem 0; opacity: 0.3;">
            <p>&copy; 2024 Descubre Güiria. Todos los derechos reservados.</p>
        </div>
    </footer>

    <!-- WhatsApp Float -->
    <a href="https://wa.me/584141234567" class="whatsapp-float" target="_blank">
        <i class="fab fa-whatsapp"></i>
    </a>

    <!-- Back to Top -->
    <button onclick="topFunction()" id="myBtn" title="Go to top" style="display: none; position: fixed; bottom: 85px; right: 20px; z-index: 99; border: none; outline: none; background-color: var(--turquoise); color: white; cursor: pointer; padding: 15px; border-radius: 50px; font-size: 18px;">
        <i class="fas fa-arrow-up"></i>
    </button>

    <script>
        // Hamburger Menu
        const hamburger = document.querySelector('.hamburger');
        const navMenu = document.querySelector('.nav-menu');

        hamburger.addEventListener('click', () => {
            navMenu.classList.toggle('active');
        });

        // Smooth Scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
                navMenu.classList.remove('active');
            });
        });

        // Scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Countdown Timer
        function updateCountdown() {
            const eventDate = new Date('2024-02-10T00:00:00');
            const now = new Date();
            const diff = eventDate - now;

            const days = Math.floor(diff / (1000 * 60 * 60 * 24));
            const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((diff % (1000 * 60)) / 1000);

            document.getElementById('days').textContent = days;
            document.getElementById('hours').textContent = hours;
            document.getElementById('minutes').textContent = minutes;
            document.getElementById('seconds').textContent = seconds;
        }

        setInterval(updateCountdown, 1000);
        updateCountdown();

        // Back to Top Button
        window.onscroll = function() {
            if (document.body.scrollTop > 20 || document.documentElement.scrollTop > 20) {
                document.getElementById("myBtn").style.display = "block";
            } else {
                document.getElementById("myBtn").style.display = "none";
            }
        };

        function topFunction() {
            document.body.scrollTop = 0;
            document.documentElement.scrollTop = 0;
        }

        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 100) {
                navbar.style.background = 'rgba(255, 255, 255, 0.98)';
                navbar.style.boxShadow = '0 2px 20px rgba(0,0,0,0.1)';
            } else {
                navbar.style.background = 'rgba(255, 255, 255, 0.95)';
                navbar.style.boxShadow = '0 2px 10px rgba(0,0,0,0.1)';
            }
        });

        // Form submission
        document.querySelector('.contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('¡Gracias por tu solicitud! Nos pondremos en contacto contigo pronto.');
            this.reset();
        });

        // Newsletter form
        document.querySelector('form[action="#"]').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('¡Gracias por suscribirte! Recibirás nuestras ofertas especiales.');
            this.reset();
        });
    </script>
</body>
</html>
