<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ZRJ_DreamSky的个人网站</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- 百度统计 - 新版代码 -->
    <script>
        var _hmt = _hmt || [];
        (function() {
          var hm = document.createElement("script");
          hm.src = "https://hm.baidu.com/hm.js?258ef310c5b2364e98f8cc64c21e6603";
          var s = document.getElementsByTagName("script")[0]; 
          s.parentNode.insertBefore(hm, s);
        })();
    </script>
    
    <style>
        /* 小米风格变量系统 */
        :root {
            --mi-orange: #ff6700; --mi-light-orange: #ff761a; --mi-dark-orange: #e65c00;
            --mi-bg-light: #f5f5f5; --mi-bg-dark: #181a1b; --mi-text-dark: #333;
            --mi-text-light: #fff; --mi-gray: #e0e0e0; --mi-dark-gray: #757575;
            --mi-shadow: 0 2px 10px rgba(0,0,0,0.1); --mi-transition: all 0.3s ease;
        }
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Segoe UI', 'Microsoft YaHei', sans-serif; background-color: #fff; color: var(--mi-text-dark); line-height: 1.6; overflow-x: hidden; }
        a { text-decoration: none; color: inherit; }
        ul { list-style: none; }
        .container { width: 100%; max-width: 1280px; margin: 0 auto; padding: 0 20px; }
        
        /* 导航栏 */
        .mi-header { background-color: rgba(255, 255, 255, 0.95); box-shadow: var(--mi-shadow); position: sticky; top: 0; z-index: 1000; backdrop-filter: blur(10px); }
        .header-container { display: flex; justify-content: space-between; align-items: center; height: 60px; }
        .logo { font-size: 24px; font-weight: bold; color: var(--mi-orange); }
        .nav-menu { display: flex; }
        .nav-item { padding: 0 15px; height: 60px; display: flex; align-items: center; transition: var(--mi-transition); position: relative; cursor: pointer; }
        .nav-item:hover { color: var(--mi-orange); }
        .nav-item:hover::after { content: ''; position: absolute; bottom: 0; left: 15px; right: 15px; height: 2px; background-color: var(--mi-orange); }
        
        /* 英雄区域 */
        .hero { display: flex; align-items: center; min-height: 80vh; padding: 80px 0; background: linear-gradient(135deg, #f5f5f5 0%, #ffffff 100%); }
        .hero-content { flex: 1; max-width: 600px; }
        .hero-title { font-size: 48px; font-weight: bold; margin-bottom: 20px; line-height: 1.2; }
        .hero-subtitle { font-size: 24px; color: var(--mi-dark-gray); margin-bottom: 30px; }
        .hero-desc { font-size: 18px; margin-bottom: 40px; line-height: 1.8; }
        .hero-actions { display: flex; gap: 15px; flex-wrap: wrap; }
        .btn { display: inline-block; padding: 12px 30px; border-radius: 4px; font-weight: bold; transition: var(--mi-transition); text-align: center; cursor: pointer; border: none; font-size: 16px; }
        .btn-primary { background-color: var(--mi-orange); color: white; }
        .btn-primary:hover { background-color: var(--mi-dark-orange); transform: translateY(-2px); box-shadow: 0 5px 15px rgba(255, 103, 0, 0.3); }
        .btn-outline { border: 2px solid var(--mi-orange); color: var(--mi-orange); background: transparent; }
        .btn-outline:hover { background-color: var(--mi-orange); color: white; transform: translateY(-2px); }
        .hero-image { flex: 1; display: flex; justify-content: center; align-items: center; }
        .profile-circle { width: 350px; height: 350px; border-radius: 50%; background: linear-gradient(135deg, var(--mi-orange) 0%, #ff8c00 100%); display: flex; justify-content: center; align-items: center; overflow: hidden; box-shadow: 0 20px 40px rgba(255, 103, 0, 0.2); }
        .profile-circle img { width: 100%; height: 100%; object-fit: cover; }
        
        /* 拍摄设备区域 */
        .equipment-section { padding: 100px 0; background-color: var(--mi-bg-light); }
        .section-title { font-size: 36px; text-align: center; margin-bottom: 60px; position: relative; }
        .section-title::after { content: ''; position: absolute; bottom: -15px; left: 50%; transform: translateX(-50%); width: 60px; height: 3px; background-color: var(--mi-orange); }
        .equipment-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 30px; }
        .equipment-card { background-color: white; border-radius: 12px; padding: 30px; box-shadow: var(--mi-shadow); transition: var(--mi-transition); text-align: center; cursor: pointer; }
        .equipment-card:hover { transform: translateY(-10px); box-shadow: 0 15px 30px rgba(0,0,0,0.1); }
        .equipment-icon { width: 80px; height: 80px; background-color: rgba(255, 103, 0, 0.1); border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 20px; font-size: 32px; color: var(--mi-orange); }
        .equipment-name { font-size: 24px; margin-bottom: 15px; color: var(--mi-text-dark); }
        
        /* 作品集轮播图 */
        .portfolio-section { padding: 100px 0; background-color: white; }
        .mi-carousel { position: relative; height: 500px; overflow: hidden; border-radius: 12px; box-shadow: 0 15px 30px rgba(0,0,0,0.1); }
        .carousel-inner { display: flex; transition: transform 0.5s ease; height: 100%; }
        .carousel-item { min-width: 100%; height: 100%; background-size: cover; background-position: center; display: flex; align-items: flex-end; position: relative; }
        .carousel-item::before { content: ''; position: absolute; top: 0; left: 0; right: 0; bottom: 0; background: linear-gradient(to top, rgba(0,0,0,0.8), transparent 50%); }
        .carousel-content { position: relative; z-index: 2; width: 100%; padding: 40px; color: white; }
        .carousel-title { font-size: 32px; font-weight: bold; margin-bottom: 10px; }
        .carousel-desc { font-size: 18px; max-width: 600px; opacity: 0.9; }
        .carousel-controls { position: absolute; bottom: 20px; left: 50%; transform: translateX(-50%); display: flex; gap: 10px; z-index: 3; }
        .control-dot { width: 12px; height: 12px; border-radius: 50%; background-color: rgba(255,255,255,0.5); cursor: pointer; transition: var(--mi-transition); }
        .control-dot.active { background-color: white; transform: scale(1.3); }
        
        /* 联系方式区域 */
        .contact-section { padding: 100px 0; background-color: var(--mi-bg-light); }
        .contact-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 40px; }
        .contact-card { background-color: white; border-radius: 8px; padding: 30px; box-shadow: var(--mi-shadow); transition: var(--mi-transition); text-align: center; }
        .contact-card:hover { transform: translateY(-10px); box-shadow: 0 15px 30px rgba(0,0,0,0.1); }
        .contact-icon { width: 80px; height: 80px; background-color: rgba(255, 103, 0, 0.1); border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 20px; font-size: 32px; color: var(--mi-orange); }
        .contact-title { font-size: 24px; margin-bottom: 15px; color: var(--mi-text-dark); }
        .contact-info { font-size: 18px; color: var(--mi-dark-gray); margin-bottom: 20px; }
        .contact-link { color: var(--mi-orange); font-weight: bold; transition: var(--mi-transition); display: inline-block; }
        .contact-link:hover { color: var(--mi-dark-orange); transform: translateY(-2px); }
        .social-links { display: flex; justify-content: center; gap: 15px; margin-top: 20px; }
        .social-link { width: 45px; height: 45px; border-radius: 50%; background-color: var(--mi-bg-light); display: flex; align-items: center; justify-content: center; font-size: 20px; transition: var(--mi-transition); color: var(--mi-dark-gray); }
        .social-link:hover { background-color: var(--mi-orange); color: white; transform: translateY(-5px); }
        
        /* 页脚 */
        .mi-footer { background-color: var(--mi-bg-dark); color: var(--mi-text-light); padding: 60px 0 30px; }
        .footer-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 30px; margin-bottom: 40px; }
        .footer-col h3 { font-size: 18px; margin-bottom: 20px; position: relative; padding-bottom: 10px; }
        .footer-col h3::after { content: ''; position: absolute; bottom: 0; left: 0; width: 30px; height: 2px; background-color: var(--mi-orange); }
        .footer-links li { margin-bottom: 10px; }
        .footer-links a { color: #aaa; transition: var(--mi-transition); }
        .footer-links a:hover { color: var(--mi-orange); }
        .footer-bottom { text-align: center; padding-top: 30px; border-top: 1px solid #333; color: #777; font-size: 14px; }
        
        /* 响应式设计 */
        @media (max-width: 1200px) { .hero-title { font-size: 42px; } .profile-circle { width: 320px; height: 320px; } }
        @media (max-width: 992px) { .hero { flex-direction: column; text-align: center; padding: 60px 0; min-height: auto; } .hero-content { margin-bottom: 50px; max-width: 100%; } .hero-actions { justify-content: center; } .profile-circle { width: 280px; height: 280px; } .mi-carousel { height: 400px; } }
        @media (max-width: 768px) { .nav-menu { display: none; } .hero-title { font-size: 36px; } .hero-subtitle { font-size: 20px; } .section-title { font-size: 28px; } .mi-carousel { height: 350px; } .carousel-content { padding: 20px; } .carousel-title { font-size: 28px; } .carousel-desc { font-size: 16px; } .equipment-grid { grid-template-columns: 1fr; gap: 20px; } }
        @media (max-width: 576px) { .container { padding: 0 15px; } .hero-title { font-size: 32px; } .hero-subtitle { font-size: 18px; } .hero-desc { font-size: 16px; } .hero-actions { flex-direction: column; align-items: center; gap: 10px; } .btn { width: 100%; max-width: 280px; } .mi-carousel { height: 300px; } .contact-card, .equipment-card { padding: 20px; } .section-title { font-size: 24px; } }
        
        /* 黑暗模式支持 */
        @media (prefers-color-scheme: dark) {
            body { background-color: #1a1a1a; color: #e0e0e0; }
            .mi-header { background-color: #2d2d2d; }
            .hero { background: linear-gradient(135deg, #2d2d2d 0%, #1a1a1a 100%); }
            .equipment-card, .contact-card { background-color: #2d2d2d; color: #e0e0e0; }
            .equipment-section, .contact-section { background-color: #1a1a1a; }
        }
    </style>
</head>
<body>
    <!-- 导航栏 -->
    <header class="mi-header">
        <div class="container header-container">
            <div class="logo">ZRJ_DreamSky</div>
            <nav class="nav-menu">
                <a href="#home" class="nav-item">首页</a>
                <a href="#equipment" class="nav-item">拍摄设备</a>
                <a href="#portfolio" class="nav-item">作品集</a>
                <a href="#contact" class="nav-item">联系我</a>
            </nav>
        </div>
    </header>

    <!-- 英雄区域 -->
    <section id="home" class="hero">
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
                    <i class="fas fa-user" style="font-size: 120px; color: white;"></i>
                </div>
            </div>
        </div>
    </section>

    <!-- 拍摄设备区域 -->
    <section id="equipment" class="equipment-section">
        <div class="container">
            <h2 class="section-title">拍摄设备</h2>
            <div class="equipment-grid">
                <a href="https://www.dji.com/cn/air-3" target="_blank" class="equipment-card">
                    <div class="equipment-icon"><i class="fas fa-drone"></i></div>
                    <h3 class="equipment-name">DJI AIR3</h3>
                </a>
                <a href="https://www.dji.com/cn/mic-2" target="_blank" class="equipment-card">
                    <div class="equipment-icon"><i class="fas fa-microphone"></i></div>
                    <h3 class="equipment-name">DJI MIC2</h3>
                </a>
                <a href="https://www.dji.com/cn/osmo-action-4" target="_blank" class="equipment-card">
                    <div class="equipment-icon"><i class="fas fa-video"></i></div>
                    <h3 class="equipment-name">DJI ACTION4</h3>
                </a>
                <a href="https://www.sonystyle.com.cn" target="_blank" class="equipment-card">
                    <div class="equipment-icon"><i class="fas fa-camera"></i></div>
                    <h3 class="equipment-name">索尼 ZEV10</h3>
                </a>
                <a href="https://www.mi.com/xiaomi-13" target="_blank" class="equipment-card">
                    <div class="equipment-icon"><i class="fas fa-mobile-alt"></i></div>
                    <h3 class="equipment-name">小米13</h3>
                </a>
                <a href="https://www.mi.com" target="_blank" class="equipment-card">
                    <div class="equipment-icon"><i class="fas fa-tablet-alt"></i></div>
                    <h3 class="equipment-name">小米 MIX FOLD4</h3>
                </a>
            </div>
        </div>
    </section>

    <!-- 作品集轮播图 -->
    <section id="portfolio" class="portfolio-section">
        <div class="container">
            <h2 class="section-title">精选作品</h2>
            <div class="mi-carousel">
                <div class="carousel-inner">
                    <div class="carousel-item" style="background-image: url('https://images.unsplash.com/photo-1477587458888-3cc2eeefff0e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80');">
                        <div class="carousel-content">
                            <h3 class="carousel-title">无人机航拍作品</h3>
                            <p class="carousel-desc">使用DJI AIR3拍摄的壮丽航拍画面，展现高空视角的独特魅力</p>
                        </div>
                    </div>
                    <div class="carousel-item" style="background-image: url('https://images.unsplash.com/photo-1550745165-9bc0b252726f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80');">
                        <div class="carousel-content">
                            <h3 class="carousel-title">手机摄影作品</h3>
                            <p class="carousel-desc">小米13拍摄的高质量影像，展现手机摄影的强大能力</p>
                        </div>
                    </div>
                    <div class="carousel-item" style="background-image: url('https://images.unsplash.com/photo-1558618047-3c8c76ca7d13?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2064&q=80');">
                        <div class="carousel-content">
                            <h3 class="carousel-title">创意视频作品</h3>
                            <p class="carousel-desc">使用DJI ACTION4拍摄的创意视频，展现动态摄影的无限可能</p>
                        </div>
                    </div>
                </div>
                <div class="carousel-controls">
                    <div class="control-dot active" data-index="0"></div>
                    <div class="control-dot" data-index="1"></div>
                    <div class="control-dot" data-index="2"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- 联系方式区域 -->
    <section id="contact" class="contact-section">
        <div class="container">
            <h2 class="section-title">关注我的频道</h2>
            <div class="contact-grid">
                <div class="contact-card">
                    <div class="contact-icon"><i class="fab fa-bilibili"></i></div>
                    <h3 class="contact-title">哔哩哔哩</h3>
                    <p class="contact-info">最新视频作品都在这里</p>
                    <a href="https://space.bilibili.com/3461577952987203" target="_blank" class="contact-link">前往主页 →</a>
                    <div class="social-links">
                        <a href="https://space.bilibili.com/3461577952987203" target="_blank" class="social-link"><i class="fas fa-external-link-alt"></i></a>
                    </div>
                </div>
                <div class="contact-card">
                    <div class="contact-icon"><i class="fab fa-tiktok"></i></div>
                    <h3 class="contact-title">抖音</h3>
                    <p class="contact-info">短视频创作与分享</p>
                    <a href="https://www.douyin.com/user/MS4wLjABAAAA5fJci06S9hUnQwYI3bzrFFapkm_qdi3tO4Ea8m_2XzRU4UapTuggLTH7TaDwMz0z" target="_blank" class="contact-link">关注我 →</a>
                    <div class="social-links">
                        <a href="https://www.douyin.com/user/MS4wLjABAAAA5fJci06S9hUnQwYI3bzrFFapkm_qdi3tO4Ea8m_2XzRU4UapTuggLTH7TaDwMz0z" target="_blank" class="social-link"><i class="fas fa-external-link-alt"></i></a>
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
                        <li><a href="#home">个人简介</a></li>
                        <li><a href="#">创作理念</a></li>
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
                        <li><a href="https://www.dji.com/cn" target="_blank">DJI设备</a></li>
                        <li><a href="https://www.sonystyle.com.cn" target="_blank">索尼相机</a></li>
                        <li><a href="https://www.mi.com" target="_blank">小米手机</a></li>
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
            let autoPlayInterval;
            const slideCount = document.querySelectorAll('.carousel-item').length;

            function updateCarousel() {
                carouselInner.style.transform = `translateX(-${currentIndex * 100}%)`;
                dots.forEach((dot, index) => {
                    dot.classList.toggle('active', index === currentIndex);
                });
            }

            function startAutoPlay() {
                autoPlayInterval = setInterval(() => {
                    currentIndex = (currentIndex + 1) % slideCount;
                    updateCarousel();
                }, 5000);
            }

            function stopAutoPlay() {
                clearInterval(autoPlayInterval);
            }

            startAutoPlay();
            dots.forEach((dot) => {
                dot.addEventListener('click', (e) => {
                    currentIndex = parseInt(e.target.getAttribute('data-index'));
                    updateCarousel();
                    stopAutoPlay();
                    startAutoPlay();
                });
            });

            const carousel = document.querySelector('.mi-carousel');
            carousel.addEventListener('mouseenter', stopAutoPlay);
            carousel.addEventListener('mouseleave', startAutoPlay);

            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                    }
                });
            });
        });
    </script>
</body>
</html>
