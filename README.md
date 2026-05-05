<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Taha Mert Dülger | Dijital Portfolyo</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&family=Poppins:wght@700&display=swap" rel="stylesheet">
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #3b82f6;
            --secondary: #8b5cf6;
            --dark: #0f172a;
            --darker: #020617;
            --light: #f8fafc;
            --gray: #94a3b8;
            --glass: rgba(30, 41, 59, 0.7);
            --border: rgba(255, 255, 255, 0.1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--darker);
            color: var(--light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Arka Plan Efekti */
        .bg-glow {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: radial-gradient(circle at 50% -20%, #1e293b, transparent);
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Navbar */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(2, 6, 23, 0.8);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 1px solid var(--border);
        }

        nav .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 70px;
        }

        .logo {
            font-family: 'Poppins', sans-serif;
            font-size: 1.5rem;
            font-weight: 700;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .nav-links {
            display: flex;
            gap: 30px;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--gray);
            font-weight: 500;
            transition: 0.3s;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        /* Hero Section */
        #hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding-top: 70px;
        }

        .hero-content h1 {
            font-family: 'Poppins', sans-serif;
            font-size: 4.5rem;
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 20px;
        }

        .hero-content span {
            color: var(--primary);
        }

        .hero-tagline {
            font-size: 1.5rem;
            color: var(--gray);
            margin-bottom: 40px;
        }

        .btn-group {
            display: flex;
            gap: 20px;
            justify-content: center;
        }

        .btn {
            padding: 14px 32px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: 0.3s;
            display: inline-block;
        }

        .btn-primary {
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white;
            box-shadow: 0 10px 20px rgba(59, 130, 246, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(59, 130, 246, 0.4);
        }

        .btn-outline {
            border: 1px solid var(--border);
            color: white;
        }

        .btn-outline:hover {
            background: rgba(255, 255, 255, 0.05);
        }

        /* Sections General */
        section {
            padding: 100px 0;
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 50px;
            text-align: center;
            font-family: 'Poppins', sans-serif;
        }

        /* Experience Timeline */
        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            width: 2px;
            height: 100%;
            background: var(--border);
            transform: translateX(-50%);
        }

        .timeline-item {
            margin-bottom: 60px;
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .timeline-content {
            width: 45%;
            background: var(--glass);
            padding: 25px;
            border-radius: 15px;
            border: 1px solid var(--border);
            backdrop-filter: blur(10px);
        }

        .timeline-item:nth-child(even) {
            flex-direction: row-reverse;
        }

        .timeline-date {
            color: var(--primary);
            font-weight: 700;
            margin-bottom: 10px;
            display: block;
        }

        .timeline-title {
            font-size: 1.25rem;
            margin-bottom: 5px;
        }

        .timeline-org {
            color: var(--gray);
            font-size: 0.9rem;
            margin-bottom: 15px;
        }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
        }

        .skill-card {
            background: var(--glass);
            padding: 30px;
            border-radius: 20px;
            border: 1px solid var(--border);
            text-align: center;
            transition: 0.3s;
        }

        .skill-card:hover {
            border-color: var(--primary);
            transform: translateY(-5px);
        }

        .skill-card i {
            font-size: 2.5rem;
            margin-bottom: 20px;
            background: linear-gradient(var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Footer */
        footer {
            padding: 50px 0;
            border-top: 1px solid var(--border);
            text-align: center;
            color: var(--gray);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 20px;
        }

        .social-links a {
            color: var(--light);
            font-size: 1.5rem;
            transition: 0.3s;
        }

        .social-links a:hover {
            color: var(--primary);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero-content h1 { font-size: 2.8rem; }
            .timeline::before { left: 0; }
            .timeline-item, .timeline-item:nth-child(even) { flex-direction: column; align-items: flex-start; }
            .timeline-content { width: 100%; margin-left: 20px; }
            .nav-links { display: none; }
        }
    </style>
</head>
<body>

    <div class="bg-glow"></div>

    <nav>
        <div class="container">
            <div class="logo">TM.</div>
            <ul class="nav-links">
                <li><a href="#hero">Giriş</a></li>
                <li><a href="#experience">Deneyim</a></li>
                <li><a href="#skills">Yetenekler</a></li>
                <li><a href="#contact">İletişim</a></li>
            </ul>
        </div>
    </nav>

    <header id="hero">
        <div class="container hero-content">
            <h1>Taha Mert <span>Dülger</span></h1>
            <p class="hero-tagline">Video Editörü | E-Ticaret Uzmanı | Teknoloji Meraklısı</p>
            <div class="btn-group">
                <a href="#contact" class="btn btn-primary">İletişime Geç</a>
                <a href="#experience" class="btn btn-outline">Deneyimleri Gör</a>
            </div>
        </div>
    </header>

    <section id="about">
        <div class="container">
            <h2 class="section-title">Hakkımda</h2>
            <div style="max-width: 800px; margin: 0 auto; text-align: center; color: var(--gray); font-size: 1.1rem;">
                <p>İstinye Üniversitesi Bilgisayar Teknolojisi mezunu bir profesyonel olarak, dijital dünyanın hem yaratıcı hem de teknik tarafında yer alıyorum. Video prodüksiyonundan e-ticaret yönetimine kadar geniş bir yelpazede, modern araçları (AI, Adobe Suite, 3D Tasarım) kullanarak etkileyici sonuçlar üretiyorum.</p>
                <div style="margin-top: 30px; display: flex; justify-content: center; gap: 40px; color: white;">
                    <div><i class="fas fa-map-marker-alt"></i> İstanbul, Kağıthane</div>
                    <div><i class="fas fa-birthday-cake"></i> 22 Yaş</div>
                    <div><i class="fas fa-shield-alt"></i> Askerlik: Muaf</div>
                </div>
            </div>
        </div>
    </section>

    <section id="experience">
        <div class="container">
            <h2 class="section-title">İş Deneyimi</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-content">
                        <span class="timeline-date">Mart 2025 - Eylül 2025</span>
                        <h3 class="timeline-title">Video Editörü</h3>
                        <p class="timeline-org">Kaset Medya</p>
                        <p style="font-size: 0.9rem; color: var(--gray);">Reklam ve röportaj projeleri için profesyonel çekim ve kurgu süreçlerinin yönetilmesi.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-content">
                        <span class="timeline-date">Mart 2025 - Haziran 2025</span>
                        <h3 class="timeline-title">E-ticaret Yetkilisi</h3>
                        <p class="timeline-org">Snowy Ulu Kardeşler Gıda</p>
                        <p style="font-size: 0.9rem; color: var(--gray);">Online satış operasyonlarının uçtan uca yönetimi ve sistem takibi.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-content">
                        <span class="timeline-date">Ekim 2024 - Mart 2025</span>
                        <h3 class="timeline-title">Online Satış Müdürü</h3>
                        <p class="timeline-org">Tunay.co</p>
                        <p style="font-size: 0.9rem; color: var(--gray);">Müşteri memnuniyeti ve ürün satış performans süreçlerinin optimizasyonu.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-content">
                        <span class="timeline-date">Haziran 2014 - Eylül 2020</span>
                        <h3 class="timeline-title">Teknik Servis Teknikeri</h3>
                        <p class="timeline-org">Telkom Teknik / LG Elektronik</p>
                        <p style="font-size: 0.9rem; color: var(--gray);">Donanım onarımı ve teknik bakım süreçlerinde uzmanlık.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="skills">
        <div class="container">
            <h2 class="section-title">Yetenekler</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <i class="fas fa-video"></i>
                    <h3>Video & Kurgu</h3>
                    <p style="color: var(--gray); font-size: 0.9rem;">Adobe Premiere, After Effects</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-cube"></i>
                    <h3>3D & Tasarım</h3>
                    <p style="color: var(--gray); font-size: 0.9rem;">Blender, Cinema 4D</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-shopping-cart"></i>
                    <h3>E-Ticaret</h3>
                    <p style="color: var(--gray); font-size: 0.9rem;">Operasyon Yönetimi, Satış Stratejisi</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-code"></i>
                    <h3>Yazılım</h3>
                    <p style="color: var(--gray); font-size: 0.9rem;">Visual C#, WordPress, AI Araçları</p>
                </div>
            </div>
        </div>
    </section>

    <section id="contact">
        <div class="container" style="text-align: center;">
            <h2 class="section-title">İletişime Geç</h2>
            <p style="color: var(--gray); margin-bottom: 40px;">Yeni projeler veya iş birlikleri için bana ulaşabilirsiniz.</p>
            <div style="display: flex; flex-direction: column; gap: 20px; align-items: center;">
                <a href="mailto:t.mert.d1@gmail.com" class="btn btn-primary"><i class="fas fa-envelope"></i> t.mert.d1@gmail.com</a>
                <a href="tel:+905434124078" class="btn btn-outline"><i class="fas fa-phone"></i> +90 (543) 412 40 78</a>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="social-links">
                <a href="#"><i class="fab fa-linkedin"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
                <a href="#"><i class="fab fa-youtube"></i></a>
            </div>
            <p>&copy; 2026 Taha Mert Dülger. Tüm Hakları Saklıdır.</p>
        </div>
    </footer>

</body>
</html>
