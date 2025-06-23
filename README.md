<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Уютные свечи ручной работы | CandleCraft</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        :root {
            --primary-color: #f8e9d6;
            --secondary-color: #d4a76a;
            --accent-color: #a67c52;
            --text-color: #5a4a42;
            --light-color: #fff9f0;
            --cart-bg: #fff;
            --cart-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
            --error-color: #ff6b6b;
            --success-color: #4caf50;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Georgia', serif;
        }
        
        body {
            background-color: var(--primary-color);
            color: var(--text-color);
            line-height: 1.6;
        }
        
        header {
            background-color: var(--light-color);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            position: relative;
        }
        
        .logo {
            font-size: 28px;
            font-weight: bold;
            color: var(--accent-color);
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
            color: var(--secondary-color);
        }
        
        .nav-links {
            display: flex;
            list-style: none;
            align-items: center;
        }
        
        .nav-links li {
            margin-left: 20px;
        }
        
        .nav-links a {
            text-decoration: none;
            color: var(--text-color);
            font-weight: 500;
            transition: color 0.3s;
        }
        
        .nav-links a:hover {
            color: var(--secondary-color);
        }
        
        .user-actions {
            display: flex;
            align-items: center;
        }
        
        .cart-icon, .user-icon {
            position: relative;
            margin-left: 20px;
            cursor: pointer;
        }
        
        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: var(--secondary-color);
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 12px;
        }

        .menu-toggle {
            display: none;
            background: none;
            border: none;
            font-size: 24px;
            color: var(--accent-color);
            cursor: pointer;
            z-index: 100;
        }
        
        .hero {
            background: linear-gradient(rgba(248, 233, 214, 0.8), rgba(248, 233, 214, 0.8)), 
                        url('https://images.unsplash.com/photo-1605000797499-95a51c5269ae?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            height: 500px;
            display: flex;
            align-items: center;
            text-align: center;
        }
        
        .hero-content {
            max-width: 600px;
            margin: 0 auto;
        }
        
        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
            color: var(--accent-color);
        }
        
        .hero p {
            font-size: 20px;
            margin-bottom: 30px;
            color: var(--text-color);
        }
        
        .btn {
            display: inline-block;
            background-color: var(--secondary-color);
            color: white;
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background-color: var(--accent-color);
            transform: translateY(-2px);
        }
        
        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--secondary-color);
            color: var(--secondary-color);
        }
        
        .btn-outline:hover {
            background-color: var(--secondary-color);
            color: white;
        }
        
        .btn-small {
            padding: 8px 16px;
            font-size: 14px;
        }
        
        .section-title {
            text-align: center;
            margin: 60px 0 40px;
            font-size: 36px;
            color: var(--accent-color);
        }
        
        .products {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
            padding: 0 20px;
        }
        
        .product-card {
            background-color: var(--light-color);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
            display: flex;
            flex-direction: column;
            position: relative;
        }
        
        .admin-controls {
            position: absolute;
            top: 10px;
            right: 10px;
            display: flex;
            gap: 5px;
            z-index: 2;
        }
        
        .product-card:hover {
            transform: translateY(-10px);
        }
        
        .product-img {
            height: 250px;
            overflow: hidden;
        }
        
        .product-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .product-card:hover .product-img img {
            transform: scale(1.1);
        }
        
        .product-info {
            padding: 20px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }
        
        .product-info h3 {
            font-size: 22px;
            margin-bottom: 10px;
            color: var(--accent-color);
        }
        
        .product-info p {
            margin-bottom: 15px;
            color: var(--text-color);
            flex-grow: 1;
        }
        
        .price {
            font-size: 20px;
            font-weight: bold;
            color: var(--secondary-color);
            margin-bottom: 15px;
            display: block;
        }
        
        .about {
            background-color: var(--light-color);
            padding: 80px 20px;
            margin: 60px 0;
        }
        
        .about-content {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }
        
        .about h2 {
            margin-bottom: 30px;
        }
        
        .about p {
            margin-bottom: 20px;
            font-size: 18px;
        }
        
        .testimonials {
            padding: 0 20px 60px;
        }
        
        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .testimonial-card {
            background-color: var(--light-color);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .testimonial-card p {
            font-style: italic;
            margin-bottom: 20px;
        }
        
        .testimonial-author {
            display: flex;
            align-items: center;
        }
        
        .testimonial-author img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            object-fit: cover;
            margin-right: 15px;
        }
        
        .author-info h4 {
            color: var(--accent-color);
        }
        
        .author-info p {
            font-style: normal;
            font-size: 14px;
            color: var(--text-color);
            opacity: 0.8;
        }
        
        .cart-overlay, .auth-overlay, .admin-overlay {
            position: fixed;
            top: 0;
            right: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 999;
            display: none;
            justify-content: flex-end;
        }
        
        .cart-container, .auth-container, .admin-container {
            width: 100%;
            max-width: 450px;
            height: 100%;
            background-color: var(--cart-bg);
            box-shadow: var(--cart-shadow);
            padding: 20px;
            overflow-y: auto;
            transform: translateX(100%);
            transition: transform 0.3s ease;
        }
        
        .cart-overlay.active, .auth-overlay.active, .admin-overlay.active {
            display: flex;
        }
        
        .cart-overlay.active .cart-container,
        .auth-overlay.active .auth-container,
        .admin-overlay.active .admin-container {
            transform: translateX(0);
        }
        
        .cart-header, .auth-header, .admin-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 1px solid #eee;
        }
        
        .cart-title, .auth-title, .admin-title {
            font-size: 24px;
            color: var(--accent-color);
        }
        
        .close-cart, .close-auth, .close-admin {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--text-color);
        }
        
        .cart-items {
            margin-bottom: 20px;
        }
        
        .cart-item {
            display: flex;
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid #eee;
        }
        
        .cart-item-img {
            width: 80px;
            height: 80px;
            object-fit: cover;
            border-radius: 5px;
            margin-right: 15px;
        }
        
        .cart-item-info {
            flex-grow: 1;
        }
        
        .cart-item-title {
            font-weight: bold;
            margin-bottom: 5px;
        }
        
        .cart-item-price {
            color: var(--secondary-color);
            margin-bottom: 5px;
        }
        
        .cart-item-remove {
            background: none;
            border: none;
            color: #ff6b6b;
            cursor: pointer;
            font-size: 14px;
        }
        
        .cart-item-quantity {
            display: flex;
            align-items: center;
            margin-top: 5px;
        }
        
        .quantity-btn {
            background-color: #f0f0f0;
            border: none;
            width: 25px;
            height: 25px;
            border-radius: 50%;
            cursor: pointer;
        }
        
        .quantity {
            margin: 0 10px;
        }
        
        .cart-total {
            font-size: 20px;
            font-weight: bold;
            text-align: right;
            margin-bottom: 20px;
        }
        
        .cart-actions {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        
        .auth-form {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        
        .form-group {
            display: flex;
            flex-direction: column;
            gap: 5px;
        }
        
        .form-group label {
            font-weight: 500;
        }
        
        .form-group input {
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }
        
        .auth-switch {
            text-align: center;
            margin-top: 10px;
        }
        
        .auth-switch button {
            background: none;
            border: none;
            color: var(--secondary-color);
            text-decoration: underline;
            cursor: pointer;
            font-size: 14px;
        }
        
        .message {
            padding: 10px;
            border-radius: 5px;
            margin-bottom: 15px;
            text-align: center;
        }
        
        .error {
            background-color: rgba(255, 107, 107, 0.2);
            color: var(--error-color);
        }
        
        .success {
            background-color: rgba(76, 175, 80, 0.2);
            color: var(--success-color);
        }
        
        .admin-panel {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        .admin-section {
            background-color: var(--light-color);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
        }
        
        .admin-section h3 {
            margin-bottom: 15px;
            color: var(--accent-color);
        }
        
        .product-form {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        
        footer {
            background-color: var(--accent-color);
            color: var(--primary-color);
            padding: 60px 20px 30px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            font-size: 20px;
            margin-bottom: 20px;
            color: var(--primary-color);
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 10px;
        }
        
        .footer-column a {
            color: var(--primary-color);
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-column a:hover {
            color: var(--secondary-color);
        }
        
        .social-links {
            display: flex;
            gap: 15px;
        }
        
        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            transition: background-color 0.3s;
        }
        
        .social-links a:hover {
            background-color: var(--secondary-color);
        }
        
        .social-links i {
            font-size: 20px;
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 36px;
            }
            
            .hero p {
                font-size: 18px;
            }
            
            .nav-links {
                position: fixed;
                top: 0;
                left: 0;
                width: 100%;
                height: 100vh;
                background-color: var(--light-color);
                flex-direction: column;
                justify-content: center;
                align-items: center;
                transform: translateX(-100%);
                transition: transform 0.3s ease;
                z-index: 99;
                padding-top: 80px;
            }
            
            .nav-links.active {
                transform: translateX(0);
            }
            
            .nav-links li {
                margin: 15px 0;
            }
            
            .menu-toggle {
                display: block;
            }
            
            .cart-container, .auth-container, .admin-container {
                max-width: 100%;
            }
        }
        
        @media (max-width: 768px) {
            .hero {
                height: 400px;
            }
            
            .hero h1 {
                font-size: 32px;
            }
            
            .section-title {
                font-size: 28px;
            }
            
            .footer-content {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 576px) {
            .hero {
                height: 350px;
            }
            
            .product-card {
                max-width: 100%;
            }
            
            .cart-item {
                flex-direction: column;
            }
            
            .cart-item-img {
                width: 100%;
                height: auto;
                margin-bottom: 10px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <nav>
                <div class="logo">
                    <i class="fas fa-fire"></i>
                    <span>CandleCraft</span>
                </div>
                
                <button class="menu-toggle" id="menuToggle">
                    <i class="fas fa-bars"></i>
                </button>
                
                <ul class="nav-links" id="navLinks">
                    <li><a href="#">Главная</a></li>
                    <li><a href="#products">Каталог</a></li>
                    <li><a href="#about">О нас</a></li>
                    <li><a href="#testimonials">Отзывы</a></li>
                    <li><a href="#contact">Контакты</a></li>
                    <li class="user-actions">
                        <div class="user-icon" id="userIcon">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="cart-icon" id="cartIcon">
                            <i class="fas fa-shopping-cart"></i>
                            <span class="cart-count" id="cartCount">0</span>
                        </div>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
    
    <section class="hero">
        <div class="hero-content">
            <h1>Уют в каждой свече</h1>
            <p>Ручная работа с любовью и натуральными материалами для создания теплой атмосферы в вашем доме</p>
            <a href="#products" class="btn">Выбрать свечу</a>
        </div>
    </section>
    
    <section id="products">
        <h2 class="section-title">Наши свечи</h2>
        <div class="products" id="productsContainer">
            <!-- Товары будут добавляться динамически -->
        </div>
    </section>
    
    <section id="about" class="about">
        <div class="about-content">
            <h2 class="section-title">О нашем производстве</h2>
            <p>Мы создаем свечи вручную, используя только натуральные материалы: пчелиный воск, соевый воск и эфирные масла высшего качества. Каждая свеча - это результат кропотливой работы и внимания к деталям.</p>
            <p>Наша миссия - привнести в ваш дом тепло, уют и гармонию через природные ароматы и мягкий свет ручной работы.</p>
            <p>Присоединяйтесь к нашему сообществу ценителей качественных свечей и натуральных ароматов.</p>
        </div>
    </section>
    
    <section id="testimonials" class="testimonials">
        <h2 class="section-title">Отзывы наших клиентов</h2>
        <div class="testimonial-grid">
            <div class="testimonial-card">
                <p>"Свечи от CandleCraft - это настоящее удовольствие! Аромат наполняет всю комнату и держится очень долго. Особенно люблю 'Лавандовый сон' - действительно помогает расслабиться после трудного дня."</p>
                <div class="testimonial-author">
                    <img src="https://randomuser.me/api/portraits/women/43.jpg" alt="Анна">
                    <div class="author-info">
                        <h4>Анна</h4>
                        <p>Постоянный клиент</p>
                    </div>
                </div>
            </div>
            
            <div class="testimonial-card">
                <p>"Заказала набор свечей в подарок подруге - осталась довольна и я, и она! Красивая упаковка, приятный аромат, который не раздражает, а горят свечи ровно и долго. Обязательно закажу еще!"</p>
                <div class="testimonial-author">
                    <img src="https://randomuser.me/api/portraits/women/65.jpg" alt="Елена">
                    <div class="author-info">
                        <h4>Елена</h4>
                        <p>Клиент</p>
                    </div>
                </div>
            </div>
            
            <div class="testimonial-card">
                <p>"Как приятно вечером зажечь свечу 'Ванильное облако' - сразу создается атмосфера уюта и спокойствия. Качество на высоте, аромат натуральный, не химический. Рекомендую всем ценителям хороших свечей!"</p>
                <div class="testimonial-author">
                    <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Дмитрий">
                    <div class="author-info">
                        <h4>Дмитрий</h4>
                        <p>Клиент</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Корзина -->
    <div class="cart-overlay" id="cartOverlay">
        <div class="cart-container">
            <div class="cart-header">
                <h2 class="cart-title">Ваша корзина</h2>
                <button class="close-cart" id="closeCart">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div class="cart-items" id="cartItems">
                <p class="empty-cart-message">Ваша корзина пуста</p>
            </div>
            
            <div class="cart-total">
                Итого: <span id="cartTotal">0</span> ₽
            </div>
            
            <div class="cart-actions">
                <button class="btn" id="checkoutBtn">Оформить заказ</button>
                <button class="btn btn-outline" id="clearCartBtn">Очистить корзину</button>
            </div>
        </div>
    </div>
    
    <!-- Форма авторизации/регистрации -->
    <div class="auth-overlay" id="authOverlay">
        <div class="auth-container">
            <div class="auth-header">
                <h2 class="auth-title" id="authTitle">Вход</h2>
                <button class="close-auth" id="closeAuth">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div id="authMessage" class="message" style="display: none;"></div>
            
            <form class="auth-form" id="loginForm">
                <div class="form-group">
                    <label for="loginEmail">Email</label>
                    <input type="email" id="loginEmail" required>
                </div>
                
                <div class="form-group">
                    <label for="loginPassword">Пароль</label>
                    <input type="password" id="loginPassword" required>
                </div>
                
                <button type="submit" class="btn">Войти</button>
                
                <div class="auth-switch">
                    Нет аккаунта? <button type="button" id="switchToRegister">Зарегистрироваться</button>
                </div>
            </form>
            
            <form class="auth-form" id="registerForm" style="display: none;">
                <div class="form-group">
                    <label for="registerName">Имя</label>
                    <input type="text" id="registerName" required>
                </div>
                
                <div class="form-group">
                    <label for="registerEmail">Email</label>
                    <input type="email" id="registerEmail" required>
                </div>
                
                <div class="form-group">
                    <label for="registerPassword">Пароль</label>
                    <input type="password" id="registerPassword" required minlength="6">
                </div>
                
                <div class="form-group">
                    <label for="registerConfirmPassword">Подтвердите пароль</label>
                    <input type="password" id="registerConfirmPassword" required minlength="6">
                </div>
                
                <button type="submit" class="btn">Зарегистрироваться</button>
                
                <div class="auth-switch">
                    Уже есть аккаунт? <button type="button" id="switchToLogin">Войти</button>
                </div>
            </form>
        </div>
    </div>
    
    <!-- Админ-панель -->
    <div class="admin-overlay" id="adminOverlay">
        <div class="admin-container">
            <div class="admin-header">
                <h2 class="admin-title">Админ-панель</h2>
                <button class="close-admin" id="closeAdmin">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div id="adminMessage" class="message" style="display: none;"></div>
            
            <div class="admin-panel">
                <div class="admin-section">
                    <h3>Добавить новый товар</h3>
                    <form class="product-form" id="addProductForm">
                        <div class="form-group">
                            <label for="productName">Название</label>
                            <input type="text" id="productName" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="productDescription">Описание</label>
                            <input type="text" id="productDescription" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="productPrice">Цена (₽)</label>
                            <input type="number" id="productPrice" required min="1">
                        </div>
                        
                        <div class="form-group">
                            <label for="productImage">URL изображения</label>
                            <input type="text" id="productImage" required>
                        </div>
                        
                        <button type="submit" class="btn">Добавить товар</button>
                    </form>
                </div>
                
                <div class="admin-section">
                    <h3>Управление товарами</h3>
                    <div id="adminProductsList">
                        <!-- Список товаров для администрирования -->
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>CandleCraft</h3>
                    <p>Свечи ручной работы из натуральных материалов для вашего уюта и комфорта.</p>
                    <div class="social-links">
                        <a href="https://instagram.com" target="_blank"><i class="fab fa-instagram"></i></a>
                        <a href="https://facebook.com" target="_blank"><i class="fab fa-facebook-f"></i></a>
                        <a href="https://pinterest.com" target="_blank"><i class="fab fa-pinterest-p"></i></a>
                        <a href="https://vk.com" target="_blank"><i class="fab fa-vk"></i></a>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3>Меню</h3>
                    <ul>
                        <li><a href="#">Главная</a></li>
                        <li><a href="#products">Каталог</a></li>
                        <li><a href="#about">О нас</a></li>
                        <li><a href="#testimonials">Отзывы</a></li>
                        <li><a href="#contact">Контакты</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Контакты</h3>
                    <ul>
                        <li><i class="fas fa-phone"></i> +7 (123) 456-78-90</li>
                        <li><i class="fas fa-envelope"></i> info@candlecraft.ru</li>
                        <li><i class="fas fa-map-marker-alt"></i> г. Москва, ул. Свечная, 15</li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Подписаться на новости</h3>
                    <p>Узнавайте первыми о новых ароматах и специальных предложениях.</p>
                    <form>
                        <input type="email" placeholder="Ваш email" style="padding: 10px; width: 100%; margin-bottom: 10px; border-radius: 5px; border: none;">
                        <button type="submit" class="btn" style="width: 100%;">Подписаться</button>
                    </form>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2023 CandleCraft. Все права защищены.</p>
            </div>
        </div>
    </footer>

    <script>
        // Данные приложения
        const appData = {
            users: JSON.parse(localStorage.getItem('users')) || [],
            products: JSON.parse(localStorage.getItem('products')) || [
                {
                    id: '1',
                    name: 'Ванильное облако',
                    description: 'Нежная ваниль с нотками карамели создаст атмосферу уюта и комфорта',
                    price: 1490,
                    image: 'https://images.unsplash.com/photo-1585771724684-38269d6639fd?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80'
                },
                {
                    id: '2',
                    name: 'Лавандовый сон',
                    description: 'Расслабляющий аромат лаванды поможет снять стресс и подготовиться ко сну',
                    price: 1690,
                    image: 'file:///E:/3667200372368320461.jpg'
                },
                {
                    id: '3',
                    name: 'Цитрусовый рассвет',
                    description: 'Бодрящая смесь апельсина, лимона и грейпфрута зарядит энергией на весь день',
                    price: 1590,
                    image: 'https://images.unsplash.com/photo-1594035910387-fea47794261f?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80'
                },
                {
                    id: '4',
                    name: 'Древесный покой',
                    description: 'Теплые нотки сандала, кедра и пачули создадут атмосферу умиротворения',
                    price: 1790,
                    image: 'https://images.unsplash.com/photo-1594035910387-fea47794261f?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80'
                }
            ],
            cart: JSON.parse(localStorage.getItem('cart')) || [],
            currentUser: JSON.parse(localStorage.getItem('currentUser')) || null,
            adminUser: {
                email: 'admin@candlecraft.ru',
                password: 'admin123',
                name: 'Администратор',
                isAdmin: true
            }
        };

        // Проверяем, есть ли админ в списке пользователей
        if (!appData.users.some(user => user.email === appData.adminUser.email)) {
            appData.users.push(appData.adminUser);
            localStorage.setItem('users', JSON.stringify(appData.users));
        }

        // Элементы интерфейса
        const cartOverlay = document.getElementById('cartOverlay');
        const cartIcon = document.getElementById('cartIcon');
        const closeCart = document.getElementById('closeCart');
        const cartItems = document.getElementById('cartItems');
        const cartCount = document.getElementById('cartCount');
        const cartTotal = document.getElementById('cartTotal');
        const checkoutBtn = document.getElementById('checkoutBtn');
        const clearCartBtn = document.getElementById('clearCartBtn');
        const productsContainer = document.getElementById('productsContainer');
        const menuToggle = document.getElementById('menuToggle');
        const navLinks = document.getElementById('navLinks');
        const userIcon = document.getElementById('userIcon');
        const authOverlay = document.getElementById('authOverlay');
        const closeAuth = document.getElementById('closeAuth');
        const authTitle = document.getElementById('authTitle');
        const loginForm = document.getElementById('loginForm');
        const registerForm = document.getElementById('registerForm');
        const switchToRegister = document.getElementById('switchToRegister');
        const switchToLogin = document.getElementById('switchToLogin');
        const authMessage = document.getElementById('authMessage');
        const adminOverlay = document.getElementById('adminOverlay');
        const closeAdmin = document.getElementById('closeAdmin');
        const adminMessage = document.getElementById('adminMessage');
        const addProductForm = document.getElementById('addProductForm');
        const adminProductsList = document.getElementById('adminProductsList');

        // Инициализация приложения
        function initApp() {
            renderProducts();
            updateCart();
            checkAuthStatus();
            
            // Плавная прокрутка для якорных ссылок
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        window.scrollTo({
                            top: target.offsetTop - 80,
                            behavior: 'smooth'
                        });
                        
                        // Закрываем меню на мобильных устройствах
                        navLinks.classList.remove('active');
                    }
                });
            });
            
            // Мобильное меню
            menuToggle.addEventListener('click', function(e) {
                e.stopPropagation();
                navLinks.classList.toggle('active');
            });
            
            // Закрытие меню при клике вне его области
            document.addEventListener('click', function(e) {
                if (!navLinks.contains(e.target) && e.target !== menuToggle) {
                    navLinks.classList.remove('active');
                }
            });
        }

        // Валидация email
        function isValidEmail(email) {
            return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
        }

        // Рендер товаров
        function renderProducts() {
            productsContainer.innerHTML = '';
            
            appData.products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.innerHTML = `
                    ${appData.currentUser?.isAdmin ? `
                    <div class="admin-controls">
                        <button class="btn btn-small edit-product" data-id="${product.id}">
                            <i class="fas fa-edit"></i>
                        </button>
                        <button class="btn btn-small delete-product" data-id="${product.id}">
                            <i class="fas fa-trash"></i>
                        </button>
                    </div>
                    ` : ''}
                    <div class="product-img">
                        <img src="${product.image}" alt="${product.name}">
                    </div>
                    <div class="product-info">
                        <h3>${product.name}</h3>
                        <p>${product.description}</p>
                        <span class="price">${product.price.toLocaleString()} ₽</span>
                        <button class="btn add-to-cart" data-id="${product.id}" data-name="${product.name}" data-price="${product.price}" data-img="${product.image}">В корзину</button>
                    </div>
                `;
                
                productsContainer.appendChild(productCard);
            });
            
            // Добавляем обработчики событий для кнопок корзины
            document.querySelectorAll('.add-to-cart').forEach(button => {
                button.addEventListener('click', addToCart);
            });
            
            // Добавляем обработчики для кнопок админа
            if (appData.currentUser?.isAdmin) {
                document.querySelectorAll('.edit-product').forEach(button => {
                    button.addEventListener('click', (e) => {
                        const productId = e.target.closest('button').getAttribute('data-id');
                        editProduct(productId);
                    });
                });
                
                document.querySelectorAll('.delete-product').forEach(button => {
                    button.addEventListener('click', (e) => {
                        const productId = e.target.closest('button').getAttribute('data-id');
                        deleteProduct(productId);
                    });
                });
            }
        }

        // Добавление товара в корзину
        function addToCart(e) {
            const id = e.target.getAttribute('data-id');
            const name = e.target.getAttribute('data-name');
            const price = parseInt(e.target.getAttribute('data-price'));
            const img = e.target.getAttribute('data-img');
            
            // Проверяем, есть ли товар уже в корзине
            const existingItem = appData.cart.find(item => item.id === id);
            
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                appData.cart.push({
                    id,
                    name,
                    price,
                    img,
                    quantity: 1
                });
            }
            
            saveCart();
            updateCart();
            cartOverlay.classList.add('active');
            
            // Анимация кнопки
            e.target.textContent = 'Добавлено!';
            setTimeout(() => {
                e.target.textContent = 'В корзину';
            }, 1000);
        }

        // Обновление корзины
        function updateCart() {
            // Обновляем количество товаров
            const totalCount = appData.cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCount.textContent = totalCount;
            
            // Обновляем общую сумму
            const totalPrice = appData.cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            cartTotal.textContent = totalPrice.toLocaleString();
            
            // Очищаем содержимое корзины
            cartItems.innerHTML = '';
            
            if (appData.cart.length === 0) {
                cartItems.innerHTML = '<p class="empty-cart-message">Ваша корзина пуста</p>';
                return;
            }
            
            // Добавляем товары в корзину
            appData.cart.forEach(item => {
                const cartItemElement = document.createElement('div');
                cartItemElement.className = 'cart-item';
                cartItemElement.innerHTML = `
                    <img src="${item.img}" alt="${item.name}" class="cart-item-img">
                    <div class="cart-item-info">
                        <h4 class="cart-item-title">${item.name}</h4>
                        <p class="cart-item-price">${item.price.toLocaleString()} ₽</p>
                        <button class="cart-item-remove" data-id="${item.id}">Удалить</button>
                        <div class="cart-item-quantity">
                            <button class="quantity-btn minus" data-id="${item.id}">-</button>
                            <span class="quantity">${item.quantity}</span>
                            <button class="quantity-btn plus" data-id="${item.id}">+</button>
                        </div>
                    </div>
                `;
                
                cartItems.appendChild(cartItemElement);
            });
            
            // Добавляем обработчики событий для кнопок удаления и изменения количества
            document.querySelectorAll('.cart-item-remove').forEach(button => {
                button.addEventListener('click', () => {
                    const id = button.getAttribute('data-id');
                    const index = appData.cart.findIndex(item => item.id === id);
                    if (index !== -1) {
                        appData.cart.splice(index, 1);
                        saveCart();
                        updateCart();
                    }
                });
            });
            
            document.querySelectorAll('.quantity-btn.minus').forEach(button => {
                button.addEventListener('click', () => {
                    const id = button.getAttribute('data-id');
                    const item = appData.cart.find(item => item.id === id);
                    if (item && item.quantity > 1) {
                        item.quantity -= 1;
                        saveCart();
                        updateCart();
                    }
                });
            });
            
            document.querySelectorAll('.quantity-btn.plus').forEach(button => {
                button.addEventListener('click', () => {
                    const id = button.getAttribute('data-id');
                    const item = appData.cart.find(item => item.id === id);
                    if (item) {
                        item.quantity += 1;
                        saveCart();
                        updateCart();
                    }
                });
            });
        }

        // Сохранение корзины в localStorage
        function saveCart() {
            localStorage.setItem('cart', JSON.stringify(appData.cart));
        }

        // Очистка корзины
        clearCartBtn.addEventListener('click', () => {
            appData.cart = [];
            saveCart();
            updateCart();
        });

        // Оформление заказа
        checkoutBtn.addEventListener('click', () => {
            if (appData.cart.length === 0) {
                showMessage(authMessage, 'Ваша корзина пуста!', 'error');
                return;
            }
            
            if (!appData.currentUser) {
                showMessage(authMessage, 'Для оформления заказа необходимо авторизоваться', 'error');
                cartOverlay.classList.remove('active');
                authOverlay.classList.add('active');
                return;
            }
            
            alert(`Заказ оформлен! Сумма: ${cartTotal.textContent} ₽`);
            appData.cart = [];
            saveCart();
            updateCart();
            cartOverlay.classList.remove('active');
        });

        // Открытие/закрытие корзины
        cartIcon.addEventListener('click', () => {
            cartOverlay.classList.add('active');
        });

        closeCart.addEventListener('click', () => {
            cartOverlay.classList.remove('active');
        });

        // Закрытие корзины при клике вне ее области
        cartOverlay.addEventListener('click', (e) => {
            if (e.target === cartOverlay) {
                cartOverlay.classList.remove('active');
            }
        });

        // Авторизация/регистрация
        userIcon.addEventListener('click', () => {
            if (appData.currentUser) {
                if (appData.currentUser.isAdmin) {
                    adminOverlay.classList.add('active');
                    renderAdminProducts();
                } else {
                    if (confirm(`Вы вошли как ${appData.currentUser.name}. Выйти?`)) {
                        logout();
                    }
                }
            } else {
                authOverlay.classList.add('active');
                showLoginForm();
            }
        });

        closeAuth.addEventListener('click', () => {
            authOverlay.classList.remove('active');
        });

        closeAdmin.addEventListener('click', () => {
            adminOverlay.classList.remove('active');
        });

        // Переключение между формами входа и регистрации
        switchToRegister.addEventListener('click', showRegisterForm);
        switchToLogin.addEventListener('click', showLoginForm);

        function showLoginForm() {
            loginForm.style.display = 'block';
            registerForm.style.display = 'none';
            authTitle.textContent = 'Вход';
            authMessage.style.display = 'none';
        }

        function showRegisterForm() {
            loginForm.style.display = 'none';
            registerForm.style.display = 'block';
            authTitle.textContent = 'Регистрация';
            authMessage.style.display = 'none';
        }

        // Обработка формы входа
        loginForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            
            const user = appData.users.find(user => user.email === email && user.password === password);
            
            if (user) {
                appData.currentUser = user;
                localStorage.setItem('currentUser', JSON.stringify(user));
                authOverlay.classList.remove('active');
                checkAuthStatus();
                showMessage(authMessage, 'Вы успешно вошли в систему', 'success');
            } else {
                showMessage(authMessage, 'Неверный email или пароль', 'error');
            }
        });

        // Обработка формы регистрации
        registerForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const name = document.getElementById('registerName').value;
            const email = document.getElementById('registerEmail').value;
            const password = document.getElementById('registerPassword').value;
            const confirmPassword = document.getElementById('registerConfirmPassword').value;
            
            if (!isValidEmail(email)) {
                showMessage(authMessage, 'Введите корректный email', 'error');
                return;
            }
            
            if (password.length < 6) {
                showMessage(authMessage, 'Пароль должен содержать минимум 6 символов', 'error');
                return;
            }
            
            if (password !== confirmPassword) {
                showMessage(authMessage, 'Пароли не совпадают', 'error');
                return;
            }
            
            if (appData.users.some(user => user.email === email)) {
                showMessage(authMessage, 'Пользователь с таким email уже существует', 'error');
                return;
            }
            
            const newUser = {
                name,
                email,
                password,
                isAdmin: false
            };
            
            appData.users.push(newUser);
            localStorage.setItem('users', JSON.stringify(appData.users));
            
            appData.currentUser = newUser;
            localStorage.setItem('currentUser', JSON.stringify(newUser));
            
            authOverlay.classList.remove('active');
            checkAuthStatus();
            showMessage(authMessage, 'Регистрация прошла успешно', 'success');
            showLoginForm();
        });

        // Выход из системы
        function logout() {
            appData.currentUser = null;
            localStorage.removeItem('currentUser');
            checkAuthStatus();
        }

        // Проверка статуса авторизации
        function checkAuthStatus() {
            if (appData.currentUser) {
                userIcon.innerHTML = `<i class="fas fa-user"></i>`;
                if (appData.currentUser.isAdmin) {
                    // Добавляем кнопку админа, если нужно
                }
            } else {
                userIcon.innerHTML = `<i class="fas fa-user"></i>`;
            }
        }

        // Показать сообщение
        function showMessage(element, text, type) {
            element.textContent = text;
            element.className = `message ${type}`;
            element.style.display = 'block';
            
            setTimeout(() => {
                element.style.display = 'none';
            }, 3000);
        }

        // Обработчик добавления товара
        function handleAddProduct(e) {
            e.preventDefault();
            
            const name = document.getElementById('productName').value;
            const description = document.getElementById('productDescription').value;
            const price = parseInt(document.getElementById('productPrice').value);
            const image = document.getElementById('productImage').value;
            
            // Генерируем уникальный ID
            const newId = Date.now().toString();
            
            const newProduct = {
                id: newId,
                name,
                description,
                price,
                image
            };
            
            appData.products.push(newProduct);
            localStorage.setItem('products', JSON.stringify(appData.products));
            
            addProductForm.reset();
            renderProducts();
            renderAdminProducts();
            showMessage(adminMessage, 'Товар успешно добавлен', 'success');
        }

        // Рендер списка товаров для админа
        function renderAdminProducts() {
            adminProductsList.innerHTML = '';
            
            appData.products.forEach(product => {
                const productItem = document.createElement('div');
                productItem.className = 'product-item';
                productItem.innerHTML = `
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px; padding-bottom: 15px; border-bottom: 1px solid #eee;">
                        <div>
                            <h4>${product.name}</h4>
                            <p>${product.price.toLocaleString()} ₽</p>
                        </div>
                        <div>
                            <button class="btn btn-small edit-product-admin" data-id="${product.id}">
                                <i class="fas fa-edit"></i>
                            </button>
                            <button class="btn btn-small delete-product-admin" data-id="${product.id}">
                                <i class="fas fa-trash"></i>
                            </button>
                        </div>
                    </div>
                `;
                
                adminProductsList.appendChild(productItem);
            });
            
            // Добавляем обработчики для кнопок админа
            document.querySelectorAll('.edit-product-admin').forEach(button => {
                button.addEventListener('click', (e) => {
                    const productId = e.target.closest('button').getAttribute('data-id');
                    editProduct(productId);
                });
            });
            
            document.querySelectorAll('.delete-product-admin').forEach(button => {
                button.addEventListener('click', (e) => {
                    const productId = e.target.closest('button').getAttribute('data-id');
                    deleteProduct(productId);
                });
            });
        }

        // Редактирование товара
        function editProduct(productId) {
            const product = appData.products.find(p => p.id === productId);
            if (!product) return;
            
            // Заполняем форму данными товара
            document.getElementById('productName').value = product.name;
            document.getElementById('productDescription').value = product.description;
            document.getElementById('productPrice').value = product.price;
            document.getElementById('productImage').value = product.image;
            
            // Прокручиваем к форме
            document.getElementById('productName').scrollIntoView({ behavior: 'smooth' });
            
            showMessage(adminMessage, 'Заполните форму для редактирования товара. После сохранения товар будет обновлен.', 'success');
            
            // Удаляем старый товар только после сохранения нового
            addProductForm.onsubmit = function(e) {
                e.preventDefault();
                
                const name = document.getElementById('productName').value;
                const description = document.getElementById('productDescription').value;
                const price = parseInt(document.getElementById('productPrice').value);
                const image = document.getElementById('productImage').value;
                
                const updatedProduct = {
                    id: productId, // Сохраняем старый ID
                    name,
                    description,
                    price,
                    image
                };
                
                // Удаляем старый товар
                appData.products = appData.products.filter(p => p.id !== productId);
                
                // Добавляем обновленный
                appData.products.push(updatedProduct);
                localStorage.setItem('products', JSON.stringify(appData.products));
                
                addProductForm.reset();
                renderProducts();
                renderAdminProducts();
                showMessage(adminMessage, 'Товар успешно обновлен', 'success');
                
                // Возвращаем стандартный обработчик
                addProductForm.onsubmit = handleAddProduct;
            };
        }

        // Удаление товара
        function deleteProduct(productId) {
            if (confirm('Вы уверены, что хотите удалить этот товар?')) {
                appData.products = appData.products.filter(p => p.id !== productId);
                localStorage.setItem('products', JSON.stringify(appData.products));
                
                // Удаляем товар из корзины, если он там есть
                appData.cart = appData.cart.filter(item => item.id !== productId);
                localStorage.setItem('cart', JSON.stringify(appData.cart));
                
                renderProducts();
                renderAdminProducts();
                updateCart();
                showMessage(adminMessage, 'Товар успешно удален', 'success');
            }
        }

        // Закрытие админ-панели при клике вне ее области
        adminOverlay.addEventListener('click', (e) => {
            if (e.target === adminOverlay) {
                adminOverlay.classList.remove('active');
            }
        });

        // Закрытие формы авторизации при клике вне ее области
        authOverlay.addEventListener('click', (e) => {
            if (e.target === authOverlay) {
                authOverlay.classList.remove('active');
            }
        });

        // Инициализация обработчика формы
        addProductForm.addEventListener('submit', handleAddProduct);

        // Инициализируем приложение
        initApp();

        // Данные для входа администратора:
        console.log('Данные для входа администратора:');
        console.log('Email: admin@candlecraft.ru');
        console.log('Пароль: admin123');
    </script>
</body>
</html>
