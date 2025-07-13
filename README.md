# nepotrebuju_debila


.manifesto-story {
                padding: 2rem;
                margin: 2rem 0;
            }

            .manifesto-story::before {
                top: 1rem;
                right: 1.5rem;
                font-size: 2rem;
            }

            .story-text {
                font-size: 1.1rem;
            }

            .story-emphasis {
                font-size: 1.2rem;
                margin-top: 1.5rem;
                padding-top: 1.5rem;
            }            .manifesto-points {
                grid-template-columns: 1fr;
                gap: 1.5rem;
            }

            .point-item {
                padding: 1.5rem;
                gap: 1rem;
            }

            .point-emoji {
                font-size: 2rem;
            }<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ND – Nepotřebuju debila</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Playfair+Display:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-pink: #FF1493;
            --primary-red: #DC143C;
            --secondary-pink: #FFB6C1;
            --dark-purple: #2D1B69;
            --deep-black: #0A0A0A;
            --soft-white: #FAFAFA;
            --glass-bg: rgba(255, 255, 255, 0.1);
            --glass-border: rgba(255, 255, 255, 0.2);
            --text-light: rgba(255, 255, 255, 0.9);
            --text-dark: #1A1A1A;
            --gradient-primary: linear-gradient(135deg, #FF1493 0%, #DC143C 50%, #8B008B 100%);
            --gradient-secondary: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --gradient-dark: linear-gradient(135deg, #0A0A0A 0%, #2D1B69 100%);
            --gradient-glass: linear-gradient(135deg, rgba(255, 255, 255, 0.1) 0%, rgba(255, 255, 255, 0.05) 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            line-height: 1.6;
            color: var(--text-dark);
            background: var(--deep-black);
            overflow-x: hidden;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 24px;
        }

        /* Glassmorphism Header */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            backdrop-filter: blur(20px);
            background: rgba(10, 10, 10, 0.8);
            border-bottom: 1px solid var(--glass-border);
            transition: all 0.3s ease;
        }

        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-primary);
            opacity: 0.1;
            pointer-events: none;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
            position: relative;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 2.5rem;
            font-weight: 900;
            background: var(--gradient-primary);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 30px rgba(255, 20, 147, 0.5);
            letter-spacing: -0.02em;
            display: flex;
            align-items: center;
            gap: 0.8rem;
        }

        .logo-icons {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo-cross {
            color: var(--primary-red);
            font-size: 2rem;
            font-weight: 900;
            text-shadow: 0 0 20px rgba(220, 20, 60, 0.5);
            animation: pulse 2s infinite;
        }

        .logo-smile {
            font-size: 2rem;
            color: var(--primary-pink);
            text-shadow: 0 0 20px rgba(255, 20, 147, 0.5);
            animation: bounce 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-5px); }
            60% { transform: translateY(-3px); }
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 2.5rem;
        }

        nav a {
            color: var(--text-light);
            text-decoration: none;
            font-weight: 500;
            font-size: 0.95rem;
            position: relative;
            transition: all 0.3s ease;
            cursor: pointer;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }

        nav a::before {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gradient-primary);
            transition: width 0.3s ease;
        }

        nav a:hover::before,
        nav a.active::before {
            width: 100%;
        }

        nav a:hover {
            color: var(--primary-pink);
            text-shadow: 0 0 10px rgba(255, 20, 147, 0.5);
        }

        /* Main Content */
        main {
            margin-top: 80px;
        }

        .section {
            display: none;
            min-height: 100vh;
            position: relative;
        }

        .section.active {
            display: block;
            animation: fadeInUp 0.6s ease-out;
        }

        .section-header {
            text-align: center;
            padding: 4rem 0 2rem;
            background: var(--gradient-dark);
            position: relative;
            overflow: hidden;
        }

        .section-header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="50" cy="50" r="1" fill="white" opacity="0.03"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
            opacity: 0.1;
        }

        .section-title {
            font-family: 'Playfair Display', serif;
            font-size: 4rem;
            font-weight: 800;
            background: var(--gradient-primary);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 1rem;
            position: relative;
            z-index: 1;
        }

        .section-subtitle {
            font-size: 1.2rem;
            color: var(--text-light);
            font-weight: 300;
            max-width: 600px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: var(--gradient-primary);
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at 30% 70%, rgba(255, 255, 255, 0.1) 0%, transparent 50%),
                        radial-gradient(circle at 70% 30%, rgba(0, 0, 0, 0.1) 0%, transparent 50%);
            animation: float 6s ease-in-out infinite;
        }

        .hero-content {
            text-align: center;
            position: relative;
            z-index: 1;
        }

        .hero-title {
            font-family: 'Playfair Display', serif;
            font-size: clamp(3rem, 8vw, 6rem);
            font-weight: 900;
            color: white;
            margin-bottom: 1.5rem;
            text-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
            letter-spacing: -0.02em;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .hero-icons {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .hero-cross {
            color: #FF6B6B;
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            text-shadow: 0 0 30px rgba(255, 107, 107, 0.7);
            animation: rotateAndPulse 3s ease-in-out infinite;
        }

        .hero-smile {
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            text-shadow: 0 0 30px rgba(255, 255, 255, 0.5);
            animation: wiggle 2.5s ease-in-out infinite;
        }

        @keyframes rotateAndPulse {
            0%, 100% { transform: rotate(0deg) scale(1); }
            25% { transform: rotate(-5deg) scale(1.1); }
            50% { transform: rotate(0deg) scale(1.2); }
            75% { transform: rotate(5deg) scale(1.1); }
        }

        @keyframes wiggle {
            0%, 100% { transform: rotate(0deg) scale(1); }
            25% { transform: rotate(5deg) scale(1.05); }
            50% { transform: rotate(-5deg) scale(1.1); }
            75% { transform: rotate(3deg) scale(1.05); }
        }

        .hero-subtitle {
            font-size: clamp(1.2rem, 3vw, 1.8rem);
            color: rgba(255, 255, 255, 0.9);
            margin-bottom: 3rem;
            font-weight: 300;
            letter-spacing: 0.02em;
        }

        .hero-cta {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: rgba(255, 255, 255, 0.1);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            font-size: 0.9rem;
        }

        .hero-cta:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        /* Glass Cards */
        .glass-card {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            padding: 2.5rem;
            margin-bottom: 2rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .glass-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 1px;
            background: var(--gradient-primary);
            opacity: 0.5;
        }

        .glass-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(255, 20, 147, 0.1);
            border-color: var(--primary-pink);
        }

        /* Manifesto Section */
        .manifesto {
            background: var(--soft-white);
            padding: 6rem 0;
            position: relative;
        }

        .manifesto::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent 49%, rgba(255, 20, 147, 0.02) 50%, transparent 51%);
        }

        .manifesto-content {
            max-width: 900px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }

        .manifesto-title {
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            font-weight: 700;
            color: var(--text-dark);
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .manifesto-title::after {
            content: '';
            position: absolute;
            bottom: -20px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--gradient-primary);
            border-radius: 2px;
        }

        .manifesto-text {
            font-size: 1.3rem;
            line-height: 1.8;
            color: var(--text-dark);
            margin-bottom: 2rem;
            font-weight: 400;
            opacity: 0.9;
        }

        .manifesto-highlight {
            font-weight: 700;
            color: var(--primary-red);
            font-size: 1.4rem;
            text-align: center;
            padding: 2rem;
            background: linear-gradient(135deg, rgba(255, 20, 147, 0.05) 0%, rgba(220, 20, 60, 0.05) 100%);
            border-radius: 15px;
            border-left: 4px solid var(--primary-pink);
            margin-bottom: 3rem;
        }

        .manifesto-story {
            background: linear-gradient(135deg, rgba(255, 20, 147, 0.08) 0%, rgba(220, 20, 60, 0.08) 100%);
            padding: 3rem;
            border-radius: 20px;
            margin: 3rem 0;
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(255, 20, 147, 0.15);
        }

        .manifesto-story::before {
            content: '💭';
            position: absolute;
            top: 1.5rem;
            right: 2rem;
            font-size: 2.5rem;
            opacity: 0.3;
            animation: thoughtBubble 4s ease-in-out infinite;
        }

        .story-text {
            font-size: 1.2rem;
            line-height: 1.8;
            color: var(--text-dark);
            margin-bottom: 1.5rem;
            font-style: italic;
        }

        .story-text strong {
            color: var(--primary-red);
            font-weight: 800;
            font-style: normal;
        }

        .story-text em {
            color: var(--primary-pink);
            font-weight: 600;
        }

        .story-emphasis {
            font-size: 1.3rem;
            line-height: 1.7;
            color: var(--text-dark);
            text-align: center;
            font-weight: 600;
            margin-top: 2rem;
            padding-top: 2rem;
            border-top: 2px solid rgba(255, 20, 147, 0.2);
        }

        .story-emphasis strong {
            color: var(--primary-red);
            font-weight: 800;
            font-size: 1.1em;
        }

        @keyframes thoughtBubble {
            0%, 100% { transform: translateY(0px) scale(1); opacity: 0.3; }
            50% { transform: translateY(-10px) scale(1.1); opacity: 0.6; }
        }

        .manifesto-points {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .point-item {
            display: flex;
            align-items: flex-start;
            gap: 1.5rem;
            padding: 2rem;
            background: white;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .point-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: var(--gradient-primary);
        }

        .point-item:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 50px rgba(255, 20, 147, 0.15);
        }

        .point-emoji {
            font-size: 2.5rem;
            animation: floatEmoji 3s ease-in-out infinite;
            flex-shrink: 0;
        }

        .point-content h4 {
            font-family: 'Playfair Display', serif;
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--text-dark);
            margin-bottom: 0.8rem;
        }

        .point-content p {
            color: rgba(26, 26, 26, 0.8);
            line-height: 1.6;
            font-size: 1rem;
        }

        @keyframes floatEmoji {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            33% { transform: translateY(-5px) rotate(2deg); }
            66% { transform: translateY(3px) rotate(-1deg); }
        }

        /* Content Sections */
        .content-section {
            background: var(--soft-white);
            padding: 5rem 0;
            position: relative;
        }

        .content-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2.5rem;
            margin-top: 3rem;
        }

        /* Blog Cards */
        .blog-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            position: relative;
        }

        .blog-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--gradient-primary);
        }

        .blog-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 50px rgba(255, 20, 147, 0.2);
        }

        .blog-card-content {
            padding: 2.5rem;
        }

        .blog-card h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.6rem;
            font-weight: 700;
            color: var(--text-dark);
            margin-bottom: 1rem;
            line-height: 1.3;
        }

        .blog-card .date {
            color: var(--primary-pink);
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 1rem;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }

        .blog-card p {
            color: rgba(26, 26, 26, 0.8);
            line-height: 1.7;
            font-size: 1rem;
        }

        /* Modern Forms */
        .form-container {
            max-width: 700px;
            margin: 3rem auto 0;
            background: white;
            padding: 3rem;
            border-radius: 25px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.1);
            position: relative;
            overflow: hidden;
        }

        .form-container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 6px;
            background: var(--gradient-primary);
        }

        .form-group {
            margin-bottom: 2rem;
            position: relative;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.8rem;
            color: var(--text-dark);
            font-weight: 600;
            font-size: 1rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1.2rem 1.5rem;
            border: 2px solid #E5E7EB;
            border-radius: 15px;
            font-size: 1rem;
            transition: all 0.3s ease;
            background: #F9FAFB;
            font-family: inherit;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary-pink);
            background: white;
            box-shadow: 0 0 0 3px rgba(255, 20, 147, 0.1);
        }

        .form-group textarea {
            height: 150px;
            resize: vertical;
        }

        .btn {
            background: var(--gradient-primary);
            color: white;
            padding: 1.2rem 2.5rem;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            position: relative;
            overflow: hidden;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }

        .btn:hover::before {
            left: 100%;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(255, 20, 147, 0.3);
        }

        /* Help Cards */
        .help-card {
            background: white;
            padding: 2.5rem;
            border-radius: 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        .help-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--gradient-primary);
        }

        .help-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 50px rgba(255, 20, 147, 0.2);
        }

        .help-card h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--text-dark);
            margin-bottom: 1.5rem;
        }

        .help-card .phone {
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--primary-red);
            margin-bottom: 1rem;
            font-family: 'Inter', sans-serif;
        }

        .help-card p {
            color: rgba(26, 26, 26, 0.8);
            line-height: 1.6;
        }

        /* Admin Interface */
        .admin-section {
            background: var(--gradient-glass);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 25px;
            padding: 3rem;
            margin-top: 3rem;
        }

        .admin-tabs {
            display: flex;
            gap: 1rem;
            margin-bottom: 3rem;
            flex-wrap: wrap;
        }

        .admin-tab {
            padding: 1rem 2rem;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            color: var(--text-dark);
            font-weight: 600;
            backdrop-filter: blur(10px);
        }

        .admin-tab.active {
            background: var(--gradient-primary);
            color: white;
            border-color: transparent;
        }

        .admin-tab:hover {
            transform: translateY(-2px);
        }

        .admin-content {
            display: none;
        }

        .admin-content.active {
            display: block;
            animation: fadeIn 0.3s ease;
        }

        .admin-item {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            margin-bottom: 1.5rem;
            border-left: 4px solid var(--primary-pink);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }

        .admin-item h4 {
            font-family: 'Playfair Display', serif;
            color: var(--text-dark);
            margin-bottom: 0.8rem;
            font-size: 1.3rem;
        }

        .admin-item .meta {
            color: rgba(26, 26, 26, 0.6);
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .admin-actions {
            margin-top: 1.5rem;
        }

        .admin-actions button {
            background: var(--gradient-secondary);
            color: white;
            border: none;
            padding: 0.6rem 1.5rem;
            border-radius: 25px;
            cursor: pointer;
            margin-right: 0.8rem;
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .admin-actions button:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        /* Footer */
        footer {
            background: var(--gradient-dark);
            color: var(--text-light);
            text-align: center;
            padding: 4rem 0;
            position: relative;
            overflow: hidden;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 1px;
            background: var(--gradient-primary);
        }

        footer p {
            margin-bottom: 0.8rem;
            opacity: 0.9;
        }

        /* Animations */
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

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        /* Responsive Design */
        @media (max-width: 1200px) {
            .container {
                padding: 0 20px;
            }
        }

        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1.5rem;
                padding: 1.5rem 0;
            }

            .logo {
                font-size: 2rem;
            }

            .logo-cross,
            .logo-smile {
                font-size: 1.5rem;
            }

            nav ul {
                flex-wrap: wrap;
                gap: 1.5rem;
                justify-content: center;
            }

            .section-title {
                font-size: 2.5rem;
            }

            .hero-title {
                font-size: 2.5rem;
                flex-direction: column;
                gap: 0.5rem;
            }

            .hero-icons {
                gap: 0.5rem;
            }

            .hero-cross,
            .hero-smile {
                font-size: 2rem;
            }

            .manifesto-title {
                font-size: 2.5rem;
            }

            .content-grid {
                grid-template-columns: 1fr;
                gap: 1.5rem;
            }

            .form-container {
                padding: 2rem;
                margin: 2rem auto 0;
            }

            .admin-tabs {
                justify-content: center;
            }

            .admin-tab {
                padding: 0.8rem 1.5rem;
                font-size: 0.9rem;
            }

            main {
                margin-top: 120px;
            }
        }

        @media (max-width: 480px) {
            .section-header {
                padding: 2rem 0 1rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .hero-title {
                font-size: 2rem;
                flex-direction: column;
                gap: 0.5rem;
            }

            .hero-cross,
            .hero-smile {
                font-size: 1.8rem;
            }

            .manifesto-title {
                font-size: 2rem;
            }

            .glass-card,
            .form-container {
                padding: 1.5rem;
            }

            .admin-section {
                padding: 2rem;
            }
        }

        /* Scroll animations */
        .scroll-reveal {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.6s ease;
        }

        .scroll-reveal.revealed {
            opacity: 1;
            transform: translateY(0);
        }

        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: #f1f1f1;
        }

        ::-webkit-scrollbar-thumb {
            background: var(--gradient-primary);
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--primary-red);
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    ND
                    <div class="logo-icons">
                        <span class="logo-cross">✗</span>
                        <span class="logo-smile">😊</span>
                    </div>
                </div>
                <nav>
                    <ul>
                        <li><a href="#" onclick="showSection('home')" class="active">Domů</a></li>
                        <li><a href="#" onclick="showSection('blog')">Blog</a></li>
                        <li><a href="#" onclick="showSection('zpovědnice')">Zpovědnice</a></li>
                        <li><a href="#" onclick="showSection('pomoc')">Pomoc</a></li>
                        <li><a href="#" onclick="showSection('kontakt')">Kontakt</a></li>
                        <li><a href="#" onclick="showSection('admin')">Admin</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <main>
        <!-- Home Section -->
        <section id="home" class="section active">
            <div class="hero">
                <div class="container">
                    <div class="hero-content">
                        <h1 class="hero-title">
                            <span class="hero-cross">✗</span>
                            Nepotřebuju debila
                            <span class="hero-smile">😊</span>
                        </h1>
                        <p class="hero-subtitle">Platforma pro ženy, které si zaslouží víc než toxické vztahy</p>
                        <a href="#" class="hero-cta" onclick="showSection('zpovědnice')">Sdílet příběh</a>
                    </div>
                </div>
            </div>
            
            <div class="manifesto">
                <div class="container">
                    <div class="manifesto-content">
                        <h2 class="manifesto-title">Náš manifest</h2>
                        <p class="manifesto-text">
                            <strong>ND – Nepotřebuju debila</strong> je prostor pro ženy, které se rozhodly říct NE toxickým vztahům. 
                            Není to jen o rozchodech – je to o nalezení vlastní síly, důstojnosti a hodnoty.
                        </p>
                        <p class="manifesto-text">
                            Věříme, že každá žena má právo na lásku, která ji povznáší, ne ničí. 
                            Máš právo na partnera, který tě respektuje, podporuje a miluje takovou, jaká jsi.
                        </p>
                        <p class="manifesto-text">
                            Naše komunita je zde pro tebe – abys věděla, že nejsi sama, že tvé pocity jsou validní 
                            a že existuje cesta ven. Protože opravdu nepotřebuješ debila.
                        </p>
                        <div class="manifesto-highlight">
                            Jsi silnější, než si myslíš. Zasloužíš si víc, než máš. A my jsme tu, abychom tě podpořily.
                        </div>
                        
                        <div class="manifesto-story">
                            <p class="story-text">
                                <strong>„Nepotřebuješ debila"</strong>...říká tvá kámoška, když už nemá trpělivost poslouchat, 
                                proč si mu <em>zase</em> napsala....říká tvá mamka, která ho už nikdy nechce vidět u vás doma....říká 
                                tvůj pes, když tě slyší vzlykat do polštáře a chce tě jen obejmout.
                            </p>
                            <p class="story-text">
                                A říkáme ti to i my – ale s návodem, jak se z toho opravdu dostat.
                            </p>
                            <p class="story-emphasis">
                                ND není hejt na chlapy. Je to probuzení pro každou, která zapomněla, 
                                <strong>že má právo na víc</strong>.
                            </p>
                        </div>
                        
                        <div class="manifesto-points">
                            <div class="point-item">
                                <span class="point-emoji">💪</span>
                                <div class="point-content">
                                    <h4>Najdi svou sílu</h4>
                                    <p>Každá žena v sobě má neuvěřitelnou sílu. Pomůžeme ti ji objevit a využít.</p>
                                </div>
                            </div>
                            
                            <div class="point-item">
                                <span class="point-emoji">🚫</span>
                                <div class="point-content">
                                    <h4>Řekni NE toxicitě</h4>
                                    <p>Naučíš se rozpoznat manipulaci a postavit se za sebe s důstojností.</p>
                                </div>
                            </div>
                            
                            <div class="point-item">
                                <span class="point-emoji">👭</span>
                                <div class="point-content">
                                    <h4>Najdi komunitu</h4>
                                    <p>Nejsi na to sama. Připoj se k ženám, které prošly podobnou cestou.</p>
                                </div>
                            </div>
                            
                            <div class="point-item">
                                <span class="point-emoji">✨</span>
                                <div class="point-content">
                                    <h4>Zažij svobodu</h4>
                                    <p>Objevíš, jaké to je žít bez strachu, manipulace a neustálého hodnocení.</p>
                                </div>
                            </div>
                            
                            <div class="point-item">
                                <span class="point-emoji">💖</span>
                                <div class="point-content">
                                    <h4>Zasloužíš si lásku</h4>
                                    <p>Pravou lásku, která tě povznáší, respektuje a podporuje tvé sny.</p>
                                </div>
                            </div>
                            
                            <div class="point-item">
                                <span class="point-emoji">🌟</span>
                                <div class="point-content">
                                    <h4>Buď svou hvězdou</h4>
                                    <p>Přestaň čekat na někoho, kdo tě "zachrání". Ty jsi svou vlastní záchrankou.</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Blog Section -->
        <section id="blog" class="section">
            <div class="section-header">
                <div class="container">
                    <h2 class="section-title">Blog</h2>
                    <p class="section-subtitle">Články, tipy a podpora na cestě k lepšímu životu</p>
                </div>
            </div>
            
            <div class="content-section">
                <div class="container">
                    <div class="content-grid">
                        <article class="blog-card">
                            <div class="blog-card-content">
                                <div class="date">15. července 2025</div>
                                <h3>Jak rozpoznat toxický vztah</h3>
                                <p>Toxické vztahy často začínají nevinně, ale postupně se mění v past psychického násilí. Naučte se rozpoznat varovné signály dříve, než je pozdě, a získejte sílu říct stop.</p>
                            </div>
                        </article>
                        
                        <article class="blog-card">
                            <div class="blog-card-content">
                                <div class="date">10. července 2025</div>
                                <h3>Prvních 30 dní po rozchodu</h3>
                                <p>Rozchod s toxickým partnerem je začátek, ne konec. Zde je váš průvodce prvními kroky k novému životu plnému svobody a sebevědomí.</p>
                            </div>
                        </article>
                        
                        <article class="blog-card">
                            <div class="blog-card-content">
                                <div class="date">5. července 2025</div>
                                <h3>Budování sebevědomí po traumatu</h3>
                                <p>Toxické vztahy zanechávají hluboké šrámy na duši. Projděte si cestu k obnově své sebehodnoty a objevte sílu, kterou jste možná zapomněly, že máte.</p>
                            </div>
                        </article>
                        
                        <article class="blog-card">
                            <div class="blog-card-content">
                                <div class="date">1. července 2025</div>
                                <h3>Healthy boundaries – nastavení hranic</h3>
                                <p>Hranice nejsou zeď – jsou to dveře s klíčem v tvých rukou. Naučte se je správně nastavit a chránit své fyzické i psychické zdraví.</p>
                            </div>
