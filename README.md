# Stellar-Harvesting-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stellar Harvesting | Smart Indoor Gardening System</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        :root {
            --primary: #4CAF50;
            --secondary: #2E7D32;
            --accent: #F9A825;
            --light: #F8F9FA;
            --dark: #263238;
        }
        body { line-height: 1.6; color: var(--dark); background: #fff; }
        .container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }

        header { background: white; box-shadow: 0 2px 8px rgba(0,0,0,0.08); position: sticky; top: 0; z-index: 999; }
        .nav-bar { display: flex; justify-content: space-between; align-items: center; padding: 12px 0; }
        .logo-wrap { display: flex; align-items: center; gap: 12px; text-decoration: none; }
        .logo-img { width: 55px; height: 55px; border-radius: 50%; object-fit: cover; }
        .logo-text h1 { font-size: 22px; color: var(--secondary); line-height: 1.2; }
        .logo-text span { font-size: 12px; color: #666; }
        .nav-links { display: flex; gap: 25px; list-style: none; }
        .nav-links a { text-decoration: none; color: var(--dark); font-weight: 500; transition: 0.3s; }
        .nav-links a:hover { color: var(--primary); }
        .menu-btn { display: none; font-size: 28px; cursor: pointer; color: var(--secondary); }

        .hero { background: linear-gradient(135deg, #E8F5E9, #C8E6C9); padding: 60px 20px; text-align: center; }
        .hero-img { max-width: 450px; width: 100%; margin-bottom: 25px; border-radius: 12px; box-shadow: 0 6px 20px rgba(0,0,0,0.15); }
        .hero h2 { font-size: 32px; color: var(--secondary); margin-bottom: 12px; }
        .hero p.tagline { font-size: 20px; color: var(--accent); font-weight: 600; margin-bottom: 15px; }
        .hero p { font-size: 17px; max-width: 700px; margin: 0 auto 25px; color: #444; }
        .btn { display: inline-block; background: var(--primary); color: white; padding: 12px 28px; border-radius: 6px; text-decoration: none; font-weight: 600; transition: 0.3s; }
        .btn:hover { background: var(--secondary); transform: translateY(-2px); }

        section { padding: 60px 20px; }
        h2 { text-align: center; font-size: 28px; color: var(--secondary); margin-bottom: 40px; }
        h3 { color: var(--secondary); margin-bottom: 15px; font-size: 20px; }

        .product-overview { background: var(--light); }
        .product-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 50px; align-items: center; }
        .product-main-img { width: 100%; border-radius: 12px; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }

        .features-grid { display: flex; flex-direction: column; gap: 50px; margin-top: 40px; }
        .feature-row { display: grid; grid-template-columns: 1fr 1fr; gap: 40px; align-items: center; }
        .feature-row:nth-child(even) { direction: rtl; }
        .feature-row:nth-child(even) > * { direction: ltr; }
        .feature-img { width: 100%; border-radius: 10px; box-shadow: 0 3px 12px rgba(0,0,0,0.08); }
        .feature-content h4 { font-size: 20px; color: var(--secondary); margin-bottom: 8px; }
        .feature-content h4 span { color: var(--accent); font-size: 18px; margin-right: 8px; }
        .feature-content p.subtitle { font-weight: 500; color: #555; margin-bottom: 10px; font-style: italic; }

        .chart-section { background: var(--light); }
        .chart-container { max-width: 900px; margin: 0 auto; text-align: center; }
        .chart-img { width: 100%; border-radius: 12px; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }

        .mv-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 30px; max-width: 900px; margin: 0 auto; }
        .mv-box { background: linear-gradient(135deg, #E8F5E9, #C8E6C9); padding: 30px; border-radius: 10px; text-align: left; }
        .mv-box h3 { color: var(--secondary); text-align: center; margin-bottom: 20px; }

        .contact-box { max-width: 600px; margin: 0 auto; background: var(--light); padding: 30px; border-radius: 10px; text-align: center; }
        .contact-box p { margin: 12px 0; font-size: 17px; }

        footer { background: var(--dark); color: white; text-align: center; padding: 30px 20px; font-size: 15px; }
        footer p { margin-bottom: 8px; }

        @media(max-width:768px) {
            .nav-links { position: absolute; top: 70px; left: 0; right: 0; background: white; flex-direction: column; padding: 20px; gap: 15px; display: none; box-shadow: 0 5px 10px rgba(0,0,0,0.05); }
            .nav-links.active { display: flex; }
            .menu-btn { display: block; }
            .product-grid, .feature-row, .mv-grid { grid-template-columns: 1fr; }
            .feature-row:nth-child(even) { direction: ltr; }
        }
    </style>
</head>
<body>

<header>
    <div class="container nav-bar">
        <a href="#" class="logo-wrap">
            <img src="https://imgur.com/a/FS1ueBX" alt="Stellar Harvesting Logo" class="logo-img">
            <div class="logo-text">
                <h1>Stellar Harvesting</h1>
                <span>Smart Indoor Gardening</span>
            </div>
        </a>
        <div class="menu-btn" onclick="toggleMenu()">☰</div>
        <ul class="nav-links" id="navMenu">
            <li><a href="#home">Home</a></li>
            <li><a href="#product">Product</a></li>
            <li><a href="#features">Features</a></li>
            <li><a href="#chart">Our Team</a></li>
            <li><a href="#mission">Mission & Vision</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </div>
</header>

<section class="hero" id="home">
    <div class="container">
        <img src="https://imgur.com/a/FxAerXc" alt="Stellar Harvesting Smart Indoor Gardening System" class="hero-img">
        <h2>Stellar Harvesting</h2>
        <p class="tagline">Smart Farming. Sustainable Living.</p>
        <p>Grow fresh vegetables and herbs at home with Stellar Harvesting — a smart indoor gardening system designed to make plant care easier, more convenient, and eco-friendly.</p>
        <a href="#product" class="btn">Learn More</a>
    </div>
</section>

<section class="product-overview" id="product">
    <div class="container">
        <h2>🌿 Grow Fresh at Home, the Smart Way</h2>
        <div class="product-grid">
            <div>
                <img src=https://imgur.com/a/Akgtjrbalt="Smart Indoor Gardening System" class="product-main-img">
            </div>
            <div>
                <h3>Your Personal Indoor Garden</h3>
                <p>Experience the joy of growing your own fresh vegetables and herbs year-round — no garden, no soil, no weather worries. Our smart system brings nature into your home, kitchen, or office.</p>
                <p style="margin-top:15px;"><strong>Perfect for families, health lovers, and anyone who wants fresh produce just steps away from their table.</strong></p>
                <p style="margin-top:10px; color: var(--secondary); font-weight:500;">✨ Fresh. Organic. Sustainable. Always in season.</p>
            </div>
        </div>
    </div>
</section>

<section id="features">
    <div class="container">
        <h2>⭐ Special Features</h2>
        <p style="text-align:center; max-width:700px; margin:0 auto; font-size:17px;">Everything you need for thriving plants — built right in.</p>

        <div class="features-grid">
            <div class="feature-row">
                <div>
                    <img src="https://imgur.com/a/AGK7mli" alt="Solar-Powered System" class="feature-img">
                </div>
                <div class="feature-content">
                    <h4><span>01</span> Solar-Powered System</h4>
                    <p class="subtitle">Clean and Renewable Energy</p>
                    <p>The solar panel collects sunlight and converts it into electricity to help power the system, reducing reliance on regular electricity. Eco-friendly and cost-effective!</p>
                </div>
            </div>

            <div class="feature-row">
                <div>
                    <img src="https://imgur.com/a/btmXWKY" alt="Automatic Watering" class="feature-img">
                </div>
                <div class="feature-content">
                    <h4><span>02</span> Automatic Watering</h4>
                    <p class="subtitle">Effortless Plant Care</p>
                    <p>The system delivers water to plants when needed, helping maintain perfect moisture levels. No more guessing or daily watering — your plants stay hydrated automatically.</p>
                </div>
            </div>

            <div class="feature-row">
                <div>
                    <img src="https://imgur.com/a/gHiVKL8" alt="One Week Backup Battery" class="feature-img">
                </div>
                <div class="feature-content">
                    <h4><span>03</span> One Week Backup Battery</h4>
                    <p class="subtitle">Reliable Power, Even Without Sunlight</p>
                    <p>Equipped with a 12V 50Ah LiFePO₄ rechargeable battery that stores solar energy. Provides up to <strong>7 days of backup power</strong>, depending on usage and sunlight availability.</p>
                </div>
            </div>

            <div class="feature-row">
                <div>
                    <img src="https://imgur.com/a/06MAIZG" alt="Multi-Level Growing Space" class="feature-img">
                </div>
                <div class="feature-content">
                    <h4><span>04</span> Multi-Level Growing Space</h4>
                    <p class="subtitle">More Plants, Less Space</p>
                    <p>Stacked growing trays let you grow different vegetables and herbs in one compact cabinet. Perfect for apartments, kitchens, and homes with limited outdoor space.</p>
                </div>
            </div>

            <div class="feature-row">
                <div>
                    <img src="https://imgur.com/a/HWLaVpP" alt="Indoor Grow Lighting" class="feature-img">
                </div>
                <div class="feature-content">
                    <h4><span>05</span> Indoor Grow Lighting</h4>
                    <p class="subtitle">Growing Beyond the Outdoors</p>
                    <p>Built-in grow lights provide the perfect light spectrum for photosynthesis. Your plants grow strong and healthy even in rooms with little or no natural sunlight.</p>
                </div>
            </div>

            <div class="feature-row">
                <div>
                    <img src="https://imgur.com/a/4nPtsN9" alt="Water Reservoir System" class="feature-img">
                </div>
                <div class="feature-content">
                    <h4><span>06</span> Water Reservoir System</h4>
                    <p class="subtitle">Efficient Water Management</p>
                    <p>A built-in reservoir stores water while a pump circulates it to your plants. Recirculation minimizes waste — it's water-wise gardening at its best!</p>
                </div>
            </div>

            <div class="feature-row">
                <div>
                    <img src="https://imgur.com/a/0CRG51w" alt="Protective Glass Enclosure" class="feature-img">
                </div>
                <div class="feature-content">
                    <h4><span>07</span> Protective Glass Enclosure</h4>
                    <p class="subtitle">Modern, Organized & Safe</p>
                    <p>The transparent glass enclosure lets you watch your plants grow while keeping the area neat and protecting your greens from pets, dust, and household disturbances.</p>
                </div>
            </div>
        </div>
    </div>
</section>

<section class="chart-section" id="chart">
    <div class="container">
        <h2>📊 Meet Our Team</h2>
        <div class="chart-container">
            <img src="https://imgur.com/a/OYkUrqe" alt="Stellar Harvesting Organizational Chart" class="chart-img">
            <p style="margin-top:15px; color:#666; font-size:15px;">Our dedicated team working together to bring smart gardening to every home.</p>
        </div>
    </div>
</section>

<section id="mission">
    <div class="container">
        <h2>🎯 Our Mission & Vision</h2>
        <div class="mv-grid">
            <div class="mv-box">
                <h3>📌 Business Mission</h3>
                <p>To provide smart, solar-powered indoor gardening systems that help people grow fresh produce conveniently, reduce environmental impact, and encourage sustainable living through innovative technology.</p>
            </div>
            <div class="mv-box">
                <h3>🔭 Business Vision</h3>
                <p>To become a leading provider of innovative and sustainable indoor gardening solutions that make fresh, healthy food accessible to every home while promoting a greener future.</p>
            </div>
        </div>
    </div>
</section>

<section id="contact">
    <div class="container">
        <h2>📞 Contact Us</h2>
        <div class="contact-box">
            <p><strong>📱 Phone:</strong> +63 968 791 4490</p>
            <p><strong>📧 Email:</strong> stellarharvesting@gmail.com</p>
            <p><strong>📘 Facebook:</strong> Stellar Harvesting — La Union</p>
            <p><strong>📍 Location:</strong> La Union, Ilocos Region, Philippines</p>
            <p><strong>🕒 Business Hours:</strong> Monday – Saturday, 8:00 AM – 6:00 PM</p>
        </div>
    </div>
</section>

<footer>
    <p><strong>© 2026 Stellar Harvesting. All rights reserved.</strong></p>
    <p>Smart Indoor Gardening System | Fresh. Organic. Sustainable.</p>
</footer>

<script>
    function toggleMenu() {
        var menu = document.getElementById("navMenu");
        menu.classList.toggle("active");
    }
</script>

</body>
</html>
