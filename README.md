# Almanhaldarululummdrasha
 ﷽
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>আল-মনহাল দারুল উলূম মাদ্রাসা</title>
    
    <!-- Firebase SDK -->
    <script src="https://www.gstatic.com/firebasejs/9.22.1/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.22.1/firebase-auth-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.22.1/firebase-database-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.22.1/firebase-storage-compat.js"></script>
    
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Amiri:ital,wght@0,400;0,700;1,400;1,700&family=Hind+Siliguri:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary-green: #008000;
            --gold: #d4af37;
            --white: #ffffff;
            --light-bg: #f9f9f9;
            --dark-text: #333333;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Hind Siliguri', sans-serif;
            color: var(--dark-text);
            background-color: var(--light-bg);
            line-height: 1.6;
        }
        
        .arabic {
            font-family: 'Amiri', serif;
        }
        
        /* Header Styles */
        header {
            background-color: var(--primary-green);
            color: var(--white);
            padding: 15px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .logo {
            display: flex;
            align-items: center;
        }
        
        .logo-img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            object-fit: cover;
            margin-right: 15px;
        }
        
        .logo-text {
            margin-left: 15px;
        }
        
        .logo h1 {
            font-size: 1.8rem;
            margin-bottom: 5px;
        }
        
        .logo p {
            font-size: 0.9rem;
            opacity: 0.9;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 25px;
        }
        
        nav ul li a {
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        nav ul li a:hover {
            color: var(--gold);
        }
        
        .mobile-menu {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        /* Hero Section */
        .hero {
            background-size: cover;
            background-position: center;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--white);
            padding-top: 80px;
        }
        
        .hero-content {
            max-width: 800px;
            padding: 0 20px;
        }
        
        .hero-content .arabic {
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: var(--gold);
        }
        
        .hero-content h2 {
            font-size: 2.8rem;
            margin-bottom: 20px;
        }
        
        .hero-content p {
            font-size: 1.2rem;
            margin-bottom: 30px;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--gold);
            color: var(--white);
            padding: 12px 30px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
            margin: 0 10px;
        }
        
        .btn:hover {
            background-color: #b8941f;
            transform: translateY(-3px);
        }
        
        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--gold);
        }
        
        .btn-outline:hover {
            background-color: var(--gold);
        }
        
        /* Section Styles */
        section {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }
        
        .section-title h2 {
            font-size: 2.2rem;
            color: var(--primary-green);
            margin-bottom: 15px;
        }
        
        .section-title p {
            max-width: 700px;
            margin: 0 auto;
            color: #666;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* About Section */
        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }
        
        .about-img {
            flex: 1;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }
        
        .about-img img {
            width: 100%;
            height: auto;
            display: block;
        }
        
        .about-text {
            flex: 1;
        }
        
        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--primary-green);
        }
        
        /* Courses Section */
        .courses-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .course-card {
            background-color: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }
        
        .course-card:hover {
            transform: translateY(-10px);
        }
        
        .course-icon {
            background-color: var(--primary-green);
            color: var(--white);
            height: 80px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
        }
        
        .course-content {
            padding: 25px;
        }
        
        .course-content h3 {
            font-size: 1.4rem;
            margin-bottom: 15px;
            color: var(--primary-green);
        }
        
        /* Teachers Section */
        .teachers-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
        }
        
        .teacher-card {
            background-color: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            text-align: center;
        }
        
        .teacher-img {
            height: 200px;
            overflow: hidden;
        }
        
        .teacher-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .teacher-info {
            padding: 20px;
        }
        
        .teacher-info h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--primary-green);
        }
        
        .teacher-info p {
            color: #666;
            margin-bottom: 15px;
            font-size: 0.9rem;
        }
        
        /* Notice Board */
        .notice-board {
            background-color: var(--white);
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .notice-item {
            padding: 15px 0;
            border-bottom: 1px solid #eee;
            display: flex;
            align-items: center;
        }
        
        .notice-item:last-child {
            border-bottom: none;
        }
        
        .notice-icon {
            background-color: var(--primary-green);
            color: var(--white);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            flex-shrink: 0;
        }
        
        .notice-content h4 {
            font-size: 1.1rem;
            margin-bottom: 5px;
        }
        
        .notice-content p {
            color: #666;
            font-size: 0.9rem;
        }
        
        /* Gallery */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 15px;
        }
        
        .gallery-item {
            height: 200px;
            border-radius: 8px;
            overflow: hidden;
            cursor: pointer;
        }
        
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s;
        }
        
        .gallery-item:hover img {
            transform: scale(1.1);
        }
        
        /* Blog Section */
        .blog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }
        
        .blog-card {
            background-color: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .blog-img {
            height: 200px;
            overflow: hidden;
        }
        
        .blog-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s;
        }
        
        .blog-card:hover .blog-img img {
            transform: scale(1.1);
        }
        
        .blog-content {
            padding: 25px;
        }
        
        .blog-meta {
            display: flex;
            margin-bottom: 15px;
            font-size: 0.85rem;
            color: #666;
        }
        
        .blog-meta span {
            margin-right: 15px;
        }
        
        .blog-content h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: var(--primary-green);
        }
        
        /* Contact Section */
        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
        }
        
        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        .contact-item {
            display: flex;
            align-items: flex-start;
            gap: 15px;
        }
        
        .contact-icon {
            background-color: var(--primary-green);
            color: var(--white);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }
        
        .contact-text h4 {
            font-size: 1.1rem;
            margin-bottom: 5px;
        }
        
        .contact-form {
            background-color: var(--white);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: 'Hind Siliguri', sans-serif;
            font-size: 1rem;
        }
        
        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }
        
        /* Prayer Time Section */
        .prayer-times {
            background-color: var(--primary-green);
            color: var(--white);
            padding: 50px 0;
            text-align: center;
        }
        
        .prayer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }
        
        .prayer-card {
            background-color: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 10px;
        }
        
        .prayer-card.active {
            background-color: var(--gold);
            color: var(--dark-text);
        }
        
        .prayer-name {
            font-size: 1.2rem;
            margin-bottom: 10px;
        }
        
        .prayer-time {
            font-size: 1.5rem;
            font-weight: bold;
        }
        
        /* Quran Section */
        .quran-section {
            background-color: var(--light-bg);
            padding: 80px 0;
        }
        
        .quran-card {
            background-color: var(--white);
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            text-align: center;
            margin-bottom: 30px;
        }
        
        .quran-arabic {
            font-size: 2rem;
            margin-bottom: 20px;
            line-height: 1.8;
        }
        
        .quran-translation {
            font-size: 1.1rem;
            color: #666;
            margin-bottom: 20px;
        }
        
        .quran-reference {
            color: var(--primary-green);
            font-weight: 600;
        }
        
        /* Footer */
        footer {
            background-color: var(--primary-green);
            color: var(--white);
            padding: 60px 0 20px;
        }
        
        .footer-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
        }
        
        .footer-logo h3 {
            font-size: 1.8rem;
            margin-bottom: 15px;
        }
        
        .footer-links h4, .footer-social h4 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-links h4:after, .footer-social h4:after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 50px;
            height: 2px;
            background-color: var(--gold);
        }
        
        .footer-links ul {
            list-style: none;
        }
        
        .footer-links ul li {
            margin-bottom: 10px;
        }
        
        .footer-links ul li a {
            color: #ddd;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links ul li a:hover {
            color: var(--gold);
        }
        
        .social-icons {
            display: flex;
            gap: 15px;
        }
        
        .social-icons a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: var(--white);
            text-decoration: none;
            transition: all 0.3s;
        }
        
        .social-icons a:hover {
            background-color: var(--gold);
            transform: translateY(-5px);
        }
        
        .copyright {
            text-align: center;
            margin-top: 50px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            color: #ddd;
        }
        
        /* Login/Register Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 2000;
            align-items: center;
            justify-content: center;
        }
        
        .modal-content {
            background-color: var(--white);
            width: 90%;
            max-width: 500px;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }
        
        .modal-header {
            background-color: var(--primary-green);
            color: var(--white);
            padding: 20px;
            text-align: center;
            position: relative;
        }
        
        .close-modal {
            position: absolute;
            right: 15px;
            top: 15px;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        .modal-body {
            padding: 30px;
        }
        
        .form-tabs {
            display: flex;
            margin-bottom: 20px;
            border-bottom: 1px solid #ddd;
        }
        
        .tab-btn {
            flex: 1;
            padding: 12px;
            background: none;
            border: none;
            font-family: 'Hind Siliguri', sans-serif;
            font-size: 1rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s;
            border-bottom: 2px solid transparent;
        }
        
        .tab-btn.active {
            color: var(--primary-green);
            border-bottom: 2px solid var(--primary-green);
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
        }
        
        /* User Profile */
        .user-profile {
            display: none;
            align-items: center;
        }
        
        .profile-img {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            margin-right: 10px;
            object-fit: cover;
        }
        
        /* Admin Panel Link */
        .admin-panel-link {
            background-color: var(--gold);
            padding: 8px 15px;
            border-radius: 5px;
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            margin-left: 15px;
        }
        
        /* Responsive Styles */
        @media (max-width: 992px) {
            .about-content {
                flex-direction: column;
            }
            
            .contact-container {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 768px) {
            nav ul {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background-color: var(--primary-green);
                flex-direction: column;
                padding: 20px 0;
                box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
            }
            
            nav ul.active {
                display: flex;
            }
            
            nav ul li {
                margin: 0;
                text-align: center;
                padding: 10px 0;
            }
            
            .mobile-menu {
                display: block;
            }
            
            .hero-content h2 {
                font-size: 2.2rem;
            }
            
            .hero-content .arabic {
                font-size: 2rem;
            }
            
            .prayer-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }
        
        @media (max-width: 576px) {
            .hero-content h2 {
                font-size: 1.8rem;
            }
            
            .hero-content .arabic {
                font-size: 1.6rem;
            }
            
            .btn {
                display: block;
                margin: 10px auto;
                width: 80%;
            }
            
            .section-title h2 {
                font-size: 1.8rem;
            }
            
            .prayer-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-container">
            <div class="logo">
                <img id="headerLogo" src="" alt="Logo" class="logo-img" style="display: none;">
                <div class="logo-text">
                    <h1 class="arabic" id="headerArabicText">المنحل دارل علوم مدرسة</h1>
                    <p id="headerBengaliText">আল-মনহাল দারুল উলূম মাদ্রাসা</p>
                </div>
            </div>
            <nav>
                <div class="mobile-menu">
                    <i class="fas fa-bars"></i>
                </div>
                <ul>
                    <li><a href="#home"><i class="fas fa-home"></i> হোম</a></li>
                    <li><a href="#about"><i class="fas fa-info-circle"></i> আমাদের সম্পর্কে</a></li>
                    <li><a href="#courses"><i class="fas fa-book"></i> আমাদের ক্লাস সমুহ </a></li>
                    <li><a href="#teachers"><i class="fas fa-user-graduate"></i> আলেমদের পরামর্শ</a></li>
                    <li><a href="#prayer"><i class="fas fa-clock"></i> নামাজের সময়</a></li>
                    <li><a href="#quran"><i class="fas fa-quran"></i> কুরআন ও হাদিস</a></li>
                    <li><a href="#notice"><i class="fas fa-bullhorn"></i> নোটিশ বোর্ড</a></li>
                    <li><a href="#gallery"><i class="fas fa-images"></i> গ্যালারি</a></li>
                    <li><a href="#blog"><i class="fas fa-blog"></i> ইসলামিক ব্লগ</a></li>
                    <li><a href="#contact"><i class="fas fa-phone-alt"></i> যোগাযোগ</a></li>
                    <li class="user-profile">
                        <img src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="User" class="profile-img">
                        <span id="userName">ইউজার</span>
                        <a href="admin.html" class="admin-panel-link" id="adminLink" style="display: none;">এডমিন</a>
                        <button id="logoutBtn" class="btn btn-sm" style="margin-left: 10px; display: none;">লগআউট</button>
                    </li>
                    <li><a href="#" class="login-btn" id="loginBtn"><i class="fas fa-sign-in-alt"></i> লগইন</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home" style="background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6));">
        <div class="hero-content">
            <p class="arabic" id="heroArabicText">بِسْمِ اللهِ الرَّحْمٰنِ الرَّحِيْمِ</p>
            <h2 id="heroMainTitle">আল-মনহাল দারুল উলূম মাদ্রাসায় স্বাগতম</h2>
            <p id="heroSubTitle">"একটি আধুনিক ইসলামিক শিক্ষা কেন্দ্র"</p>
            <div class="hero-buttons">
                <a href="#about" class="btn">আমাদের সম্পর্কে জানুন</a>
                <a href="#" class="btn btn-outline register-btn">এখনই রেজিস্টার করুন</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <div class="section-title">
                <h2 id="aboutTitle">আমাদের সম্পর্কে</h2>
                <p id="aboutSubtitle">প্রতিষ্ঠার সাল, লক্ষ্য, কাজের ধরণ এবং ইসলামিক শিক্ষা ও প্রযুক্তি মিশ্রিত শিক্ষা ব্যবস্থা</p>
            </div>
            <div class="about-content">
                <div class="about-img">
                    <img id="aboutImage" src="" alt="আল-মনহাল দারুল উলূম মাদ্রাসা">
                </div>
                <div class="about-text">
                    <h3 id="aboutHeading">আল-মনহাল দারুল উলূম মাদ্রাসা</h3>
                    <p id="aboutDescription">আল-মনহাল দারুল উলূম মাদ্রাসা ১৯৯৫ সালে প্রতিষ্ঠিত একটি আধুনিক ইসলামিক শিক্ষা প্রতিষ্ঠান। আমাদের লক্ষ্য হল ইসলামিক জ্ঞান ও আধুনিক শিক্ষার সমন্বয়ে একটি ভারসাম্যপূর্ণ শিক্ষা ব্যবস্থা গড়ে তোলা।</p>
                    <p id="aboutDescription2">আমাদের মাদ্রাসায় ইবতেদায়ি থেকে শুরু করে কাফিয়া পর্যন্ত সকল স্তরের শিক্ষা প্রদান করা হয়। এছাড়াও হিফজ বিভাগে কুরআন মুখস্থ করার সুযোগ রয়েছে। আমরা শিক্ষার্থীদের নৈতিক ও আধ্যাত্মিক উন্নতির পাশাপাশি প্রযুক্তিগত দক্ষতাও প্রদান করি।</p>
                    <a href="#" class="btn">আরও পড়ুন</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Courses Section -->
    <section id="courses" class="courses">
        <div class="container">
            <div class="section-title">
                <h2>ইসলামিক কোর্সসমূহ</h2>
                <p>আমাদের মাদ্রাসায় প্রদানকৃত বিভিন্ন স্তরের ইসলামিক শিক্ষা কোর্স</p>
            </div>
            <div class="courses-grid" id="coursesContainer">
                <!-- Courses will be loaded from Firebase -->
            </div>
        </div>
    </section>

    <!-- Teachers Section -->
    <section id="teachers" class="teachers">
        <div class="container">
            <div class="section-title">
                <h2>আলেম ও শিক্ষকবৃন্দ</h2>
                <p>আমাদের মাদ্রাসার অভিজ্ঞ ও যোগ্য আলেম ও শিক্ষকবৃন্দ</p>
            </div>
            <div class="teachers-grid" id="teachersContainer">
                <!-- Teachers will be loaded from Firebase -->
            </div>
        </div>
    </section>

    <!-- Prayer Times Section -->
    <section id="prayer" class="prayer-times">
        <div class="container">
            <div class="section-title">
                <h2 style="color: var(--white);">নামাজের সময়সূচী</h2>
                <p style="color: rgba(255,255,255,0.8);">আজকের নামাজের সময়সূচী</p>
            </div>
            <div class="prayer-grid" id="prayerTimesContainer">
                <!-- Prayer times will be loaded by JavaScript -->
            </div>
        </div>
    </section>

    <!-- Quran Section -->
    <section id="quran" class="quran-section">
        <div class="container">
            <div class="section-title">
                <h2>কুরআন ও হাদিস</h2>
                <p>প্রতিদিনের কুরআনের আয়াত ও হাদিস</p>
            </div>
            <div class="quran-card">
                <div class="quran-arabic" id="quranVerse">
                    بِسْمِ اللَّهِ الرَّحْمَٰنِ الرَّحِيمِ
                </div>
                <div class="quran-translation" id="quranTranslation">
                    পরম করুণাময় ও অসীম দয়ালু আল্লাহর নামে শুরু করছি।
                </div>
                <div class="quran-reference" id="quranReference">
                    সূরা আল-ফাতিহা, আয়াত: ১
                </div>
                <button class="btn" id="nextVerse">পরবর্তী আয়াত</button>
            </div>
        </div>
    </section>

    <!-- Notice Board Section -->
    <section id="notice" class="notice">
        <div class="container">
            <div class="section-title">
                <h2>নোটিশ বোর্ড</h2>
                <p>মাদ্রাসার সর্বশেষ নোটিশ ও ঘোষণাসমূহ</p>
            </div>
            <div class="notice-board" id="noticesContainer">
                <!-- Notices will be loaded from Firebase -->
            </div>
            <div style="text-align: center; margin-top: 30px;">
                <a href="#" class="btn">সব নোটিশ দেখুন</a>
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section id="gallery" class="gallery">
        <div class="container">
            <div class="section-title">
                <h2>গ্যালারি</h2>
                <p>আমাদের মাদ্রাসার বিভিন্ন কার্যক্রম ও অনুষ্ঠানের ছবিসমূহ</p>
            </div>
            <div class="gallery-grid" id="galleryContainer">
                <!-- Gallery images will be loaded from Firebase -->
            </div>
        </div>
    </section>

    <!-- Blog Section -->
    <section id="blog" class="blog">
        <div class="container">
            <div class="section-title">
                <h2>ইসলামিক ব্লগ</h2>
                <p>ইসলামিক আর্টিকেল, গল্প ও শিক্ষামূলক পোস্ট</p>
            </div>
            <div class="blog-grid" id="blogContainer">
                <!-- Blog posts will be loaded from Firebase -->
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <div class="section-title">
                <h2>যোগাযোগ</h2>
                <p>আমাদের সাথে যোগাযোগ করুন, আমরা আপনার যেকোনো প্রশ্নের উত্তর দিতে প্রস্তুত</p>
            </div>
            <div class="contact-container">
                <div class="contact-info">
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div class="contact-text">
                            <h4>ঠিকানা</h4>
                            <p id="contactAddress">১২৩ ইসলামিক রোড, ধানমন্ডি, ঢাকা-১২০৫, বাংলাদেশ</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-phone-alt"></i>
                        </div>
                        <div class="contact-text">
                            <h4>ফোন নম্বর</h4>
                            <p id="contactPhone">+৮৮০ ১৭১২-৩৪৫৬৭৮, +৮৮০ ১৯১২-৩৪৫৬৭৮</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div class="contact-text">
                            <h4>ইমেইল</h4>
                            <p id="contactEmail">info@almanhal.edu.bd, admin@almanhal.edu.bd</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-clock"></i>
                        </div>
                        <div class="contact-text">
                            <h4>কার্যসময়</h4>
                            <p id="contactHours">শনিবার - বৃহস্পতিবার: সকাল ৮:০০ - বিকাল ৫:০০</p>
                            <p>শুক্রবার: বন্ধ</p>
                        </div>
                    </div>
                </div>
                <div class="contact-form">
                    <form id="contactForm">
                        <div class="form-group">
                            <label for="name">আপনার নাম</label>
                            <input type="text" id="name" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="email">ইমেইল</label>
                            <input type="email" id="email" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="subject">বিষয়</label>
                            <input type="text" id="subject" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="message">বার্তা</label>
                            <textarea id="message" class="form-control" required></textarea>
                        </div>
                        <button type="submit" class="btn">বার্তা পাঠান</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-container">
            <div class="footer-logo">
                <h3 class="arabic" id="footerArabicText">المنحل دارل علوم مدرسة</h3>
                <p id="footerBengaliText">আল-মনহাল দারুল উলূম মাদ্রাসা</p>
                <p id="footerDescription">একটি আধুনিক ইসলামিক শিক্ষা কেন্দ্র, যেখানে ইসলামিক শিক্ষা ও আধুনিক শিক্ষার সমন্বয়ে ভারসাম্যপূর্ণ শিক্ষা প্রদান করা হয়।</p>
            </div>
            <div class="footer-links">
                <h4>দ্রুত লিঙ্ক</h4>
                <ul>
                    <li><a href="#home">হোম</a></li>
                    <li><a href="#about">আমাদের সম্পর্কে</a></li>
                    <li><a href="#courses">ইসলামিক কোর্স</a></li>
                    <li><a href="#teachers">আলেমদের পরামর্শ</a></li>
                    <li><a href="#prayer">নামাজের সময়</a></li>
                    <li><a href="#quran">কুরআন ও হাদিস</a></li>
                    <li><a href="#notice">নোটিশ বোর্ড</a></li>
                    <li><a href="#gallery">গ্যালারি</a></li>
                    <li><a href="#blog">ইসলামিক ব্লগ</a></li>
                    <li><a href="#contact">যোগাযোগ</a></li>
                </ul>
            </div>
            <div class="footer-social">
                <h4>সামাজিক যোগাযোগ</h4>
                <p>আমাদের সামাজিক যোগাযোগ মাধ্যমে ফলো করুন</p>
                <div class="social-icons">
                    <a href="#" id="facebookLink"><i class="fab fa-facebook-f"></i></a>
                    <a href="#" id="youtubeLink"><i class="fab fa-youtube"></i></a>
                    <a href="#" id="whatsappLink"><i class="fab fa-whatsapp"></i></a>
                    <a href="#" id="telegramLink"><i class="fab fa-telegram"></i></a>
                </div>
            </div>
        </div>
        <div class="copyright">
            <p id="copyrightText">© ২০২৪ المنحل دارل علوم مدرسة. সকল স্বত্ব সংরক্ষিত।</p>
        </div>
    </footer>

    <!-- Login/Register Modal -->
    <div class="modal" id="authModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>লগইন / রেজিস্ট্রেশন</h2>
                <span class="close-modal">&times;</span>
            </div>
            <div class="modal-body">
                <div class="form-tabs">
                    <button class="tab-btn active" data-tab="login">লগইন</button>
                    <button class="tab-btn" data-tab="register">রেজিস্ট্রেশন</button>
                </div>
                
                <div class="tab-content active" id="login">
                    <form id="loginForm">
                        <div class="form-group">
                            <label for="loginEmail">ইমেইল</label>
                            <input type="email" id="loginEmail" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="loginPassword">পাসওয়ার্ড</label>
                            <input type="password" id="loginPassword" class="form-control" required>
                        </div>
                        <button type="submit" class="btn">লগইন</button>
                    </form>
                </div>
                
                <div class="tab-content" id="register">
                    <form id="registerForm">
                        <div class="form-group">
                            <label for="regName">পূর্ণ নাম</label>
                            <input type="text" id="regName" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="regEmail">ইমেইল</label>
                            <input type="email" id="regEmail" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="regPhone">ফোন নম্বর</label>
                            <input type="tel" id="regPhone" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="regClass">ক্লাস নির্বাচন করুন</label>
                            <select id="regClass" class="form-control" required>
                                <option value="">ক্লাস নির্বাচন করুন</option>
                                <option value="ibtedai">ইবতেদায়ি</option>
                                <option value="taisir">তাইসির</option>
                                <option value="mizan">মিজান</option>
                                <option value="nahwemir">নাহবেমির</option>
                                <option value="hedayetunnahu">হেদায়াতুন্নাহু</option>
                                <option value="kafiya">কাফিয়া</option>
                                <option value="hifz">হিফজ</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="regPassword">পাসওয়ার্ড</label>
                            <input type="password" id="regPassword" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="regConfirmPassword">পাসওয়ার্ড নিশ্চিত করুন</label>
                            <input type="password" id="regConfirmPassword" class="form-control" required>
                        </div>
                        <button type="submit" class="btn">রেজিস্টার</button>
                    </form>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Firebase Configuration
        const firebaseConfig = {
            apiKey: "AIzaSyCYHAXdBXixLpAtQZSiX2r9dAIvC2CF7Qs",
            authDomain: "almanhal-f858b.firebaseapp.com",
            databaseURL: "https://almanhal-f858b-default-rtdb.firebaseio.com",
            projectId: "almanhal-f858b",
            storageBucket: "almanhal-f858b.firebasestorage.app",
            messagingSenderId: "1085892990859",
            appId: "1:1085892990859:web:aa88e5551159dd7f21818e",
            measurementId: "G-6G3T9N83K9"
        };

        // Initialize Firebase
        firebase.initializeApp(firebaseConfig);
        const auth = firebase.auth();
        const database = firebase.database();
        const storage = firebase.storage();

        // DOM Elements
        const mobileMenu = document.querySelector('.mobile-menu');
        const navUl = document.querySelector('nav ul');
        const loginBtn = document.getElementById('loginBtn');
        const logoutBtn = document.getElementById('logoutBtn');
        const registerBtn = document.querySelector('.register-btn');
        const authModal = document.getElementById('authModal');
        const closeModal = document.querySelector('.close-modal');
        const tabBtns = document.querySelectorAll('.tab-btn');
        const tabContents = document.querySelectorAll('.tab-content');
        const loginForm = document.getElementById('loginForm');
        const registerForm = document.getElementById('registerForm');
        const contactForm = document.getElementById('contactForm');
        const userProfile = document.querySelector('.user-profile');
        const userName = document.getElementById('userName');
        const adminLink = document.getElementById('adminLink');
        const nextVerseBtn = document.getElementById('nextVerse');

        // Mobile Menu Toggle
        mobileMenu.addEventListener('click', () => {
            navUl.classList.toggle('active');
        });

        // Modal Functions
        function openModal() {
            authModal.style.display = 'flex';
        }

        function closeModalFunc() {
            authModal.style.display = 'none';
        }

        // Tab Switching
        tabBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                const tabId = btn.getAttribute('data-tab');
                
                // Remove active class from all buttons and contents
                tabBtns.forEach(b => b.classList.remove('active'));
                tabContents.forEach(c => c.classList.remove('active'));
                
                // Add active class to clicked button and corresponding content
                btn.classList.add('active');
                document.getElementById(tabId).classList.add('active');
            });
        });

        // Event Listeners
        loginBtn.addEventListener('click', (e) => {
            e.preventDefault();
            openModal();
            document.querySelector('[data-tab="login"]').click();
        });

        registerBtn.addEventListener('click', (e) => {
            e.preventDefault();
            openModal();
            document.querySelector('[data-tab="register"]').click();
        });

        closeModal.addEventListener('click', closeModalFunc);

        window.addEventListener('click', (e) => {
            if (e.target === authModal) {
                closeModalFunc();
            }
        });

        // Firebase Authentication - Login
        loginForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            
            auth.signInWithEmailAndPassword(email, password)
                .then((userCredential) => {
                    // Signed in
                    const user = userCredential.user;
                    alert('সফলভাবে লগইন হয়েছে!');
                    closeModalFunc();
                    updateUI();
                })
                .catch((error) => {
                    const errorCode = error.code;
                    const errorMessage = error.message;
                    alert('লগইন ব্যর্থ: ' + errorMessage);
                });
        });

        // Firebase Authentication - Registration
        registerForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const name = document.getElementById('regName').value;
            const email = document.getElementById('regEmail').value;
            const phone = document.getElementById('regPhone').value;
            const classSelected = document.getElementById('regClass').value;
            const password = document.getElementById('regPassword').value;
            const confirmPassword = document.getElementById('regConfirmPassword').value;
            
            if (password !== confirmPassword) {
                alert('পাসওয়ার্ড মিলছে না!');
                return;
            }
            
            auth.createUserWithEmailAndPassword(email, password)
                .then((userCredential) => {
                    // Signed up
                    const user = userCredential.user;
                    
                    // Save user data to Realtime Database
                    database.ref('users/' + user.uid).set({
                        name: name,
                        email: email,
                        phone: phone,
                        class: classSelected,
                        role: 'student',
                        createdAt: new Date().toISOString()
                    });
                    
                    alert('সফলভাবে রেজিস্ট্রেশন সম্পন্ন হয়েছে!');
                    closeModalFunc();
                    updateUI();
                })
                .catch((error) => {
                    const errorCode = error.code;
                    const errorMessage = error.message;
                    alert('রেজিস্ট্রেশন ব্যর্থ: ' + errorMessage);
                });
        });

        // Logout Function
        logoutBtn.addEventListener('click', () => {
            auth.signOut().then(() => {
                alert('সফলভাবে লগআউট হয়েছে!');
                updateUI();
            });
        });

        // Contact Form Submission
        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const subject = document.getElementById('subject').value;
            const message = document.getElementById('message').value;
            
            // Save contact message to Firebase
            const newMessageRef = database.ref('messages').push();
            newMessageRef.set({
                name: name,
                email: email,
                subject: subject,
                message: message,
                timestamp: new Date().toISOString()
            });
            
            alert('আপনার বার্তা সফলভাবে পাঠানো হয়েছে! আমরা শীঘ্রই আপনার সাথে যোগাযোগ করব।');
            contactForm.reset();
        });

        // Update UI based on authentication state
        function updateUI() {
            const user = auth.currentUser;
            
            if (user) {
                // User is signed in
                loginBtn.style.display = 'none';
                userProfile.style.display = 'flex';
                logoutBtn.style.display = 'inline-block';
                
                // Get user data from database
                database.ref('users/' + user.uid).once('value').then((snapshot) => {
                    const userData = snapshot.val();
                    if (userData) {
                        userName.textContent = userData.name;
                        
                        // Show admin link if user is admin
                        if (userData.role === 'admin' || user.email === 'mdrefatahmod49@gmail.com') {
                            adminLink.style.display = 'inline-block';
                        }
                    }
                });
            } else {
                // User is signed out
                loginBtn.style.display = 'block';
                userProfile.style.display = 'none';
                logoutBtn.style.display = 'none';
                adminLink.style.display = 'none';
            }
        }

        // Load Website Data from Firebase
        function loadWebsiteData() {
            // Load Header Data
            database.ref('website/header').on('value', (snapshot) => {
                const data = snapshot.val();
                if (data) {
                    if (data.logoText) document.getElementById('headerArabicText').textContent = data.logoText;
                    if (data.logoSubtext) document.getElementById('headerBengaliText').textContent = data.logoSubtext;
                    if (data.logo) {
                        document.getElementById('headerLogo').src = data.logo;
                        document.getElementById('headerLogo').style.display = 'block';
                    }
                }
            });

            // Load Hero Section Data
            database.ref('website/hero').on('value', (snapshot) => {
                const data = snapshot.val();
                if (data) {
                    if (data.arabicText) document.getElementById('heroArabicText').textContent = data.arabicText;
                    if (data.mainTitle) document.getElementById('heroMainTitle').textContent = data.mainTitle;
                    if (data.subTitle) document.getElementById('heroSubTitle').textContent = data.subTitle;
                    if (data.backgroundImage) {
                        document.querySelector('.hero').style.background = `linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('${data.backgroundImage}')`;
                        document.querySelector('.hero').style.backgroundSize = 'cover';
                        document.querySelector('.hero').style.backgroundPosition = 'center';
                    }
                }
            });

            // Load About Section Data
            database.ref('website/about').on('value', (snapshot) => {
                const data = snapshot.val();
                if (data) {
                    if (data.title) document.getElementById('aboutTitle').textContent = data.title;
                    if (data.subtitle) document.getElementById('aboutSubtitle').textContent = data.subtitle;
                    if (data.heading) document.getElementById('aboutHeading').textContent = data.heading;
                    if (data.description) document.getElementById('aboutDescription').textContent = data.description;
                    if (data.description2) document.getElementById('aboutDescription2').textContent = data.description2;
                    if (data.image) document.getElementById('aboutImage').src = data.image;
                }
            });

            // Load Courses Data
            database.ref('courses').on('value', (snapshot) => {
                const courses = snapshot.val();
                const coursesContainer = document.getElementById('coursesContainer');
                coursesContainer.innerHTML = '';
                
                if (courses) {
                    Object.values(courses).forEach(course => {
                        if (course.status === 'active') {
                            const courseCard = document.createElement('div');
                            courseCard.className = 'course-card';
                            courseCard.innerHTML = `
                                <div class="course-icon">
                                    <i class="${course.icon}"></i>
                                </div>
                                <div class="course-content">
                                    <h3>${course.name}</h3>
                                    <p>${course.description}</p>
                                    <a href="#" class="btn">বিস্তারিত দেখুন</a>
                                </div>
                            `;
                            coursesContainer.appendChild(courseCard);
                        }
                    });
                }
            });

            // Load Teachers Data
            database.ref('teachers').on('value', (snapshot) => {
                const teachers = snapshot.val();
                const teachersContainer = document.getElementById('teachersContainer');
                teachersContainer.innerHTML = '';
                
                if (teachers) {
                    Object.values(teachers).forEach(teacher => {
                        const teacherCard = document.createElement('div');
                        teacherCard.className = 'teacher-card';
                        teacherCard.innerHTML = `
                            <div class="teacher-img">
                                <img src="${teacher.image || 'https://images.unsplash.com/photo-1580301762386-5b5d06a4b5a3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=880&q=80'}" alt="${teacher.name}">
                            </div>
                            <div class="teacher-info">
                                <h3>${teacher.name}</h3>
                                <p>${teacher.title}</p>
                                <p>${teacher.description}</p>
                                <a href="#" class="btn">আরও পড়ুন</a>
                            </div>
                        `;
                        teachersContainer.appendChild(teacherCard);
                    });
                }
            });

            // Load Notices Data
            database.ref('notices').on('value', (snapshot) => {
                const notices = snapshot.val();
                const noticesContainer = document.getElementById('noticesContainer');
                noticesContainer.innerHTML = '';
                
                if (notices) {
                    Object.values(notices).forEach(notice => {
                        if (notice.status === 'active') {
                            const noticeItem = document.createElement('div');
                            noticeItem.className = 'notice-item';
                            noticeItem.innerHTML = `
                                <div class="notice-icon">
                                    <i class="fas fa-bullhorn"></i>
                                </div>
                                <div class="notice-content">
                                    <h4>${notice.title}</h4>
                                    <p>${notice.content}</p>
                                    <p class="notice-date">${new Date(notice.date).toLocaleDateString('bn-BD')}</p>
                                </div>
                            `;
                            noticesContainer.appendChild(noticeItem);
                        }
                    });
                }
            });

            // Load Gallery Data
            database.ref('gallery').on('value', (snapshot) => {
                const gallery = snapshot.val();
                const galleryContainer = document.getElementById('galleryContainer');
                galleryContainer.innerHTML = '';
                
                if (gallery) {
                    Object.values(gallery).forEach(item => {
                        if (item.status === 'active') {
                            const galleryItem = document.createElement('div');
                            galleryItem.className = 'gallery-item';
                            galleryItem.innerHTML = `
                                <img src="${item.imageUrl}" alt="${item.caption || 'গ্যালারি ছবি'}">
                            `;
                            galleryContainer.appendChild(galleryItem);
                        }
                    });
                }
            });

            // Load Blog Data
            database.ref('blog').on('value', (snapshot) => {
                const blogPosts = snapshot.val();
                const blogContainer = document.getElementById('blogContainer');
                blogContainer.innerHTML = '';
                
                if (blogPosts) {
                    Object.values(blogPosts).forEach(post => {
                        if (post.status === 'active') {
                            const blogCard = document.createElement('div');
                            blogCard.className = 'blog-card';
                            blogCard.innerHTML = `
                                <div class="blog-img">
                                    <img src="${post.imageUrl || 'https://images.unsplash.com/photo-1541336032412-2048a678540d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80'}" alt="${post.title}">
                                </div>
                                <div class="blog-content">
                                    <div class="blog-meta">
                                        <span><i class="far fa-user"></i> ${post.author}</span>
                                        <span><i class="far fa-calendar"></i> ${new Date(post.date).toLocaleDateString('bn-BD')}</span>
                                    </div>
                                    <h3>${post.title}</h3>
                                    <p>${post.content.substring(0, 150)}...</p>
                                    <a href="#" class="btn">আরও পড়ুন</a>
                                </div>
                            `;
                            blogContainer.appendChild(blogCard);
                        }
                    });
                }
            });

            // Load Contact Data
            database.ref('website/contact').on('value', (snapshot) => {
                const data = snapshot.val();
                if (data) {
                    if (data.address) document.getElementById('contactAddress').textContent = data.address;
                    if (data.phone) document.getElementById('contactPhone').textContent = data.phone;
                    if (data.email) document.getElementById('contactEmail').textContent = data.email;
                    if (data.hours) document.getElementById('contactHours').textContent = data.hours;
                }
            });

            // Load Footer Data
            database.ref('website/footer').on('value', (snapshot) => {
                const data = snapshot.val();
                if (data) {
                    if (data.arabicText) document.getElementById('footerArabicText').textContent = data.arabicText;
                    if (data.bengaliText) document.getElementById('footerBengaliText').textContent = data.bengaliText;
                    if (data.description) document.getElementById('footerDescription').textContent = data.description;
                    if (data.copyright) document.getElementById('copyrightText').textContent = data.copyright;
                }
            });
        }

        // Load Prayer Times
        function loadPrayerTimes() {
            const prayerTimesContainer = document.getElementById('prayerTimesContainer');
            
            database.ref('prayerTimes').on('value', (snapshot) => {
                const prayerTimes = snapshot.val();
                prayerTimesContainer.innerHTML = '';
                
                if (prayerTimes) {
                    const prayers = [
                        { name: 'ফজর', time: prayerTimes.fajr, active: false },
                        { name: 'যোহর', time: prayerTimes.dhuhr, active: false },
                        { name: 'আসর', time: prayerTimes.asr, active: true },
                        { name: 'মাগরিব', time: prayerTimes.maghrib, active: false },
                        { name: 'ইশা', time: prayerTimes.isha, active: false }
                    ];
                    
                    prayers.forEach(prayer => {
                        const prayerCard = document.createElement('div');
                        prayerCard.className = `prayer-card ${prayer.active ? 'active' : ''}`;
                        prayerCard.innerHTML = `
                            <div class="prayer-name">${prayer.name}</div>
                            <div class="prayer-time">${prayer.time}</div>
                        `;
                        prayerTimesContainer.appendChild(prayerCard);
                    });
                } else {
                    // Default prayer times
                    const defaultPrayers = [
                        { name: 'ফজর', time: '৪:৪৫ AM', active: false },
                        { name: 'যোহর', time: '১২:১৫ PM', active: false },
                        { name: 'আসর', time: '৪:৩০ PM', active: true },
                        { name: 'মাগরিব', time: '৬:২৫ PM', active: false },
                        { name: 'ইশা', time: '৭:৪৫ PM', active: false }
                    ];
                    
                    defaultPrayers.forEach(prayer => {
                        const prayerCard = document.createElement('div');
                        prayerCard.className = `prayer-card ${prayer.active ? 'active' : ''}`;
                        prayerCard.innerHTML = `
                            <div class="prayer-name">${prayer.name}</div>
                            <div class="prayer-time">${prayer.time}</div>
                        `;
                        prayerTimesContainer.appendChild(prayerCard);
                    });
                }
            });
        }

        // Load Quran Verses
        const quranVerses = [
            {
                arabic: 'بِسْمِ اللَّهِ الرَّحْمَٰنِ الرَّحِيمِ',
                translation: 'পরম করুণাময় ও অসীম দয়ালু আল্লাহর নামে শুরু করছি।',
                reference: 'সূরা আল-ফাতিহা, আয়াত: ১'
            },
            {
                arabic: 'الْحَمْدُ لِلَّهِ رَبِّ الْعَالَمِينَ',
                translation: 'সমস্ত প্রশংসা আল্লাহর জন্য, যিনি সমগ্র বিশ্বজগতের পালনকর্তা।',
                reference: 'সূরা আল-ফাতিহা, আয়াত: ২'
            },
            {
                arabic: 'مَالِكِ يَوْمِ الدِّينِ',
                translation: 'যিনি বিচার দিনের মালিক।',
                reference: 'সূরা আল-ফাতিহা, আয়াত: ৩'
            },
            {
                arabic: 'إِيَّاكَ نَعْبُدُ وَإِيَّاكَ نَسْتَعِينُ',
                translation: 'আমরা একমাত্র তোমারই ইবাদত করি এবং একমাত্র তোমারই কাছে সাহায্য চাই।',
                reference: 'সূরা আল-ফাতিহা, আয়াত: ৪'
            }
        ];
        
        let currentVerseIndex = 0;
        
        function loadQuranVerse() {
            const verse = quranVerses[currentVerseIndex];
            document.getElementById('quranVerse').textContent = verse.arabic;
            document.getElementById('quranTranslation').textContent = verse.translation;
            document.getElementById('quranReference').textContent = verse.reference;
        }
        
        nextVerseBtn.addEventListener('click', () => {
            currentVerseIndex = (currentVerseIndex + 1) % quranVerses.length;
            loadQuranVerse();
        });

        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                    
                    // Close mobile menu if open
                    navUl.classList.remove('active');
                }
            });
        });

        // Initialize the website
        function init() {
            updateUI();
            loadPrayerTimes();
            loadQuranVerse();
            loadWebsiteData();
            
            // Check if user is logged in on page load
            auth.onAuthStateChanged((user) => {
                updateUI();
            });
        }

        // Run initialization when page loads
        window.addEventListener('load', init);
    </script>
</body>
</html>
