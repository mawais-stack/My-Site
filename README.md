<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LuxeLocks - Premium Hair Oil</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --gold: #D4AF37;
            --gold-light: #F4E4BC;
            --dark: #1A1A1A;
            --cream: #FAF7F2;
            --sage: #8B9A7C;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--cream);
            color: var(--dark);
            overflow-x: hidden;
        }

        h1, h2, h3 {
            font-family: 'Playfair Display', serif;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1.5rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            background: rgba(250, 247, 242, 0.9);
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--dark);
            text-decoration: none;
            letter-spacing: -0.5px;
        }

        .logo span {
            color: var(--gold);
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            font-size: 0.95rem;
            position: relative;
            transition: color 0.3s;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gold);
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .cart-btn {
            background: var(--dark);
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
            border: 2px solid var(--dark);
        }

        .cart-btn:hover {
            background: transparent;
            color: var(--dark);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 0 5%;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            max-width: 600px;
            z-index: 2;
            animation: fadeInUp 1s ease;
        }

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

        .hero-tag {
            display: inline-block;
            background: var(--gold-light);
            color: var(--gold);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
            margin-bottom: 1.5rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .hero h1 {
            font-size: 4rem;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            color: var(--dark);
        }

        .hero p {
            font-size: 1.2rem;
            line-height: 1.6;
            color: #666;
            margin-bottom: 2rem;
            max-width: 500px;
        }

        .cta-group {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .btn-primary {
            background: var(--gold);
            color: white;
            padding: 1rem 2.5rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            display: inline-block;
            transition: all 0.3s;
            border: 2px solid var(--gold);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(212, 175, 55, 0.3);
        }

        .btn-secondary {
            background: transparent;
            color: var(--dark);
            padding: 1rem 2.5rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            display: inline-block;
            border: 2px solid var(--dark);
            transition: all 0.3s;
        }

        .btn-secondary:hover {
            background: var(--dark);
            color: white;
        }

        .hero-image {
            position: absolute;
            right: 5%;
            top: 50%;
            transform: translateY(-50%);
            width: 45%;
            max-width: 600px;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(-50%) translateX(0); }
            50% { transform: translateY(-55%) translateX(10px); }
        }

        .hero-image img {
            width: 100%;
            height: auto;
            filter: drop-shadow(0 30px 60px rgba(0,0,0,0.15));
        }

        /* Features Section */
        .features {
            padding: 6rem 5%;
            background: white;
        }

        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .section-header h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .section-header p {
            color: #666;
            font-size: 1.1rem;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .feature-card {
            text-align: center;
            padding: 2rem;
            border-radius: 20px;
            transition: all 0.3s;
            background: var(--cream);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.08);
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            background: var(--gold-light);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1.5rem;
            font-size: 2rem;
        }

        .feature-card h3 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
        }

        .feature-card p {
            color: #666;
            line-height: 1.6;
        }

        /* Product Section */
        .product-showcase {
            padding: 6rem 5%;
            display: flex;
            align-items: center;
            gap: 5rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .product-images {
            flex: 1;
            position: relative;
        }

        .product-main-img {
            width: 100%;
            border-radius: 20px;
            box-shadow: 0 30px 60px rgba(0,0,0,0.1);
        }

        .product-details {
            flex: 1;
        }

        .product-details h2 {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .price {
            font-size: 2rem;
            color: var(--gold);
            font-weight: 700;
            margin-bottom: 1.5rem;
            font-family: 'Playfair Display', serif;
        }

        .description {
            color: #666;
            line-height: 1.8;
            margin-bottom: 2rem;
            font-size: 1.1rem;
        }

        .ingredients {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            margin-bottom: 2rem;
        }

        .ingredient-tag {
            background: var(--gold-light);
            color: var(--dark);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 500;
        }

        .quantity-selector {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .qty-btn {
            width: 40px;
            height: 40px;
            border: 2px solid #ddd;
            background: white;
            border-radius: 50%;
            cursor: pointer;
            font-size: 1.2rem;
            transition: all 0.3s;
        }

        .qty-btn:hover {
            border-color: var(--gold);
            color: var(--gold);
        }

        .qty-display {
            font-weight: 600;
            font-size: 1.2rem;
            min-width: 40px;
            text-align: center;
        }

        /* Testimonials */
        .testimonials {
            padding: 6rem 5%;
            background: var(--dark);
            color: white;
            text-align: center;
        }

        .testimonials h2 {
            font-size: 2.5rem;
            margin-bottom: 3rem;
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .testimonial-card {
            background: rgba(255,255,255,0.05);
            padding: 2rem;
            border-radius: 20px;
            border: 1px solid rgba(255,255,255,0.1);
            transition: all 0.3s;
        }

        .testimonial-card:hover {
            transform: translateY(-5px);
            background: rgba(255,255,255,0.08);
        }

        .stars {
            color: var(--gold);
            font-size: 1.2rem;
            margin-bottom: 1rem;
        }

        .testimonial-text {
            font-style: italic;
            line-height: 1.6;
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
        }

        .testimonial-author {
            font-weight: 600;
            color: var(--gold-light);
        }

        /* Newsletter */
        .newsletter {
            padding: 6rem 5%;
            text-align: center;
            background: linear-gradient(135deg, var(--gold-light) 0%, var(--cream) 100%);
        }

        .newsletter h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .newsletter p {
            color: #666;
            margin-bottom: 2rem;
            max-width: 500px;
            margin-left: auto;
            margin-right: auto;
        }

        .newsletter-form {
            display: flex;
            gap: 1rem;
            justify-content: center;
            max-width: 500px;
            margin: 0 auto;
            flex-wrap: wrap;
        }

        .newsletter-form input {
            flex: 1;
            min-width: 250px;
            padding: 1rem 1.5rem;
            border: 2px solid var(--dark);
            border-radius: 30px;
            font-size: 1rem;
            outline: none;
            transition: all 0.3s;
        }

        .newsletter-form input:focus {
            border-color: var(--gold);
        }

        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 4rem 5% 2rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 3rem;
            max-width: 1200px;
            margin: 0 auto;
            margin-bottom: 3rem;
        }

        .footer-section h4 {
            font-family: 'Playfair Display', serif;
            margin-bottom: 1.5rem;
            color: var(--gold);
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 0.8rem;
        }

        .footer-section a {
            color: #aaa;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: var(--gold);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #666;
        }

        /* Mobile Menu */
        .mobile-menu {
            display: none;
            flex-direction: column;
            gap: 4px;
            cursor: pointer;
        }

        .mobile-menu span {
            width: 25px;
            height: 2px;
            background: var(--dark);
            transition: all 0.3s;
        }

        @media (max-width: 968px) {
            .hero-image {
                display: none;
            }
            
            .hero-content {
                max-width: 100%;
                text-align: center;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .product-showcase {
                flex-direction: column;
            }
            
            .nav-links {
                display: none;
            }
            
            .mobile-menu {
                display: flex;
            }
        }
    </style>
</head>
<body>

    <!-- Navigation -->
    <nav>
        <a href="#" class="logo">Luxe<span>Locks</span></a>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#benefits">Benefits</a></li>
            <li><a href="#product">Product</a></li>
            <li><a href="#reviews">Reviews</a></li>
        </ul>
        <a href="#product" class="cart-btn">Shop Now — $49</a>
        <div class="mobile-menu">
            <span></span>
            <span></span>
            <span></span>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <span class="hero-tag">New Formula 2026</span>
            <h1>Transform Your Hair with Nature's Golden Elixir</h1>
            <p>Our premium hair oil blend combines ancient Ayurvedic wisdom with modern science. Experience stronger, shinier, and healthier hair in just 30 days.</p>
            <div class="cta-group">
                <a href="#product" class="btn-primary">Shop Now</a>
                <a href="#benefits" class="btn-secondary">Learn More</a>
            </div>
        </div>
        <div class="hero-image">
            <img src="https://images.unsplash.com/photo-1608248597279-f99d160bfbc8?w=600&auto=format&fit=crop&q=80" alt="Premium Hair Oil Bottle">
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="benefits">
        <div class="section-header">
            <h2>Why Choose LuxeLocks?</h2>
            <p>Clinically proven ingredients for visible results</p>
        </div>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">🌿</div>
                <h3>100% Natural</h3>
                <p>Organic cold-pressed oils with no sulfates, parabens, or artificial fragrances</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">✨</div>
                <h3>Instant Shine</h3>
                <p>Lightweight formula absorbs quickly without greasy residue</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">💪</div>
                <h3>Strengthens Roots</h3>
                <p>Reduces hair fall by up to 80% with regular use</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🌙</div>
                <h3>Overnight Repair</h3>
                <p>Deep conditioning treatment while you sleep</p>
            </div>
        </div>
    </section>

    <!-- Product Section -->
    <section class="product-showcase" id="product">
        <div class="product-images">
            <img src="https://images.unsplash.com/photo-1620916566398-39f1143ab7be?w=600&auto=format&fit=crop&q=80" alt="LuxeLocks Hair Oil" class="product-main-img">
        </div>
        <div class="product-details">
            <h2>LuxeLocks Gold Elixir</h2>
            <div class="price">$49.00</div>
            <p class="description">
                Our signature blend features Moroccan Argan Oil, Indian Amla, and Jamaican Black Castor Oil. 
                This lightweight yet potent formula penetrates deep into the hair shaft to repair damage, 
                seal split ends, and stimulate healthy growth.
            </p>
            <div class="ingredients">
                <span class="ingredient-tag">Argan Oil</span>
                <span class="ingredient-tag">Amla Extract</span>
                <span class="ingredient-tag">Castor Oil</span>
                <span class="ingredient-tag">Vitamin E</span>
            </div>
            <div class="quantity-selector">
                <button class="qty-btn" onclick="updateQty(-1)">−</button>
                <span class="qty-display" id="qty">1</span>
                <button class="qty-btn" onclick="updateQty(1)">+</button>
            </div>
            <a href="#" class="btn-primary" style="display: inline-block;" onclick="addToCart()">Add to Cart — $49</a>
        </div>
    </section>

    <!-- Testimonials -->
    <section class="testimonials" id="reviews">
        <h2>Loved by 50,000+ Customers</h2>
        <div class="testimonial-grid">
            <div class="testimonial-card">
                <div class="stars">★★★★★</div>
                <p class="testimonial-text">"I've tried countless hair oils, but this is the only one that actually delivered on its promises. My hair has never been softer!"</p>
                <div class="testimonial-author">— Sarah M.</div>
            </div>
            <div class="testimonial-card">
                <div class="stars">★★★★★</div>
                <p class="testimonial-text">"Finally, an oil that doesn't weigh down my fine hair. The shine is incredible and it smells divine."</p>
                <div class="testimonial-author">— Jessica K.</div>
            </div>
            <div class="testimonial-card">
                <div class="stars">★★★★★</div>
                <p class="testimonial-text">"After 3 weeks of use, my hair fall reduced dramatically. This is now a permanent part of my routine."</p>
                <div class="testimonial-author">— Priya R.</div>
            </div>
        </div>
    </section>

    <!-- Newsletter -->
    <section class="newsletter">
        <h2>Join the LuxeLocks Family</h2>
        <p>Subscribe for exclusive offers, hair care tips, and early access to new products.</p>
        <form class="newsletter-form" onsubmit="event.preventDefault(); alert('Thank you for subscribing!');">
            <input type="email" placeholder="Enter your email" required>
            <button type="submit" class="btn-primary">Subscribe</button>
        </form>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h4>Shop</h4>
                <ul>
                    <li><a href="#">Hair Oil</a></li>
                    <li><a href="#">Hair Mask</a></li>
                    <li><a href="#">Serum</a></li>
                    <li><a href="#">Gift Sets</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h4>Help</h4>
                <ul>
                    <li><a href="#">Shipping Info</a></li>
