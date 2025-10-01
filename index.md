<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ZRJ_DreamSky的个人网站</title>
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
            flex: 1;
            max-width: 600px;
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

        /* 拍摄设备区域 */
        .equipment-section {
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

        .equipment-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .equipment-card {
            background-color: white;
            border-radius: 12px;
            padding: 30px;
            box-shadow: var(--mi-shadow);
            transition: var(--mi-transition);
            text-align: center;
        }

        .equipment-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }

        .equipment-icon {
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

        .equipment-name {
            font-size: 24px;
            margin-bottom: 15px;
            color: var(--mi-text-dark);
        }

        /* 作品集轮播图 */
        .portfolio-section {
            padding: 100px 0;
            background-color: white;
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
            background-color: var(--mi-bg-light);
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

        /* 响应式设计 - 修复布局问题 */
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
            
            .equipment-grid {
                grid-template-columns: 1fr;
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
            
            .contact-card, .equipment-card {
                padding: 20px;
            }
            
            .hero-actions {
                flex-direction: column;
                gap: 10px;
            }
        }
    </style>
</head>
<body>
    <!-- 导航栏 -->
    <header class="mi-header">
        <div class="container header-container">
            <a href="#" class="logo">ZRJ_DreamSky的个人网站</a>
            <ul class="nav-menu">
                <li class="nav-item">首页</li>
                <li class="nav-item">关于我</li>
                <li class="nav-item">摄影作品</li>
                <li class="nav-item">拍摄设备</li>
                <li class="nav-item">联系方式</li>
            </ul>
        </div>
    </header>

    <!-- 英雄区域 -->
    <section class="hero">
        <div class="container" style="display: flex; align-items: center; flex-wrap: wrap;">
            <div class="hero-content">
                <h1 class="hero-title">ZRJ_DreamSky | 摄影UP主</h1>
                <h2 class="hero-subtitle">用镜头记录美好瞬间</h2>
                <p class="hero-desc">
                    我是一名热爱摄影和视频创作的UP主，专注于分享高质量的视觉内容。拥有丰富的创作经验，擅长无人机航拍、运动摄影和视频剪辑。希望通过我的作品，为大家带来美的享受和创作灵感。
                </p>
                <div class="hero-actions">
                    <a href="https://space.bilibili.com/3461577952987203" target="_blank" class="btn btn-primary">查看作品</a>
                    <a href="#equipment" class="btn btn-outline">拍摄设备</a>
                </div>
            </div>
            <div class="hero-image">
                <div class="profile-circle">
                    <img src="https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80" alt="ZRJ_DreamSky照片">
                </div>
            </div>
        </div>
    </section>

    <!-- 拍摄设备区域 -->
    <section id="equipment" class="equipment-section">
        <div class="container">
            <h2 class="section-title">拍摄设备</h2>
            <div class="equipment-grid">
                <div class="equipment-card">
                    <div class="equipment-icon">
                        <i class="fas fa-drone"></i>
                    </div>
                    <h3 class="equipment-name">DJI AIR3</h3>
                </div>
                
                <div class="equipment-card">
                    <div class="equipment-icon">
                        <i class="fas fa-microphone"></i>
                    </div>
                    <h3 class="equipment-name">DJI MIC2</h3>
                </div>
                
                <div class="equipment-card">
                    <div class="equipment-icon">
                        <i class="fas fa-video"></i>
                    </div>
                    <h3 class="equipment-name">DJI ACTION4</h3>
                </div>
                
                <div class="equipment-card">
                    <div class="equipment-icon">
                        <i class="fas fa-camera"></i>
                    </div>
                    <h3 class="equipment-name">索尼 ZEV10</h3>
                </div>
                
                <div class="equipment-card">
                    <div class="equipment-icon">
                        <i class="fas fa-mobile"></i>
                    </div>
                    <h3 class="equipment-name">小米13</h3>
                </div>
                
                <div class="equipment-card">
                    <div class="equipment-icon">
                        <i class="fas fa-tablet"></i>
                    </div>
                    <h3 class="equipment-name">小米 MIX FLOD4</h3>
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
                    <!-- 航拍作品 -->
                    <div class="carousel-item" style="background-image: url('https://i2.hdslb.com/bfs/archive/4c8e7d9c3a2f1b8e5d6c7b9a8f1e2d3c4.jpg');">
                        <div class="carousel-content">
                            <h3 class="carousel-title">无人机航拍作品</h3>
                            <p class="carousel-desc">使用DJI AIR3拍摄的壮丽航拍画面，展现高空视角的独特魅力</p>
                        </div>
                    </div>
                    
                    <!-- 手机摄影 -->
                    <div class="carousel-item" style="background-image: url('https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/ae07e7c9c8a1b2d3e4f5a6b7c8d9e0f1.jpg');">
                        <div class="carousel-content">
                            <h3 class="carousel-title">手机摄影作品</h3>
                            <p class="carousel-desc">小米13拍摄的高质量影像，展现手机摄影的强大能力</p>
                        </div>
                    </div>
                    
                    <!-- 创意视频 -->
                    <div class="carousel-item" style="background-image: url('https://i1.hdslb.com/bfs/archive/9a8b7c6d5e4f3a2b1c0d9e8f7a6b5c4d3.jpg');">
                        <div class="carousel-content">
                            <h3 class="carousel-title">创意视频作品</h3>
                            <p class="carousel-desc">使用DJI ACTION4拍摄的创意视频，展现动态摄影的无限可能</p>
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
            <h2 class="section-title">关注我的频道</h2>
            <div class="contact-grid">
                <!-- 哔哩哔哩 -->
                <div class="contact-card">
                    <div class="contact-icon">
                        <i class="fab fa-bilibili"></i>
                    </div>
                    <h3 class="contact-title">哔哩哔哩</h3>
                    <p class="contact-info">最新视频作品都在这里</p>
                    <a href="https://space.bilibili.com/3461577952987203" target="_blank" class="contact-link">前往主页</a>
                </div>
                
                <!-- 抖音 -->
                <div class="contact-card">
                    <div class="contact-icon">
                        <i class="fab fa-tiktok"></i>
                    </div>
                    <h3 class="contact-title">抖音</h3>
                    <p class="contact-info">短视频创作与分享</p>
                    <a href="https://www.douyin.com/user/MS4wLjABAAAA5fJci06S9hUnQwYI3bzrFFapkm_qdi3tO4Ea8m_2XzRU4UapTuggLTH7TaDwMz0z?from_tab_name=main" target="_blank" class="contact-link">关注我</a>
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
                        <li><a href="#">创作理念</a></li>
                        <li><a href="#">合作经历</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>作品分类</h3>
                    <ul class="footer-links">
                        <li><a href="https://www.bilibili.com/video/BV1oDL7zKEGB" target="_blank">无人机航拍</a></li>
                        <li><a href="https://www.mi.com/visual/award/workDetail?id=68a43c7ce9d03a2fc649d5ce&status=3&spmref=my_works.my_works_list.5" target="_blank">手机摄影</a></li>
                        <li><a href="https://www.bilibili.com/video/BV1BraDzuELy" target="_blank">创意视频</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>设备评测</h3>
                    <ul class="footer-links">
                        <li><a href="#">DJI设备</a></li>
                        <li><a href="#">索尼相机</a></li>
                        <li><a href="#">小米手机</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>商务合作</h3>
                    <ul class="footer-links">
                        <li><a href="mailto:contact@example.com">合作邮箱</a></li>
                        <li><a href="tel:+8613888888888">联系电话</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>© 2024 ZRJ_DreamSky个人网站 版权所有</p>
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
            
            // 点击轮播图跳转到对应作品
            const carouselLinks = [
                'https://www.bilibili.com/video/BV1oDL7zKEGB',
                'https://www.mi.com/visual/award/workDetail?id=68a43c7ce9d03a2fc649d5ce&status=3&spmref=my_works.my_works_list.5',
                'https://www.bilibili.com/video/BV1BraDzuELy'
            ];
            
            document.querySelectorAll('.carousel-item').forEach((item, index) => {
                item.style.cursor = 'pointer';
                item.addEventListener('click', () => {
                    window.open(carouselLinks[index], '_blank');
                });
            });
        });
    </script>
</body>
</html>
