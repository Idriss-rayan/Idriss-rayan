<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Idriss Rayan - Developer Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a1628 0%, #0f3460 50%, #162a3f 100%);
            color: #e0e7ff;
            line-height: 1.6;
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* ===== GRADIENT DEFINITIONS ===== */
        .gradient-primary {
            background: linear-gradient(135deg, #00d4ff 0%, #00ff88 100%);
        }

        .gradient-secondary {
            background: linear-gradient(135deg, #0084ff 0%, #00d4ff 100%);
        }

        .gradient-accent {
            background: linear-gradient(135deg, #00ff88 0%, #00d4ff 100%);
        }

        /* ===== HEADER SECTION ===== */
        .header {
            text-align: center;
            padding: 80px 20px 60px;
            background: linear-gradient(180deg, rgba(0, 212, 255, 0.1) 0%, rgba(0, 255, 136, 0.05) 100%);
            border-bottom: 2px solid rgba(0, 212, 255, 0.3);
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -10%;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(0, 212, 255, 0.15) 0%, transparent 70%);
            border-radius: 50%;
            pointer-events: none;
        }

        .header::after {
            content: '';
            position: absolute;
            bottom: -30%;
            left: -5%;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(0, 255, 136, 0.15) 0%, transparent 70%);
            border-radius: 50%;
            pointer-events: none;
        }

        .header-content {
            position: relative;
            z-index: 1;
        }

        .typing-title {
            font-size: 3.5em;
            font-weight: 800;
            margin-bottom: 30px;
            background: linear-gradient(135deg, #00d4ff 0%, #00ff88 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -1px;
        }

        .subtitle {
            font-size: 1.2em;
            color: #a8d5ff;
            margin-bottom: 40px;
            font-style: italic;
            font-weight: 300;
        }

        /* ===== SOCIAL BADGES ===== */
        .social-badges {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 30px;
        }

        .social-badge {
            padding: 12px 24px;
            border-radius: 50px;
            background: rgba(0, 212, 255, 0.15);
            border: 2px solid rgba(0, 212, 255, 0.4);
            color: #00d4ff;
            text-decoration: none;
            font-weight: 600;
            font-size: 0.95em;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .social-badge:hover {
            background: rgba(0, 255, 136, 0.2);
            border-color: rgba(0, 255, 136, 0.6);
            color: #00ff88;
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 212, 255, 0.2);
        }

        /* ===== MAIN CONTAINER ===== */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* ===== ABOUT SECTION ===== */
        .about-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            margin-bottom: 60px;
            align-items: center;
        }

        .about-content h2 {
            font-size: 2.5em;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #00d4ff 0%, #00ff88 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .about-content p {
            font-size: 1.1em;
            line-height: 1.8;
            color: #cbd5e1;
            margin-bottom: 20px;
        }

        .highlight-box {
            background: rgba(0, 212, 255, 0.1);
            border-left: 4px solid;
            border-image: linear-gradient(180deg, #00d4ff, #00ff88) 1;
            padding: 20px;
            border-radius: 8px;
            margin: 15px 0;
            backdrop-filter: blur(10px);
        }

        .highlight-box strong {
            color: #00d4ff;
        }

        .about-image {
            text-align: center;
        }

        .about-image img {
            max-width: 100%;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0, 212, 255, 0.2);
            transition: transform 0.3s ease;
        }

        .about-image img:hover {
            transform: scale(1.05);
        }

        /* ===== TECH STACK SECTION ===== */
        .tech-section {
            margin-bottom: 60px;
        }

        .section-title {
            font-size: 2.2em;
            margin-bottom: 40px;
            text-align: center;
            background: linear-gradient(135deg, #00d4ff 0%, #00ff88 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            position: relative;
            padding-bottom: 20px;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #00d4ff, #00ff88);
            border-radius: 2px;
        }

        .tech-categories {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .tech-card {
            background: rgba(0, 212, 255, 0.08);
            border: 2px solid rgba(0, 212, 255, 0.2);
            border-radius: 16px;
            padding: 30px;
            backdrop-filter: blur(20px);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .tech-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #00d4ff, #00ff88);
            transform: translateX(-100%);
            transition: transform 0.3s ease;
        }

        .tech-card:hover {
            border-color: rgba(0, 255, 136, 0.4);
            background: rgba(0, 212, 255, 0.15);
            transform: translateY(-8px);
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.15);
        }

        .tech-card:hover::before {
            transform: translateX(0);
        }

        .tech-card-title {
            font-size: 1.5em;
            font-weight: 700;
            margin-bottom: 20px;
            color: #00d4ff;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .tech-badge {
            display: inline-block;
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.2), rgba(0, 255, 136, 0.2));
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.85em;
            font-weight: 600;
            color: #00d4ff;
            margin: 8px 8px 8px 0;
            border: 1px solid rgba(0, 212, 255, 0.3);
            transition: all 0.3s ease;
        }

        .tech-badge:hover {
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.4), rgba(0, 255, 136, 0.4));
            border-color: rgba(0, 255, 136, 0.6);
            color: #00ff88;
        }

        /* ===== GOALS SECTION ===== */
        .goals-section {
            margin-bottom: 60px;
        }

        .goals-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
        }

        .goal-card {
            background: rgba(0, 212, 255, 0.1);
            border: 2px solid rgba(0, 212, 255, 0.2);
            border-radius: 12px;
            padding: 25px;
            backdrop-filter: blur(20px);
            transition: all 0.3s ease;
            position: relative;
        }

        .goal-card::before {
            content: '✓';
            position: absolute;
            top: 15px;
            right: 20px;
            font-size: 1.5em;
            color: #00ff88;
            opacity: 0;
            transition: all 0.3s ease;
        }

        .goal-card:hover {
            background: rgba(0, 255, 136, 0.15);
            border-color: rgba(0, 255, 136, 0.4);
            transform: translateY(-5px);
        }

        .goal-card:hover::before {
            opacity: 1;
            right: 15px;
        }

        .goal-title {
            color: #00d4ff;
            font-weight: 700;
            margin-bottom: 10px;
            font-size: 1.1em;
        }

        .goal-desc {
            color: #a8d5ff;
            font-size: 0.95em;
        }

        /* ===== STATS SECTION ===== */
        .stats-section {
            margin-bottom: 60px;
            text-align: center;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .stat-card {
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.15), rgba(0, 255, 136, 0.05));
            border: 2px solid rgba(0, 212, 255, 0.3);
            border-radius: 12px;
            padding: 25px;
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            border-color: rgba(0, 255, 136, 0.6);
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.25), rgba(0, 255, 136, 0.15));
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0, 212, 255, 0.2);
        }

        .stat-number {
            font-size: 2.5em;
            font-weight: 900;
            background: linear-gradient(135deg, #00d4ff, #00ff88);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stat-label {
            color: #a8d5ff;
            font-size: 0.9em;
            margin-top: 10px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* ===== FOOTER SECTION ===== */
        .footer {
            text-align: center;
            padding: 60px 20px 40px;
            border-top: 2px solid rgba(0, 212, 255, 0.2);
            background: linear-gradient(180deg, transparent 0%, rgba(0, 212, 255, 0.05) 100%);
        }

        .footer-text {
            color: #a8d5ff;
            margin-bottom: 20px;
            font-size: 0.95em;
        }

        .footer-links {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .footer-link {
            color: #00d4ff;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
        }

        .footer-link::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, #00d4ff, #00ff88);
            transition: width 0.3s ease;
        }

        .footer-link:hover::after {
            width: 100%;
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 768px) {
            .typing-title {
                font-size: 2.2em;
            }

            .about-section {
                grid-template-columns: 1fr;
            }

            .section-title {
                font-size: 1.8em;
            }

            .header {
                padding: 50px 20px 40px;
            }

            .tech-categories {
                grid-template-columns: 1fr;
            }

            .social-badges {
                flex-direction: column;
                align-items: center;
            }

            .social-badge {
                width: fit-content;
            }
        }

        /* ===== ANIMATIONS ===== */
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

        .container > * {
            animation: fadeInUp 0.6s ease-out forwards;
        }

        .container > *:nth-child(n) {
            animation-delay: calc(0.1s * var(--index, 0));
        }
    </style>
</head>
<body>
    <!-- ===== HEADER ===== -->
    <header class="header">
        <div class="header-content">
            <h1 class="typing-title">Idriss Rayan</h1>
            <p class="subtitle">✨ Passionate Developer | Flutter Expert | Cloud Architect ✨</p>
            
            <div class="social-badges">
                <a href="https://www.linkedin.com/in/njutapmvoui-idriss-rayan-37477a28a/" class="social-badge">
                    💼 LinkedIn
                </a>
                <a href="mailto:rayanidriss27@gmail.com" class="social-badge">
                    📧 Email
                </a>
                <a href="https://github.com/Idriss-rayan" class="social-badge">
                    🔗 GitHub
                </a>
            </div>
        </div>
    </header>

    <!-- ===== MAIN CONTENT ===== -->
    <div class="container">
        <!-- ABOUT SECTION -->
        <section class="about-section" style="--index: 1;">
            <div class="about-content">
                <h2>👨‍💻 À propos de moi</h2>
                
                <div class="highlight-box">
                    <strong>🔹 Développeur polyglotte</strong><br>
                    Python, C/C++, C#, Dart, Java — expert en construction d'applications robustes
                </div>

                <div class="highlight-box">
                    <strong>🔹 Spécialiste Mobile</strong><br>
                    Flutter & Dart pour le développement cross-platform performant
                </div>

                <div class="highlight-box">
                    <strong>🔹 Architecte Cloud</strong><br>
                    Firebase, Supabase, AWS, Azure, GCP — infrastructure scalable
                </div>

                <div class="highlight-box">
                    <strong>🔹 Maître des données</strong><br>
                    MySQL, PostgreSQL, MongoDB, SQLite — conception et optimisation BD
                </div>

                <p style="margin-top: 30px; font-size: 1em; color: #cbd5e1;">
                    Je conçois des solutions <strong style="color: #00d4ff;">robustes, efficaces et bien pensées</strong> — du mobile au backend, en passant par l'infrastructure cloud. Toujours curieux, toujours en apprentissage.
                </p>
            </div>

            <div class="about-image">
                <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExbnQwdWoycHczZHJ1Z2Q0c2pzbHo4a2x0em9uN3hwNnJzYm1nN3E5MSZlcD12MV9naWZzX3NlYXJjaCZjdD1n/ZVik7pBtu9dNS/giphy.gif" alt="Developer Animation" />
            </div>
        </section>

        <!-- TECH STACK SECTION -->
        <section class="tech-section" style="--index: 2;">
            <h2 class="section-title">🛠️ Tech Stack</h2>
            
            <div class="tech-categories">
                <!-- Languages -->
                <div class="tech-card">
                    <div class="tech-card-title">💻 Langages</div>
                    <div class="tech-badge">Python</div>
                    <div class="tech-badge">C</div>
                    <div class="tech-badge">C++</div>
                    <div class="tech-badge">C#</div>
                    <div class="tech-badge">Dart</div>
                    <div class="tech-badge">Java</div>
                </div>

                <!-- Mobile -->
                <div class="tech-card">
                    <div class="tech-card-title">📱 Mobile</div>
                    <div class="tech-badge">Flutter</div>
                    <div class="tech-badge">Dart</div>
                    <div class="tech-badge">Cross-Platform</div>
                    <div class="tech-badge">Native</div>
                </div>

                <!-- Backend & Cloud -->
                <div class="tech-card">
                    <div class="tech-card-title">☁️ Cloud</div>
                    <div class="tech-badge">Firebase</div>
                    <div class="tech-badge">Supabase</div>
                    <div class="tech-badge">Node.js</div>
                    <div class="tech-badge">AWS</div>
                    <div class="tech-badge">Azure</div>
                    <div class="tech-badge">GCP</div>
                </div>

                <!-- Databases -->
                <div class="tech-card">
                    <div class="tech-card-title">🗄️ Bases de données</div>
                    <div class="tech-badge">MySQL</div>
                    <div class="tech-badge">PostgreSQL</div>
                    <div class="tech-badge">MongoDB</div>
                    <div class="tech-badge">SQLite</div>
                </div>

                <!-- Tools -->
                <div class="tech-card">
                    <div class="tech-card-title">🔧 Outils</div>
                    <div class="tech-badge">Git</div>
                    <div class="tech-badge">GitHub</div>
                    <div class="tech-badge">Postman</div>
                    <div class="tech-badge">Figma</div>
                </div>

                <!-- Specialties -->
                <div class="tech-card">
                    <div class="tech-card-title">⚡ Spécialités</div>
                    <div class="tech-badge">Architecture</div>
                    <div class="tech-badge">DevOps</div>
                    <div class="tech-badge">Scalability</div>
                    <div class="tech-badge">Performance</div>
                </div>
            </div>
        </section>

        <!-- STATS SECTION -->
        <section class="stats-section" style="--index: 3;">
            <h2 class="section-title">📊 Statistiques</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-number">15+</div>
                    <div class="stat-label">Projets Complétés</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">6</div>
                    <div class="stat-label">Langages Maîtrisés</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">4+</div>
                    <div class="stat-label">Années d'Expérience</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">100%</div>
                    <div class="stat-label">Dédication</div>
                </div>
            </div>
        </section>

        <!-- GOALS SECTION -->
        <section class="goals-section" style="--index: 4;">
            <h2 class="section-title">🎯 Objectifs 2026</h2>
            <div class="goals-grid">
                <div class="goal-card">
                    <div class="goal-title">🏗️ System Architecture</div>
                    <div class="goal-desc">Approfondir expertise en architecture système et scalabilité</div>
                </div>
                <div class="goal-card">
                    <div class="goal-title">🌍 Open Source</div>
                    <div class="goal-desc">Contribuer à des projets Flutter open source majeurs</div>
                </div>
                <div class="goal-card">
                    <div class="goal-title">☁️ AWS Certification</div>
                    <div class="goal-desc">Obtenir la certification AWS Certified Developer</div>
                </div>
                <div class="goal-card">
                    <div class="goal-title">🚀 SaaS Product</div>
                    <div class="goal-desc">Construire un produit SaaS avec Flutter + Supabase</div>
                </div>
                <div class="goal-card">
                    <div class="goal-title">✍️ Technical Writing</div>
                    <div class="goal-desc">Publier des articles techniques sur Dev.to</div>
                </div>
                <div class="goal-card">
                    <div class="goal-title">🤝 Mentoring</div>
                    <div class="goal-desc">Mentorer les jeunes développeurs en formation</div>
                </div>
            </div>
        </section>
    </div>

    <!-- ===== FOOTER ===== -->
    <footer class="footer" style="--index: 5;">
        <div class="footer-text">
            ✨ Passionné par le code, toujours en quête d'apprentissage ✨
        </div>
        <p style="color: #64748b; margin-bottom: 20px;">
            Explorons ensemble comment la technologie peut résoudre les vrais problèmes.
        </p>
        <div class="footer-links">
            <a href="https://www.linkedin.com/in/njutapmvoui-idriss-rayan-37477a28a/" class="footer-link">LinkedIn</a>
            <a href="mailto:rayanidriss27@gmail.com" class="footer-link">Email</a>
            <a href="https://github.com/Idriss-rayan" class="footer-link">GitHub</a>
        </div>
        <div class="footer-text" style="margin-top: 30px; font-size: 0.9em;">
            © 2026 Idriss Rayan. Crafted with 💜 using modern web technologies.
        </div>
    </footer>
</body>
</html>
