# FirstBlood
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VVSERVER - CS 1.6 Сервер</title>
    <style>
        /* Общие стили */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            background-color: #0d1117;
            color: #f0f0f0;
            line-height: 1.6;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Шапка */
        header {
            background-color: #161b22;
            padding: 15px 0;
            border-bottom: 2px solid #30363d;
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
            color: #ff4655;
            text-transform: uppercase;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 25px;
        }
        
        .nav-links a {
            color: #f0f0f0;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .nav-links a:hover {
            color: #ff4655;
        }
        
        /* Герой секция */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1542751371-adc38448a05e?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            padding: 100px 0;
            text-align: center;
        }
        
        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
            color: #fff;
        }
        
        .hero p {
            font-size: 20px;
            margin-bottom: 30px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .btn {
            display: inline-block;
            background-color: #ff4655;
            color: white;
            padding: 12px 30px;
            border-radius: 4px;
            text-decoration: none;
            font-weight: bold;
            transition: background-color 0.3s;
        }
        
        .btn:hover {
            background-color: #e03e4c;
        }
        
        /* Секции */
        section {
            padding: 70px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            color: #fff;
            font-size: 36px;
        }
        
        /* О сервере */
        .about-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
        }
        
        .about-text {
            flex: 1;
            min-width: 300px;
            padding-right: 30px;
        }
        
        .server-info {
            flex: 1;
            min-width: 300px;
            background-color: #161b22;
            padding: 20px;
            border-radius: 8px;
        }
        
        .info-item {
            margin-bottom: 15px;
            display: flex;
            align-items: center;
        }
        
        .info-item span {
            font-weight: bold;
            margin-right: 10px;
            color: #ff4655;
        }
        
        /* Статистика */
        .stats {
            background-color: #161b22;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }
        
        .stat-card {
            background-color: #0d1117;
            padding: 20px;
            border-radius: 8px;
            text-align: center;
            border: 1px solid #30363d;
        }
        
        .stat-number {
            font-size: 36px;
            font-weight: bold;
            color: #ff4655;
            margin-bottom: 10px;
        }
        
        /* Правила */
        .rules-list {
            background-color: #161b22;
            padding: 30px;
            border-radius: 8px;
        }
        
        .rules-list ol {
            margin-left: 20px;
        }
        
        .rules-list li {
            margin-bottom: 10px;
        }
        
        /* Как подключиться */
        .connect-steps {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }
        
        .step-card {
            background-color: #161b22;
            padding: 20px;
            border-radius: 8px;
            text-align: center;
        }
        
        .step-number {
            background-color: #ff4655;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 15px;
            font-weight: bold;
        }
        
        /* Футер */
        footer {
            background-color: #161b22;
            padding: 30px 0;
            text-align: center;
            border-top: 2px solid #30363d;
        }
        
        .footer-links {
            display: flex;
            justify-content: center;
            list-style: none;
            margin-bottom: 20px;
        }
        
        .footer-links li {
            margin: 0 15px;
        }
        
        .footer-links a {
            color: #f0f0f0;
            text-decoration: none;
        }
        
        .footer-links a:hover {
            color: #ff4655;
        }
        
        /* Адаптивность */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 36px;
            }
            
            .about-content {
                flex-direction: column;
            }
            
            .about-text {
                padding-right: 0;
                margin-bottom: 30px;
            }
        }
    </style>
</head>
<body>
    <!-- Шапка -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">VVSERVER</div>
                <ul class="nav-links">
                    <li><a href="#about">О сервере</a></li>
                    <li><a href="#stats">Статистика</a></li>
                    <li><a href="#rules">Правила</a></li>
                    <li><a href="#connect">Как подключиться</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Герой секция -->
    <section class="hero">
        <div class="container">
            <h1>VVSERVER CS 1.6</h1>
            <p>Лучший сервер Counter-Strike 1.6 с уникальными возможностями и дружным сообществом. Присоединяйся!</p>
            <a href="#connect" class="btn">Подключиться</a>
        </div>
    </section>

    <!-- О сервере -->
    <section id="about">
        <div class="container">
            <h2 class="section-title">О нашем сервере</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>Добро пожаловать на VVSERVER - один из лучших серверов Counter-Strike 1.6! Наш сервер работает 24/7 и предлагает стабильное соединение, различные режимы игры и регулярные обновления.</p>
                    <p>Мы создали дружелюбное сообщество игроков, где ценятся честная игра и уважение к другим участникам. Присоединяйся к нашей растущей команде!</p>
                </div>
                <div class="server-info">
                    <div class="info-item">
                        <span>IP:</span> 192.168.0.1:27015
                    </div>
                    <div class="info-item">
                        <span>Версия:</span> CS 1.6 Steam
                    </div>
                    <div class="info-item">
                        <span>Режимы:</span> Classic, Deathmatch, Zombie Plague
                    </div>
                    <div class="info-item">
                        <span>Слоты:</span> 24/32
                    </div>
                    <div class="info-item">
                        <span>Карты:</span> de_dust2, de_inferno, de_nuke и другие
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Статистика -->
    <section id="stats" class="stats">
        <div class="container">
            <h2 class="section-title">Статистика сервера</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-number">2,548</div>
                    <div>Игроков онлайн</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">15,732</div>
                    <div>Всего игроков</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">98%</div>
                    <div>Аптайм сервера</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">356</div>
                    <div>Дней работы</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Правила -->
    <section id="rules">
        <div class="container">
            <h2 class="section-title">Правила сервера</h2>
            <div class="rules-list">
                <ol>
                    <li>Запрещено использование читов и любых нечестных преимуществ</li>
                    <li>Уважайте других игроков, запрещены оскорбления и унижения</li>
                    <li>Запрещен гриферство и намеренная порча игры</li>
                    <li>Не спамите в чат и микрофон</li>
                    <li>Соблюдайте правила выбранного режима игры</li>
                    <li>Администрация вправе выдать наказание даже за нарушения, не указанные явно в правилах</li>
                </ol>
            </div>
        </div>
    </section>

    <!-- Как подключиться -->
    <section id="connect">
        <div class="container">
            <h2 class="section-title">Как подключиться</h2>
            <div class="connect-steps">
                <div class="step-card">
                    <div class="step-number">1</div>
                    <h3>Запустите CS 1.6</h3>
                    <p>Убедитесь, что у вас установлена последняя версия игры</p>
                </div>
                <div class="step-card">
                    <div class="step-number">2</div>
                    <h3>Откройте консоль</h3>
                    <p>Нажмите клавишу ~ для открытия консоли</p>
                </div>
                <div class="step-card">
                    <div class="step-number">3</div>
                    <h3>Введите IP</h3>
                    <p>Наберите: connect 192.168.0.1:27015</p>
                </div>
                <div class="step-card">
                    <div class="step-number">4</div>
                    <h3>Наслаждайтесь игрой!</h3>
                    <p>Присоединяйтесь к нашему сообществу</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Футер -->
    <footer>
        <div class="container">
            <ul class="footer-links">
                <li><a href="#about">О сервере</a></li>
                <li><a href="#stats">Статистика</a></li>
                <li><a href="#rules">Правила</a></li>
                <li><a href="#connect">Подключение</a></li>
            </ul>
            <p>© 2023 VVSERVER CS 1.6. Все права защищены.</p>
        </div>
    </footer>
</body>
</html><!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VVSERVER - CS 1.6 Сервер</title>
    <style>
        /* Общие стили */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            background-color: #0d1117;
            color: #f0f0f0;
            line-height: 1.6;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Шапка */
        header {
            background-color: #161b22;
            padding: 15px 0;
            border-bottom: 2px solid #30363d;
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
            color: #ff4655;
            text-transform: uppercase;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 25px;
        }
        
        .nav-links a {
            color: #f0f0f0;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .nav-links a:hover {
            color: #ff4655;
        }
        
        /* Герой секция */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1542751371-adc38448a05e?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            padding: 100px 0;
            text-align: center;
        }
        
        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
            color: #fff;
        }
        
        .hero p {
            font-size: 20px;
            margin-bottom: 30px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .btn {
            display: inline-block;
            background-color: #ff4655;
            color: white;
            padding: 12px 30px;
            border-radius: 4px;
            text-decoration: none;
            font-weight: bold;
            transition: background-color 0.3s;
        }
        
        .btn:hover {
            background-color: #e03e4c;
        }
        
        /* Секции */
        section {
            padding: 70px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            color: #fff;
            font-size: 36px;
        }
        
        /* О сервере */
        .about-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
        }
        
        .about-text {
            flex: 1;
            min-width: 300px;
            padding-right: 30px;
        }
        
        .server-info {
            flex: 1;
            min-width: 300px;
            background-color: #161b22;
            padding: 20px;
            border-radius: 8px;
        }
        
        .info-item {
            margin-bottom: 15px;
            display: flex;
            align-items: center;
        }
        
        .info-item span {
            font-weight: bold;
            margin-right: 10px;
            color: #ff4655;
        }
        
        /* Статистика */
        .stats {
            background-color: #161b22;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }
        
        .stat-card {
            background-color: #0d1117;
            padding: 20px;
            border-radius: 8px;
            text-align: center;
            border: 1px solid #30363d;
        }
        
        .stat-number {
            font-size: 36px;
            font-weight: bold;
            color: #ff4655;
            margin-bottom: 10px;
        }
        
        /* Правила */
        .rules-list {
            background-color: #161b22;
            padding: 30px;
            border-radius: 8px;
        }
        
        .rules-list ol {
            margin-left: 20px;
        }
        
        .rules-list li {
            margin-bottom: 10px;
        }
        
        /* Как подключиться */
        .connect-steps {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }
        
        .step-card {
            background-color: #161b22;
            padding: 20px;
            border-radius: 8px;
            text-align: center;
        }
        
        .step-number {
            background-color: #ff4655;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 15px;
            font-weight: bold;
        }
        
        /* Футер */
        footer {
            background-color: #161b22;
            padding: 30px 0;
            text-align: center;
            border-top: 2px solid #30363d;
        }
        
        .footer-links {
            display: flex;
            justify-content: center;
            list-style: none;
            margin-bottom: 20px;
        }
        
        .footer-links li {
            margin: 0 15px;
        }
        
        .footer-links a {
            color: #f0f0f0;
            text-decoration: none;
        }
        
        .footer-links a:hover {
            color: #ff4655;
        }
        
        /* Адаптивность */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 36px;
            }
            
            .about-content {
                flex-direction: column;
            }
            
            .about-text {
                padding-right: 0;
                margin-bottom: 30px;
            }
        }
    </style>
</head>
<body>
    <!-- Шапка -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">VVSERVER</div>
                <ul class="nav-links">
                    <li><a href="#about">О сервере</a></li>
                    <li><a href="#stats">Статистика</a></li>
                    <li><a href="#rules">Правила</a></li>
                    <li><a href="#connect">Как подключиться</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Герой секция -->
    <section class="hero">
        <div class="container">
            <h1>VVSERVER CS 1.6</h1>
            <p>Лучший сервер Counter-Strike 1.6 с уникальными возможностями и дружным сообществом. Присоединяйся!</p>
            <a href="#connect" class="btn">Подключиться</a>
        </div>
    </section>

    <!-- О сервере -->
    <section id="about">
        <div class="container">
            <h2 class="section-title">О нашем сервере</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>Добро пожаловать на VVSERVER - один из лучших серверов Counter-Strike 1.6! Наш сервер работает 24/7 и предлагает стабильное соединение, различные режимы игры и регулярные обновления.</p>
                    <p>Мы создали дружелюбное сообщество игроков, где ценятся честная игра и уважение к другим участникам. Присоединяйся к нашей растущей команде!</p>
                </div>
                <div class="server-info">
                    <div class="info-item">
                        <span>IP:</span> 192.168.0.1:27015
                    </div>
                    <div class="info-item">
                        <span>Версия:</span> CS 1.6 Steam
                    </div>
                    <div class="info-item">
                        <span>Режимы:</span> Classic, Deathmatch, Zombie Plague
                    </div>
                    <div class="info-item">
                        <span>Слоты:</span> 24/32
                    </div>
                    <div class="info-item">
                        <span>Карты:</span> de_dust2, de_inferno, de_nuke и другие
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Статистика -->
    <section id="stats" class="stats">
        <div class="container">
            <h2 class="section-title">Статистика сервера</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-number">2,548</div>
                    <div>Игроков онлайн</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">15,732</div>
                    <div>Всего игроков</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">98%</div>
                    <div>Аптайм сервера</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">356</div>
                    <div>Дней работы</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Правила -->
    <section id="rules">
        <div class="container">
            <h2 class="section-title">Правила сервера</h2>
            <div class="rules-list">
                <ol>
                    <li>Запрещено использование читов и любых нечестных преимуществ</li>
                    <li>Уважайте других игроков, запрещены оскорбления и унижения</li>
                    <li>Запрещен гриферство и намеренная порча игры</li>
                    <li>Не спамите в чат и микрофон</li>
                    <li>Соблюдайте правила выбранного режима игры</li>
                    <li>Администрация вправе выдать наказание даже за нарушения, не указанные явно в правилах</li>
                </ol>
            </div>
        </div>
    </section>

    <!-- Как подключиться -->
    <section id="connect">
        <div class="container">
            <h2 class="section-title">Как подключиться</h2>
            <div class="connect-steps">
                <div class="step-card">
                    <div class="step-number">1</div>
                    <h3>Запустите CS 1.6</h3>
                    <p>Убедитесь, что у вас установлена последняя версия игры</p>
                </div>
                <div class="step-card">
                    <div class="step-number">2</div>
                    <h3>Откройте консоль</h3>
                    <p>Нажмите клавишу ~ для открытия консоли</p>
                </div>
                <div class="step-card">
                    <div class="step-number">3</div>
                    <h3>Введите IP</h3>
                    <p>Наберите: connect 192.168.0.1:27015</p>
                </div>
                <div class="step-card">
                    <div class="step-number">4</div>
                    <h3>Наслаждайтесь игрой!</h3>
                    <p>Присоединяйтесь к нашему сообществу</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Футер -->
    <footer>
        <div class="container">
            <ul class="footer-links">
                <li><a href="#about">О сервере</a></li>
                <li><a href="#stats">Статистика</a></li>
                <li><a href="#rules">Правила</a></li>
                <li><a href="#connect">Подключение</a></li>
            </ul>
            <p>© 2023 VVSERVER CS 1.6. Все права защищены.</p>
        </div>
    </footer>
</body>
</html>
