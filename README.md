<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Yamen Raslan - السيرة الذاتية</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <style>
        :root {
            --primary: #1a2a3a;
            --primary-dark: #0d1b26;
            --secondary: #2c3e50;
            --accent: #3498db;
            --accent2: #2ecc71;
            --accent3: #9b59b6;
            --accent-light: #5dade2;
            --light: #ecf0f1;
            --dark: #1a2a3a;
            --gray: #95a5a6;
            --transition: all 0.3s ease;
            --shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            --radius: 8px;
        }

        .light-mode {
            --primary: #f0f2f5;
            --primary-dark: #e4e7eb;
            --secondary: #dde1e5;
            --accent: #2980b9;
            --accent2: #27ae60;
            --accent3: #8e44ad;
            --light: #2c3e50;
            --dark: #f8f9fa;
            --gray: #7f8c8d;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Tajawal', sans-serif;
            line-height: 1.6;
        }

        body {
            background: linear-gradient(135deg, var(--primary-dark) 0%, var(--primary) 100%);
            color: var(--light);
            overflow-x: hidden;
            position: relative;
            transition: var(--transition);
        }

        #tech-background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 10;
        }

        section {
            padding: 60px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 30px;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.2rem;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            display: inline-block;
            position: relative;
            padding-bottom: 10px;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .section-title h2::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 70px;
            height: 4px;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            border-radius: 2px;
        }

        .theme-toggle {
            position: fixed;
            top: 20px;
            left: 20px;
            z-index: 1100;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--accent);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .theme-toggle:hover {
            transform: rotate(30deg) scale(1.1);
        }

        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(26, 42, 58, 0.95);
            box-shadow: var(--shadow);
            backdrop-filter: blur(10px);
            transition: var(--transition);
            border-bottom: 1px solid rgba(52, 152, 219, 0.2);
        }

        .light-mode header {
            background: rgba(240, 242, 245, 0.95);
            border-bottom: 1px solid rgba(41, 128, 185, 0.2);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 12px 0;
        }

        .logo {
            font-size: 1.6rem;
            font-weight: 700;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-decoration: none;
            display: flex;
            align-items: center;
            transition: var(--transition);
        }

        .logo:hover {
            transform: scale(1.05);
        }

        .nav-links {
            display: flex;
            list-style: none;
            align-items: center;
        }

        .nav-links li {
            margin-left: 25px;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--light);
            font-weight: 600;
            transition: var(--transition);
            position: relative;
            padding: 4px 0;
            font-size: 0.95rem;
        }

        .light-mode .nav-links a {
            color: #2c3e50;
        }

        .nav-links a::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--accent);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .menu-toggle {
            display: none;
            font-size: 1.6rem;
            cursor: pointer;
            color: var(--accent);
            transition: var(--transition);
        }

        .menu-toggle:hover {
            transform: rotate(90deg);
        }

        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
            padding-top: 70px;
        }

        .hero-content {
            width: 100%;
            max-width: 900px;
            margin: 0 auto;
            padding: 35px;
            z-index: 2;
            text-align: center;
            background: rgba(13, 27, 38, 0.7);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            border: 1px solid rgba(52, 152, 219, 0.3);
            backdrop-filter: blur(10px);
        }

        .light-mode .hero-content {
            background: rgba(255, 255, 255, 0.8);
            border: 1px solid rgba(41, 128, 185, 0.3);
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 12px;
            line-height: 1.2;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
        }

        .english-name {
            font-size: 2rem;
            margin-bottom: 15px;
            color: var(--accent);
            font-weight: 600;
        }

        .hero p {
            font-size: 1.2rem;
            margin: 0 auto 25px;
            color: var(--light);
            max-width: 700px;
            position: relative;
        }

        .light-mode .hero p {
            color: #2c3e50;
        }

        .about {
            position: relative;
            overflow: hidden;
        }

        .about::before {
            content: '';
            position: absolute;
            top: 50%;
            right: -100px;
            width: 200px;
            height: 200px;
            background: linear-gradient(135deg, var(--accent) 0%, var(--accent3) 100%);
            border-radius: 50%;
            opacity: 0.1;
            filter: blur(20px);
        }

        .about-content {
            display: flex;
            gap: 35px;
            align-items: center;
        }

        .about-text {
            flex: 1;
        }

        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 15px;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            position: relative;
            padding-bottom: 10px;
        }

        .about-text h3::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 3px;
            background: linear-gradient(to right, var(--accent), var(--accent3));
        }

        .about-text p {
            margin-bottom: 15px;
            color: #d1e0e8;
            font-size: 1.05rem;
        }

        .light-mode .about-text p {
            color: #4a5568;
        }

        .about-details {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            margin-top: 25px;
        }

        .detail-item {
            background: rgba(26, 42, 58, 0.7);
            padding: 18px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid rgba(52, 152, 219, 0.2);
            position: relative;
            overflow: hidden;
        }

        .light-mode .detail-item {
            background: rgba(255, 255, 255, 0.75);
            border: 1px solid rgba(41, 128, 185, 0.2);
        }

        .detail-item:hover {
            transform: translateY(-5px);
            border-color: var(--accent);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }

        .detail-item::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 100%;
            background: linear-gradient(to bottom, var(--accent), var(--accent3));
        }

        .detail-item i {
            font-size: 2rem;
            margin-bottom: 12px;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            transition: var(--transition);
        }

        .detail-item:hover i {
            transform: scale(1.1);
        }

        .detail-item h4 {
            font-size: 1.3rem;
            margin-bottom: 8px;
            color: white;
        }

        .light-mode .detail-item h4 {
            color: #2c3e50;
        }

        .detail-item p {
            color: #b0c4d9;
            font-size: 0.95rem;
        }

        .light-mode .detail-item p {
            color: #4a5568;
        }

        .skills {
            position: relative;
        }

        .skills::before {
            content: '';
            position: absolute;
            top: 10%;
            left: -50px;
            width: 150px;
            height: 150px;
            background: linear-gradient(135deg, var(--accent) 0%, var(--accent3) 100%);
            border-radius: 50%;
            opacity: 0.1;
            filter: blur(20px);
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
        }

        .skill-category {
            background: rgba(26, 42, 58, 0.7);
            padding: 18px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            border: 1px solid rgba(52, 152, 219, 0.2);
            position: relative;
            z-index: 2;
            transition: var(--transition);
        }

        .light-mode .skill-category {
            background: rgba(255, 255, 255, 0.75);
            border: 1px solid rgba(41, 128, 185, 0.2);
        }

        .skill-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }

        .skill-category h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            position: relative;
            padding-bottom: 6px;
        }

        .skill-category h3::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 2px;
            background: linear-gradient(to right, var(--accent), var(--accent3));
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
        }

        .skill-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            background: rgba(13, 27, 38, 0.5);
            padding: 12px;
            border-radius: var(--radius);
            transition: var(--transition);
        }

        .light-mode .skill-item {
            background: rgba(255, 255, 255, 0.5);
        }

        .skill-item:hover {
            transform: translateY(-3px);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }

        .skill-name {
            font-size: 0.95rem;
            margin-bottom: 8px;
            color: white;
            font-weight: 600;
        }

        .light-mode .skill-name {
            color: #2c3e50;
        }

        .skill-percentage {
            font-size: 1.3rem;
            font-weight: 700;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 6px;
        }

        .skill-bar {
            width: 100%;
            height: 6px;
            background: rgba(52, 152, 219, 0.2);
            border-radius: 3px;
            overflow: hidden;
        }

        .light-mode .skill-bar {
            background: rgba(41, 128, 185, 0.2);
        }

        .skill-progress {
            height: 100%;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            border-radius: 3px;
            position: relative;
            transition: width 1.5s ease-in-out;
        }

        .experiences {
            position: relative;
            overflow: hidden;
        }

        .experiences-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
            gap: 25px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .experience-card {
            background: rgba(26, 42, 58, 0.8);
            padding: 20px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            position: relative;
            border: 1px solid rgba(52, 152, 219, 0.3);
            transition: var(--transition);
        }

        .light-mode .experience-card {
            background: rgba(255, 255, 255, 0.8);
            border: 1px solid rgba(41, 128, 185, 0.3);
        }

        .experience-card:hover {
            transform: translateY(-4px);
            border-color: var(--accent);
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.12);
        }

        .experience-card h3 {
            font-size: 1.4rem;
            margin-bottom: 10px;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .experience-card .date {
            display: block;
            font-weight: 600;
            margin-bottom: 12px;
            color: var(--accent);
            font-size: 1rem;
            padding: 5px 10px;
            background: rgba(52, 152, 219, 0.15);
            border-radius: var(--radius);
            display: inline-block;
        }

        .light-mode .experience-card .date {
            background: rgba(41, 128, 185, 0.15);
        }

        .experience-card ul {
            padding-right: 0;
            margin-top: 12px;
            list-style: none;
        }

        .experience-card ul li {
            margin-bottom: 10px;
            color: #d1e0e8;
            font-size: 0.95rem;
            position: relative;
            padding-right: 15px;
        }

        .light-mode .experience-card ul li {
            color: #4a5568;
        }

        .experience-card ul li::before {
            content: '';
            position: absolute;
            top: 8px;
            right: 0;
            width: 6px;
            height: 6px;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            border-radius: 50%;
        }

        .interests {
            padding: 60px 0;
        }

        .interests-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 20px;
            max-width: 1000px;
            margin: 0 auto;
        }

        .interest-card {
            background: rgba(26, 42, 58, 0.7);
            padding: 20px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            border: 1px solid rgba(52, 152, 219, 0.2);
            text-align: center;
            transition: var(--transition);
        }

        .light-mode .interest-card {
            background: rgba(255, 255, 255, 0.75);
            border: 1px solid rgba(41, 128, 185, 0.2);
        }

        .interest-card:hover {
            transform: translateY(-5px);
            border-color: var(--accent);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.12);
        }

        .interest-card i {
            font-size: 2.5rem;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 15px;
            transition: var(--transition);
        }

        .interest-card:hover i {
            transform: scale(1.1);
        }

        .interest-card h3 {
            font-size: 1.5rem;
            margin-bottom: 12px;
            color: white;
        }

        .light-mode .interest-card h3 {
            color: #2c3e50;
        }

        .interest-card p {
            color: #b0c4d9;
            font-size: 0.95rem;
        }

        .light-mode .interest-card p {
            color: #4a5568;
        }

        .contact {
            color: white;
            position: relative;
            overflow: hidden;
            padding: 60px 0;
        }

        .contact::before {
            content: '';
            position: absolute;
            bottom: -50px;
            right: -50px;
            width: 200px;
            height: 200px;
            background: linear-gradient(135deg, var(--accent) 0%, var(--accent3) 100%);
            border-radius: 50%;
            opacity: 0.1;
            filter: blur(20px);
        }

        .contact-container {
            max-width: 800px;
            margin: 0 auto;
            padding: 25px;
            background: rgba(26, 42, 58, 0.7);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            border: 1px solid rgba(52, 152, 219, 0.3);
        }

        .light-mode .contact-container {
            background: rgba(255, 255, 255, 0.75);
            border: 1px solid rgba(41, 128, 185, 0.3);
        }

        .contact-info {
            text-align: center;
        }

        .contact-info h3 {
            font-size: 1.6rem;
            margin-bottom: 15px;
            color: white;
        }

        .light-mode .contact-info h3 {
            color: #2c3e50;
        }

        .contact-info p {
            font-size: 1.05rem;
            margin-bottom: 20px;
            color: #d1e0e8;
        }

        .light-mode .contact-info p {
            color: #4a5568;
        }

        .contact-details {
            margin-bottom: 20px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            background: rgba(13, 27, 38, 0.5);
            padding: 12px;
            border-radius: var(--radius);
            border: 1px solid rgba(52, 152, 219, 0.3);
            transition: var(--transition);
            cursor: pointer;
        }

        .light-mode .contact-item {
            background: rgba(255, 255, 255, 0.5);
            border: 1px solid rgba(41, 128, 185, 0.3);
        }

        .contact-item:hover {
            transform: translateY(-3px);
            border-color: var(--accent);
        }

        .contact-item i {
            width: 40px;
            height: 40px;
            background: rgba(52, 152, 219, 0.15);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-left: 10px;
            font-size: 1.2rem;
            transition: var(--transition);
            color: var(--accent);
        }

        .light-mode .contact-item i {
            background: rgba(41, 128, 185, 0.15);
        }

        footer {
            background: var(--primary-dark);
            color: white;
            padding: 30px 0 15px;
            text-align: center;
            border-top: 1px solid rgba(52, 152, 219, 0.2);
            position: relative;
        }

        .light-mode footer {
            background: #dde1e5;
            border-top: 1px solid rgba(41, 128, 185, 0.2);
        }

        .footer-logo {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 15px;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            list-style: none;
            margin: 25px 0;
            flex-wrap: wrap;
        }

        .footer-links li {
            margin: 0 12px;
        }

        .footer-links a {
            color: var(--light);
            text-decoration: none;
            transition: var(--transition);
            font-size: 0.95rem;
            position: relative;
            padding-bottom: 3px;
        }

        .light-mode .footer-links a {
            color: #2c3e50;
        }

        .footer-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: var(--accent);
        }

        .footer-links a:hover::after {
            width: 100%;
        }

        .copyright {
            margin-top: 25px;
            padding-top: 15px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: var(--gray);
            font-size: 0.85rem;
        }

        .light-mode .copyright {
            border-top: 1px solid rgba(0, 0, 0, 0.1);
        }

        .animate-on-scroll {
            opacity: 0;
            transform: translateY(25px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .animate-on-scroll.animated {
            opacity: 1;
            transform: translateY(0);
        }

        /* تحسين أيقونات التواصل الاجتماعي */
        .social-icons {
            display: flex;
            gap: 12px;
            margin-top: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .social-icons a {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            width: 55px;
            height: 55px;
            background: rgba(26, 42, 58, 0.7);
            border-radius: 50%;
            color: var(--accent);
            font-size: 1.5rem;
            transition: var(--transition);
            border: 1px solid rgba(52, 152, 219, 0.3);
            text-decoration: none;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .light-mode .social-icons a {
            background: rgba(255, 255, 255, 0.7);
            border: 1px solid rgba(41, 128, 185, 0.3);
        }

        .social-icons a::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 0;
            background: linear-gradient(to right, var(--accent), var(--accent3));
            transition: var(--transition);
            z-index: -1;
        }

        .social-icons a:hover {
            transform: translateY(-5px);
            color: white;
            border-color: var(--accent);
            box-shadow: 0 5px 12px rgba(52, 152, 219, 0.25);
        }

        .social-icons a:hover::before {
            height: 100%;
        }

        .social-icons span {
            font-size: 0.65rem;
            margin-top: 2px;
            opacity: 0;
            transition: var(--transition);
            position: absolute;
            bottom: -15px;
            width: 100%;
            text-align: center;
        }

        .social-icons a:hover span {
            opacity: 1;
            bottom: 3px;
        }

        .social-icons a i {
            transition: var(--transition);
        }

        .social-icons a:hover i {
            transform: translateY(-6px);
        }

        @media (max-width: 1200px) {
            .hero {
                height: auto;
                padding-top: 90px;
            }
            
            .hero-content {
                text-align: center;
            }
            
            .about-content {
                flex-direction: column;
            }
        }

        @media (max-width: 992px) {
            .section-title h2 {
                font-size: 2rem;
            }
            
            .hero h1 {
                font-size: 2.6rem;
            }
            
            .english-name {
                font-size: 1.8rem;
            }
            
            .skills-container {
                grid-template-columns: 1fr;
            }
            
            .about-details {
                grid-template-columns: 1fr;
            }
            
            .experiences-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }

            .nav-links {
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: var(--primary);
                flex-direction: column;
                align-items: center;
                padding: 20px 0;
                box-shadow: var(--shadow);
                clip-path: polygon(0 0, 100% 0, 100% 0, 0 0);
                transition: var(--transition);
            }
            
            .light-mode .nav-links {
                background: #f0f2f5;
            }

            .nav-links.active {
                clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%);
            }

            .nav-links li {
                margin: 12px 0;
            }
            
            .section-title h2 {
                font-size: 1.8rem;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .english-name {
                font-size: 1.6rem;
            }
            
            .hero p {
                font-size: 1.05rem;
            }
            
            .experience-card {
                padding: 18px;
            }
            
            .social-icons a {
                width: 50px;
                height: 50px;
                font-size: 1.4rem;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .english-name {
                font-size: 1.4rem;
            }
            
            .detail-item h4 {
                font-size: 1.2rem;
            }
            
            .section-title h2 {
                font-size: 1.6rem;
            }
            
            .social-icons a {
                width: 45px;
                height: 45px;
                font-size: 1.3rem;
            }
            
            .contact-item {
                padding: 10px;
            }
            
            .contact-item span {
                font-size: 0.85rem;
            }
            
            .skills-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div id="tech-background"></div>
    
    <div class="theme-toggle" id="themeToggle">
        <i class="fas fa-moon"></i>
    </div>
    
    <header>
        <div class="container">
            <nav>
                <a href="#" class="logo">Yamen Raslan</a>
                <div class="menu-toggle" id="menuToggle">
                    <i class="fas fa-bars"></i>
                </div>
                <ul class="nav-links" id="navLinks">
                    <li><a href="#home">الرئيسية</a></li>
                    <li><a href="#about">عني</a></li>
                    <li><a href="#skills">المهارات</a></li>
                    <li><a href="#experiences">الخبرات</a></li>
                    <li><a href="#interests">الاهتمامات</a></li>
                    <li><a href="#contact">التواصل</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content animate-on-scroll">
                <h1><span>يامن رسلان</span></h1>
                <div class="english-name">Yamen Raslan</div>
                <p>مهندس معلوماتية متخصص في إدارة الأنظمة وتطوير البرمجيات، مع خبرة واسعة في إدارة الأعمال والصيانة الإلكترونية. أسعى لتطبيق حلول تقنية مبتكرة تعزز كفاءة المؤسسات وتحقق أهدافها.</p>
            </div>
        </div>
    </section>

    <section class="about" id="about">
        <div class="container">
            <div class="section-title">
                <h2>عني</h2>
            </div>
            <div class="about-content">
                <div class="about-text animate-on-scroll">
                    <h3>مهندس معلوماتية ومدير أنظمة</h3>
                    <p>أنا يامن رسلان، طالب في كلية الهندسة المعلوماتية بجامعة حلب، أتممت حتى الآن 4 سنوات من الدراسة. أمتلك خبرة عملية في إدارة مراكز إلكترونيات، وصيانة الأجهزة، وإدارة أنظمة Odoo في الشركات.</p>
                    <p>أؤمن بالجمع بين المعرفة الأكاديمية والتطبيق العملي لتقديم حلول تقنية مبتكرة تلبي احتياجات السوق وتحقق أهداف العملاء والشركات.</p>
                    
                    <div class="about-details">
                        <div class="detail-item animate-on-scroll">
                            <i class="fas fa-user-graduate"></i>
                            <h4>التعليم</h4>
                            <p>كلية الهندسة المعلوماتية - جامعة حلب (2019 - حتى الآن)</p>
                        </div>
                        <div class="detail-item animate-on-scroll">
                            <i class="fas fa-language"></i>
                            <h4>اللغات</h4>
                            <p>العربية (اللغة الأم)<br>الإنجليزية (متوسطة)</p>
                        </div>
                        <div class="detail-item animate-on-scroll">
                            <i class="fas fa-calendar-alt"></i>
                            <h4>العمر</h4>
                            <p id="ageDisplay">جاري حساب العمر...</p>
                        </div>
                        <div class="detail-item animate-on-scroll">
                            <i class="fas fa-star"></i>
                            <h4>الاهتمامات</h4>
                            <p>تطوير البرمجيات، إدارة الأنظمة، التجارة الإلكترونية، مجال الـ IT وإيجاد الحلول التقنية</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="skills" id="skills">
        <div class="container">
            <div class="section-title">
                <h2>المهارات</h2>
            </div>
            <div class="skills-container">
                <div class="skill-category animate-on-scroll">
                    <h3>المهارات التقنية</h3>
                    <div class="skills-grid">
                        <div class="skill-item">
                            <div class="skill-name">Java</div>
                            <div class="skill-percentage">85%</div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 85%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-name">Python</div>
                            <div class="skill-percentage">90%</div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 90%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-name">C++</div>
                            <div class="skill-percentage">80%</div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 80%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-name">نظام Odoo</div>
                            <div class="skill-percentage">95%</div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 95%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-name">صيانة الأجهزة</div>
                            <div class="skill-percentage">85%</div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 85%"></div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-category animate-on-scroll">
                    <h3>المهارات العملية والإدارية</h3>
                    <div class="skills-grid">
                        <div class="skill-item">
                            <div class="skill-name">إدارة الأعمال</div>
                            <div class="skill-percentage">90%</div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 90%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-name">التواصل مع العملاء</div>
                            <div class="skill-percentage">95%</div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 95%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-name">إدارة الفريق</div>
                            <div class="skill-percentage">85%</div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 85%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-name">Microsoft Office</div>
                            <div class="skill-percentage">90%</div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 90%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-name">سرعة التعلم</div>
                            <div class="skill-percentage">95%</div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 95%"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="experiences" id="experiences">
        <div class="container">
            <div class="section-title">
                <h2>الخبرات المهنية</h2>
            </div>
            <div class="experiences-grid">
                <div class="experience-card animate-on-scroll">
                    <h3>مدير مركز تجارة وصيانة إلكترونيات</h3>
                    <span class="date">2020 - 2024</span>
                    <ul>
                        <li>التعامل المباشر مع الزبائن وشرح مواصفات الأجهزة الإلكترونية</li>
                        <li>تسيير العمل بشكل أمثل عبر إعطاء مهام للموظفين</li>
                        <li>المشرف على جميع عمليات الصيانة لتحقيق الكفاءة الأمثل</li>
                        <li>إدارة المخزون والمشتريات وتحديث قاعدة بيانات المنتجات</li>
                    </ul>
                </div>
                
                <div class="experience-card animate-on-scroll">
                    <h3>مساعد مدير معلوماتية - شركة كارتل غروب</h3>
                    <span class="date">2024 - 2025</span>
                    <ul>
                        <li>حل المشاكل التقنية التي تواجه الموظفين ضمن سيستم Odoo</li>
                        <li>مسؤول قسم الصيانة لجميع أجهزة الشركة</li>
                        <li>كشف الثغرات ومطالبة الفريق البرمجي بإصلاح المشاكل</li>
                        <li>اختبار التعديلات البرمجية قبل اعتمادها على السيستم</li>
                        <li>سحب تقارير من سيستم Odoo ومتابعة نشاط الشركة</li>
                        <li>العمل على الواجهة المحاسبية ومتابعة القيود المالية</li>
                        <li>إعداد تقارير أداء الموظفين ومتابعة مؤشرات الأداء</li>
                    </ul>
                </div>
                
                <div class="experience-card animate-on-scroll">
                    <h3>تسويق عبر الانترنت والتعامل مع العملاء</h3>
                    <span class="date">2020 - حتى الآن</span>
                    <ul>
                        <li>نشر إعلانات عبر تطبيق Facebook ومشاركته</li>
                        <li>التواصل مع العملاء للإجابة عن استفساراتهم</li>
                        <li>إدارة الحملات التسويقية عبر منصات التواصل الاجتماعي</li>
                        <li>تحليل أداء الحملات التسويقية وتقديم تقارير شهرية</li>
                        <li>إدارة حسابات التواصل الاجتماعي للعديد من العلامات التجارية</li>
                    </ul>
                </div>
                
                <div class="experience-card animate-on-scroll">
                    <h3>مدرس مادة التقانة والمعلومات - مدرسة مدينة العلم</h3>
                    <span class="date">2025</span>
                    <ul>
                        <li>تدريس منهاج المعلوماتية لطلاب المرحلة الثانوية</li>
                        <li>تطوير طرق تعليم تفاعلية لزيادة استيعاب الطلاب</li>
                        <li>تدريب الطلاب على أساسيات البرمجة وتطوير التطبيقات</li>
                        <li>تنظيم مسابقات تقنية لتنمية المهارات الإبداعية لدى الطلاب</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <section class="interests" id="interests">
        <div class="container">
            <div class="section-title">
                <h2>الاهتمامات التقنية</h2>
            </div>
            <div class="interests-container">
                <div class="interest-card animate-on-scroll">
                    <i class="fas fa-brain"></i>
                    <h3>الذكاء الاصطناعي</h3>
                    <p>استخدام تقنيات الذكاء الاصطناعي لإيجاد حلول تقنية مبتكرة لمختلف التحديات في مجال الأعمال والتكنولوجيا.</p>
                </div>
                
                <div class="interest-card animate-on-scroll">
                    <i class="fas fa-laptop-code"></i>
                    <h3>تطوير البرمجيات</h3>
                    <p>تصميم وتطوير تطبيقات ويب وموبايل باستخدام أحدث التقنيات، مع التركيز على تجربة المستخدم والأداء العالي.</p>
                </div>
                
                <div class="interest-card animate-on-scroll">
                    <i class="fas fa-network-wired"></i>
                    <h3>إدارة الأنظمة والشبكات</h3>
                    <p>تصميم وتنفيذ حلول الشبكات وإدارة الأنظمة لضمان استقرار وأمن البنية التحتية التقنية للمؤسسات.</p>
                </div>
                
                <div class="interest-card animate-on-scroll">
                    <i class="fas fa-graduation-cap"></i>
                    <h3>تطوير الخبرات</h3>
                    <p>التوسع في المعرفة والتعرف على مجالات أوسع في عالم التكنولوجيا لتطوير المهارات الشخصية والمهنية.</p>
                </div>
            </div>
        </div>
    </section>

    <section class="contact" id="contact">
        <div class="container">
            <div class="section-title">
                <h2>تواصل معي</h2>
            </div>
            <div class="contact-container animate-on-scroll">
                <div class="contact-info">
                    <h3>دعنا نتحدث عن فرص العمل والتعاون!</h3>
                    <p>أنا متاح دائمًا للعمل الحر أو فرص العمل بدوام كامل. يمكنك التواصل معي مباشرة عبر المعلومات التالية.</p>
                    
                    <div class="contact-details">
                        <div class="contact-item" onclick="window.location.href='tel:+963943381488'">
                            <i class="fas fa-phone"></i>
                            <span>+963 943 381 488</span>
                        </div>
                        <div class="contact-item" onclick="window.location.href='https://wa.me/963943381488'">
                            <i class="fab fa-whatsapp"></i>
                            <span>+963 943 381 488</span>
                        </div>
                        <div class="contact-item" onclick="window.location.href='mailto:yamenraslan.syria@gmail.com'">
                            <i class="fas fa-envelope"></i>
                            <span>yamenraslan.syria@gmail.com</span>
                        </div>
                        <div class="contact-item">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>حلب، سوريا</span>
                        </div>
                    </div>
                    
                    <div class="social-icons">
                        <a href="mailto:yamenraslan.syria@gmail.com" title="البريد الإلكتروني">
                            <i class="fas fa-envelope"></i>
                            <span>البريد</span>
                        </a>
                        <a href="https://www.facebook.com/yamen.raslan.90/" target="_blank" title="فيسبوك">
                            <i class="fab fa-facebook-f"></i>
                            <span>فيسبوك</span>
                        </a>
                        <a href="https://www.instagram.com/yamen.raslan/" target="_blank" title="إنستغرام">
                            <i class="fab fa-instagram"></i>
                            <span>إنستغرام</span>
                        </a>
                        <a href="https://t.me/raslan_yamen" target="_blank" title="تلغرام">
                            <i class="fab fa-telegram-plane"></i>
                            <span>تلغرام</span>
                        </a>
                        <a href="https://wa.me/963943381488" target="_blank" title="واتساب">
                            <i class="fab fa-whatsapp"></i>
                            <span>واتساب</span>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-logo">يامن رسلان</div>
            <ul class="footer-links">
                <li><a href="#home">الرئيسية</a></li>
                <li><a href="#about">عني</a></li>
                <li><a href="#skills">المهارات</a></li>
                <li><a href="#experiences">الخبرات</a></li>
                <li><a href="#interests">الاهتمامات</a></li>
                <li><a href="#contact">التواصل</a></li>
            </ul>
            <div class="copyright">
                <p>© 2025 يامن رسلان. جميع الحقوق محفوظة.</p>
            </div>
        </div>
    </footer>

    <script>
        // Initialize 3D background
        function initBackground() {
            const scene = new THREE.Scene();
            const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
            const renderer = new THREE.WebGLRenderer({ alpha: true });
            renderer.setSize(window.innerWidth, window.innerHeight);
            document.getElementById('tech-background').appendChild(renderer.domElement);

            // Create geometric shapes
            const geometry = new THREE.TorusGeometry(10, 3, 16, 100);
            const material = new THREE.MeshBasicMaterial({ 
                color: 0x3498db, 
                wireframe: true,
                transparent: true,
                opacity: 0.1
            });
            const torus = new THREE.Mesh(geometry, material);
            scene.add(torus);

            const geometry2 = new THREE.IcosahedronGeometry(7, 0);
            const material2 = new THREE.MeshBasicMaterial({ 
                color: 0x5dade2, 
                wireframe: true,
                transparent: true,
                opacity: 0.1
            });
            const icosahedron = new THREE.Mesh(geometry2, material2);
            scene.add(icosahedron);

            camera.position.z = 30;

            // Animation
            function animate() {
                requestAnimationFrame(animate);

                torus.rotation.x += 0.001;
                torus.rotation.y += 0.002;

                icosahedron.rotation.x -= 0.001;
                icosahedron.rotation.y -= 0.002;

                renderer.render(scene, camera);
            }

            animate();

            // Handle window resize
            window.addEventListener('resize', () => {
                camera.aspect = window.innerWidth / window.innerHeight;
                camera.updateProjectionMatrix();
                renderer.setSize(window.innerWidth, window.innerHeight);
            });
        }

        function calculateAge() {
            const birthDate = new Date(2001, 6, 22);
            const today = new Date();
            
            let age = today.getFullYear() - birthDate.getFullYear();
            const monthDiff = today.getMonth() - birthDate.getMonth();
            
            if (monthDiff < 0 || (monthDiff === 0 && today.getDate() < birthDate.getDate())) {
                age--;
            }
            
            document.getElementById('ageDisplay').textContent = `${age} سنة`;
        }

        // Theme toggle functionality
        const themeToggle = document.getElementById('themeToggle');
        const themeIcon = themeToggle.querySelector('i');
        
        themeToggle.addEventListener('click', () => {
            document.body.classList.toggle('light-mode');
            
            if (document.body.classList.contains('light-mode')) {
                themeIcon.classList.remove('fa-moon');
                themeIcon.classList.add('fa-sun');
            } else {
                themeIcon.classList.remove('fa-sun');
                themeIcon.classList.add('fa-moon');
            }
        });

        const menuToggle = document.getElementById('menuToggle');
        const navLinks = document.getElementById('navLinks');
        
        menuToggle.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            menuToggle.classList.toggle('active');
        });
        
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                menuToggle.classList.remove('active');
            });
        });
        
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                window.scrollTo({
                    top: targetElement.offsetTop - 70,
                    behavior: 'smooth'
                });
            });
        });
        
        const animateElements = document.querySelectorAll('.animate-on-scroll');
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animated');
                    
                    // Animate skill bars
                    if (entry.target.classList.contains('skill-progress')) {
                        const width = entry.target.style.width;
                        entry.target.style.width = '0';
                        setTimeout(() => {
                            entry.target.style.width = width;
                        }, 300);
                    }
                }
            });
        }, {
            threshold: 0.1
        });
        
        animateElements.forEach(element => {
            observer.observe(element);
        });
        
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 80) {
                header.style.boxShadow = '0 3px 15px rgba(0, 0, 0, 0.25)';
                header.style.background = 'rgba(26, 42, 58, 0.98)';
                
                if (document.body.classList.contains('light-mode')) {
                    header.style.background = 'rgba(240, 242, 245, 0.98)';
                }
            } else {
                header.style.boxShadow = 'var(--shadow)';
                header.style.background = 'rgba(26, 42, 58, 0.95)';
                
                if (document.body.classList.contains('light-mode')) {
                    header.style.background = 'rgba(240, 242, 245, 0.95)';
                }
            }
        });
        
        window.addEventListener('load', () => {
            document.body.classList.add('loaded');
            calculateAge();
            initBackground();
            
            setTimeout(() => {
                document.querySelectorAll('.skill-progress').forEach(progress => {
                    const width = progress.style.width;
                    progress.style.width = '0';
                    setTimeout(() => {
                        progress.style.width = width;
                    }, 500);
                });
            }, 500);
        });
    </script>
</body>
</html>
