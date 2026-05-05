<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Taha Mert Dülger | Portfolyo</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --bg-color: #0d1117;
            --accent: #4285F4;
            --secondary: #6366F1;
            --text: #e6edf3;
            --muted: #8b949e;
            --card: #161b22;
            --border: #30363d;
        }
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Inter', sans-serif; }
        body { background: var(--bg-color); color: var(--text); line-height: 1.6; }
        .container { max-width: 1100px; margin: 0 auto; padding: 40px 20px; }
        
        /* Header */
        header { text-align: center; padding: 80px 0; background: radial-gradient(circle at top, #1a237e 0%, var(--bg-color) 70%); }
        h1 { font-size: 3.5rem; margin-bottom: 10px; background: linear-gradient(90deg, #fff, var(--accent)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .subtitle { font-size: 1.2rem; color: var(--muted); letter-spacing: 2px; text-transform: uppercase; }

        /* Sections */
        section { margin-top: 80px; }
        h2 { font-size: 1.8rem; margin-bottom: 30px; border-left: 4px solid var(--accent); padding-left: 15px; }

        /* Grid Layout */
        .main-grid { display: grid; grid-template-columns: 2fr 1fr; gap: 40px; }

        /* Timeline */
        .timeline { position: relative; padding-left: 30px; border-left: 1px solid var(--border); }
        .timeline-item { margin-bottom: 40px; position: relative; }
        .timeline-item::before { content: ''; position: absolute; left: -36px; top: 8px; width: 10px; height: 10px; background: var(--accent); border-radius: 50%; box-shadow: 0 0 10px var(--accent); }
        .date { font-weight: bold; color: var(--accent); font-size: 0.9rem; }
        .role { font-size: 1.3rem; font-weight: 700; color: #fff; }
        .company { color: var(--secondary); font-weight: 500; margin-bottom: 8px; }
        .desc { font-size: 0.95rem; color: var(--muted); }

        /* Sidebar Cards */
        .card { background: var(--card); border: 1px solid var(--border); padding: 25px; border-radius: 12px; margin-bottom: 25px; }
        .card h3 { margin-bottom: 15px; font-size: 1.1rem; color: var(--accent); }
        .contact-link { display: flex; align-items: center; gap: 12px; margin-bottom: 12px; color: var(--text); text-decoration: none; font-size: 0.9rem; }
        .contact-link i { color: var(--accent); width: 20px; }

        /* Skills Tag */
        .tags { display: flex; wrap: wrap; gap: 8px; }
        .tag { background: #21262d; border: 1px solid var(--border); padding: 5px 12px; border-radius: 6px; font-size: 0.85rem; }

        @media (max-width: 850px) { .main-grid { grid-template-columns: 1fr; } h1 { font-size: 2.5rem; } }
    </style>
</head>
<body>

    <header>
        <h1>Taha Mert Dülger</h1>
        <div class="subtitle">Video Editörü & E-Ticaret Uzmanı</div>
    </header>

    <div class="container">
        <div class="main-grid">
            
            <main>
                <section>
                    <h2><i class="fas fa-briefcase"></i> İş Deneyimi</h2>
                    <div class="timeline">
                        <div class="timeline-item">
                            <div class="date">Mart 2025 - Eylül 2025</div>
                            <div class="role">Video Editörü</div>
                            <div class="company">Kaset Medya</div>
                            <p class="desc">Reklam, röportaj ve benzeri projeler için kamera çekimi ve kurgu süreçlerinin yürütülmesi.</p>
                        </div>
                        <div class="timeline-item">
                            <div class="date">Mart 2025 - Haziran 2025</div>
                            <div class="role">E-ticaret Yetkilisi</div>
                            <div class="company">Snowy Ulu Kardeşler Gıda</div>
                            <p class="desc">Online satış operasyonlarının yönetimi ve takibi.</p>
                        </div>
                        <div class="timeline-item">
                            <div class="date">Ekim 2024 - Mart 2025</div>
                            <div class="role">Online Satış Müdürü</div>
                            <div class="company">Tunay.co</div>
                            <p class="desc">Online satışların yönetilmesi, ürün durum takibi ve müşteri memnuniyeti süreçleri.</p>
                        </div>
                        <div class="timeline-item">
                            <div class="date">Ağustos 2024 - Eylül 2024</div>
