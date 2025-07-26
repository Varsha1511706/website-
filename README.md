<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Explore Udupi - Discover Karnataka's Coastal Paradise</title>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        /* Custom CSS Styles */
        :root {
            --primary-color: #1e6091;
            --secondary-color: #ff9e1b;
            --accent-color: #e86a33;
            --light-color: #f8f9fa;
            --dark-color: #1a1a1a;
            --transition: all 0.5s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            color: var(--dark-color);
            overflow-x: hidden;
        }
        
        h1, h2, h3, h4, h5, h6 {
            font-family: 'Playfair Display', serif;
            font-weight: 700;
        }
        
        /* Navbar Styles */
        .navbar {
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
            transition: var(--transition);
        }
        
        .navbar.scrolled {
            padding: 0.5rem 0;
            background-color: rgba(255, 255, 255, 0.98);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }
        
        .nav-link {
            position: relative;
            margin: 0 1rem;
            padding: 0.5rem 0;
            font-weight: 500;
            color: var(--dark-color);
            transition: var(--transition);
        }
        
        .nav-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--accent-color);
            transition: var(--transition);
        }
        
        .nav-link:hover::after,
        .nav-link.active::after {
            width: 100%;
        }
        
        .nav-link:hover,
        .nav-link.active {
            color: var(--accent-color);
        }
        
        /* Hero Section Styles */
        .hero {
            position: relative;
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.6)), url('https://karnatakatourism.org/wp-content/uploads/2020/06/Kapu-Lighthouse-min.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .hero-content {
            text-align: center;
            color: white;
            max-width: 800px;
            padding: 0 2rem;
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 1s ease forwards 0.5s;
        }
        
        .hero-title {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
        }
        
        .hero-subtitle {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.5);
        }
        
        .btn {
            padding: 0.75rem 2rem;
            border-radius: 50px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: var(--transition);
            display: inline-block;
        }
        
        .btn-primary {
            background-color: var(--accent-color);
            color: white;
            border: 2px solid var(--accent-color);
        }
        
        .btn-primary:hover {
            background-color: transparent;
            color: white;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }
        
        .btn-outline {
            background-color: transparent;
            color: white;
            border: 2px solid white;
            margin-left: 1rem;
        }
        
        .btn-outline:hover {
            background-color: white;
            color: var(--accent-color);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }
        
        /* Highlights Section */
        .section {
            padding: 6rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            display: inline-block;
            position: relative;
            z-index: 1;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background-color: var(--accent-color);
        }
        
        .highlight-card {
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: var(--transition);
            margin-bottom: 2rem;
        }
        
        .highlight-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }
        
        .highlight-img {
            height: 250px;
            overflow: hidden;
        }
        
        .highlight-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .highlight-card:hover .highlight-img img {
            transform: scale(1.1);
        }
        
        .highlight-content {
            padding: 1.5rem;
        }
        
        .highlight-title {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            color: var(--primary-color);
        }
        
        /* Destinations Section */
        .destinations {
            background-color: #f8f9fa;
        }
        
        .tab-container {
            max-width: 1000px;
            margin: 0 auto;
        }
        
        .tabs {
            display: flex;
            justify-content: center;
            margin-bottom: 2rem;
            border-bottom: 1px solid #dee2e6;
        }
        
        .tab {
            padding: 1rem 2rem;
            font-weight: 500;
            cursor: pointer;
            transition: var(--transition);
            border-bottom: 2px solid transparent;
        }
        
        .tab.active {
            color: var(--accent-color);
            border-bottom: 2px solid var(--accent-color);
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
            animation: fadeIn 0.5s ease forwards;
        }
        
        .destination-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .destination-card {
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: var(--transition);
        }
        
        .destination-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }
        
        .destination-img {
            height: 250px;
            overflow: hidden;
        }
        
        .destination-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .destination-card:hover .destination-img img {
            transform: scale(1.1);
        }
        
        .destination-content {
            padding: 1.5rem;
        }
        
        .destination-title {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: var(--primary-color);
        }
        
        /* Food & Culture Section */
        .food-culture {
            background: linear-gradient(rgba(255, 255, 255, 0.9), rgba(255, 255, 255, 0.9)), url('https://www.indianhealthyrecipes.com/wp-content/uploads/2021/06/masala-dosa.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
        }
        
        .food-card, .culture-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: var(--transition);
            margin-bottom: 2rem;
            display: flex;
            flex-direction: column;
            height: 100%;
        }
        
        .food-card:hover, .culture-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }
        
        .food-img, .culture-img {
            height: 250px;
            overflow: hidden;
        }
        
        .food-img img, .culture-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .food-card:hover .food-img img, .culture-card:hover .culture-img img {
            transform: scale(1.1);
        }
        
        .food-content, .culture-content {
            padding: 1.5rem;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }
        
        .food-title, .culture-title {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: var(--primary-color);
        }
        
        /* Gallery Section */
        .gallery {
            background-color: #f8f9fa;
        }
        
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1rem;
        }
        
        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            cursor: pointer;
            height: 250px;
        }
        
        .gallery-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .gallery-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: var(--transition);
        }
        
        .gallery-item:hover .gallery-overlay {
            opacity: 1;
        }
        
        .gallery-item:hover .gallery-img {
            transform: scale(1.1);
        }
        
        .lightbox {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            opacity: 0;
            pointer-events: none;
            transition: var(--transition);
            flex-direction: column;
            padding: 20px;
        }
        
        .lightbox.active {
            opacity: 1;
            pointer-events: auto;
        }
        
        .lightbox-img {
            max-width: 90%;
            max-height: 80%;
            border-radius: 5px;
            box-shadow: 0 0 30px rgba(0, 0, 0, 0.5);
        }
        
        .lightbox-caption {
            color: white;
            text-align: center;
            margin-top: 1rem;
            max-width: 80%;
            font-size: 1rem;
            line-height: 1.5;
        }
        
        .lightbox-close {
            position: absolute;
            top: 20px;
            right: 30px;
            color: white;
            font-size: 2.5rem;
            cursor: pointer;
            line-height: 1;
        }
        
        /* Contact Section */
        .contact {
            background: linear-gradient(rgba(255, 255, 255, 0.9), rgba(255, 255, 255, 0.9)), url('https://karnatakatourism.org/wp-content/uploads/2020/05/Malpe-Beach-800x450-1.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
        }
        
        .contact-card {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            padding: 2rem;
            transition: var(--transition);
        }
        
        .contact-info {
            margin-bottom: 2rem;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
        }
        
        .contact-icon {
            width: 40px;
            height: 40px;
            background-color: var(--accent-color);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            margin-right: 1rem;
        }
        
        .form-control {
            width: 100%;
            padding: 0.75rem;
            margin-bottom: 1rem;
            border: 1px solid #dee2e6;
            border-radius: 5px;
            transition: var(--transition);
        }
        
        .form-control:focus {
            outline: none;
            border-color: var(--accent-color);
            box-shadow: 0 0 0 0.2rem rgba(232, 106, 51, 0.25);
        }
        
        /* Map */
        .map-container {
            height: 400px;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }
        
        /* Footer */
        .footer {
            background-color: var(--primary-color);
            color: white;
            padding: 3rem 0 2rem;
        }
        
        .footer-logo {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 1rem;
        }
        
        .footer-links h3 {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
            position: relative;
        }
        
        .footer-links h3::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 50px;
            height: 2px;
            background-color: var(--accent-color);
        }
        
        .footer-links ul {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 0.75rem;
        }
        
        .footer-links a {
            color: #ccc;
            transition: var(--transition);
        }
        
        .footer-links a:hover {
            color: white;
            padding-left: 5px;
        }
        
        .social-links {
            display: flex;
            margin-top: 1rem;
        }
        
        .social-link {
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            margin-right: 1rem;
            transition: var(--transition);
        }
        
        .social-link:hover {
            background-color: var(--accent-color);
            transform: translateY(-3px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 2rem;
            margin-top: 3rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        /* Animations */
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
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
        
        .fade-in {
            opacity: 0;
            animation: fadeIn 1s ease forwards;
        }
        
        .fade-in-up {
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 1s ease forwards;
        }
        
        /* Responsive Styles */
        @media (max-width: 991px) {
            .hero-title {
                font-size: 2.8rem;
            }
            
            .hero-subtitle {
                font-size: 1.2rem;
            }
            
            .section {
                padding: 4rem 0;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
        }
        
        @media (max-width: 767px) {
            .hero-title {
                font-size: 2.2rem;
            }
            
            .btn {
                padding: 0.6rem 1.5rem;
            }
            
            .tabs {
                flex-wrap: wrap;
            }
            
            .tab {
                padding: 0.75rem 1rem;
                font-size: 0.9rem;
            }
            
            .destination-grid,
            .gallery-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
        
        @media (max-width: 575px) {
            .hero-title {
                font-size: 2rem;
            }
            
            .hero-subtitle {
                font-size: 1rem;
            }
            
            .section-title h2 {
                font-size: 1.8rem;
            }
            
            .destination-grid,
            .gallery-grid {
                grid-template-columns: 1fr;
            }
        }
        
        /* Additional styles for scroll animations */
        .animate-on-scroll {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 1s ease, transform 1s ease;
        }
        
        .animate-on-scroll.animated {
            opacity: 1;
            transform: translateY(0);
        }

        /* Mobile navigation */
        .mobile-menu-btn {
            display: none;
            cursor: pointer;
            z-index: 101;
        }
        
        .mobile-menu-icon {
            width: 25px;
            height: 3px;
            background-color: var(--dark-color);
            position: relative;
            transition: var(--transition);
        }
        
        .mobile-menu-icon::before,
        .mobile-menu-icon::after {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background-color: var(--dark-color);
            transition: var(--transition);
        }
        
        .mobile-menu-icon::before {
            transform: translateY(-8px);
        }
        
        .mobile-menu-icon::after {
            transform: translateY(8px);
        }
        
        .mobile-menu-btn.active .mobile-menu-icon {
            background-color: transparent;
        }
        
        .mobile-menu-btn.active .mobile-menu-icon::before {
            transform: rotate(45deg);
        }
        
        .mobile-menu-btn.active .mobile-menu-icon::after {
            transform: rotate(-45deg);
        }
        
        @media (max-width: 991px) {
            .nav-links {
                position: fixed;
                top: 0;
                right: -100%;
                width: 250px;
                height: 100%;
                background-color: white;
                flex-direction: column;
                padding: 80px 30px 30px;
                transition: var(--transition);
                box-shadow: -5px 0 15px rgba(0, 0, 0, 0.1);
                z-index: 100;
            }
            
            .nav-links.active {
                right: 0;
            }
            
            .nav-link {
                margin: 0.5rem 0;
                padding: 0.5rem 0;
                width: 100%;
                text-align: left;
            }
            
            .mobile-menu-btn {
                display: block;
                position: relative;
                z-index: 102;
            }
            
            .overlay {
                position: fixed;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                background-color: rgba(0, 0, 0, 0.5);
                z-index: 99;
                opacity: 0;
                pointer-events: none;
                transition: var(--transition);
            }
            
            .overlay.active {
                opacity: 1;
                pointer-events: auto;
            }
        }
    </style>
</head>
<body>
    <!-- Navbar -->
    <nav class="navbar py-3">
        <div class="container mx-auto flex justify-between items-center px-4">
            <a href="#home" class="text-2xl font-bold text-primary-color">
                <span class="text-accent-color">Explore</span> Udupi
            </a>
            
            <div class="mobile-menu-btn">
                <div class="mobile-menu-icon"></div>
            </div>
            
            <div class="overlay"></div>
            
            <div class="nav-links flex">
                <a href="#home" class="nav-link active">Home</a>
                <a href="#destinations" class="nav-link">Destinations</a>
                <a href="#food-culture" class="nav-link">Food & Culture</a>
                <a href="#gallery" class="nav-link">Gallery</a>
                <a href="#contact" class="nav-link">Contact</a>
            </div>
        </div>
    </nav>
    
    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1 class="hero-title">Discover the Soul of Coastal Karnataka</h1>
            <p class="hero-subtitle">Immerse yourself in a land of divine temples, sun-kissed beaches, unique geological wonders, and a culinary heritage that delights the senses.</p>
            <div class="hero-buttons">
                <a href="#destinations" class="btn btn-primary">Explore Now</a>
                <a href="#contact" class="btn btn-outline">Contact Us</a>
            </div>
        </div>
    </section>
    
    <!-- Highlights Section -->
    <section class="section highlights">
        <div class="container mx-auto px-4">
            <div class="section-title animate-on-scroll">
                <h2>Why Visit Udupi?</h2>
                <p class="text-center text-gray-600 mt-4">Discover the treasures that make this coastal paradise unforgettable.</p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                <div class="highlight-card animate-on-scroll">
                    <div class="highlight-img">
                        <img src="https://static.toiimg.com/thumb/msid-47157527,width=1200,height=900/47157527.jpg" alt="Sri Krishna Temple">
                    </div>
                    <div class="highlight-content">
                        <h3 class="highlight-title">Spiritual Sanctuaries</h3>
                        <p class="text-gray-600">Home to the famous 13th-century Sri Krishna Matha, Udupi is a revered pilgrimage center, offering peace and a deep sense of spiritual history.
</p>
                    </div>
                </div>
                
                <div class="highlight-card animate-on-scroll" style="animation-delay: 0.2s;">
                    <div class="highlight-img">
                        <img src="https://thrillingtravel.in/wp-content/uploads/2021/10/Malpe-beach-karnataka.jpg" alt="Malpe Beach">
                    </div>
                    <div class="highlight-content">
                        <h3 class="highlight-title">Pristine Beaches</h3>
                        <p class="text-gray-600">Unwind on the golden sands of Malpe Beach, witness stunning sunsets from the Kapu lighthouse, and explore the unique shores of St. Mary's Island.
</p>
                    </div>
                </div>
                
                <div class="highlight-card animate-on-scroll" style="animation-delay: 0.4s;">
                    <div class="highlight-img">
                        <img src="https://www.indianhealthyrecipes.com/wp-content/uploads/2021/06/masala-dosa.jpg" alt="Udupi Cuisine">
                    </div>
                    <div class="highlight-content">
                        <h3 class="highlight-title">Legendary Cuisine</h3>
                        <p class="text-gray-600">Savor the authentic flavors of world-famous Udupi cuisine, a vegetarian's paradise known for its sattvic principles and iconic dishes like the Masala Dosa.
</p>
                    </div>
                </div>
                
                <div class="highlight-card animate-on-scroll" style="animation-delay: 0.6s;">
                    <div class="highlight-img">
                        <img src="https://karnatakatourism.org/wp-content/uploads/2020/05/Yakshagana-1.jpg" alt="Yakshagana">
                    </div>
                    <div class="highlight-content">
                        <h3 class="highlight-title">Vibrant Culture</h3>
                        <p class="text-gray-600">Witness the dramatic storytelling of Yakshagana and the ancient, powerful rituals of Bhuta Kola, unique folk traditions that bring the region's mythology to life.
</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Destinations Section -->
    <section id="destinations" class="section destinations">
        <div class="container mx-auto px-4">
            <div class="section-title animate-on-scroll">
                <h2>Explore Destinations</h2>
                <p class="text-center text-gray-600 mt-4">Discover the must-visit places in and around Udupi</p>
            </div>
            
            <div class="tab-container">
                <div class="tabs animate-on-scroll">
                    <div class="tab active" data-tab="temples">Temples</div>
                    <div class="tab" data-tab="beaches">Beaches</div>
                    <div class="tab" data-tab="landmarks">Landmarks</div>
                </div>
                
                <div class="tab-content active" id="temples-content">
                    <div class="destination-grid">
                        <div class="destination-card animate-on-scroll">
                            <div class="destination-img">
                                <img src="https://thrillingtravel.in/wp-content/uploads/2021/05/Entrance-Krishna-temple-udupi.jpg" alt="Sri Krishna Temple">
                            </div>
                            <div class="destination-content">
                                <h3 class="destination-title">Sri Krishna Temple</h3>
                                <p class="text-gray-600 mb-3">Founded by the 13th-century saint Madhvacharya, this temple is famous for the Kanakana Kindi, a window through which the idol of Lord Krishna is said to have miraculously turned to give darshan to his devotee, Kanakadasa.
</p>
                                <p class="text-sm text-gray-500"><i class="fas fa-map-marker-alt mr-1"></i> Car Street, Udupi</p>
                            </div>
                        </div>
                        
                        <div class="destination-card animate-on-scroll" style="animation-delay: 0.2s;">
                            <div class="destination-img">
                                <img src="https://live.staticflickr.com/3738/9071517367_9ba322768c_b.jpg" alt="Anantheshwara Temple">
                            </div>
                            <div class="destination-content">
                                <h3 class="destination-title">Anantheshwara Temple</h3>
                                <p class="text-gray-600 mb-3">Considered one of the oldest temples in the region, this sanctuary is dedicated to Lord Shiva and is believed to be the place where Saint Madhvacharya spiritually departed to the Himalayas.
</p>
                                <p class="text-sm text-gray-500"><i class="fas fa-map-marker-alt mr-1"></i> Car Street, Udupi</p>
                            </div>
                        </div>
                        
                        <div class="destination-card animate-on-scroll" style="animation-delay: 0.4s;">
                            <div class="destination-img">
                                <img src="https://thrillingtravel.in/wp-content/uploads/2021/05/Chariot-udupi-krishna-matha.jpg" alt="Chandramouleshwara Temple">
                            </div>
                            <div class="destination-content">
                                <h3 class="destination-title">Chandramouleshwara Temple</h3>
                                <p class="text-gray-600 mb-3">Adjacent to the Anantheshwara Temple, this ancient Shiva temple is said to be where the Moon God performed penance, lending the city its ancient name, Rajathapeetha Pura (Silver Seat).
</p>
                                <p class="text-sm text-gray-500"><i class="fas fa-map-marker-alt mr-1"></i> Car Street, Udupi</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="tab-content" id="beaches-content">
                    <div class="destination-grid">
                        <div class="destination-card">
                            <div class="destination-img">
                                <img src="https://thrillingtravel.in/wp-content/uploads/2021/10/Arabian-sea-malpe-beach-karnataka.jpg" alt="Malpe Beach">
                            </div>
                            <div class="destination-content">
                                <h3 class="destination-title">Malpe Beach</h3>
                                <p class="text-gray-600 mb-3">A bustling hub of activity with golden sands and swaying palms, Malpe Beach offers thrilling water sports like parasailing and jet skiing, and is the launching point for ferries to St. Mary's Island.
</p>
                                <p class="text-sm text-gray-500"><i class="fas fa-map-marker-alt mr-1"></i> 6km from Udupi</p>
                            </div>
                        </div>
                        
                        <div class="destination-card">
                            <div class="destination-img">
                                <img src="https://karnatakatourism.org/wp-content/uploads/2020/06/Kapu-Beach-Lighthouse-min.jpeg" alt="Kapu Beach">
                            </div>
                            <div class="destination-content">
                                <h3 class="destination-title">Kapu Beach</h3>
                                <p class="text-gray-600 mb-3">Renowned for its historic 100-foot lighthouse built in 1901. Visitors can climb to the top for a spectacular panoramic view of the Arabian Sea, especially during sunset.
</p>
                                <p class="text-sm text-gray-500"><i class="fas fa-map-marker-alt mr-1"></i> 12km from Udupi</p>
                            </div>
                        </div>
                        
                        <div class="destination-card">
                            <div class="destination-img">
                                <img src="https://www.storiesbysoumya.com/wp-content/uploads/2021/03/St-Marys-Island-Malpe-Udupi.jpg" alt="St. Mary's Island">
                            </div>
                            <div class="destination-content">
                                <h3 class="destination-title">St. Mary's Island</h3>
                                <p class="text-gray-600 mb-3">A National Geological Monument, this island is famed for its unique hexagonal basaltic rock formations, created from volcanic activity millions of years ago when Madagascar was still joined to India.
</p>
                                <p class="text-sm text-gray-500"><i class="fas fa-map-marker-alt mr-1"></i> Off the coast of Malpe</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="tab-content" id="landmarks-content">
                    <div class="destination-grid">
                        <div class="destination-card">
                            <div class="destination-img">
                                <img src="https://karnatakatourism.org/wp-content/uploads/2020/06/Kapu-Lighthouse-min.jpg" alt="Kaup Lighthouse">
                            </div>
                            <div class="destination-content">
                                <h3 class="destination-title">Kaup Lighthouse</h3>
                                <p class="text-gray-600 mb-3">This iconic black-and-white striped lighthouse has guided sailors for over a century. A climb up its winding staircase rewards you with one of the most breathtaking coastal views in Karnataka, typically open to visitors in the late afternoon.
</p>
                                <p class="text-sm text-gray-500"><i class="fas fa-map-marker-alt mr-1"></i> Kaup Beach, 12km from Udupi</p>
                            </div>
                        </div>
                        
                        <div class="destination-card">
                            <div class="destination-img">
                                <img src="https://c8.alamy.com/comp/DBEJCW/columnar-basaltic-lava-rocks-at-st-marys-island-in-the-arabian-sea-DBEJCW.jpg" alt="Basaltic Lava Columns">
                            </div>
                            <div class="destination-content">
                                <h3 class="destination-title">St. Mary's Island Basaltic Lava</h3>
                                <p class="text-gray-600 mb-3">These incredible geometric rock pillars are a geological marvel, formed from cooling rhyolitic lava flows around 88 million years ago. It is also where Portuguese explorer Vasco da Gama is believed to have landed in 1498.
</p>
                                <p class="text-sm text-gray-500"><i class="fas fa-map-marker-alt mr-1"></i> St. Mary's Island</p>
                            </div>
                        </div>
                        
                        <div class="destination-card">
                            <div class="destination-img">
                                <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4b/Kapu_Beach_Lighthouse_.jpg/1200px-Kapu_Beach_Lighthouse_.jpg" alt="End Point">
                            </div>
                            <div class="destination-content">
                                <h3 class="destination-title">End Point, Manipal</h3>
                                <p class="text-gray-600 mb-3">A beautifully landscaped park situated on a cliff, End Point offers serene, panoramic views of the Swarna River valley meeting the distant Arabian Sea. It's a favorite spot for tranquil walks, especially at sunrise and sunset.
</p>
                                <p class="text-sm text-gray-500"><i class="fas fa-map-marker-alt mr-1"></i> Manipal, Udupi District</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Food & Culture Section -->
    <section id="food-culture" class="section food-culture">
        <div class="container mx-auto px-4">
            <div class="section-title animate-on-scroll">
                <h2>Food & Culture</h2>
                <p class="text-center text-gray-600 mt-4">Experience the rich culinary heritage and vibrant cultural traditions</p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div>
                    <h3 class="text-2xl font-bold mb-4 text-primary-color animate-on-scroll">Udupi Cuisine</h3>
                    <div class="grid grid-cols-1 gap-6">
                        <div class="food-card animate-on-scroll">
                            <div class="food-img">
                                <img src="https://www.indianhealthyrecipes.com/wp-content/uploads/2021/06/masala-dosa-recipe-500x375.jpg" alt="Masala Dosa">
                            </div>
                            <div class="food-content">
                                <h4 class="food-title">Masala Dosa</h4>
                                <p class="text-gray-600 mb-3">The quintessential Udupi dish, believed to have originated here. A crispy, golden-brown fermented crepe made from rice and lentils, filled with a savory spiced potato mash.
</p>
                            </div>
                        </div>
                        
                        <div class="food-card animate-on-scroll" style="animation-delay: 0.2s;">
                            <div class="food-img">
                                <img src="https://udupi-recipes.com/wp-content/uploads/2017/04/Mysore-Masala-Dosa.jpg" alt="Mysore Masala Dosa">
                            </div>
                            <div class="food-content">
                                <h4 class="food-title">Sattvic Flavors</h4>
                                <p class="text-gray-600 mb-3">Originating from the Krishna Matha, the cuisine is traditionally sattvic, meaning it avoids onion, garlic, meat, and fish, focusing on fresh, local ingredients that nourish both body and soul.
</p>
                            </div>
                        </div>
                        
                        <div class="food-card animate-on-scroll" style="animation-delay: 0.4s;">
                            <div class="food-img">
                                <img src="https://www.masalakorb.com/wp-content/uploads/2016/01/Uppu-Huli-Dosa-V3.jpg" alt="Uppu Huli Dosa">
                            </div>
                            <div class="food-content">
                                <h4 class="food-title">Uppu Huli Dosa</h4>
                                <p class="text-gray-600 mb-3">A unique local specialty, this dosa offers a delightful explosion of flavors. 'Uppu' (salt) and 'Huli' (sour from tamarind) are balanced with spices to create a dosa that needs no accompaniment.
</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div>
                    <h3 class="text-2xl font-bold mb-4 text-primary-color animate-on-scroll">Cultural Heritage</h3>
                    <div class="grid grid-cols-1 gap-6">
                        <div class="culture-card animate-on-scroll">
                            <div class="culture-img">
                                <img src="https://karnatakatourism.org/wp-content/uploads/2020/05/Yakshagana-1.jpg" alt="Yakshagana">
                            </div>
                            <div class="culture-content">
                                <h4 class="culture-title">Yakshagana</h4>
                                <p class="text-gray-600 mb-3">A traditional night-long theatre form, Yakshagana is a spectacular blend of vigorous dance, elaborate costumes, vibrant makeup, and extempore dialogue, narrating stories from Hindu epics.
</p>
                            </div>
                        </div>
                        
                        <div class="culture-card animate-on-scroll" style="animation-delay: 0.2s;">
                            <div class="culture-img">
                                <img src="https://assets.thehansindia.com/h-upload/2023/02/18/1336905-yakshagana-sammelana.webp" alt="Bhuta Kola">
                            </div>
                            <div class="culture-content">
                                <h4 class="culture-title">Bhuta Kola</h4>
                                <p class="text-gray-600 mb-3">An ancient and powerful spirit worship ritual of the Tulu Nadu region. A performer, believed to be possessed by a deity, dances fiercely and acts as an oracle, offering blessings and justice to the community.
</p>
                            </div>
                        </div>
                        
                        <div class="culture-card animate-on-scroll" style="animation-delay: 0.4s;">
                            <div class="culture-img">
                                <img src="https://www.shutterstock.com/shutterstock/photos/2177588983/display_1500/stock-vector-performing-yakshagana-classical-dance-of-karnataka-state-india-vector-illustration-design-2177588983.jpg" alt="Krishna Janmashtami">
                            </div>
                            <div class="culture-content">
                                <h4 class="culture-title">Krishna Janmashtami</h4>
                                <p class="text-gray-600 mb-3">Celebrated with immense devotion, the festival's highlight is "Mosaru Kudike," where groups form human pyramids to break pots of curd hung high above, re-enacting the playful childhood of Lord Krishna.
</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Gallery Section -->
    <section id="gallery" class="section gallery">
        <div class="container mx-auto px-4">
            <div class="section-title animate-on-scroll">
                <h2>Photo Gallery</h2>
                <p class="text-center text-gray-600 mt-4">A visual journey through the beauty of Udupi</p>
            </div>
            
            <div class="gallery-grid animate-on-scroll">
                <div class="gallery-item" data-description="The Udupi Sri Krishna Matha is a famous Hindu temple dedicated to Lord Krishna and Dvaita philosophy. It was founded by the Vaishnavite saint Jagadguru Shri Madhvacharya in the 13th century.">
                    <img src="https://static.toiimg.com/thumb/msid-47157527,width=1200,height=900/47157527.jpg" alt="Sri Krishna Temple" class="gallery-img">
                    <div class="gallery-overlay">
                        <i class="fas fa-expand-alt text-white text-2xl"></i>
                    </div>
                </div>
                
                <div class="gallery-item" data-description="Malpe Beach is known for its picturesque stretch of golden sand, clear blue waters, and palm-fringed shoreline. It is a major fishing harbor and offers a variety of water sports.">
                    <img src="https://thrillingtravel.in/wp-content/uploads/2021/10/Malpe-beach-karnataka.jpg" alt="Malpe Beach" class="gallery-img">
                    <div class="gallery-overlay">
                        <i class="fas fa-expand-alt text-white text-2xl"></i>
                    </div>
                </div>
                
                <div class="gallery-item" data-description="The lighthouse at Kapu (Kaup) Beach was built in 1901 and stands 27 meters tall. It offers breathtaking panoramic views of the Arabian Sea and the surrounding coastline, especially at sunset.">
                    <img src="https://karnatakatourism.org/wp-content/uploads/2020/06/Kapu-Lighthouse-min.jpg" alt="Kaup Lighthouse" class="gallery-img">
                    <div class="gallery-overlay">
                        <i class="fas fa-expand-alt text-white text-2xl"></i>
                    </div>
                </div>
                
                <div class="gallery-item" data-description="St. Mary's Islands are a set of four small islands known for their unique geological formation of columnar basaltic lava. They are a National Geological Monument of India.">
                    <img src="https://www.storiesbysoumya.com/wp-content/uploads/2021/03/St-Marys-Island-Malpe-Udupi.jpg" alt="St. Mary's Island" class="gallery-img">
                    <div class="gallery-overlay">
                        <i class="fas fa-expand-alt text-white text-2xl"></i>
                    </div>
                </div>
                
                <div class="gallery-item" data-description="The Masala Dosa, a world-renowned dish, is a crispy crepe made from rice and lentils, stuffed with a spiced potato filling. It is a signature dish of Udupi cuisine.">
                    <img src="https://www.indianhealthyrecipes.com/wp-content/uploads/2021/06/masala-dosa-recipe-500x375.jpg" alt="Masala Dosa" class="gallery-img">
                    <div class="gallery-overlay">
                        <i class="fas fa-expand-alt text-white text-2xl"></i>
                    </div>
                </div>
                
                <div class="gallery-item" data-description="Yakshagana is a traditional theatre form of coastal Karnataka. It combines dance, music, dialogue, elaborate costumes, and vibrant make-up to narrate stories from epics and Puranas.">
                    <img src="https://karnatakatourism.org/wp-content/uploads/2020/05/Yakshagana-1.jpg" alt="Yakshagana" class="gallery-img">
                    <div class="gallery-overlay">
                        <i class="fas fa-expand-alt text-white text-2xl"></i>
                    </div>
                </div>
                
                <div class="gallery-item" data-description="These hexagonal basaltic columns on St. Mary's Island were formed by volcanic activity around 88 million years ago when the island of Madagascar rifted apart from India.">
                    <img src="https://c8.alamy.com/comp/DBEJCW/columnar-basaltic-lava-rocks-at-st-marys-island-in-the-arabian-sea-DBEJCW.jpg" alt="Basaltic Lava Columns" class="gallery-img">
                    <div class="gallery-overlay">
                        <i class="fas fa-expand-alt text-white text-2xl"></i>
                    </div>
                </div>
                
                <div class="gallery-item" data-description="The temple chariot, or 'Ratha', is an integral part of festivals at the Udupi Krishna Matha. It is beautifully decorated and pulled by devotees in a grand procession.">
                    <img src="https://thrillingtravel.in/wp-content/uploads/2021/05/Chariot-udupi-krishna-matha.jpg" alt="Krishna Temple Chariot" class="gallery-img">
                    <div class="gallery-overlay">
                        <i class="fas fa-expand-alt text-white text-2xl"></i>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Contact Section -->
    <section id="contact" class="section contact">
        <div class="container mx-auto px-4">
            <div class="section-title animate-on-scroll">
                <h2>Contact Us</h2>
                <p class="text-center text-gray-600 mt-4">Get in touch for personalized travel experiences</p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="contact-card animate-on-scroll">
                    <h3 class="text-2xl font-bold mb-4 text-primary-color">Get in Touch</h3>
                    
                    <div class="contact-info">
                        <div class="contact-item">
                            <div class="contact-icon">
                                <i class="fas fa-map-marker-alt"></i>
                            </div>
                            <div>
                                <h4 class="font-bold">Address</h4>
                                <p>Tourism Information Center, Udupi District, Karnataka, India</p>
                            </div>
                        </div>
                        
                        <div class="contact-item">
                            <div class="contact-icon">
                                <i class="fas fa-phone"></i>
                            </div>
                            <div>
                                <h4 class="font-bold">Phone</h4>
                                <p>+91 820 2574868</p>
                            </div>
                        </div>
                        
                        <div class="contact-item">
                            <div class="contact-icon">
                                <i class="fas fa-envelope"></i>
                            </div>
                            <div>
                                <h4 class="font-bold">Email</h4>
                                <p>tourism.udupi@karnataka.gov.in</p>
                            </div>
                        </div>
                    </div>
                    
                    <form>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div>
                                <input type="text" class="form-control" placeholder="Your Name">
                            </div>
                            
                            <div>
                                <input type="email" class="form-control" placeholder="Your Email">
                            </div>
                        </div>
                        
                        <div class="mt-4">
                            <input type="text" class="form-control" placeholder="Subject">
                        </div>
                        
                        <div class="mt-4">
                            <textarea class="form-control" rows="5" placeholder="Your Message"></textarea>
                        </div>
                        
                        <div class="mt-4">
                            <button type="submit" class="btn btn-primary">Send Message</button>
                        </div>
                    </form>
                </div>
                
                <div class="map-container animate-on-scroll">
                    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d31121.60140497542!2d74.72608567338153!3d13.343177176024984!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3bbcbb69938f41cf%3A0xcccc99e431f7ca76!2sUdupi%2C%20Karnataka!5e0!3m2!1sen!2sin!4v1659012345678!5m2!1sen!2sin" width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer class="footer">
        <div class="container mx-auto px-4">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <div>
                    <div class="footer-logo"><span class="text-accent-color">Explore</span> Udupi</div>
                    <p class="text-gray-300 mb-4">Discover the beauty and culture of Udupi, Karnataka's coastal gem with pristine beaches, ancient temples, and rich heritage.</p>
                    <div class="social-links">
                        <a href="#" class="social-link"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
                
                <div class="footer-links">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#home">Home</a></li>
                        <li><a href="#destinations">Destinations</a></li>
                        <li><a href="#food-culture">Food & Culture</a></li>
                        <li><a href="#gallery">Gallery</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                
                <div class="footer-links">
                    <h3>Popular Places</h3>
                    <ul>
                        <li><a href="#destinations">Sri Krishna Temple</a></li>
                        <li><a href="#destinations">Malpe Beach</a></li>
                        <li><a href="#destinations">St. Mary's Island</a></li>
                        <li><a href="#destinations">Kaup Lighthouse</a></li>
                        <li><a href="#destinations">Manipal End Point</a></li>
                    </ul>
                </div>
                
                <div class="footer-links">
                    <h3>Need Help?</h3>
                    <ul>
                        <li><a href="#contact">Contact Us</a></li>
                        <li><a href="#">Travel Guide</a></li>
                        <li><a href="#">FAQs</a></li>
                        <li><a href="#">Terms & Conditions</a></li>
                        <li><a href="#">Privacy Policy</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="copyright">
                <p>© 2025 Explore Udupi. All Rights Reserved.</p>
            </div>
        </div>
    </footer>
    
    <!-- Lightbox -->
    <div class="lightbox">
        <div class="lightbox-close">×</div>
        <img src="" alt="" class="lightbox-img">
        <p class="lightbox-caption"></p>
    </div>
    
    <!-- JavaScript -->
    <script>
        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });
        
        // Mobile Menu Toggle
        const mobileMenuBtn = document.querySelector('.mobile-menu-btn');
        const navLinks = document.querySelector('.nav-links');
        const overlay = document.querySelector('.overlay');
        
        mobileMenuBtn.addEventListener('click', function() {
            this.classList.toggle('active');
            navLinks.classList.toggle('active');
            overlay.classList.toggle('active');
        });
        
        overlay.addEventListener('click', function() {
            mobileMenuBtn.classList.remove('active');
            navLinks.classList.remove('active');
            this.classList.remove('active');
        });
        
        // Active Navigation Link
        const sections = document.querySelectorAll('section');
        const navItems = document.querySelectorAll('.nav-link');
        
        window.addEventListener('scroll', function() {
            let current = '';
            
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                if (window.scrollY >= (sectionTop - 100)) {
                    current = section.getAttribute('id');
                }
            });
            
            navItems.forEach(item => {
                item.classList.remove('active');
                if (item.getAttribute('href').substring(1) === current) {
                    item.classList.add('active');
                }
            });
        });
        
        // Smooth Scrolling for Navigation Links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 70,
                        behavior: 'smooth'
                    });
                    
                    // Close mobile menu if open
                    if (navLinks.classList.contains('active')) {
                        mobileMenuBtn.classList.remove('active');
                        navLinks.classList.remove('active');
                        overlay.classList.remove('active');
                    }
                }
            });
        });
        
        // Tabs Functionality
        const tabs = document.querySelectorAll('.tab');
        
        tabs.forEach(tab => {
            tab.addEventListener('click', function() {
                tabs.forEach(t => t.classList.remove('active'));
                this.classList.add('active');
                
                document.querySelectorAll('.tab-content').forEach(content => {
                    content.classList.remove('active');
                });
                
                const tabContentId = this.getAttribute('data-tab') + '-content';
                document.getElementById(tabContentId).classList.add('active');
            });
        });
        
        // Lightbox Functionality
        const galleryItems = document.querySelectorAll('.gallery-item');
        const lightbox = document.querySelector('.lightbox');
        const lightboxImg = document.querySelector('.lightbox-img');
        const lightboxCaption = document.querySelector('.lightbox-caption');
        const lightboxClose = document.querySelector('.lightbox-close');
        
        galleryItems.forEach(item => {
            item.addEventListener('click', function() {
                const imgSrc = this.querySelector('.gallery-img').getAttribute('src');
                const description = this.getAttribute('data-description');
                
                lightboxImg.setAttribute('src', imgSrc);
                lightboxCaption.textContent = description;
                lightbox.classList.add('active');
            });
        });
        
        function closeLightbox() {
            lightbox.classList.remove('active');
            // Clear content to prevent flash of old content
            lightboxImg.setAttribute('src', "");
            lightboxCaption.textContent = "";
        }

        lightboxClose.addEventListener('click', closeLightbox);
        
        lightbox.addEventListener('click', function(e) {
            if (e.target === lightbox) {
                closeLightbox();
            }
        });
        
        // Scroll Animation
        function animateOnScroll() {
            const elements = document.querySelectorAll('.animate-on-scroll');
            
            elements.forEach(element => {
                const elementPosition = element.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                
                if (elementPosition < windowHeight - 100) {
                    element.classList.add('animated');
                }
            });
        }
        
        window.addEventListener('scroll', animateOnScroll);
        window.addEventListener('load', animateOnScroll);
    </script>
</body>
</html>
