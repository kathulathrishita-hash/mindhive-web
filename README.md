<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MindHive - Smart Connectivity Solutions</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #5d5dff; /* Vibrant Purple/Blue */
            --secondary-color: #b0b0f0; /* Lighter shade */
            --accent-color: #00ffc6; /* Neon green/cyan for highlights */
            --dark-bg: #1a1a2e; /* Deep purple background */
            --light-bg: #21283a; /* Slightly lighter bg */
            --text-color: #e0e0f0; /* Light text for dark bg */
            --subtle-text-color: #a0a0c0; /* Subtle text */
            --animation-speed: 1.5s;
            --bezier-ease: cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }

        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            background-color: var(--dark-bg);
            color: var(--text-color);
            line-height: 1.8;
            overflow-x: hidden;
            position: relative;
        }
        
        /* Stunning background effect */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--dark-bg) 0%, #0c1524 100%);
            z-index: -1;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px 0;
        }

        /* --- Global Animations & Styles --- */
        h1, h2, h3, h4, p {
            margin-bottom: 15px;
        }

        h1, h2 {
            font-family: 'Playfair Display', serif;
            font-weight: 700;
            text-align: center;
        }

        h2 {
            font-size: 3em;
            color: var(--primary-color);
            margin-bottom: 30px;
            position: relative;
            display: inline-block;
        }

        h2::after {
            content: '';
            position: absolute;
            left: 50%;
            bottom: -10px;
            transform: translateX(-50%) scaleX(0);
            width: 100px;
            height: 4px;
            background-color: var(--accent-color);
            transition: transform 0.8s var(--bezier-ease);
        }

        section.animate h2::after {
            transform: translateX(-50%) scaleX(1);
        }
        
        /* Floating words animation */
        .animated-text span {
            display: inline-block;
            animation: floatIn var(--animation-speed) ease-out forwards;
            opacity: 0;
            margin-right: 0.25em;
        }

        .animated-heading span {
            display: inline-block;
            animation: slideUpIn 1s var(--bezier-ease) forwards;
            opacity: 0;
        }

        @keyframes floatIn {
            from {
                opacity: 0;
                transform: translateY(20px) scale(0.9);
            }
            to {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
        }

        @keyframes slideUpIn {
            from {
                opacity: 0;
                transform: translateY(50px) rotateX(-90deg);
            }
            to {
                opacity: 1;
                transform: translateY(0) rotateX(0deg);
            }
        }

        .btn {
            display: inline-block;
            padding: 12px 28px;
            background: linear-gradient(45deg, var(--primary-color), var(--accent-color));
            color: var(--dark-bg);
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: transform 0.3s var(--bezier-ease), box-shadow 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
        }

        .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0,255,198,0.4);
        }

        section {
            padding: 80px 0;
            opacity: 0;
            transform: translateY(50px);
            transition: opacity 1s ease-out, transform 1s ease-out;
        }

        section.animate {
            opacity: 1;
            transform: translateY(0);
        }

        /* --- Navbar --- */
        .navbar {
            background-color: rgba(26, 26, 46, 0.8);
            backdrop-filter: blur(10px);
            padding: 15px 0;
            box-shadow: 0 4px 20px rgba(0,0,0,0.5);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .navbar .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .navbar-brand {
            display: flex;
            align-items: center;
            text-decoration: none;
        }
        
        .navbar-logo {
            width: 40px;
            height: 40px;
            background: linear-gradient(45deg, var(--primary-color), var(--accent-color));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 10px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.5);
            position: relative;
            overflow: hidden;
            animation: pulse 2s infinite ease-in-out;
        }
        
        .navbar-logo::before {
            content: '⚡';
            font-size: 1.5em;
            color: var(--light-text);
        }

        .navbar-logo-text {
            color: var(--light-text);
            font-size: 1.8em;
            font-weight: 700;
            font-family: 'Playfair Display', serif;
            letter-spacing: 1px;
        }

        .nav-links {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
        }

        .nav-links li {
            margin-left: 30px;
        }

        .nav-links a {
            color: var(--subtle-text-color);
            text-decoration: none;
            font-weight: 400;
            font-size: 1.1em;
            position: relative;
            transition: color 0.3s ease;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: -5px;
            width: 0;
            height: 3px;
            background-color: var(--accent-color);
            transition: width 0.3s var(--bezier-ease);
        }

        .nav-links a:hover::after,
        .nav-links a.active::after {
            width: 100%;
        }
        
        .nav-links a:hover,
        .nav-links a.active {
            color: var(--accent-color);
        }

        /* --- Page Content Styles (Common) --- */
        #page-header {
            background: linear-gradient(135deg, var(--primary-color) 0%, #206596 100%);
            color: var(--light-text);
            padding: 100px 0 70px;
            text-align: center;
            position: relative;
            overflow: hidden;
            clip-path: polygon(0 0, 100% 0, 100% 80%, 0% 100%);
        }

        #page-header h1 {
            font-size: 4em;
            text-shadow: 2px 2px 10px rgba(0,0,0,0.5);
            animation: fadeInDown 1s var(--bezier-ease) forwards;
            opacity: 0;
        }

        #page-header p {
            font-size: 1.5em;
            max-width: 700px;
            margin: 20px auto 0;
            animation: fadeInUp 1s var(--bezier-ease) 0.3s forwards;
            opacity: 0;
        }

        /* --- Home Page Specific Styles --- */
        #hero {
            background: linear-gradient(to bottom, transparent, var(--light-bg));
            color: var(--text-color);
            padding: 100px 0;
            text-align: center;
            overflow: hidden;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .hero-content {
            position: relative;
            z-index: 1;
            animation: fadeInUp 1s ease-out forwards;
        }

        #hero h1 {
            font-size: 4.5em;
            margin-bottom: 20px;
            text-shadow: 3px 3px 10px rgba(0,0,0,0.5);
            color: var(--accent-color);
        }

        #hero p {
            font-size: 1.8em;
            max-width: 800px;
            margin: 0 auto 40px auto;
            color: var(--light-text);
        }

        #features {
            background-color: var(--light-bg);
            text-align: center;
        }

        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .feature-card {
            background-color: rgba(255,255,255,0.05);
            backdrop-filter: blur(5px);
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 6px 20px rgba(0,0,0,0.3);
            border: 1px solid rgba(255,255,255,0.1);
            transition: transform 0.4s var(--bezier-ease), box-shadow 0.4s ease, border-color 0.4s ease;
            text-align: center;
            position: relative;
            overflow: hidden;
            opacity: 0;
            transform: translateY(20px);
        }

        .feature-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 12px 30px rgba(0,255,198,0.2);
            border-color: var(--accent-color);
        }

        .feature-card.animate {
            opacity: 1;
            transform: translateY(0);
        }

        .feature-card h3 {
            font-size: 2em;
            color: var(--accent-color);
            margin-bottom: 15px;
            font-family: 'Poppins', sans-serif;
            font-weight: 600;
        }

        .feature-card p {
            color: var(--secondary-color);
            font-size: 1.1em;
        }

        #contact {
            background: linear-gradient(135deg, var(--accent-color), #218838);
            color: var(--dark-bg);
            text-align: center;
            padding: 80px 0;
        }

        #contact h2 {
            color: var(--dark-bg);
            font-size: 3.5em;
            margin-bottom: 25px;
        }
        #contact h2::after {
            background-color: var(--dark-bg);
        }

        #contact p {
            font-size: 1.4em;
            max-width: 900px;
            margin: 0 auto 40px auto;
        }

        /* --- About Page Specific Styles --- */
        #about-content {
            padding: 60px 0;
            text-align: center;
        }

        .vision-motto, .company-concept, .target-audience-section, #team {
            margin-bottom: 80px;
        }

        .vision-motto h3, .company-concept h3, .target-audience-section h3, #team h3 {
            font-size: 2.5em;
            color: var(--primary-color);
            margin-bottom: 25px;
            font-family: 'Playfair Display', serif;
            animation: slideInLeft 0.8s var(--bezier-ease) forwards;
            opacity: 0;
        }
        .vision-motto p, .company-concept p, .target-audience-section p, #team p {
            font-size: 1.2em;
            max-width: 900px;
            margin: 0 auto 30px auto;
            color: var(--subtle-text-color);
            animation: slideInRight 0.8s var(--bezier-ease) 0.2s forwards;
            opacity: 0;
        }

        .vision-motto .image-container {
            width: 100%;
            max-width: 800px;
            margin: 40px auto;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            transform: scale(0.9);
            opacity: 0;
            animation: zoomIn 0.8s var(--bezier-ease) 0.4s forwards;
        }
        .vision-motto .image-container img {
            width: 100%;
            height: auto;
            display: block;
        }

        .business-points {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 30px;
            margin-top: 40px;
        }

        .point-card {
            background-color: rgba(255,255,255,0.05);
            backdrop-filter: blur(5px);
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 6px 20px rgba(0,0,0,0.3);
            border: 1px solid rgba(255,255,255,0.1);
            width: 300px;
            text-align: left;
            transition: transform 0.4s var(--bezier-ease), box-shadow 0.4s ease;
            opacity: 0;
            transform: translateY(20px);
        }
        .point-card.animate {
            opacity: 1;
            transform: translateY(0);
        }

        .point-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 12px 30px rgba(0,255,198,0.2);
        }

        .point-card h4 {
            color: var(--accent-color);
            font-size: 1.5em;
            margin-bottom: 10px;
            font-family: 'Poppins', sans-serif;
            font-weight: 600;
        }
        .point-card p {
            font-size: 1.1em;
            color: var(--subtle-text-color);
            text-align: left;
        }
        
        #team {
            background-color: var(--light-bg);
            padding: 80px 0;
        }
        
        #team h2 {
            color: var(--primary-color);
        }

        .team-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
            margin-top: 40px;
        }

        .team-member-card {
            background-color: rgba(255,255,255,0.08);
            border-radius: 15px;
            padding: 30px 20px;
            text-align: center;
            width: 240px;
            box-shadow: 0 8px 25px rgba(0,0,0,0.5);
            border: 1px solid rgba(255,255,255,0.1);
            transition: transform 0.4s var(--bezier-ease), background-color 0.3s ease;
            opacity: 0;
            transform: translateY(20px);
        }
        .team-member-card.animate {
            opacity: 1;
            transform: translateY(0);
        }

        .team-member-card:hover {
            transform: translateY(-15px);
            background-color: rgba(255,255,255,0.15);
            box-shadow: 0 15px 40px rgba(0,255,198,0.3);
        }

        .member-name {
            font-size: 1.8em;
            color: var(--accent-color);
            margin-bottom: 5px;
            font-family: 'Playfair Display', serif;
        }

        .member-role {
            color: var(--subtle-text-color);
            font-style: italic;
            font-size: 1.1em;
            margin-bottom: 15px;
        }
        .member-email {
            font-size: 0.9em;
            color: rgba(255,255,255,0.7);
            word-break: break-all;
        }

        /* --- Projects Page Specific Styles --- */
        #projects-grid {
            padding: 60px 0;
            text-align: center;
        }

        .project-category {
            margin-bottom: 80px;
        }

        .project-category h3 {
            font-size: 2.5em;
            color: var(--primary-color);
            margin-bottom: 40px;
            font-family: 'Playfair Display', serif;
            animation: slideInLeft 0.8s var(--bezier-ease) forwards;
            opacity: 0;
        }

        .project-cards-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            margin-top: 30px;
        }

        .project-card {
            background-color: rgba(255,255,255,0.05);
            backdrop-filter: blur(5px);
            border-radius: 15px;
            box-shadow: 0 8px 25px rgba(0,0,0,0.3);
            border: 1px solid rgba(255,255,255,0.1);
            overflow: hidden;
            text-align: left;
            transition: transform 0.4s var(--bezier-ease), box-shadow 0.4s ease;
            opacity: 0;
            transform: translateY(30px);
        }
        .project-card.animate {
            opacity: 1;
            transform: translateY(0);
        }

        .project-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 12px 30px rgba(0,255,198,0.2);
        }

        .project-card img {
            width: 100%;
            height: 220px;
            object-fit: cover;
            transition: transform 0.5s ease-out;
        }

        .project-card:hover img {
            transform: scale(1.05);
        }

        .project-content {
            padding: 25px;
        }

        .project-content h4 {
            font-size: 1.8em;
            color: var(--primary-color);
            margin-bottom: 10px;
            font-family: 'Poppins', sans-serif;
            font-weight: 600;
        }

        .project-content p {
            font-size: 1.1em;
            color: var(--subtle-text-color);
            margin-bottom: 20px;
        }

        .project-content .btn {
            font-size: 0.9em;
            padding: 10px 20px;
        }

        /* --- Case Study Details Section --- */
        #case-study-details {
            padding: 80px 0;
            display: none; /* Initially hidden */
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease-out, transform 0.8s ease-out;
        }

        #case-study-details.active {
            display: block;
            opacity: 1;
            transform: translateY(0);
        }

        #case-study-details h2 {
            font-size: 3.5em;
            margin-bottom: 20px;
            color: var(--primary-color);
        }
        
        #case-study-details p {
            max-width: 800px;
            margin: 0 auto 30px auto;
            font-size: 1.2em;
            color: var(--subtle-text-color);
        }

        #case-study-details .image-container {
            width: 100%;
            max-width: 900px;
            margin: 40px auto;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }
        #case-study-details .image-container img {
            width: 100%;
            height: auto;
            display: block;
        }

        .case-study-points {
            display: flex;
            flex-direction: column;
            gap: 25px;
            max-width: 800px;
            margin: 40px auto 0;
            text-align: left;
        }

        .case-study-point {
            background-color: rgba(255,255,255,0.05);
            backdrop-filter: blur(5px);
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            border-left: 5px solid var(--accent-color);
        }

        .case-study-point h4 {
            font-size: 1.6em;
            color: var(--accent-color);
            margin-bottom: 10px;
            font-family: 'Poppins', sans-serif;
            font-weight: 600;
        }
        .case-study-point p {
            font-size: 1.1em;
            margin-bottom: 0;
        }


        /* --- Footer --- */
        footer {
            background-color: var(--light-bg);
            color: var(--light-text);
            padding: 40px 0;
            text-align: center;
            font-size: 0.95em;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        footer .navbar-brand {
            justify-content: center;
            margin-bottom: 20px;
        }

        footer .nav-links {
            justify-content: center;
            margin-bottom: 20px;
        }

        footer .nav-links li {
            margin: 0 15px;
        }

        /* --- Keyframe Animations --- */
        @keyframes floatIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-50px); }
            to { opacity: 1; transform: translateY(0); }
        }
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }
        @keyframes slideInLeft {
            from { opacity: 0; transform: translateX(-50px); }
            to { opacity: 1; transform: translateX(0); }
        }
        @keyframes slideInRight {
            from { opacity: 0; transform: translateX(50px); }
            to { opacity: 1; transform: translateX(0); }
        }
        @keyframes zoomIn {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }
        @keyframes pulse {
            0% { transform: scale(1); box-shadow: 0 0 0 0 rgba(0,255,198, 0.7); }
            70% { transform: scale(1.05); box-shadow: 0 0 0 10px rgba(0,255,198, 0); }
            100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(0,255,198, 0); }
        }
        /* Responsive Design */
        @media (max-width: 768px) {
            .navbar .container {
                flex-direction: column;
            }
            .nav-links {
                margin-top: 20px;
                flex-wrap: wrap;
                justify-content: center;
            }
            .nav-links li {
                margin: 0 10px 10px 10px;
            }
            #hero h1, #page-header h1 {
                font-size: 2.5em;
            }
            #hero p, #page-header p {
                font-size: 1.2em;
            }
            h2 {
                font-size: 2em;
            }
            .feature-grid, .project-cards-container {
                grid-template-columns: 1fr;
            }
            .vision-motto h3, .company-concept h3 {
                font-size: 1.8em;
            }
            .point-card {
                width: 90%;
            }
        }
        
        /* New Styles for one-page layout */
        .page-section {
            display: none;
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease-out, transform 0.8s ease-out;
        }

        .page-section.active {
            display: block;
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>

    <nav class="navbar">
        <div class="container">
            <a href="#home" class="navbar-brand">
                <div class="navbar-logo"></div>
                <span class="navbar-logo-text">MindHive</span>
            </a>
            <ul class="nav-links">
                <li><a href="#home" class="nav-link active">Home</a></li>
                <li><a href="#about" class="nav-link">About Us</a></li>
                <li><a href="#projects" class="nav-link">Projects</a></li>
                <li><a href="#contact" class="nav-link">Contact</a></li>
            </ul>
        </div>
    </nav>

    <div id="home" class="page-section active">
        <section id="hero">
            <div class="hero-content">
                <h1 class="animated-heading">
                    <span>Connecting</span> <span>Devices,</span> <span>Anywhere,</span> <span>Anytime</span>
                </h1>
                <p class="animated-text">
                    <span>Your</span> <span>ultimate</span> <span>solution</span> <span>for</span> <span>uninterrupted</span> <span>smart</span> <span>connectivity.</span> <span>We</span> <span>power</span> <span>the</span> <span>future</span> <span>of</span> <span>IoT.</span>
                </p>
                <a href="#about" class="btn nav-link" data-page="about">Discover MindHive</a>
            </div>
        </section>
    
        <section id="features">
            <div class="container">
                <h2>Our Core Offerings</h2>
                <div class="feature-grid">
                    <div class="feature-card">
                        <h3>Always-On Connectivity</h3>
                        <p>Our multi-network IoT modules ensure seamless, uninterrupted connectivity by intelligently switching between available networks.</p>
                    </div>
                    <div class="feature-card">
                        <h3>Cost Optimization</h3>
                        <p>Minimize operational costs with smart data routing and optimized network usage, designed to reduce roaming charges and improve efficiency.</p>
                    </div>
                    <div class="feature-card">
                        <h3>Global Coverage</h3>
                        <p>Deploy your IoT devices with confidence, knowing they'll have reliable access to networks across the globe, without limitations.</p>
                    </div>
                </div>
            </div>
        </section>
    
        <section id="contact">
            <div class="container">
                <h2>Get in Touch</h2>
                <p>To learn more about MindHive's services, you can send an email to shaikjasmin966@gmail.com.</p>
                <a href="mailto:shaikjasmin966@gmail.com?subject=Inquiry about MindHive&body=My name is: %5BYour Name%5D%0A%0AI represent: %5BYour Company%5D%0A%0AMy area of interest is: %5BYour Area of Interest%5D" class="btn">Send Us an Email</a>
            </div>
        </section>
    </div>

    <div id="about" class="page-section">
        <section id="page-header">
            <div class="container">
                <h1>About MindHive</h1>
                <p>Our journey to revolutionize smart connectivity solutions.</p>
            </div>
        </section>

        <section id="about-content">
            <div class="container">
                <div class="vision-motto">
                    <h2>Our Vision & Motto</h2>
                    <h3>Team Motto: Many minds, one vision.</h3>
                    <p>This motto defines the spirit of Core Innovators. We believe that by combining diverse perspectives and expertise, we can achieve a singular, powerful goal: to connect devices anywhere, anytime.</p>
                    <h3>Company Vision: Connecting devices anywhere, anytime.</h3>
                    <p>We are solving the pervasive problem of unreliable connectivity for IoT devices. Our vision is a world where every smart device operates seamlessly, without interruption, regardless of its location or environmental challenges.</p>
                </div>

                <div class="company-concept">
                    <h2>Our Business Concept</h2>
                    <h3>What We Do:</h3>
                    <p>MindHive provides multi-network IoT modules that ensure uninterrupted connectivity for IoT devices. Our technology intelligently switches between cellular networks, Wi-Fi, and other available protocols to maintain a constant, reliable connection.</p>
                    <h3>Unique Selling Proposition (USP):</h3>
                    <p>What sets MindHive apart is our commitment to "Always-on connectivity" through our multi-network failover system, significant "Cost optimization" by intelligently selecting the best network, and true "Global coverage" that allows devices to operate anywhere in the world.</p>
                </div>

                <div class="target-audience-section">
                    <h2>Target Audience</h2>
                    <p>MindHive's solutions are designed for a broad range of industries that require constant, reliable connectivity for their IoT devices. These include:</p>
                    <div class="business-points">
                        <div class="point-card animate-on-scroll">
                            <h4>Smart Agriculture</h4>
                            <p>Our modules enable real-time monitoring of crops, soil, and livestock in remote areas, ensuring optimal growth and health.</p>
                        </div>
                        <div class="point-card animate-on-scroll">
                            <h4>Healthcare</h4>
                            <p>The technology ensures continuous data transmission for remote patient monitoring and critical medical devices, providing peace of mind and safety.</p>
                        </div>
                        <div class="point-card animate-on-scroll">
                            <h4>Smart Cities</h4>
                            <p>We power connected infrastructure such as smart streetlights, waste management systems, and traffic systems, leading to more efficient urban environments.</p>
                        </div>
                        <div class="point-card animate-on-scroll">
                            <h4>Industries (IoT)</h4>
                            <p>Our solutions provide robust connectivity for industrial sensors, asset tracking, and automated processes, crucial for boosting productivity and operational efficiency.</p>
                        </div>
                    </div>
                </div>

                <section id="team">
                    <h2>Meet the Core Innovators</h2>
                    <div class="team-grid">
                        <div class="team-member-card">
                            <h4 class="member-name">SK.Jasmin</h4>
                            <p class="member-role">Team Leader</p>
                            <p class="member-email">shaikjasmin966@gmail.com</p>
                        </div>
                        <div class="team-member-card">
                            <h4 class="member-name">N.Sai Preethi</h4>
                            <p class="member-role">Member 2</p>
                            <p class="member-email">saipreethika2004@gmail.com</p>
                        </div>
                        <div class="team-member-card">
                            <h4 class="member-name">G.Naga Madhavi</h4>
                            <p class="member-role">Member 3</p>
                            <p class="member-email">madhavigajendra06@gmail.com</p>
                        </div>
                        <div class="team-member-card">
                            <h4 class="member-name">K.Trishita</h4>
                            <p class="member-role">Member 4</p>
                            <p class="member-email">kathulathrishita@gmail.com</p>
                        </div>
                        <div class="team-member-card">
                            <h4 class="member-name">Y.Roja</h4>
                            <p class="member-role">Member 5</p>
                            <p class="member-email">yanamalamandaroja@gmail.com</p>
                        </div>
                    </div>
                </section>

            </div>
        </section>
    </div>
    
    <div id="projects" class="page-section">
        <section id="page-header">
            <div class="container">
                <h1>Our Innovations in Action</h1>
                <p>Explore the diverse projects where MindHive's smart connectivity solutions are making a real impact.</p>
            </div>
        </section>

        <section id="projects-grid">
            <div class="container">
                <h2>Featured Implementations</h2>
                <div class="project-category">
                    <h3>Smart City & Industrial IoT</h3>
                    <div class="project-cards-container">
                        <div class="project-card">
                            <img src="https://via.placeholder.com/400x220/007bff/ffffff?text=Smart+City" alt="Intelligent Urban Infrastructure">
                            <div class="project-content">
                                <h4>Intelligent Urban Infrastructure</h4>
                                <p>Integrated our modules into smart city systems for traffic management, public safety, and environmental monitoring, ensuring seamless data flow for efficient urban operations.</p>
                                <a href="#case-study-details" class="btn view-case-study" data-case-study="smart-city">View Case Study</a>
                            </div>
                        </div>
                        <div class="project-card">
                            <img src="https://via.placeholder.com/400x220/28a745/ffffff?text=Industrial+IoT" alt="Factory Automation & Asset Tracking">
                            <div class="project-content">
                                <h4>Factory Automation & Asset Tracking</h4>
                                <p>Provided reliable connectivity for industrial sensors and machinery, enabling predictive maintenance, asset tracking, and optimizing complex manufacturing processes.</p>
                                <a href="#case-study-details" class="btn view-case-study" data-case-study="industrial-iot">View Case Study</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <div id="case-study-details" class="page-section">
        <section id="case-study-content">
            <div class="container">
                <h2 id="case-study-title"></h2>
                <p id="case-study-intro"></p>
                <div class="case-study-points" id="case-study-info"></div>
            </div>
        </section>
    </div>

    <footer>
        <div class="container">
            <a href="#home" class="navbar-brand">
                <div class="navbar-logo"></div>
                <span class="navbar-logo-text">MindHive</span>
            </a>
            <ul class="nav-links">
                <li><a href="#home" class="nav-link active">Home</a></li>
                <li><a href="#about" class="nav-link">About Us</a></li>
                <li><a href="#projects" class="nav-link">Projects</a></li>
                <li><a href="#contact" class="nav-link">Contact</a></li>
            </ul>
            <p>&copy; 2025 MindHive. All rights reserved. Prepared by Core Innovators.</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const navLinks = document.querySelectorAll('.nav-link');
            const pageSections = document.querySelectorAll('.page-section');
            const caseStudyBtns = document.querySelectorAll('.view-case-study');
            const caseStudyData = {
                'smart-city': {
                    title: 'Intelligent Urban Infrastructure',
                    intro: 'We partnered with a municipality to create a smart city infrastructure that manages traffic, monitors air quality, and optimizes energy consumption in real-time.',
                    points: [
                        { title: 'The Challenge', description: 'Managing a city’s worth of IoT data was challenging due to inconsistent network coverage and high data costs across different urban zones.' },
                        { title: 'The Solution', description: 'MindHive’s modules were embedded in smart traffic signals, waste bins, and streetlights, providing a single, reliable network for all devices. Our system intelligently routes data to minimize cost.' },
                        { title: 'The Outcome', description: 'The city reduced its energy consumption by 20%, improved traffic flow by 15%, and streamlined public services, resulting in a more efficient and livable urban environment.' }
                    ]
                },
                'industrial-iot': {
                    title: 'Factory Automation & Asset Tracking',
                    intro: 'A global manufacturing company utilized MindHive’s modules to digitize their factory floor, improving automation and gaining full visibility into their supply chain.',
                    points: [
                        { title: 'The Challenge', description: 'Connectivity was a constant issue inside the factory’s metal-heavy environment, leading to interruptions in automated processes and asset tracking.' },
                        { title: 'The Solution', description: 'We installed our industrial-grade modules on factory machinery and mobile assets. The modules were designed to penetrate difficult environments and automatically switch to a more robust internal or external network when needed.' },
                        { title: 'The Outcome', description: 'The company achieved a 30% increase in operational uptime and a significant reduction in downtime due to equipment failure, boosting productivity and cutting costs.' }
                    ]
                }
            };
            
            const applyFloatingAnimation = (element) => {
                const text = element.textContent;
                element.textContent = '';
                const words = text.split(' ');
                words.forEach((word, index) => {
                    const span = document.createElement('span');
                    span.textContent = word;
                    span.style.animationDelay = `${index * 0.1}s`;
                    element.appendChild(span);
                    element.appendChild(document.createTextNode(' '));
                });
            };

            const sectionObserver = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('animate');
                        const elementsToAnimate = entry.target.querySelectorAll('h2, .feature-card, .vision-motto h3, .vision-motto p, .company-concept h3, .company-concept p, .point-card, .team-member-card, .project-card, .project-category h3');
                        elementsToAnimate.forEach((el, index) => {
                            el.style.animationDelay = `${index * 0.1}s`;
                            el.classList.add('animate');
                        });
                        observer.unobserve(entry.target);
                    }
                });
            }, { rootMargin: '0px', threshold: 0.1 });
    
            const showPage = (pageId, delay = 0) => {
                pageSections.forEach(page => page.classList.remove('active'));
                setTimeout(() => {
                    const targetPage = document.getElementById(pageId);
                    if (targetPage) {
                        targetPage.classList.add('active');
                        const sectionsToObserve = targetPage.querySelectorAll('section');
                        sectionsToObserve.forEach(section => {
                            section.classList.remove('animate');
                            sectionObserver.observe(section);
                        });
                        window.scrollTo({ top: 0, behavior: 'smooth' });
                    }
                }, delay);
            };
    
            const loadCaseStudy = (caseStudyId) => {
                const data = caseStudyData[caseStudyId];
                if (!data) return;
    
                document.getElementById('case-study-title').textContent = data.title;
                document.getElementById('case-study-intro').textContent = data.intro;
    
                const infoContainer = document.getElementById('case-study-info');
                infoContainer.innerHTML = ''; // Clear previous content
                data.points.forEach(point => {
                    const pointDiv = document.createElement('div');
                    pointDiv.className = 'case-study-point';
                    pointDiv.innerHTML = `<h4>${point.title}</h4><p>${point.description}</p>`;
                    infoContainer.appendChild(pointDiv);
                });
    
                showPage('case-study-details');
            };
    
            navLinks.forEach(link => {
                link.addEventListener('click', (e) => {
                    e.preventDefault();
                    const targetId = e.target.getAttribute('href').substring(1);
                    navLinks.forEach(navLink => navLink.classList.remove('active'));
                    e.target.classList.add('active');
    
                    if (targetId === 'contact') {
                        showPage('home');
                        setTimeout(() => {
                            const contactSection = document.getElementById('contact');
                            if (contactSection) {
                                window.scrollTo({
                                    top: contactSection.offsetTop - document.querySelector('.navbar').offsetHeight,
                                    behavior: 'smooth'
                                });
                            }
                        }, 100);
                    } else if (targetId === 'about') {
                        showPage('about');
                    } else if (targetId === 'projects') {
                        showPage('projects');
                    } else {
                        showPage('home');
                    }
                });
            });
    
            caseStudyBtns.forEach(btn => {
                btn.addEventListener('click', (e) => {
                    e.preventDefault();
                    const caseStudyId = e.target.getAttribute('data-case-study');
                    loadCaseStudy(caseStudyId);
                });
            });

            // Apply floating animation to hero text
            const heroText = document.querySelector('#hero p.animated-text');
            if (heroText) {
                applyFloatingAnimation(heroText);
            }

            // Apply floating animation to hero heading
            const heroHeading = document.querySelector('#hero h1.animated-heading');
            if (heroHeading) {
                const text = heroHeading.textContent;
                heroHeading.textContent = '';
                const words = text.split(' ');
                words.forEach((word, index) => {
                    const span = document.createElement('span');
                    span.textContent = word;
                    span.style.animationDelay = `${index * 0.1}s`;
                    heroHeading.appendChild(span);
                    heroHeading.appendChild(document.createTextNode(' '));
                });
            }
    
            // Initial setup: show home page
            showPage('home');
        });
    </script>
</body>
</html>
