<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Profil Développeur — Glassmorphisme</title>

    <!-- Font Awesome pour les icônes -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />

    <style>
        /* ===== RESET & GLOBAL ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: radial-gradient(circle at 20% 30%, #2b2d42, #1a1a2e, #0f0f1a);
            padding: 2rem;
            position: relative;
            overflow-x: hidden;
        }

        /* ===== ANIMATED BACKGROUND BLOBS ===== */
        body::before,
        body::after {
            content: '';
            position: fixed;
            border-radius: 50%;
            filter: blur(120px);
            opacity: 0.4;
            z-index: 0;
            animation: floatBlob 12s ease-in-out infinite alternate;
        }

        body::before {
            width: 500px;
            height: 500px;
            background: #6c5ce7;
            top: -100px;
            left: -100px;
        }

        body::after {
            width: 600px;
            height: 600px;
            background: #00b894;
            bottom: -150px;
            right: -150px;
            animation-duration: 16s;
            animation-delay: 2s;
        }

        @keyframes floatBlob {
            0% {
                transform: translate(0, 0) scale(1);
            }
            100% {
                transform: translate(60px, 40px) scale(1.2);
            }
        }

        /* ===== CARD PRINCIPALE — GLASSMORPHISM ===== */
        .glass-card {
            position: relative;
            z-index: 1;
            max-width: 1100px;
            width: 100%;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(24px) saturate(180%);
            -webkit-backdrop-filter: blur(24px) saturate(180%);
            border-radius: 48px;
            border: 1px solid rgba(255, 255, 255, 0.12);
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.6), inset 0 1px 0 rgba(255, 255, 255, 0.06);
            padding: 2.5rem 3rem;
            transition: transform 0.3s ease;
        }

        .glass-card:hover {
            transform: translateY(-4px);
        }

        /* ===== EN-TÊTE ===== */
        .header {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: flex-start;
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .identity h1 {
            font-size: 2.4rem;
            font-weight: 700;
            background: linear-gradient(135deg, #f7f7ff, #b2b5e0);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -0.5px;
        }

        .identity .tagline {
            color: rgba(255, 255, 255, 0.6);
            font-size: 1.05rem;
            font-weight: 300;
            margin-top: 0.2rem;
            letter-spacing: 0.3px;
        }

        .identity .tagline i {
            color: #fdcb6e;
            margin-right: 6px;
        }

        .badge-container {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            align-items: center;
        }

        .badge-glass {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: rgba(255, 255, 255, 0.06);
            backdrop-filter: blur(8px);
            padding: 0.5rem 1.2rem;
            border-radius: 60px;
            border: 1px solid rgba(255, 255, 255, 0.08);
            color: rgba(255, 255, 255, 0.8);
            font-size: 0.85rem;
            text-decoration: none;
            transition: all 0.25s ease;
        }

        .badge-glass:hover {
            background: rgba(255, 255, 255, 0.12);
            border-color: rgba(255, 255, 255, 0.2);
            transform: scale(1.04);
            color: #fff;
        }

        .badge-glass i {
            font-size: 1.1rem;
            color: #74b9ff;
        }

        .badge-glass .fa-linkedin {
            color: #0a66c2;
        }
        .badge-glass .fa-envelope {
            color: #ea4335;
        }

        /* ===== BIO ===== */
        .bio {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 24px;
            padding: 1.5rem 2rem;
            border: 1px solid rgba(255, 255, 255, 0.05);
            margin-bottom: 2rem;
            color: rgba(255, 255, 255, 0.8);
            line-height: 1.7;
            font-size: 1rem;
        }

        .bio strong {
            color: #dfe6e9;
        }

        .bio i {
            color: #fdcb6e;
            margin-right: 6px;
        }

        /* ===== TECH STACK ===== */
        .section-title {
            font-size: 1.2rem;
            font-weight: 600;
            color: rgba(255, 255, 255, 0.7);
            letter-spacing: 1px;
            text-transform: uppercase;
            margin-bottom: 1.2rem;
            border-bottom: 1px solid rgba(255, 255, 255, 0.06);
            padding-bottom: 0.6rem;
        }

        .section-title i {
            margin-right: 10px;
            color: #74b9ff;
        }

        .tech-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 0.7rem 1rem;
            margin-bottom: 2.2rem;
        }

        .tech-tag {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(6px);
            padding: 0.4rem 1.2rem;
            border-radius: 40px;
            border: 1px solid rgba(255, 255, 255, 0.06);
            color: rgba(255, 255, 255, 0.75);
            font-size: 0.85rem;
            font-weight: 400;
            transition: all 0.2s ease;
            letter-spacing: 0.2px;
        }

        .tech-tag:hover {
            background: rgba(255, 255, 255, 0.10);
            border-color: rgba(255, 255, 255, 0.15);
            transform: translateY(-2px);
            color: #fff;
        }

        .tech-tag i {
            margin-right: 6px;
            font-size: 0.9rem;
        }

        .tech-tag .fa-python {
            color: #3776ab;
        }
        .tech-tag .fa-cuttlefish {
            color: #00599c;
        }
        .tech-tag .fa-dart {
            color: #00b4ab;
        }
        .tech-tag .fa-flutter {
            color: #54c5f8;
        }
        .tech-tag .fa-java {
            color: #f89820;
        }
        .tech-tag .fa-database {
            color: #47a248;
        }
        .tech-tag .fa-cloud {
            color: #ff9900;
        }
        .tech-tag .fa-fire {
            color: #ffca28;
        }
        .tech-tag .fa-aws {
            color: #ff9900;
        }
        .tech-tag .fa-microsoft {
            color: #0078d4;
        }
        .tech-tag .fa-google {
            color: #4285f4;
        }
        .tech-tag .fa-git-alt {
            color: #f05032;
        }
        .tech-tag .fa-figma {
            color: #f24e1e;
        }
        .tech-tag .fa-node {
            color: #68a063;
        }

        /* ===== STATS + TROPHIES ===== */
        .stats-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .stat-box {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 20px;
            padding: 1.2rem 1.5rem;
            border: 1px solid rgba(255, 255, 255, 0.04);
            text-align: center;
            transition: all 0.25s ease;
        }

        .stat-box:hover {
            background: rgba(255, 255, 255, 0.06);
            border-color: rgba(255, 255, 255, 0.08);
        }

        .stat-box .number {
            font-size: 1.8rem;
            font-weight: 700;
            background: linear-gradient(135deg, #a29bfe, #6c5ce7);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stat-box .label {
            color: rgba(255, 255, 255, 0.5);
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            margin-top: 2px;
        }

        .stat-box i {
            color: #fdcb6e;
            margin-right: 6px;
        }

        /* ===== TROPHIES ===== */
        .trophy-row {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 0.8rem 1.5rem;
            padding: 1rem 0;
            margin-bottom: 1rem;
            border-top: 1px solid rgba(255, 255, 255, 0.04);
        }

        .trophy-item {
            display: flex;
            align-items: center;
            gap: 8px;
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.9rem;
        }

        .trophy-item i {
            font-size: 1.3rem;
            color: #fdcb6e;
        }

        /* ===== FOOTER ===== */
        .footer-note {
            text-align: center;
            color: rgba(255, 255, 255, 0.2);
            font-size: 0.75rem;
            letter-spacing: 0.5px;
            margin-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.03);
            padding-top: 1.2rem;
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 768px) {
            .glass-card {
                padding: 1.5rem;
            }

            .header {
                flex-direction: column;
                align-items: stretch;
            }

            .identity h1 {
                font-size: 1.8rem;
            }

            .stats-row {
                grid-template-columns: 1fr;
            }

            .bio {
                padding: 1rem;
                font-size: 0.92rem;
            }

            .badge-container {
                justify-content: flex-start;
            }
        }

        @media (max-width: 480px) {
            .glass-card {
                padding: 1rem;
                border-radius: 32px;
            }

            .tech-tag {
                font-size: 0.75rem;
                padding: 0.3rem 1rem;
            }
        }
    </style>
</head>
<body>

    <div class="glass-card">

        <!-- ===== HEADER ===== -->
        <div class="header">
            <div class="identity">
                <h1>Idriss Rayan N.</h1>
                <div class="tagline">
                    <i class="fas fa-code"></i> Développeur polyglotte · Flutter · Backend · Cloud
                </div>
            </div>
            <div class="badge-container">
                <a href="https://www.linkedin.com/in/njutapmvoui-idriss-rayan-37477a28a/" class="badge-glass" target="_blank">
                    <i class="fab fa-linkedin"></i> LinkedIn
                </a>
                <a href="mailto:rayanidriss27@gmail.com" class="badge-glass">
                    <i class="fas fa-envelope"></i> Email
                </a>
                <span class="badge-glass">
                    <i class="fas fa-eye"></i> 1.2k vues
                </span>
            </div>
        </div>

        <!-- ===== BIO ===== -->
        <div class="bio">
            <i class="fas fa-quote-left"></i>
            <strong>Passionate developer</strong> — toujours curieux, en quête perpétuelle d’apprentissage.
            <br />
            <i class="fas fa-laptop-code"></i> Expert en <strong>Flutter &amp; Dart</strong>, maîtrise de <strong>C / C++ / C# / Python / Java</strong>.
            <br />
            <i class="fas fa-database"></i> Bases de données <strong>relationnelles</strong> (MySQL, PostgreSQL) et <strong>BaaS</strong> (Firebase, Supabase).
            <br />
            <i class="fas fa-cloud-upload-alt"></i> Architecte <strong>cloud multi-fournisseur</strong> — AWS · Azure · GCP · Oracle.
            <br />
            <i class="fas fa-rocket"></i> Conception de solutions <strong>solides, efficaces et pérennes</strong> — du mobile au backend.
        </div>

        <!-- ===== TECH STACK ===== -->
        <div class="section-title">
            <i class="fas fa-cogs"></i> Stack technique
        </div>
        <div class="tech-grid">
            <span class="tech-tag"><i class="fab fa-python"></i> Python</span>
            <span class="tech-tag"><i class="fas fa-cuttlefish"></i> C / C++</span>
            <span class="tech-tag"><i class="fas fa-code"></i> C#</span>
            <span class="tech-tag"><i class="fab fa-dart"></i> Dart</span>
            <span class="tech-tag"><i class="fab fa-flutter"></i> Flutter</span>
            <span class="tech-tag"><i class="fab fa-java"></i> Java</span>
            <span class="tech-tag"><i class="fas fa-database"></i> MySQL</span>
            <span class="tech-tag"><i class="fas fa-database"></i> PostgreSQL</span>
            <span class="tech-tag"><i class="fas fa-leaf"></i> MongoDB</span>
            <span class="tech-tag"><i class="fas fa-database"></i> SQLite</span>
            <span class="tech-tag"><i class="fas fa-fire"></i> Firebase</span>
            <span class="tech-tag"><i class="fas fa-cloud"></i> Supabase</span>
            <span class="tech-tag"><i class="fab fa-aws"></i> AWS</span>
            <span class="tech-tag"><i class="fab fa-microsoft"></i> Azure</span>
            <span class="tech-tag"><i class="fab fa-google"></i> GCP</span>
            <span class="tech-tag"><i class="fas fa-cloud"></i> Oracle Cloud</span>
            <span class="tech-tag"><i class="fab fa-node"></i> NodeJS</span>
            <span class="tech-tag"><i class="fab fa-git-alt"></i> Git</span>
            <span class="tech-tag"><i class="fab fa-github"></i> GitHub</span>
            <span class="tech-tag"><i class="fas fa-cube"></i> RayLib</span>
            <span class="tech-tag"><i class="fab fa-figma"></i> Figma</span>
            <span class="tech-tag"><i class="fas fa-flask"></i> Postman</span>
        </div>

        <!-- ===== STATS ===== -->
        <div class="section-title">
            <i class="fas fa-chart-line"></i> Activité GitHub
        </div>
        <div class="stats-row">
            <div class="stat-box">
                <div class="number">127</div>
                <div class="label"><i class="fas fa-code-branch"></i> Dépôts publics</div>
            </div>
            <div class="stat-box">
                <div class="number">486</div>
                <div class="label"><i class="fas fa-fire"></i> Jours de streak</div>
            </div>
        </div>

        <!-- ===== TROPHIES ===== -->
        <div class="section-title">
            <i class="fas fa-trophy"></i> Récompenses
        </div>
        <div class="trophy-row">
            <span class="trophy-item"><i class="fas fa-star"></i> 4x Top Contributor</span>
            <span class="trophy-item"><i class="fas fa-award"></i> Pair Extraordinaire</span>
            <span class="trophy-item"><i class="fas fa-medal"></i> Pulse Maintainer</span>
            <span class="trophy-item"><i class="fas fa-code"></i> 2x Hackathon Winner</span>
        </div>

        <!-- ===== FOOTER ===== -->
        <div class="footer-note">
            <i class="fas fa-crown"></i> Profil généré avec  · Glassmorphisme · 2026
        </div>

    </div>

</body>
</html>
