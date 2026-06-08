<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Борисовская РО БОКК - Красный Крест</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-red: #C41E3A;
            --dark-red: #A01730;
            --light-gray: #F5F5F5;
            --dark-gray: #333;
            --text-gray: #555;
            --border-gray: #DDD;
            --white: #FFFFFF;
            --accent-blue: #2C5AA0;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text-gray);
            background: var(--white);
        }

        body.accessibility-mode {
            font-size: 18px;
            letter-spacing: 0.05em;
            line-height: 1.8;
        }

        /* Header & Navigation */
        header {
            background: var(--white);
            border-bottom: 2px solid var(--primary-red);
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .header-container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
            text-decoration: none;
            color: var(--dark-gray);
        }

        .logo-circle {
            width: 50px;
            height: 50px;
            background: var(--primary-red);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 24px;
            flex-shrink: 0;
        }

        .logo-text h1 {
            font-size: 14px;
            font-weight: 600;
            line-height: 1.2;
            margin: 0;
        }

        .header-controls {
            display: flex;
            gap: 15px;
            align-items: center;
            flex-wrap: wrap;
        }

        .lang-switcher {
            display: flex;
            gap: 8px;
            border: 1px solid var(--border-gray);
            border-radius: 4px;
            padding: 5px;
        }

        .lang-btn {
            padding: 8px 12px;
            border: none;
            background: transparent;
            cursor: pointer;
            font-size: 13px;
            font-weight: 600;
            color: var(--text-gray);
            transition: all 0.3s ease;
            border-radius: 3px;
        }

        .lang-btn.active {
            background: var(--primary-red);
            color: white;
        }

        .lang-btn:hover {
            background: var(--light-gray);
        }

        .accessibility-btn {
            padding: 10px 12px;
            background: transparent;
            border: 2px solid var(--primary-red);
            color: var(--primary-red);
            cursor: pointer;
            font-weight: 600;
            border-radius: 4px;
            transition: all 0.3s ease;
            font-size: 13px;
        }

        .accessibility-btn:hover {
            background: var(--primary-red);
            color: white;
        }

        .donate-btn {
            padding: 12px 24px;
            background: var(--primary-red);
            color: white;
            border: none;
            border-radius: 4px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 14px;
        }

        .donate-btn:hover {
            background: var(--dark-red);
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(196, 30, 58, 0.3);
        }

        /* Hero Section */
        .hero {
            min-height: 600px;
            background: linear-gradient(135deg, rgba(196, 30, 58, 0.95) 0%, rgba(160, 23, 48, 0.95) 100%);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -10%;
            width: 600px;
            height: 600px;
            background: rgba(255,255,255,0.05);
            border-radius: 50%;
        }

        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 700px;
            animation: fadeInUp 0.8s ease;
        }

        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
            font-weight: 700;
            line-height: 1.2;
        }

        .hero p {
            font-size: 20px;
            margin-bottom: 40px;
            opacity: 0.95;
            font-weight: 300;
        }

        .hero-buttons {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .hero-btn {
            padding: 14px 28px;
            border: 2px solid white;
            background: transparent;
            color: white;
            border-radius: 4px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 15px;
        }

        .hero-btn:hover {
            background: white;
            color: var(--primary-red);
        }

        .hero-btn.primary {
            background: white;
            color: var(--primary-red);
            border-color: white;
        }

        .hero-btn.primary:hover {
            background: rgba(255,255,255,0.9);
        }

        /* Quick Actions */
        .quick-actions {
            max-width: 1400px;
            margin: -80px auto 60px;
            padding: 0 20px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            position: relative;
            z-index: 10;
        }

        .action-card {
            background: white;
            padding: 35px 25px;
            border-radius: 8px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            cursor: pointer;
            border-top: 4px solid var(--primary-red);
        }

        .action-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 8px 25px rgba(196, 30, 58, 0.15);
        }

        .action-icon {
            font-size: 40px;
            margin-bottom: 15px;
        }

        .action-card h3 {
            font-size: 18px;
            margin-bottom: 12px;
            color: var(--dark-gray);
        }

        .action-card p {
            font-size: 14px;
            color: var(--text-gray);
            margin-bottom: 20px;
        }

        .action-link {
            color: var(--primary-red);
            text-decoration: none;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .action-link:hover {
            text-decoration: underline;
        }

        /* Stats Section */
        .stats {
            background: var(--light-gray);
            padding: 60px 20px;
        }

        .stats-container {
            max-width: 1400px;
            margin: 0 auto;
        }

        .stats-title {
            text-align: center;
            font-size: 32px;
            margin-bottom: 50px;
            color: var(--dark-gray);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
        }

        .stat-item {
            background: white;
            padding: 40px 25px;
            border-radius: 8px;
            text-align: center;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        }

        .stat-number {
            font-size: 48px;
            font-weight: 700;
            color: var(--primary-red);
            margin-bottom: 10px;
        }

        .stat-label {
            font-size: 16px;
            color: var(--text-gray);
            font-weight: 500;
        }

        /* Content Sections */
        .section {
            max-width: 1400px;
            margin: 0 auto;
            padding: 60px 20px;
        }

        .section h2 {
            font-size: 36px;
            margin-bottom: 40px;
            color: var(--dark-gray);
            border-left: 5px solid var(--primary-red);
            padding-left: 20px;
        }

        /* News Section */
        .news-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }

        .news-card {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 12px rgba(0,0,0,0.08);
            transition: all 0.3s ease;
        }

        .news-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 6px 20px rgba(0,0,0,0.12);
        }

        .news-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, var(--primary-red), var(--dark-red));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 48px;
        }

        .news-content {
            padding: 25px;
        }

        .news-date {
            font-size: 12px;
            color: var(--primary-red);
            font-weight: 600;
            text-transform: uppercase;
            margin-bottom: 8px;
        }

        .news-card h3 {
            font-size: 18px;
            margin-bottom: 12px;
            color: var(--dark-gray);
            line-height: 1.3;
        }

        .news-card p {
            font-size: 14px;
            color: var(--text-gray);
            margin-bottom: 15px;
        }

        .read-more {
            color: var(--primary-red);
            text-decoration: none;
            font-weight: 600;
            font-size: 13px;
        }

        .read-more:hover {
            text-decoration: underline;
        }

        /* Services Section */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
        }

        .service-card {
            background: white;
            padding: 30px;
            border-radius: 8px;
            border-left: 5px solid var(--primary-red);
            box-shadow: 0 2px 12px rgba(0,0,0,0.08);
            transition: all 0.3s ease;
        }

        .service-card:hover {
            box-shadow: 0 6px 20px rgba(0,0,0,0.12);
        }

        .service-icon {
            font-size: 32px;
            margin-bottom: 15px;
        }

        .service-card h3 {
            font-size: 20px;
            margin-bottom: 12px;
            color: var(--dark-gray);
        }

        .service-card p {
            font-size: 14px;
            line-height: 1.7;
            margin-bottom: 15px;
        }

        .service-btn {
            display: inline-block;
            padding: 10px 20px;
            background: var(--primary-red);
            color: white;
            text-decoration: none;
            border-radius: 4px;
            font-weight: 600;
            font-size: 13px;
            transition: all 0.3s ease;
        }

        .service-btn:hover {
            background: var(--dark-red);
        }

        /* Help Section */
        .help-column {
            margin-bottom: 40px;
            background: white;
            padding: 30px;
            border-radius: 8px;
            border-top: 4px solid var(--primary-red);
        }

        .help-column h3 {
            font-size: 24px;
            margin-bottom: 20px;
            color: var(--dark-gray);
        }

        .help-list {
            list-style: none;
        }

        .help-list li {
            padding: 12px 0;
            border-bottom: 1px solid var(--border-gray);
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .help-list li:last-child {
            border-bottom: none;
        }

        .help-list li::before {
            content: '✓';
            color: var(--primary-red);
            font-weight: bold;
            font-size: 18px;
            flex-shrink: 0;
        }

        .qr-code {
            width: 150px;
            height: 150px;
            background: linear-gradient(135deg, var(--primary-red), var(--dark-red));
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            margin: 20px 0;
            font-size: 12px;
            text-align: center;
        }

        /* Volunteering Section */
        .volunteer-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .volunteer-card {
            background: white;
            padding: 25px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.08);
            border-left: 4px solid var(--primary-red);
        }

        .volunteer-card h4 {
            color: var(--primary-red);
            font-size: 16px;
            margin-bottom: 10px;
        }

        .volunteer-card p {
            font-size: 14px;
            color: var(--text-gray);
        }

        .step {
            display: flex;
            align-items: center;
            gap: 20px;
            margin-bottom: 20px;
        }

        .step-number {
            width: 50px;
            height: 50px;
            background: var(--primary-red);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-size: 20px;
            flex-shrink: 0;
        }

        .step-content h4 {
            color: var(--dark-gray);
            margin-bottom: 5px;
        }

        .step-content p {
            font-size: 14px;
            color: var(--text-gray);
        }

        /* Contact Section */
        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .contact-item {
            background: white;
            padding: 25px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.08);
        }

        .contact-item h3 {
            color: var(--primary-red);
            font-size: 16px;
            margin-bottom: 15px;
            text-transform: uppercase;
            font-size: 13px;
            font-weight: 700;
        }

        .contact-item p {
            font-size: 15px;
            color: var(--dark-gray);
            margin-bottom: 8px;
        }

        .contact-item a {
            color: var(--primary-red);
            text-decoration: none;
            font-weight: 600;
        }

        .contact-item a:hover {
            text-decoration: underline;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 15px;
        }

        .social-link {
            display: inline-flex;
            width: 40px;
            height: 40px;
            background: var(--primary-red);
            color: white;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            text-decoration: none;
            transition: all 0.3s ease;
            font-weight: bold;
        }

        .social-link:hover {
            background: var(--dark-red);
            transform: translateY(-3px);
        }

        /* Footer */
        footer {
            background: var(--dark-gray);
            color: white;
            padding: 40px 20px 20px;
            text-align: center;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            margin-bottom: 20px;
        }

        .footer-text {
            font-size: 13px;
            line-height: 1.8;
            opacity: 0.85;
        }

        .footer-divider {
            height: 1px;
            background: rgba(255,255,255,0.2);
            margin: 20px 0;
        }

        .legal-text {
            font-size: 12px;
            opacity: 0.7;
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

        .action-card {
            animation: fadeInUp 0.6s ease;
        }

        .action-card:nth-child(2) {
            animation-delay: 0.1s;
        }

        .action-card:nth-child(3) {
            animation-delay: 0.2s;
        }

        .action-card:nth-child(4) {
            animation-delay: 0.3s;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 36px;
            }

            .hero p {
                font-size: 16px;
            }

            .section h2 {
                font-size: 28px;
            }

            .header-container {
                flex-direction: column;
                gap: 12px;
            }

            .hero-buttons {
                flex-direction: column;
                align-items: stretch;
            }

            .hero-btn {
                width: 100%;
            }

            .action-card {
                padding: 25px 15px;
            }
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            align-items: center;
            justify-content: center;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: white;
            padding: 40px;
            border-radius: 8px;
            max-width: 600px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
            position: relative;
        }

        .modal-close {
            position: absolute;
            right: 20px;
            top: 20px;
            background: none;
            border: none;
            font-size: 28px;
            cursor: pointer;
            color: var(--text-gray);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark-gray);
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid var(--border-gray);
            border-radius: 4px;
            font-family: inherit;
            font-size: 14px;
        }

        .form-group textarea {
            resize: vertical;
            min-height: 120px;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary-red);
            box-shadow: 0 0 0 3px rgba(196, 30, 58, 0.1);
        }

        .checkbox-group {
            display: flex;
            align-items: flex-start;
            gap: 10px;
            margin: 20px 0;
            font-size: 13px;
        }

        .checkbox-group input {
            margin-top: 4px;
        }

        .form-submit {
            width: 100%;
            padding: 14px;
            background: var(--primary-red);
            color: white;
            border: none;
            border-radius: 4px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 15px;
        }

        .form-submit:hover {
            background: var(--dark-red);
        }

        .modal-title {
            font-size: 28px;
            margin-bottom: 25px;
            color: var(--dark-gray);
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-container">
            <a href="#" class="logo">
                <div class="logo-circle">✚</div>
                <div class="logo-text">
                    <h1>Борисовская РО<br>БОКК</h1>
                </div>
            </a>
            <div class="header-controls">
                <div class="lang-switcher">
                    <button class="lang-btn active" data-lang="ru">РУ</button>
                    <button class="lang-btn" data-lang="be">БЕ</button>
                </div>
                <button class="accessibility-btn" id="accessibilityToggle">🔍 A+</button>
                <button class="donate-btn" onclick="openDonateModal()">ПОЖЕРТВОВАТЬ</button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Милосердие и помощь рядом</h1>
            <p>В Борисове и для борисовчан</p>
            <div class="hero-buttons">
                <button class="hero-btn primary" onclick="openHelpModal()">🆘 Мне нужна помощь</button>
                <button class="hero-btn" onclick="openVolunteerModal()">💪 Стать волонтером</button>
                <button class="hero-btn" onclick="openDonateModal()">❤️ Перечислить средства</button>
            </div>
        </div>
    </section>

    <!-- Quick Actions -->
    <div class="quick-actions">
        <div class="action-card">
            <div class="action-icon">🆘</div>
            <h3>Нужна помощь?</h3>
            <p>Услуги медико-социальной службы, помощь в ЧС</p>
            <a href="#services" class="action-link">Подробнее →</a>
        </div>
        <div class="action-card">
            <div class="action-icon">💪</div>
            <h3>Стать волонтером</h3>
            <p>Помогайте людям и развивайтесь вместе с нами</p>
            <a href="#volunteering" class="action-link">Узнать больше →</a>
        </div>
        <div class="action-card">
            <div class="action-icon">❤️</div>
            <h3>Пожертвовать</h3>
            <p>Вся помощь идет напрямую нуждающимся</p>
            <a href="#help" class="action-link">Способы помощи →</a>
        </div>
        <div class="action-card">
            <div class="action-icon">🩸</div>
            <h3>Сдать кровь</h3>
            <p>Спасите жизнь — станьте донором</p>
            <a href="#blood" class="action-link">График дней →</a>
        </div>
    </div>

    <!-- Statistics -->
    <section class="stats">
        <div class="stats-container">
            <h2 class="stats-title">Наша работа в цифрах</h2>
            <div class="stats-grid">
                <div class="stat-item">
                    <div class="stat-number">247</div>
                    <div class="stat-label">Подопечных на обслуживании</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">143</div>
                    <div class="stat-label">Подготовленных волонтеров</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">58 т</div>
                    <div class="stat-label">Гуманитарной помощи собрано</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">2100+</div>
                    <div class="stat-label">Часов волонтерской работы</div>
                </div>
            </div>
        </div>
    </section>

    <!-- News Section -->
    <section class="section" id="news">
        <h2>Новости и события</h2>
        <div class="news-grid">
            <div class="news-card">
                <div class="news-image">📰</div>
                <div class="news-content">
                    <div class="news-date">5 июня 2026</div>
                    <h3>Борисовский Красный Крест поздравил ветеранов</h3>
                    <p>Волонтеры организации посетили ветеранов Великой Отечественной войны с поздравлениями и подарками.</p>
                    <a href="#" class="read-more">Читать далее →</a>
                </div>
            </div>
            <div class="news-card">
                <div class="news-image">🩸</div>
                <div class="news-content">
                    <div class="news-date">16 июня 2026</div>
                    <h3>День Донора в Борисове</h3>
                    <p>Приглашаем на акцию сдачи крови в ЦРБ. Участие волонтеров, подарки донорам и горячий чай.</p>
                    <a href="#blood" class="read-more">Подробнее →</a>
                </div>
            </div>
            <div class="news-card">
                <div class="news-image">🎓</div>
                <div class="news-content">
                    <div class="news-date">22 июня 2026</div>
                    <h3>Курс первой помощи</h3>
                    <p>Новый набор на базовый курс обучения первой помощи. Сертификат по окончании курса.</p>
                    <a href="#services" class="read-more">Записаться →</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="section" id="services">
        <h2>Наши направления деятельности</h2>
        <div class="services-grid">
            <div class="service-card">
                <div class="service-icon">🏥</div>
                <h3>Медико-социальная служба</h3>
                <p>Услуги сестер милосердия: уход за пожилыми, инвалидами и тяжелобольными на дому в Борисове.</p>
                <a href="#" class="service-btn" onclick="alert('Подробнее о службе Дапамога'); return false;">Подробнее</a>
            </div>
            <div class="service-card">
                <div class="service-icon">🚨</div>
                <h3>Помощь в ЧС</h3>
                <p>Волонтерская команда реагирования на чрезвычайные ситуации: поиск, гуманитарная помощь, пункты обогрева.</p>
                <a href="#" class="service-btn" onclick="alert('О программе помощи в ЧС'); return false;">Узнать</a>
            </div>
            <div class="service-card">
                <div class="service-icon">📚</div>
                <h3>Обучение первой помощи</h3>
                <p>Курсы для населения, организаций и молодых мам. Обучение базовой и специальной первой помощи.</p>
                <a href="#" class="service-btn" onclick="openCoursesModal()">Записаться</a>
            </div>
            <div class="service-card">
                <div class="service-icon">👨‍👩‍👧‍👦</div>
                <h3>Помощь уязвимым</h3>
                <p>Программы для многодетных семей, детей-инвалидов, беженцев и лиц без определенного места жительства.</p>
                <a href="#" class="service-btn" onclick="alert('Программы помощи'); return false;">Подробнее</a>
            </div>
            <div class="service-card">
                <div class="service-icon">🎗️</div>
                <h3>Социальная работа</h3>
                <p>Консультирование, поддержка и координация помощи для категорий населения, оказавшихся в сложной ситуации.</p>
                <a href="#" class="service-btn" onclick="alert('О социальных программах'); return false;">Узнать</a>
            </div>
            <div class="service-card">
                <div class="service-icon">👶</div>
                <h3>Работа с детьми</h3>
                <p>Помощь детским учреждениям, волонтерские клоун-терапия в детской больнице, развивающие программы.</p>
                <a href="#" class="service-btn" onclick="alert('О работе с детьми'); return false;">Узнать</a>
            </div>
        </div>
    </section>

    <!-- How to Help -->
    <section class="section" id="help">
        <h2>Как помочь организации</h2>
        
        <div class="help-column">
            <h3>💳 Финансовое пожертвование</h3>
            <p><strong>Способ 1: Система ЕРИП</strong></p>
            <ol style="margin-left: 20px; margin-bottom: 15px;">
                <li>Благотворительность</li>
                <li>Красный Крест</li>
                <li>Минская область</li>
                <li>Борисовская РО</li>
                <li>Благотворительный взнос</li>
            </ol>
            
            <p><strong>Способ 2: Мобильный банкинг</strong></p>
            <div class="qr-code">Отсканируйте QR-код<br>для оплаты</div>
            
            <p><strong>Способ 3: Банковский реквизит (для юридических лиц)</strong></p>
            <ul class="help-list">
                <li>Получатель: Борисовская районная организация БОКК</li>
                <li>УНП: 100000000</li>
                <li>Счет: BY00BLBB30130000000000000000</li>
                <li>БИК: BLBBBY22</li>
            </ul>
        </div>

        <div class="help-column">
            <h3>📦 Гуманитарная помощь</h3>
            <p><strong>Что принимаем:</strong></p>
            <ul class="help-list">
                <li>Чистая сезонная одежда и обувь</li>
                <li>Постельное белье</li>
                <li>Продукты с длительным сроком хранения</li>
                <li>Подгузники для взрослых и детей</li>
                <li>Инвалидные коляски и костыли</li>
                <li>Предметы личной гигиены</li>
            </ul>
            
            <p style="margin-top: 20px;"><strong>Что НЕ принимаем:</strong></p>
            <ul class="help-list">
                <li>Грязные, порванные вещи</li>
                <li>Лекарства без рецепта</li>
                <li>Срок годности истек</li>
            </ul>
            
            <p style="margin-top: 20px;"><strong>📍 Пункт приема:</strong><br>
            г. Борисов, ул. Ленина, д. 47<br>
            Пн-Пт: 09:00 - 17:00 (перерыв 13:00 - 14:00)<br>
            Сб: 10:00 - 15:00</p>
        </div>

        <div class="help-column">
            <h3>🏪 Копилки Красного Креста</h3>
            <p>Вы можете пожертвовать наличные деньги в стационарные копилки, установленные в:</p>
            <ul class="help-list">
                <li>ТЦ «Борисов-Мол» (каф. «Гарнир»)</li>
                <li>ТЦ «Галактика»</li>
                <li>Аптека №5 (ул. Советская, 49)</li>
                <li>Аптека №11 (ул. Парковая, 15)</li>
                <li>Магазин «Евроопт» (ул. Космонавтов)</li>
            </ul>
        </div>
    </section>

    <!-- Volunteering -->
    <section class="section" id="volunteering">
        <h2>Волонтерство в Борисове</h2>
        <p style="margin-bottom: 30px; font-size: 16px; color: var(--text-gray);">Присоединяйтесь к нашей команде добровольцев. Волонтерство развивает, помогает людям и дает ощущение смысла.</p>
        
        <h3 style="margin: 40px 0 25px; color: var(--dark-gray); font-size: 22px;">Как стать волонтером</h3>
        <div style="margin-bottom: 40px;">
            <div class="step">
                <div class="step-number">1</div>
                <div class="step-content">
                    <h4>Заполните анкету</h4>
                    <p>Расскажите о себе и своих интересах. Это займет всего 5 минут.</p>
                </div>
            </div>
            <div class="step">
                <div class="step-number">2</div>
                <div class="step-content">
                    <h4>Пройдите собеседование</h4>
                    <p>Обсудим ваш опыт, интересы и возможности участия.</p>
                </div>
            </div>
            <div class="step">
                <div class="step-number">3</div>
                <div class="step-content">
                    <h4>Вводный курс волонтера</h4>
                    <p>Узнайте о миссии организации, правилах и безопасности.</p>
                </div>
            </div>
            <div class="step">
                <div class="step-number">4</div>
                <div class="step-content">
                    <h4>Получите волонтерскую книжку</h4>
                    <p>Начните помогать и получайте волонтерские часы.</p>
                </div>
            </div>
        </div>

        <button class="donate-btn" style="padding: 14px 32px; font-size: 16px;" onclick="openVolunteerModal()">Заполнить анкету волонтера →</button>

        <h3 style="margin: 50px 0 25px; color: var(--dark-gray); font-size: 22px;">Направления волонтерства</h3>
        <div class="volunteer-cards">
            <div class="volunteer-card">
                <h4>🤡 Клоун-терапия</h4>
                <p>Творческие волонтеры приносят радость в детскую больницу. Нужны люди с юмором и энергией!</p>
            </div>
            <div class="volunteer-card">
                <h4>🌳 Экологическое волонтерство</h4>
                <p>Помощь в уборке парков, посадке деревьев и экологических акциях города.</p>
            </div>
            <div class="volunteer-card">
                <h4>👴 Помощь пожилым</h4>
                <p>Посещение дома престарелых, помощь в хозяйстве, общение с одинокими людьми.</p>
            </div>
            <div class="volunteer-card">
                <h4>🚗 Авто-волонтеры</h4>
                <p>Помощь с транспортом: доставка помощи, помощь пожилым в передвижении.</p>
            </div>
            <div class="volunteer-card">
                <h4>📚 Образовательное волонтерство</h4>
                <p>Проведение лекций, мастер-классов по первой помощи и здоровому образу жизни.</p>
            </div>
            <div class="volunteer-card">
                <h4>🤝 Социальное волонтерство</h4>
                <p>Работа с многодетными семьями, помощь беженцам и уязвимым группам населения.</p>
            </div>
        </div>
    </section>

    <!-- Blood Donation -->
    <section class="section" id="blood">
        <h2>Донорство крови в Борисове</h2>
        <p style="margin-bottom: 30px; font-size: 16px; color: var(--text-gray);">Спасите жизнь — станьте донором! Ваша кровь может спасить до 3 человек.</p>
        
        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 30px; margin-bottom: 40px;">
            <div class="help-column">
                <h3>📅 График дней донора</h3>
                <p><strong>Каждое 2-е воскресенье месяца</strong></p>
                <p>Время: 09:00 - 14:00</p>
                <p>Место: Борисовская ЦРБ, кабинет 104<br>
                ул. Космонавтов, 28</p>
                <p style="margin-top: 15px; font-size: 13px; color: var(--primary-red); font-weight: 600;">📞 Справки: +375 (177) 73-46-67</p>
            </div>
            <div class="help-column">
                <h3>✅ Требования к донору</h3>
                <ul class="help-list">
                    <li>Возраст: от 18 до 60 лет</li>
                    <li>Вес: не менее 55 кг</li>
                    <li>Нет противопоказаний по здоровью</li>
                    <li>Украинская/белорусская регистрация</li>
                    <li>Паспорт или ID-карта</li>
                </ul>
            </div>
        </div>

        <div class="help-column">
            <h3>💡 Памятка донору</h3>
            <p><strong>За день до донации:</strong></p>
            <ul class="help-list">
                <li>Избегайте жирных и острых блюд</li>
                <li>Не пейте спиртные напитки</li>
                <li>Не курите за 1 час до донации</li>
                <li>Спите достаточно (7-8 часов)</li>
            </ul>
            
            <p style="margin-top: 20px;"><strong>В день донации:</strong></p>
            <ul class="help-list">
                <li>Обязательно позавтракайте (легкий завтрак)</li>
                <li>Приходите рано (9:00-10:00)</li>
                <li>Возьмите паспорт</li>
                <li>Избегайте тяжелых физических нагрузок</li>
            </ul>
        </div>
    </section>

    <!-- About -->
    <section class="section" id="about">
        <h2>Об организации</h2>
        <div style="max-width: 900px;">
            <h3 style="color: var(--dark-gray); margin: 25px 0 15px;">История Борисовского отделения БОКК</h3>
            <p style="margin-bottom: 20px;">Борисовская районная организация Белорусского Общества Красного Креста является филиалом международного движения, работающей в нашем городе более 25 лет. Мы руководствуемся 7 основополагающими принципами Красного Креста: гуманность, беспристрастность, нейтральность, независимость, добровольность, единство и универсальность.</p>
            
            <h3 style="color: var(--dark-gray); margin: 25px 0 15px;">Миссия и ценности</h3>
            <p style="margin-bottom: 20px;">Наша миссия — способствовать благополучию уязвимых слоев населения Борисова через предоставление социальных услуг, волонтерской помощи и обучения. Мы верим, что каждый человек достоин уважения и помощи в трудной ситуации.</p>
            
            <h3 style="color: var(--dark-gray); margin: 25px 0 15px;">Руководство</h3>
            <div style="background: white; padding: 20px; border-radius: 8px; border-left: 4px solid var(--primary-red);">
                <p><strong>Председатель:</strong> Петрова Светлана Ивановна</p>
                <p><strong>Главный бухгалтер:</strong> Смирнов Геннадий Васильевич</p>
                <p><strong>Руководитель социальной службы:</strong> Колесникова Мария Сергеевна</p>
            </div>

            <h3 style="color: var(--dark-gray); margin: 25px 0 15px;">Официальные документы</h3>
            <ul class="help-list" style="margin-bottom: 0;">
                <li><a href="#" style="color: var(--primary-red);">Устав БОКК</a></li>
                <li><a href="#" style="color: var(--primary-red);">Закон РБ «О Белорусском Обществе Красного Креста»</a></li>
                <li><a href="#" style="color: var(--primary-red);">Свидетельство о государственной регистрации</a></li>
                <li><a href="#" style="color: var(--primary-red);">Ежегодный финансовый отчет</a></li>
            </ul>
        </div>
    </section>

    <!-- Contacts -->
    <section class="section" id="contacts">
        <h2>Контакты</h2>
        <div class="contact-info">
            <div class="contact-item">
                <h3>📍 Адрес</h3>
                <p>220037, г. Борисов</p>
                <p>ул. Ленина, дом 47, офис 24</p>
                <p style="margin-top: 10px; font-size: 13px;">Первый этаж, левое крыло здания</p>
            </div>
            <div class="contact-item">
                <h3>📞 Телефоны</h3>
                <p><a href="tel:+37517375463">+375 (177) 37-54-63</a> (городской)</p>
                <p><a href="tel:+375293324567">+375 (29) 332-45-67</a> (мобильный)</p>
                <p style="margin-top: 10px; font-size: 13px; color: var(--text-gray);">Факс: +375 (177) 37-54-64</p>
            </div>
            <div class="contact-item">
                <h3>📧 Email</h3>
                <p><a href="mailto:borisov@redcross.by">borisov@redcross.by</a></p>
                <p style="margin-top: 15px; font-size: 13px;">Ответ на письма 1-2 рабочих дня</p>
            </div>
            <div class="contact-item">
                <h3>🕐 График работы</h3>
                <p>Пн-Пт: 09:00 - 17:00</p>
                <p>Перерыв: 13:00 - 14:00</p>
                <p>Сб: 10:00 - 15:00</p>
                <p>Вск: выходной</p>
            </div>
            <div class="contact-item">
                <h3>👤 Личный прием</h3>
                <p>Председатель принимает:</p>
                <p>Вт, Чт: 14:00 - 17:00</p>
                <p style="margin-top: 10px; font-size: 13px;">Запись по телефону</p>
            </div>
            <div class="contact-item">
                <h3>📱 Социальные сети</h3>
                <p style="margin-bottom: 12px;">Следите за новостями:</p>
                <div class="social-links">
                    <a href="#" class="social-link" title="ВКонтакте">VK</a>
                    <a href="#" class="social-link" title="Instagram">📷</a>
                    <a href="#" class="social-link" title="Telegram">✈️</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Modals -->
    <div id="donateModal" class="modal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeDonateModal()">✕</button>
            <h2 class="modal-title">Пожертвовать</h2>
            <form onsubmit="handleDonate(event)">
                <div class="form-group">
                    <label>Ваше имя *</label>
                    <input type="text" required>
                </div>
                <div class="form-group">
                    <label>Телефон *</label>
                    <input type="tel" required>
                </div>
                <div class="form-group">
                    <label>Email</label>
                    <input type="email">
                </div>
                <div class="form-group">
                    <label>Сумма пожертвования (BYN) *</label>
                    <input type="number" min="1" required placeholder="50">
                </div>
                <div class="form-group">
                    <label>Сообщение</label>
                    <textarea placeholder="Напишите, для чего вы хотите помочь..."></textarea>
                </div>
                <div class="checkbox-group">
                    <input type="checkbox" required>
                    <label>Я согласен на обработку персональных данных согласно <a href="#" style="color: var(--primary-red);">Политике конфиденциальности</a></label>
                </div>
                <button type="submit" class="form-submit">Помочь организации</button>
            </form>
        </div>
    </div>

    <div id="volunteerModal" class="modal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeVolunteerModal()">✕</button>
            <h2 class="modal-title">Анкета волонтера</h2>
            <form onsubmit="handleVolunteer(event)">
                <div class="form-group">
                    <label>Ваше имя *</label>
                    <input type="text" required>
                </div>
                <div class="form-group">
                    <label>Дата рождения *</label>
                    <input type="date" required>
                </div>
                <div class="form-group">
                    <label>Телефон *</label>
                    <input type="tel" required>
                </div>
                <div class="form-group">
                    <label>Email</label>
                    <input type="email">
                </div>
                <div class="form-group">
                    <label>Интересующие направления *</label>
                    <textarea placeholder="Что вас интересует? (клоун-терапия, помощь пожилым, экология и т.д.)" required></textarea>
                </div>
                <div class="form-group">
                    <label>Опыт волонтерства</label>
                    <textarea placeholder="Расскажите о вашем опыте..."></textarea>
                </div>
                <div class="checkbox-group">
                    <input type="checkbox" required>
                    <label>Я согласен на обработку персональных данных согласно <a href="#" style="color: var(--primary-red);">Политике конфиденциальности</a></label>
                </div>
                <button type="submit" class="form-submit">Отправить анкету</button>
            </form>
        </div>
    </div>

    <div id="helpModal" class="modal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeHelpModal()">✕</button>
            <h2 class="modal-title">Запрос помощи</h2>
            <form onsubmit="handleHelp(event)">
                <div class="form-group">
                    <label>Ваше имя *</label>
                    <input type="text" required>
                </div>
                <div class="form-group">
                    <label>Телефон *</label>
                    <input type="tel" required>
                </div>
                <div class="form-group">
                    <label>Описание ситуации *</label>
                    <textarea placeholder="Расскажите о вашей ситуации и необходимой помощи..." required></textarea>
                </div>
                <div class="form-group">
                    <label>Тип нужной помощи *</label>
                    <select style="width: 100%; padding: 12px; border: 1px solid var(--border-gray); border-radius: 4px; font-family: inherit; font-size: 14px;" required>
                        <option value="">-- Выберите --</option>
                        <option value="medical">Медико-социальная помощь</option>
                        <option value="emergency">Помощь в ЧС</option>
                        <option value="material">Материальная помощь</option>
                        <option value="social">Социальная консультация</option>
                        <option value="other">Другое</option>
                    </select>
                </div>
                <div class="checkbox-group">
                    <input type="checkbox" required>
                    <label>Я согласен на обработку персональных данных согласно <a href="#" style="color: var(--primary-red);">Политике конфиденциальности</a></label>
                </div>
                <button type="submit" class="form-submit">Подать заявку</button>
            </form>
        </div>
    </div>

    <div id="coursesModal" class="modal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeCoursesModal()">✕</button>
            <h2 class="modal-title">Запись на курс первой помощи</h2>
            <form onsubmit="handleCourses(event)">
                <div class="form-group">
                    <label>Ваше имя *</label>
                    <input type="text" required>
                </div>
                <div class="form-group">
                    <label>Телефон *</label>
                    <input type="tel" required>
                </div>
                <div class="form-group">
                    <label>Email</label>
                    <input type="email">
                </div>
                <div class="form-group">
                    <label>Выбранный курс *</label>
                    <select style="width: 100%; padding: 12px; border: 1px solid var(--border-gray); border-radius: 4px; font-family: inherit; font-size: 14px;" required>
                        <option value="">-- Выберите курс --</option>
                        <option value="basic">Базовый курс первой помощи</option>
                        <option value="accident">Первая помощь при ДТП</option>
                        <option value="mothers">Первая помощь для молодых мам</option>
                        <option value="corporate">Корпоративный курс</option>
                    </select>
                </div>
                <div class="checkbox-group">
                    <input type="checkbox" required>
                    <label>Я согласен на обработку персональных данных согласно <a href="#" style="color: var(--primary-red);">Политике конфиденциальности</a></label>
                </div>
                <button type="submit" class="form-submit">Зарегистрироваться</button>
            </form>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-text">
                <p><strong>Борисовская районная организация Белорусского Общества Красного Креста</strong></p>
                <p>Благодарим за внимание к нашей миссии помощи и поддержки нуждающихся жителей Борисова</p>
                <p style="margin-top: 15px; font-size: 13px;">© 2024 БОКК. Все права защищены. | Создано с ❤️ для Борисова</p>
            </div>
            <div class="footer-divider"></div>
            <div class="legal-text">
                <p>Сайт размещен в соответствии с требованиями законодательства Республики Беларусь.
                <br>Обработка персональных данных в соответствии с <a href="#" style="color: var(--primary-red);">Политикой конфиденциальности</a></p>
            </div>
        </div>
    </footer>

    <script>
        // Language switching
        document.querySelectorAll('.lang-btn').forEach(btn => {
            btn.addEventListener('click', function() {
                document.querySelectorAll('.lang-btn').forEach(b => b.classList.remove('active'));
                this.classList.add('active');
                const lang = this.dataset.lang;
                // Here you would implement language switching logic
                alert('Переключение на ' + (lang === 'ru' ? 'русский' : 'белорусский') + ' язык');
            });
        });

        // Accessibility mode
        document.getElementById('accessibilityToggle').addEventListener('click', function() {
            document.body.classList.toggle('accessibility-mode');
            this.textContent = document.body.classList.contains('accessibility-mode') ? '🔍 A-' : '🔍 A+';
        });

        // Modal functions
        function openDonateModal() {
            document.getElementById('donateModal').classList.add('active');
        }

        function closeDonateModal() {
            document.getElementById('donateModal').classList.remove('active');
        }

        function openVolunteerModal() {
            document.getElementById('volunteerModal').classList.add('active');
        }

        function closeVolunteerModal() {
            document.getElementById('volunteerModal').classList.remove('active');
        }

        function openHelpModal() {
            document.getElementById('helpModal').classList.add('active');
        }

        function closeHelpModal() {
            document.getElementById('helpModal').classList.remove('active');
        }

        function openCoursesModal() {
            document.getElementById('coursesModal').classList.add('active');
        }

        function closeCoursesModal() {
            document.getElementById('coursesModal').classList.remove('active');
        }

        // Form handlers
        function handleDonate(e) {
            e.preventDefault();
            alert('Спасибо за пожертвование! Ваша помощь очень важна.');
            closeDonateModal();
        }

        function handleVolunteer(e) {
            e.preventDefault();
            alert('Благодарим за интерес к волонтерству! Мы свяжемся с вами в ближайшее время.');
            closeVolunteerModal();
        }

        function handleHelp(e) {
            e.preventDefault();
            alert('Ваша заявка принята. Мы рассмотрим ее и свяжемся с вами.');
            closeHelpModal();
        }

        function handleCourses(e) {
            e.preventDefault();
            alert('Вы зарегистрированы на курс! Уточнения по телефону +375 (177) 37-54-63');
            closeCoursesModal();
        }

        // Close modals on background click
        document.querySelectorAll('.modal').forEach(modal => {
            modal.addEventListener('click', function(e) {
                if (e.target === this) {
                    this.classList.remove('active');
                }
            });
        });

        // Smooth scroll for navigation
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                const href = this.getAttribute('href');
                if (href !== '#' && document.querySelector(href)) {
                    e.preventDefault();
                    document.querySelector(href).scrollIntoView({ behavior: 'smooth' });
                }
            });
        });

        // Smooth scrolling fallback
        if (!CSS.supports('scroll-behavior', 'smooth')) {
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        target.scrollIntoView();
                    }
                });
            });
        }
    </script>
</body>
</html>
