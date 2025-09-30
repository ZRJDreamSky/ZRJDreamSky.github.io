<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>科技产品商城 - 小米风格网站</title>
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

        .header-actions {
            display: flex;
            gap: 15px;
        }

        .action-btn {
            display: flex;
            align-items: center;
            gap: 5px;
            padding: 8px 15px;
            border-radius: 4px;
            transition: var(--mi-transition);
        }

        .action-btn:hover {
            background-color: var(--mi-gray);
        }

        .search-btn {
            background-color: var(--mi-orange);
            color: white;
        }

        .search-btn:hover {
            background-color: var(--mi-dark-orange);
        }

        /* 轮播图区域 */
        .mi-carousel {
            position: relative;
            height: 500px;
            overflow: hidden;
            margin-bottom: 40px;
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
            align-items: center;
        }

        .carousel-content {
            max-width: 600px;
            padding: 0 60px;
            color: white;
        }

        .carousel-title {
            font-size: 48px;
            font-weight: bold;
            margin-bottom: 20px;
            text-shadow: 0 2px 4px rgba(0,0,0,0.3);
        }

        .carousel-desc {
            font-size: 20px;
            margin-bottom: 30px;
            text-shadow: 0 1px 2px rgba(0,0,0,0.3);
        }

        .carousel-btn {
            display: inline-block;
            padding: 12px 30px;
            background-color: var(--mi-orange);
            color: white;
            border-radius: 4px;
            font-weight: bold;
            transition: var(--mi-transition);
        }

        .carousel-btn:hover {
            background-color: var(--mi-dark-orange);
            transform: translateY(-2px);
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
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background-color: rgba(255,255,255,0.5);
            cursor: pointer;
            transition: var(--mi-transition);
        }

        .control-dot.active {
            background-color: white;
            transform: scale(1.2);
        }

        /* 产品展示区 */
        .section-title {
            font-size: 28px;
            text-align: center;
            margin: 40px 0 30px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 40px;
            height: 2px;
            background-color: var(--mi-orange);
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }

        .product-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--mi-shadow);
            transition: var(--mi-transition);
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }

        .product-img {
            height: 200px;
            background-color: var(--mi-bg-light);
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .product-img img {
            max-width: 100%;
            max-height: 160px;
            object-fit: contain;
        }

        .product-info {
            padding: 20px;
        }

        .product-name {
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .product-desc {
            color: var(--mi-dark-gray);
            font-size: 14px;
            margin-bottom: 15px;
            height: 40px;
            overflow: hidden;
        }

        .product-price {
            color: var(--mi-orange);
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 15px;
        }

        .product-btn {
            display: block;
            width: 100%;
            padding: 10px;
            text-align: center;
            background-color: var(--mi-orange);
            color: white;
            border-radius: 4px;
            transition: var(--mi-transition);
        }

        .product-btn:hover {
            background-color: var(--mi-dark-orange);
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
        @media (max-width: 768px) {
            .nav-menu {
                display: none;
            }
            
            .carousel-title {
                font-size: 36px;
            }
            
            .carousel-desc {
                font-size: 18px;
            }
            
            .products-grid {
                grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            }
        }
    </style>
</head>
<body>
    <!-- 导航栏 -->
    <header class="mi-header">
        <div class="container header-container">
            <a href="#" class="logo">TechStore</a>
            <ul class="nav-menu">
                <li class="nav-item">首页</li>
                <li class="nav-item">手机</li>
                <li class="nav-item">笔记本</li>
                <li class="nav-item">电视</li>
                <li class="nav-item">智能家居</li>
                <li class="nav-item">配件</li>
                <li class="nav-item">服务</li>
            </ul>
            <div class="header-actions">
                <a href="#" class="action-btn">
                    <i class="fas fa-user"></i>
                    <span>登录</span>
                </a>
                <a href="#" class="action-btn">
                    <i class="fas fa-shopping-cart"></i>
                    <span>购物车</span>
                </a>
                <a href="#" class="action-btn search-btn">
                    <i class="fas fa-search"></i>
                    <span>搜索</span>
                </a>
            </div>
        </div>
    </header>

    <!-- 轮播图 -->
    <section class="mi-carousel">
        <div class="carousel-inner">
            <div class="carousel-item" style="background: linear-gradient(to right, #4a00e0, #8e2de2);">
                <div class="carousel-content">
                    <h2 class="carousel-title">全新旗舰手机</h2>
                    <p class="carousel-desc">突破性创新，重新定义智能手机体验</p>
                    <a href="#" class="carousel-btn">立即购买</a>
                </div>
            </div>
            <div class="carousel-item" style="background: linear-gradient(to right, #11998e, #38ef7d);">
                <div class="carousel-content">
                    <h2 class="carousel-title">智能家居套装</h2>
                    <p class="carousel-desc">打造您的智慧生活，让科技更懂您</p>
                    <a href="#" class="carousel-btn">查看详情</a>
                </div>
            </div>
        </div>
        <div class="carousel-controls">
            <div class="control-dot active"></div>
            <div class="control-dot"></div>
        </div>
    </section>

    <!-- 产品展示区 -->
    <section class="container">
        <h2 class="section-title">热门产品</h2>
        <div class="products-grid">
            <!-- 产品卡片 1 -->
            <div class="product-card">
                <div class="product-img">
                    <img src="https://via.placeholder.com/200x150?text=旗舰手机" alt="旗舰手机">
                </div>
                <div class="product-info">
                    <h3 class="product-name">旗舰智能手机 Pro</h3>
                    <p class="product-desc">高性能处理器，超清摄像头，长续航电池</p>
                    <div class="product-price">¥3,299</div>
                    <a href="#" class="product-btn">加入购物车</a>
                </div>
            </div>
            
            <!-- 产品卡片 2 -->
            <div class="product-card">
                <div class="product-img">
                    <img src="https://via.placeholder.com/200x150?text=轻薄笔记本" alt="轻薄笔记本">
                </div>
                <div class="product-info">
                    <h3 class="product-name">超薄笔记本电脑</h3>
                    <p class="product-desc">轻薄设计，强劲性能，超长续航</p>
                    <div class="product-price">¥5,999</div>
                    <a href="#" class="product-btn">加入购物车</a>
                </div>
            </div>
            
            <!-- 产品卡片 3 -->
            <div class="product-card">
                <div class="product-img">
                    <img src="https://via.placeholder.com/200x150?text=智能手表" alt="智能手表">
                </div>
                <div class="product-info">
                    <h3 class="product-name">智能运动手表</h3>
                    <p class="product-desc">健康监测，运动追踪，超长续航</p>
                    <div class="product-price">¥899</div>
                    <a href="#" class="product-btn">加入购物车</a>
                </div>
            </div>
            
            <!-- 产品卡片 4 -->
            <div class="product-card">
                <div class="product-img">
                    <img src="https://via.placeholder.com/200x150?text=无线耳机" alt="无线耳机">
                </div>
                <div class="product-info">
                    <h3 class="product-name">真无线蓝牙耳机</h3>
                    <p class="product-desc">主动降噪，高清音质，舒适佩戴</p>
                    <div class="product-price">¥399</div>
                    <a href="#" class="product-btn">加入购物车</a>
                </div>
            </div>
        </div>
    </section>

    <!-- 页脚 -->
    <footer class="mi-footer">
        <div class="container">
            <div class="footer-grid">
                <div class="footer-col">
                    <h3>帮助中心</h3>
                    <ul class="footer-links">
                        <li><a href="#">账户管理</a></li>
                        <li><a href="#">购物指南</a></li>
                        <li><a href="#">订单操作</a></li>
                        <li><a href="#">配送方式</a></li>
                        <li><a href="#">售后服务</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>服务支持</h3>
                    <ul class="footer-links">
                        <li><a href="#">售后政策</a></li>
                        <li><a href="#">自助服务</a></li>
                        <li><a href="#">维修网点</a></li>
                        <li><a href="#">预约维修</a></li>
                        <li><a href="#">防伪查询</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>关于我们</h3>
                    <ul class="footer-links">
                        <li><a href="#">公司介绍</a></li>
                        <li><a href="#">加入我们</a></li>
                        <li><a href="#">联系我们</a></li>
                        <li><a href="#">投资者关系</a></li>
                        <li><a href="#">企业社会责任</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>关注我们</h3>
                    <ul class="footer-links">
                        <li><a href="#"><i class="fab fa-weixin"></i> 微信公众号</a></li>
                        <li><a href="#"><i class="fab fa-weibo"></i> 新浪微博</a></li>
                        <li><a href="#"><i class="fab fa-tiktok"></i> 抖音</a></li>
                        <li><a href="#"><i class="fab fa-youtube"></i> YouTube</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>© 2023 TechStore 科技产品商城 版权所有 保留所有权利</p>
                <p>京ICP备12345678号 | 增值电信业务经营许可证：京B2-20230101</p>
