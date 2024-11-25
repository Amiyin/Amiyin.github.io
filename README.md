<!DOCTYPE html>
<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MyWelding Solutions</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        :root {
            --primary-color: #1e3799;
            --secondary-color: #4a69bd;
            --accent-color: #ff6b6b;
            --gradient-start: #1e3799;
            --gradient-end: #4a69bd;
            --light-bg: #f8f9fa;
        }

        /* Navigation */
        nav {
            background: linear-gradient(135deg, var(--gradient-start), var(--gradient-end));
            padding: 1rem;
            position: fixed;
            width: 100%;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav ul {
            display: flex;
            justify-content: center;
            gap: 2rem;
            list-style: none;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 20px;
        }

        nav a:hover {
            background-color: rgba(255,255,255,0.2);
            color: var(--accent-color);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(30,55,153,0.8), rgba(74,105,189,0.8)), url('/api/placeholder/1920/1080') center/cover;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            height: 150px;
            background: linear-gradient(transparent, var(--light-bg));
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 600px;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.3);
        }

        /* Projects Section */
        .projects {
            padding: 4rem 2rem;
            background-color: var(--light-bg);
            position: relative;
        }

        .projects h2 {
            text-align: center;
            margin-bottom: 2rem;
            color: var(--primary-color);
            font-size: 2.5rem;
            position: relative;
            padding-bottom: 1rem;
        }

        .projects h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
        }

        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .project-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.2);
        }

        .project-card img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .project-card:hover img {
            transform: scale(1.05);
        }

        .project-info {
            padding: 1.5rem;
        }

        .project-info h3 {
            color: var(--primary-color);
            margin-bottom: 0.5rem;
            font-size: 1.4rem;
        }

        /* Services Section */
        .services {
            padding: 4rem 2rem;
            background: linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%);
        }

        .services h2 {
            text-align: center;
            margin-bottom: 2rem;
            color: var(--primary-color);
            font-size: 2.5rem;
        }

        .service-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .service-card {
            text-align: center;
            padding: 2rem;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
        }

        .service-card:hover {
            transform: translateY(-5px);
        }

        .service-card h3 {
            color: var(--primary-color);
            margin-bottom: 1rem;
            font-size: 1.4rem;
        }

        /* Contact Section */
        .contact {
            padding: 4rem 2rem;
            background: linear-gradient(135deg, var(--gradient-start), var(--gradient-end));
            color: white;
            text-align: center;
            position: relative;
        }

        .contact h2 {
            margin-bottom: 2rem;
            font-size: 2.5rem;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.3);
        }

        .contact-info {
            max-width: 600px;
            margin: 0 auto;
            background: rgba(255,255,255,0.1);
            padding: 2rem;
            border-radius: 15px;
            backdrop-filter: blur(10px);
        }

        .contact-info p {
            margin: 1rem 0;
            font-size: 1.1rem;
        }

        /* Footer */
        footer {
            background-color: #0a1f44;
            color: white;
            text-align: center;
            padding: 1.5rem;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            nav ul {
                flex-direction: column;
                text-align: center;
                gap: 1rem;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .project-card {
                margin: 1rem;
            }
        }

        /* Animated Gradient Background */
        @keyframes gradientBG {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }

        .gradient-bg {
            background: linear-gradient(-45deg, var(--primary-color), var(--secondary-color), var(--accent-color), #4834d4);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#home">Utama</a></li>
            <li><a href="#projects">Projek</a></li>
            <li><a href="#services">Perkhidmatan</a></li>
            <li><a href="#contact">Hubungi Kami</a></li>
        </ul>
    </nav>

    <section class="hero gradient-bg" id="home">
        <div class="hero-content">
            <h1>MyWelding Solutions</h1>
            <p>Pakar dalam kerja-kerja kimpalan dan fabrikasi logam berkualiti tinggi</p>
        </div>
    </section>

    <section class="projects" id="projects">
        <h2>Projek-Projek Kami</h2>
        <div class="project-grid">
            <div class="project-card">
                <img src="/api/placeholder/400/300" alt="Projek Garaj">
                <div class="project-info">
                    <h3>Pembinaan Garaj</h3>
                    <p>Pembinaan garaj kediaman dengan struktur besi yang kukuh dan kemas</p>
                </div>
            </div>
            <div class="project-card">
                <img src="/api/placeholder/400/300" alt="Projek Pagar">
                <div class="project-info">
                    <h3>Pemasangan Pagar</h3>
                    <p>Rekaan dan pemasangan pagar keselamatan moden</p>
                </div>
            </div>
            <div class="project-card">
                <img src="/api/placeholder/400/300" alt="Projek Struktur">
                <div class="project-info">
                    <h3>Struktur Besi</h3>
                    <p>Pembinaan struktur besi untuk bangunan komersial</p>
                </div>
            </div>
        </div>
    </section>

    <section class="services" id="services">
        <h2>Perkhidmatan</h2>
        <div class="service-grid">
            <div class="service-card">
                <h3>Kimpalan Industri</h3>
                <p>Perkhidmatan kimpalan untuk projek industri berskala besar dengan jaminan kualiti</p>
            </div>
            <div class="service-card">
                <h3>Fabrikasi Logam</h3>
                <p>Pembuatan struktur logam mengikut spesifikasi pelanggan dengan kepakaran tinggi</p>
            </div>
            <div class="service-card">
                <h3>Pemasangan</h3>
                <p>Perkhidmatan pemasangan profesional di tapak projek dengan ketelitian</p>
            </div>
        </div>
    </section>

    <section class="contact" id="contact">
        <h2>Hubungi Kami</h2>
        <div class="contact-info">
            <p>Telefon: 012-345 6789</p>
            <p>Email: info@mywelding.com</p>
            <p>Alamat: Jalan Industri 1, Taman Perindustrian, 81100 Johor Bahru</p>
        </div>
    </section>

    <footer>
        <p>&copy; 2024 MyWelding Solutions. Hak Cipta Terpelihara.</p>
    </footer>
</body>
</html>
