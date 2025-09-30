<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>个人网站 - 小米风格设计</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* 小米风格变量系统 */
        :root {
            --mi-orange: #ff6700;
            --mi-light-orange: #ff761a;
            --mi-dark-orange: #e65c00;
            --mi-bg-light: #f5f5f5;
            --mi-bg-dark: #181a1b;
            --mi-text-dark: #333;
            --mi-text-light: #fff;
            --mi-gray: #e0e0e0;
            --mi-dark-gray: #757575;
            --mi-shadow: 0 2px 10px rgba(0,0,0,0.1);
            --mi-transition: all 0.3s ease;
        }

        /* 基础重置 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', 'Microsoft YaHei', sans-serif;
            background-color: #fff;
            color: var(--mi-text-dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        ul {
            list-style: none;
        }

        .container {
            width: 100%;
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* 小米风格导航栏 */
        .mi-header {
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: var(--mi-shadow);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 60px;
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
            color: var(--mi-orange);
        }

        .nav-menu {
            display: flex;
        }

        .nav-item {
            padding: 0 15px;
            height: 60px;
            display: flex;
            align-items: center;
            transition: var(--mi-transition);
            position: relative;
        }

        .nav-item:hover {
            color: var(--mi-orange);
        }

        .nav-item:hover::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 15px;
            right: 15px;
            height: 2px;
            background-color: var(--mi-orange);
        }

        /* 简约大气的英雄区域 */
        .hero {
            display: flex;
            align-items: center;
            min-height: 80vh;
            padding: 80px 0;
            background: linear-gradient(135deg, #f5f5f5 0%, #ffffff 100%);
        }

        .hero-content {
            max-width: 600px;
            flex: 1;
        }

        .hero-title {
            font-size: 48px;
            font-weight: bold;
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .hero-subtitle {
            font-size: 24px;
            color: var(--mi-dark-gray);
            margin-bottom: 30px;
        }

        .hero-desc {
            font-size: 18px;
            margin-bottom: 40px;
            line-height: 1.8;
        }

        .hero-actions {
            display: flex;
            gap: 15px;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            border-radius: 4px;
            font-weight: bold;
            transition: var(--mi-transition);
            text-align: center;
        }

        .btn-primary {
            background-color: var(--mi-orange);
            color: white;
        }

        .btn-primary:hover {
            background-color: var(--mi-dark-orange);
            transform: translateY(-2px);
        }

        .btn-outline {
            border: 2px solid var(--mi-orange);
            color: var(--mi-orange);
        }

        .btn-outline:hover {
            background-color: var(--mi-orange);
            color: white;
        }

        .hero-image {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .profile-circle {
            width: 350px;
            height: 350px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--mi-orange) 0%, #ff8c00 100%);
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(255, 103, 0, 0.2);
        }

        .profile-circle img {
            width: 90%;
            height: 90%;
            border-radius: 50%;
            object-fit: cover;
            border: 5px solid white;
        }

        /* 轮播图区域 */
        .portfolio-section {
            padding: 100px 0;
            background-color: var(--mi-bg-light);
        }

        .section-title {
            font-size: 36px;
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background-color: var(--mi-orange);
        }

        .mi-carousel {
            position: relative;
            height: 500px;
            overflow: hidden;
            border-radius: 12px;
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }

        .carousel-inner {
            display: flex;
            transition: transform 0.5s ease;
            height: 100%;
        }

        .carousel-item {
            min-width: 100%;
            height: 100%;
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: flex-end;
        }

        .carousel-content {
            width: 100%;
            padding: 40px;
            background: linear-gradient(to top, rgba(0,0,0,0.8), transparent);
            color: white;
        }

        .carousel-title {
            font-size: 32px;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .carousel-desc {
            font-size: 18px;
            max-width: 600px;
        }

        .carousel-controls {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 10px;
        }

        .control-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background-color: rgba(255,255,255,0.5);
            cursor: pointer;
            transition: var(--mi-transition);
        }

        .control-dot.active {
            background-color: white;
            transform: scale(1.3);
        }

        /* 联系方式区域 */
        .contact-section {
            padding: 100px 0;
            background-color: white;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
        }

        .contact-card {
            background-color: white;
            border-radius: 8px;
            padding: 30px;
            box-shadow: var(--mi-shadow);
            transition: var(--mi-transition);
            text-align: center;
        }

        .contact-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }

        .contact-icon {
            width: 80px;
            height: 80px;
            background-color: rgba(255, 103, 0, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 32px;
            color: var(--mi-orange);
        }

        .contact-title {
            font-size: 24px;
            margin-bottom: 15px;
            color: var(--mi-text-dark);
        }

        .contact-info {
            font-size: 18px;
            color: var(--mi-dark-gray);
            margin-bottom: 20px;
        }

        .contact-link {
            color: var(--mi-orange);
            font-weight: bold;
            transition: var(--mi-transition);
        }

        .contact-link:hover {
            color: var(--mi-dark-orange);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }

        .social-link {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background-color: var(--mi-bg-light);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            transition: var(--mi-transition);
        }

        .social-link:hover {
            background-color: var(--mi-orange);
            color: white;
            transform: translateY(-5px);
        }

        /* 页脚 */
        .mi-footer {
            background-color: var(--mi-bg-dark);
            color: var(--mi-text-light);
            padding: 60px 0 30px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .footer-col h3 {
            font-size: 18px;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-col h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 30px;
            height: 2px;
            background-color: var(--mi-orange);
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #aaa;
            transition: var(--mi-transition);
        }

        .footer-links a:hover {
            color: var(--mi-orange);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid #333;
            color: #777;
            font-size: 14px;
        }

        /* 响应式设计 */
        @media (max-width: 1200px) {
            .hero-title {
                font-size: 42px;
            }
            
            .hero-subtitle {
                font-size: 22px;
            }
            
            .profile-circle {
                width: 320px;
                height: 320px;
            }
        }

        @media (max-width: 992px) {
            .hero {
                flex-direction: column;
                text-align: center;
                padding: 60px 0;
            }
            
            .hero-content {
                margin-bottom: 50px;
                max-width: 100%;
            }
            
            .hero-actions {
                justify-content: center;
            }
            
            .profile-circle {
                width: 280px;
                height: 280px;
            }
            
            .mi-carousel {
                height: 400px;
            }
        }

        @media (max-width: 768px) {
            .nav-menu {
                display: none;
            }
            
            .hero-title {
                font-size: 36px;
            }
            
            .hero-subtitle {
                font-size: 20px;
            }
            
            .section-title {
                font-size: 28px;
            }
            
            .mi-carousel {
                height: 350px;
            }
            
            .carousel-content {
                padding: 20px;
            }
            
            .carousel-title {
                font-size: 28px;
            }
            
            .carousel-desc {
                font-size: 16px;
            }
        }

        @media (max-width: 576px) {
            .hero-title {
                font-size: 32px;
            }
            
            .hero-subtitle {
                font-size: 18px;
            }
            
            .hero-desc {
                font-size: 16px;
            }
            
            .btn {
                padding: 10px 20px;
                font-size: 14px;
            }
            
            .mi-carousel {
                height: 300px;
            }
            
            .contact-card {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <!-- 导航栏 -->
    <header class="mi-header">
        <div class="container header-container">
            <a href="#" class="logo">个人网站</a>
            <ul class="nav-menu">
                <li class="nav-item">首页</li>
                <li class="nav-item">关于我</li>
                <li class="nav-item">作品集</li>
                <li class="nav-item">联系方式</li>
            </ul>
        </div>
    </header>

    <!-- 英雄区域 -->
    <section class="hero">
        <div class="container" style="display: flex; align-items: center;">
            <div class="hero-content">
                <h1 class="hero-title">张明 | 设计师 & 开发者</h1>
                <h2 class="hero-subtitle">创造简约而强大的用户体验</h2>
                <p class="hero-desc">
                    我是一名专注于UI/UX设计和前端开发的创意专业人士。拥有5年行业经验，致力于打造直观、美观且功能强大的数字产品。我的设计理念融合了美学与实用性，旨在为用户提供卓越的体验。
                </p>
                <div class="hero-actions">
                    <a href="#portfolio" class="btn btn-primary">查看作品</a>
                    <a href="#contact" class="btn btn-outline">联系我</a>
                </div>
            </div>
            <div class="hero-image">
                <div class="profile-circle">
                    <img src="https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80" alt="个人照片">
                </div>
            </div>
        </div>
    </section>

    <!-- 作品集轮播图 -->
    <section id="portfolio" class="portfolio-section">
        <div class="container">
            <h2 class="section-title">精选作品</h2>
            <div class="mi-carousel">
                <div class="carousel-inner">
                    <!-- 项目1 -->
                    <div class="carousel-item" style="background-image: url('https://images.unsplash.com/photo-1467232004584-a241de8bcf5d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1500&q=80');">
                        <div class="carousel-content">
                            <h3 class="carousel-title">电子商务平台设计</h3>
                            <p class="carousel-desc">为知名零售品牌设计的现代化电商平台，提升用户转化率35%</p>
                        </div>
                    </div>
                    
                    <!-- 项目2 -->
                    <div class="carousel-item" style="background-image: url('https://images.unsplash.com/photo-1551434678-e076c223a692?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1500&q=80');">
                        <div class="carousel-content">
                            <h3 class="carousel-title">移动应用用户体验优化</h3>
                            <p class="carousel-desc">为金融科技公司重新设计的移动应用，用户满意度提升42%</p>
                        </div>
                    </div>
                    
                    <!-- 项目3 -->
                    <div class="carousel-item" style="background-image: url('https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1500&q=80');">
                        <div class="carousel-content">
                            <h3 class="carousel-title">企业品牌重塑</h3>
                            <p class="carousel-desc">为科技初创公司设计的全新品牌形象和网站</p>
                        </div>
                    </div>
                </div>
                <div class="carousel-controls">
                    <div class="control-dot active"></div>
                    <div class="control-dot"></div>
                    <div class="control-dot"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- 联系方式区域 -->
    <section id="contact" class="contact-section">
        <div class="container">
            <h2 class="section-title">联系我</h2>
            <div class="contact-grid">
                <!-- 邮箱 -->
                <div class="contact-card">
                    <div class="contact-icon">
                        <i class="fas fa-envelope"></i>
                    </div>
                    <h3 class="contact-title">电子邮箱</h3>
                    <p class="contact-info">contact@example.com</p>
                    <a href="mailto:contact@example.com" class="contact-link">发送邮件</a>
                </div>
                
                <!-- 电话 -->
                <div class="contact-card">
                    <div class="contact-icon">
                        <i class="fas fa-phone"></i>
                    </div>
                    <h3 class="contact-title">电话</h3>
                    <p class="contact-info">+86 138 8888 8888</p>
                    <a href="tel:+8613888888888" class="contact-link">拨打电话</a>
                </div>
                
                <!-- 社交媒体 -->
                <div class="contact-card">
                    <div class="contact-icon">
                        <i class="fas fa-share-alt"></i>
                    </div>
                    <h3 class="contact-title">社交媒体</h3>
                    <p class="contact-info">关注我的最新动态</p>
                    <div class="social-links">
                        <a href="#" class="social-link"><i class="fab fa-weixin"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-github"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-dribbble"></i></a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 页脚 -->
    <footer class="mi-footer">
        <div class="container">
            <div class="footer-grid">
                <div class="footer-col">
                    <h3>关于我</h3>
                    <ul class="footer-links">
                        <li><a href="#">个人简介</a></li>
                        <li><a href="#">专业技能</a></li>
                        <li><a href="#">工作经历</a></li>
                        <li><a href="#">教育背景</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>我的作品</h3>
                    <ul class="footer-links">
                        <li><a href="#">UI/UX设计</a></li>
                        <li><a href="#">网页开发</a></li>
                        <li><a href="#">品牌设计</a></li>
                        <li><a href="#">移动应用</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>博客文章</h3>
                    <ul class="footer-links">
                        <li><a href="#">设计思维</a></li>
                        <li><a href="#">前端技术</a></li>
                        <li><a href="#">用户体验</a></li>
                        <li><a href="#">行业趋势</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>联系方式</h3>
                    <ul class="footer-links">
                        <li><a href="mailto:contact@example.com">contact@example.com</a></li>
                        <li><a href="tel:+8613888888888">+86 138 8888 8888</a></li>
                        <li><a href="#">北京市朝阳区</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>© 2023 个人网站 版权所有 | 设计灵感来自小米风格</p>
            </div>
        </div>
    </footer>

    <script>
        // 轮播图功能
        document.addEventListener('DOMContentLoaded', function() {
            const carouselInner = document.querySelector('.carousel-inner');
            const dots = document.querySelectorAll('.control-dot');
            let currentIndex = 0;
            const slideCount = document.querySelectorAll('.carousel-item').length;
            
            function updateCarousel() {
                carouselInner.style.transform = `translateX(-${currentIndex * 100}%)`;
                
                // 更新指示点状态
                dots.forEach((dot, index) => {
                    dot.classList.toggle('active', index === currentIndex);
                });
            }
            
            // 自动轮播
            setInterval(() => {
                currentIndex = (currentIndex + 1) % slideCount;
                updateCarousel();
            }, 5000);
            
            // 点击指示点切换
            dots.forEach((dot, index) => {
                dot.addEventListener('click', () => {
                    currentIndex = index;
                    updateCarousel();
                });
            });
        });
    </script>
</body>
</html>
