<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AUTOGLOSS | Luxury Carwash & Detailing</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    
    <style>
        /* --- Root Variables & Reset --- */
        :root {
            --primary: #FFC400;
            --dark-bg: #0a0a0a;
            --card-glass: rgba(255, 255, 255, 0.03); /* Dasar Glassmorphism */
            --glass-border: rgba(255, 255, 255, 0.1);
            --white: #ffffff;
            --soft-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            --luxury-shadow: 0 20px 40px rgba(0, 0, 0, 0.8), 0 0 1px rgba(255, 196, 0, 0.1);
        }

        * {
            margin: 0; padding: 0; box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--dark-bg);
            color: var(--white);
            overflow-x: hidden;
            scroll-behavior: smooth;
        }

        /* --- Global Styling --- */
        section { padding: 100px 8%; }
        .btn {
            padding: 14px 30px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
            display: inline-block;
            text-transform: uppercase;
            font-size: 0.85rem;
            letter-spacing: 1px;
        }

        /* --- Navbar (Glassmorphism) --- */
        nav {
            position: fixed; width: 100%; top: 0; z-index: 1000;
            display: flex; justify-content: space-between; align-items: center;
            padding: 20px 8%;
            background: rgba(10, 10, 10, 0.7);
            backdrop-filter: blur(15px); /* Efek Kaca */
            -webkit-backdrop-filter: blur(15px);
            border-bottom: 1px solid var(--glass-border);
            transition: 0.4s;
        }

        .logo { font-family: 'Montserrat'; font-size: 1.6rem; color: var(--primary); letter-spacing: 2px; }

        .nav-links { display: flex; list-style: none; gap: 30px; }
        .nav-links a { 
            color: var(--white); text-decoration: none; font-size: 0.9rem; 
            opacity: 0.7; transition: 0.3s;
        }
        .nav-links a:hover { opacity: 1; color: var(--primary); }

        /* --- Hero Section --- */
        #hero {
            height: 100vh;
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.8)), 
                        url('https://images.unsplash.com/photo-1601362840469-51e4d8d59085?auto=format&fit=crop&w=1920&q=80');
            background-size: cover; background-position: center;
            display: flex; flex-direction: column; justify-content: center; align-items: center;
            text-align: center;
        }

        .hero-box {
            background: rgba(255, 255, 255, 0.01);
            backdrop-filter: blur(5px);
            padding: 40px; border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        h1 { font-family: 'Montserrat'; font-size: 3.5rem; line-height: 1.1; margin-bottom: 15px; }
        h1 span { color: var(--primary); }
        .sub { font-size: 1.1rem; letter-spacing: 4px; color: #ccc; margin-bottom: 35px; }

        .btn-gold { background: var(--primary); color: #000; box-shadow: 0 4px 15px rgba(255, 196, 0, 0.3); }
        .btn-gold:hover { transform: translateY(-3px); box-shadow: 0 8px 25px rgba(255, 196, 0, 0.5); background: #fff; }

        /* --- Glass Cards (Layanan & Pricelist) --- */
        .grid-container {
            display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px;
        }

        .glass-card {
            background: var(--card-glass);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            box-shadow: var(--soft-shadow);
            transition: all 0.4s ease;
        }

        .glass-card:hover {
            transform: translateY(-10px);
            background: rgba(255, 255, 255, 0.06);
            border-color: var(--primary);
            box-shadow: var(--luxury-shadow);
        }

        .glass-card i { font-size: 2.5rem; color: var(--primary); margin-bottom: 20px; }

        /* --- Pricelist Detail --- */
        .price-card {
            background: rgba(20, 20, 20, 0.6);
            backdrop-filter: blur(20px);
            border-radius: 24px;
            overflow: hidden;
            border: 1px solid var(--glass-border);
            box-shadow: var(--soft-shadow);
        }

        .price-head {
            background: linear-gradient(135deg, #1a1a1a, #000);
            padding: 30px; border-bottom: 2px solid var(--primary);
        }

        .price-row {
            display: flex; justify-content: space-between;
            padding: 18px 30px; border-bottom: 1px solid rgba(255,255,255,0.05);
            font-size: 0.95rem;
        }

        .price-row span:last-child { font-weight: 700; color: var(--primary); }

        .badge {
            background: var(--primary); color: #000; font-size: 0.65rem;
            padding: 4px 12px; border-radius: 50px; font-weight: 800; vertical-align: middle;
        }

        /* --- Floating WhatsApp --- */
        .wa-float {
            position: fixed; bottom: 30px; right: 30px;
            background: #25D366; color: #fff;
            width: 60px; height: 60px; border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            font-size: 30px; z-index: 1000;
            box-shadow: 0 10px 25px rgba(37, 211, 102, 0.3);
            transition: 0.3s;
        }
        .wa-float:hover { transform: scale(1.1) rotate(10deg); }

        /* --- Footer --- */
        footer {
            padding: 60px 8%; text-align: center;
            background: #050505; border-top: 1px solid var(--glass-border);
        }

        /* --- Animations --- */
        [data-aos] { opacity: 0; transform: translateY(30px); transition: 1s all ease; }
        .aos-animate { opacity: 1; transform: translateY(0); }

        /* Responsive */
        @media (max-width: 768px) {
            h1 { font-size: 2.2rem; }
            .nav-links { display: none; }
            section { padding: 60px 5%; }
        }
    </style>
</head>
<body>

    <nav id="navbar">
        <div class="logo">AUTOGLOSS<span style="color:white">.</span></div>
        <ul class="nav-links">
            <li><a href="#hero">Home</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#pricing">Pricing</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <section id="hero">
        <div class="hero-box">
            <p class="sub" style="margin-bottom: 10px;">THE ULTIMATE CARE</p>
            <h1>STEAM MOBIL & <br><span>CARWASH PREMIUM</span></h1>
            <p class="sub">BERSIH MAKSIMAL • CEPAT • PROFESIONAL</p>
            <div style="margin-top: 30px;">
                <a href="https://wa.me/628123456789" class="btn btn-gold">Booking Sekarang</a>
                <a href="#pricing" class="btn" style="color: white; border: 1px solid white; margin-left: 15px;">Pricelist</a>
            </div>
        </div>
    </section>

    <section id="services">
        <div style="text-align: center; margin-bottom: 60px;">
            <h2 style="font-family: Montserrat; font-size: 2.5rem;">OUR <span style="color: var(--primary);">SERVICES</span></h2>
        </div>
        <div class="grid-container">
            <div class="glass-card" data-aos>
                <i class="fas fa-water"></i>
                <h3>Snow Wash</h3>
                <p style="font-weight: 300; opacity: 0.7;">Cuci salju dengan shampoo pH balance untuk menjaga kilau cat.</p>
            </div>
            <div class="glass-card" data-aos>
                <i class="fas fa-wind"></i>
                <h3>Interior Detailing</h3>
                <p style="font-weight: 300; opacity: 0.7;">Pembersihan kabin mendalam hingga sela-sela terkecil.</p>
            </div>
            <div class="glass-card" data-aos>
                <i class="fas fa-gem"></i>
                <h3>Wax & Polish</h3>
                <p style="font-weight: 300; opacity: 0.7;">Efek daun talas dan proteksi cat dari sinar UV matahari.</p>
            </div>
        </div>
    </section>

    <section id="pricing" style="background: linear-gradient(to bottom, #0a0a0a, #111);">
        <div style="text-align: center; margin-bottom: 60px;">
            <h2 style="font-family: Montserrat; font-size: 2.5rem;">PRICELIST</h2>
            <p style="opacity: 0.5;">Pilih paket yang sesuai dengan kendaraan Anda</p>
        </div>
        
        <div class="grid-container">
            <div class="price-card" data-aos>
                <div class="price-head">
                    <h3 style="font-family: Montserrat;">SMALL CAR</h3>
                    <p style="font-size: 0.8rem; opacity: 0.6;">Agya, Jazz, Brio, March</p>
                </div>
                <div class="price-row"><span>Steam Eksterior</span> <span>Rp30.000</span></div>
                <div class="price-row"><span>Steam Interior</span> <span>Rp40.000</span></div>
                <div class="price-row" style="background: rgba(255,196,0,0.05);">
                    <span>Steam Full</span> <span>Rp65.000</span>
                </div>
            </div>

            <div class="price-card" data-aos style="border: 1px solid var(--primary);">
                <div class="price-head" style="background: #111;">
                    <span class="badge">BEST VALUE</span>
                    <h3 style="font-family: Montserrat; margin-top: 10px;">MEDIUM CAR</h3>
                    <p style="font-size: 0.8rem; opacity: 0.6;">Avanza, Xpander, Civic</p>
                </div>
                <div class="price-row"><span>Steam Eksterior</span> <span>Rp35.000</span></div>
                <div class="price-row"><span>Steam Interior</span> <span>Rp45.000</span></div>
                <div class="price-row" style="background: rgba(255,196,0,0.1);">
                    <span>Steam Full</span> <span style="font-size: 1.2rem;">Rp75.000</span>
                </div>
            </div>

            <div class="price-card" data-aos>
                <div class="price-head">
                    <span class="badge" style="background: white;">PREMIUM</span>
                    <h3 style="font-family: Montserrat; margin-top: 10px;">LARGE / SUV</h3>
                    <p style="font-size: 0.8rem; opacity: 0.6;">Fortuner, Pajero, Alphard</p>
                </div>
                <div class="price-row"><span>Steam Eksterior</span> <span>Rp40.000</span></div>
                <div class="price-row"><span>Steam Interior</span> <span>Rp55.000</span></div>
                <div class="price-row" style="background: rgba(255,196,0,0.05);">
                    <span>Steam Full</span> <span>Rp90.000</span>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="logo" style="margin-bottom: 15px;">AUTOGLOSS</div>
        <p style="font-size: 0.8rem; opacity: 0.5;">&copy; 2024 Premium Carwash. Built for Excellency.</p>
        <div style="margin-top: 20px; font-size: 1.2rem;">
            <i class="fab fa-instagram" style="margin: 0 10px; cursor: pointer;"></i>
            <i class="fab fa-facebook" style="margin: 0 10px; cursor: pointer;"></i>
        </div>
    </footer>

    <a href="https://wa.me/628123456789" class="wa-float">
        <i class="fab fa-whatsapp"></i>
    </a>

    <script>
        // Simple Scroll Animation Observer
        const observer = new IntersectionObserver((entries) => {
            entries.forEach((entry) => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('aos-animate');
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('[data-aos]').forEach((el) => observer.observe(el));

        // Smooth Navbar Shrink
        window.onscroll = function() {
            const nav = document.getElementById("navbar");
            if (document.body.scrollTop > 80 || document.documentElement.scrollTop > 80) {
                nav.style.padding = "10px 8%";
                nav.style.background = "rgba(0, 0, 0, 0.9)";
            } else {
                nav.style.padding = "20px 8%";
                nav.style.background = "rgba(10, 10, 10, 0.7)";
            }
        };
    </script>
</body>
</html>
