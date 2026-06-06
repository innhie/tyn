<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Thánh Đường Của Những Phản Diện: Kho Lưu Trữ Hoàng Gia Cấm Kỵ</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600&family=Playfair+Display:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* --- Cấu Hình Biến Gốc & Reset --- */
        :root {
            --pink-pastel: #fbcbc9;
            --champagne: #f0e2d0;
            --wine-red: #58111A;
            --wine-bright: #8a1f2d;
            --cream-white: #fcf8f2;
            --glass-bg: rgba(252, 248, 242, 0.06);
            --glass-border: rgba(252, 248, 242, 0.12);
            --glass-glow: rgba(240, 226, 208, 0.3);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: #0d0406; /* Nền tối sâu thẳm trầm mặc */
            color: var(--cream-white);
            overflow-x: hidden;
            position: relative;
        }

        h1, h2, h3, .serif-font {
            font-family: 'Playfair Display', serif;
            letter-spacing: 1px;
        }

        /* --- Canvas Hạt Ánh Sáng (Particle Background) --- */
        #particle-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: 1;
            pointer-events: none;
        }

        /* --- Thanh Điều Hướng Cao Cấp --- */
        nav {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 20px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100;
            background: linear-gradient(to bottom, rgba(13,4,6,0.😎, transparent);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(240, 226, 208, 0.1);
        }

        nav .logo {
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--champagne);
            text-transform: uppercase;
            letter-spacing: 3px;
            text-shadow: 0 0 10px rgba(240, 226, 208, 0.5);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav ul li a {
            color: var(--cream-white);
            text-decoration: none;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            transition: all 0.4s ease;
            opacity: 0.8;
        }

        nav ul li a:hover {
            color: var(--pink-pastel);
            text-shadow: 0 0 8px var(--pink-pastel);
            opacity: 1;
        }

        /* --- Khung Cuộn Từng Phần --- */
        section {
            position: relative;
            min-height: 100vh;
            padding: 100px 10%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 2;
        }

        /* Hiệu ứng Fade-in khi cuộn mạng điện ảnh */
        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 1.2s cubic-bezier(0.25, 1, 0.5, 1);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* --- 1. HERO SECTION (Trang Chủ) --- */
        #hero {
            text-align: center;
            background: radial-gradient(circle at center, rgba(88, 17, 26, 0.15) 0%, transparent 70%);
            padding-top: 150px;
        }

        #hero h1 {
            font-size: 4rem;
            color: var(--champagne);
            margin-bottom: 20px;
            font-weight: 400;
            line-height: 1.2;
            text-shadow: 0 0 20px rgba(240, 226, 208, 0.2);
            animation: fadeInGlow 2.5s ease;
        }

        #hero p {
            font-style: italic;
            font-size: 1.2rem;
            color: var(--pink-pastel);
            margin-bottom: 40px;
            max-width: 600px;
            opacity: 0.9;
            animation: fadeInGlow 3.5s ease;
        }

        .cta-btn {
            display: inline-block;
            padding: 15px 40px;
            border: 1px solid var(--champagne);
            background: transparent;
            color: var(--champagne);
            font-family: 'Montserrat', sans-serif;
            text-transform: uppercase;
            letter-spacing: 3px;
            font-size: 0.8rem;
            cursor: pointer;
            text-decoration: none;
            position: relative;
            overflow: hidden;
            transition: all 0.5s ease;
            box-shadow: 0 0 15px rgba(240, 226, 208, 0.1);
        }

        .cta-btn:hover {
            color: var(--wine-red);
            background: var(--champagne);
            box-shadow: 0 0 25px var(--champagne);
            transform: translateY(-2px);
        }

        /* --- Tựa Đề Chung Cho Các Phần --- */
        .section-title {
            font-size: 2.5rem;
            color: var(--champagne);
            text-align: center;
            margin-bottom: 15px;
            text-transform: capitalize;
        }

        .section-subtitle {
            font-size: 0.9rem;
            text-align: center;
            color: var(--pink-pastel);
            margin-bottom: 60px;
            letter-spacing: 2px;
            text-transform: uppercase;
            opacity: 0.7;
        }

        /* --- 2. KHU NHÂN VẬT (Villains Grid) --- */
        .grid-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            width: 100%;
            max-width: 1200px;
        }

        .glass-card {
            background: var(--glass-bg);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border: 1px solid var(--glass-border);
            padding: 40px 30px;
            border-radius: 4px;
            text-align: center;
            transition: all 0.6s cubic-bezier(0.25, 1, 0.5, 1);
            position: relative;
            overflow: hidden;
        }

        .glass-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(251, 203, 201, 0.05), transparent);
            transform: translateX(-100%);
            transition: 0.8s;
        }

        .glass-card:hover::before {
            transform: translateX(100%);
        }

        .glass-card:hover {
            transform: translateY(-10px) scale(1.02);
            border-color: var(--pink-pastel);
            box-shadow: 0 15px 35px rgba(88, 11, 26, 0.3), 0 0 15px var(--glass-glow);
        }

        .avatar-placeholder {
            width: 100px;
            height: 100px;
            margin: 0 auto 25px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--wine-red), #1a0508);
            border: 1px solid var(--champagne);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: var(--champagne);
            transition: 0.5s;
        }

        .glass-card:hover .avatar-placeholder {
            box-shadow: 0 0 20px var(--pink-pastel);
            color: var(--pink-pastel);
        }

        .glass-card h3 {
            font-size: 1.6rem;
            color: var(--cream-white);
            margin-bottom: 8px;
        }

        .glass-card .title {
            font-size: 0.8rem;
            color: var(--pink-pastel);
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 20px;
            font-weight: 600;
        }

        .glass-card p {
            font-size: 0.9rem;
            line-height: 1.6;
            color: #dcd1c4;
            font-weight: 300;
        }

        /* --- 3. THƯ VIỆN ĐIỆN ẢNH (Cinematic Gallery) --- */
        .gallery-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            width: 100%;
            max-width: 1200px;
        }

        .gallery-item {
            position: relative;
            height: 380px;
            overflow: hidden;
            border: 1px solid rgba(252, 248, 242, 0.1);
            cursor: pointer;
            border-radius: 2px;
        }

        /* Giả lập ảnh nghệ thuật bằng gradient sang trọng hoài cổ */
        .gallery-art {
            width: 100%;
            height: 100%;
            transition: transform 0.8s ease;
            display: flex;
            align-items: flex-end;
            padding: 30px;
        }

        .art-1 { background: linear-gradient(to top, rgba(13,4,6,0.9), rgba(88, 11, 26, 0.4)), url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="%232b050a"/></svg>'); background-size: cover; }
        .art-2 { background: linear-gradient(to top, rgba(13,4,6,0.9), rgba(40, 20, 45, 0.4)), url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="%231a1026"/></svg>'); background-size: cover; }
        .art-3 { background: linear-gradient(to top, rgba(13,4,6,0.9), rgba(20, 35, 45, 0.4)), url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="%230b1c26"/></svg>'); background-size: cover; }
        .art-4 { background: linear-gradient(to top, rgba(13,4,6,0.9), rgba(50, 40, 25, 0.4)), url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="%23261a0b"/></svg>'); background-size: cover; }

        .gallery-caption {
            position: relative;
            z-index: 2;
            transform: translateY(15px);
            transition: all 0.6s ease;
            opacity: 0.7;
        }

        .gallery-caption h4 {
            font-family: 'Playfair Display', serif;
            font-size: 1.4rem;
            color: var(--champagne);
            margin-bottom: 5px;
        }

        .gallery-caption p {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--pink-pastel);
        }

        .gallery-item:hover .gallery-art {
            transform: scale(1.08);
            filter: brightness(1.2);
        }

        .gallery-item:hover .gallery-caption {
            transform: translateY(0);
            opacity: 1;
        }

        /* --- 4. KHO BÍ MẬT (Secret Archives) --- */
        .vault-container {
            width: 100%;
            max-width: 800px;
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .secret-document {
            background: rgba(13, 4, 6, 0.6);
            border: 1px dashed rgba(240, 226, 208, 0.2);
            padding: 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: relative;
            transition: all 0.8s ease;
        }

        .document-info {
            max-width: 75%;
        }

        .document-info h4 {
            font-size: 1.1rem;
            color: var(--champagne);
            margin-bottom: 8px;
            letter-spacing: 1px;
        }

        .document-info p {
            font-size: 0.85rem;
            color: #a69a8f;
            line-height: 1.5;
        }

        .lock-zone {
            font-size: 1.5rem;
            color: var(--wine-bright);
            cursor: pointer;
            width: 50px;
            height: 50px;
            border: 1px solid rgba(138, 31, 45, 0.3);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.5s ease;
            background: rgba(88, 11, 26, 0.05);
        }

        /* class kích hoạt khi cuộn đến giải mã hoàng gia */
        .secret-document.unlocked {
            border-style: solid;
            border-color: rgba(251, 203, 201, 0.3);
            background: var(--glass-bg);
            backdrop-filter: blur(10px);
            box-shadow: 0 0 15px rgba(251, 203, 201, 0.05);
        }

        .secret-document.unlocked .lock-zone {
            color: var(--pink-pastel);
            border-color: var(--pink-pastel);
            box-shadow: 0 0 10px var(--pink-pastel);
            transform: rotate(360deg);
        }

        /* --- 5. LIÊN HỆ (Royal Letter Form) --- */
        .form-container {
            width: 100%;
            max-width: 650px;
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            padding: 50px;
            border-radius: 4px;
            box-shadow: 0 20px 50px rgba(0,0,0,0.5);
        }

        .form-group {
            position: relative;
            margin-bottom: 35px;
        }

        .form-input {
            width: 100%;
            background: transparent;
            border: none;
            border-bottom: 1px solid rgba(240, 226, 208, 0.3);
            padding: 10px 0;
            color: var(--cream-white);
            font-family: 'Montserrat', sans-serif;
            font-size: 0.95rem;
            transition: all 0.4s ease;
        }

        .form-input:focus {
            outline: none;
            border-bottom-color: var(--pink-pastel);
        }

        .form-label {
            position: absolute;
            top: 10px;
            left: 0;
            font-size: 0.85rem;
            color: rgba(252, 248, 242, 0.5);
            text-transform: uppercase;
            letter-spacing: 2px;
            pointer-events: none;
            transition: all 0.4s ease;
        }

        /* Hiệu ứng nhãn nhảy lên khi focus hoặc điền chữ */
        .form-input:focus ~ .form-label,
        .form-input:not(:placeholder-shown) ~ .form-label {
            top: -15px;
            font-size: 0.7rem;
            color: var(--pink-pastel);
            letter-spacing: 1px;
        }

        .submit-btn {
            width: 100%;
            padding: 16px;
            background: linear-gradient(135deg, var(--wine-red), var(--wine-bright));
            border: 1px solid var(--pink-pastel);
            color: var(--champagne);
            font-family: 'Montserrat', sans-serif;
            text-transform: uppercase;
            letter-spacing: 3px;
            font-size: 0.85rem;
            cursor: pointer;
            transition: all 0.4s ease;
            box-shadow: 0 4px 15px rgba(88, 11, 26, 0.4);
        }

        .submit-btn:hover {
            letter-spacing: 5px;
            box-shadow: 0 0 25px var(--pink-pastel);
            color: var(--cream-white);
        }

        /* --- LIGHTBOX (Xem ảnh phóng to mượt) --- */
        .lightbox {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(13, 4, 6, 0.95);
            backdrop-filter: blur(15px);
            z-index: 1000;
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.6s ease;
        }

        .lightbox.active {
            opacity: 1;
            pointer-events: auto;
        }

        .lightbox-content {
            max-width: 80%;
            max-height: 70vh;
            width: 500px;
            height: 350px;
            border: 1px solid var(--champagne);
            box-shadow: 0 0 50px rgba(251, 203, 201, 0.2);
            border-radius: 4px;
        }

        .lightbox-close {
            position: absolute;
            top: 40px;
            right: 50px;
            color: var(--champagne);
            font-size: 2rem;
            cursor: pointer;
            transition: 0.3s;
        }

        .lightbox-close:hover {
            color: var(--pink-pastel);
            transform: scale(1.1);
        }

        /* --- FOOTER --- */
        footer {
            text-align: center;
            padding: 40px 20px;
            border-top: 1px solid rgba(240, 226, 208, 0.05);
            font-size: 0.75rem;
            letter-spacing: 2px;
            color: rgba(252, 248, 242, 0.4);
            z-index: 2;
            position: relative;
        }

        /* --- ANIMATIONS --- */
        @keyframes fadeInGlow {
            from { opacity: 0; filter: blur(10px); transform: translateY(20px); }
            to { opacity: 1; filter: blur(0); transform: translateY(0); }
        }

        /* --- RESPONSIVE DESIGN (Tương thích thiết bị di động) --- */
        @media (max-width: 768px) {
            nav { padding: 20px; }
            nav ul { display: none; } /* Thu gọn bớt menu trên Mobile để tăng sự tối giản */
            #hero h1 { font-size: 2.3rem; }
            #hero p { font-size: 1rem; }
            section { padding: 80px 5%; }
            .form-container { padding: 30px 20px; }
            .secret-document { flex-direction: column; text-align: center; gap: 20px; }
            .document-info { max-width: 100%; }
        }
    </style>
</head>
<body>

    <canvas id="particle-canvas"></canvas>

    <nav>
        <div class="logo">The Villains</div>
        <ul>
            <li><a href="#hero">Thánh Đường</a></li>
            <li><a href="#characters">Nhân Vật</a></li>
            <li><a href="#gallery">Thư Viện</a></li>
            <li><a href="#vault">Kho Bảo Mật</a></li>
            <li><a href="#contact">Mật Thư</a></li>
        </ul>
    </nav>

    <section id="hero">
        <h1 class="serif-font">Thánh Đường Của Những Phản Diện</h1>
        <p>“Mỗi linh hồn cấm kỵ đều có một câu chuyện bị phong ấn trong im lặng.”</p>
        <a href="#characters" class="cta-btn">Bước vào kho lưu trữ</a>
    </section>

    <section id="characters" class="reveal">
        <h2 class="section-title">Hồ Sơ Cấm Kỵ</h2>
        <p class="section-subtitle">Kẻ thống trị bóng đêm & quyền lực tuyệt đối</p>
        
        <div class="grid-container">
            <div class="glass-card">
                <div class="avatar-placeholder"><i class="fa-solid fa-crown"></i></div>
                <h3>Kaelen Vance</h3>
                <div class="title">Bá Tước Tối Cao</div>
                <p>Kẻ sở hữu dòng máu hoàng tộc cổ xưa đã bị vấy bẩn. Ánh mắt lạnh lùng che giấu một kế hoạch lật đổ ngai vàng nhuốm màu tàn nhẫn.</p>
            </div>
            <div class="glass-card">
                <div class="avatar-placeholder"><i class="fa-solid fa-building-columns"></i></div>
                <h3>Dominic Ross</h3>
                <div class="title">Tài Phiệt Tài Chính</div>
                <p>Thao túng nền kinh tế toàn cầu từ phòng làm việc tràn ngập bóng tối. Với anh ta, tình yêu hay thù hận đều là những quân bài có thể định giá.</p>
            </div>
            <div class="glass-card">
                <div class="avatar-placeholder"><i class="fa-solid fa-gun"></i></div>
                <h3>Renato Moretti</h3>
                <div class="title">Trùm Mafia Ý</div>
                <p>Trầm tính, khét tiếng và mang một trái tim sỏi đá mang phong vị rượu vang đắt giá. Luật lệ của anh ta chính là công lý duy nhất tại thế giới ngầm.</p>
            </div>
        </div>
    </section>

    <section id="gallery" class="reveal">
        <h2 class="section-title">Thước Phim Ghi Lại</h2>
        <p class="section-subtitle">Khoảnh khắc nguy hiểm đầy mê hoặc</p>

        <div class="gallery-container">
            <div class="gallery-item" onclick="openLightbox('art-1', 'Đêm Dạ Tiệc Đẫm Máu')">
                <div class="gallery-art art-1">
                    <div class="gallery-caption">
                        <h4>Dạ Vũ Đêm Tàn</h4>
                        <p>Bóng dáng vương giả trong bóng đêm</p>
                    </div>
                </div>
            </div>
            <div class="gallery-item" onclick="openLightbox('art-2', 'Bản Án Vô Hình')">
                <div class="gallery-art art-2">
                    <div class="gallery-caption">
                        <h4>Mật Ước Tối Cao</h4>
                        <p>Nơi quyền lực tối thượng lên tiếng</p>
                    </div>
                </div>
            </div>
            <div class="gallery-item" onclick="openLightbox('art-3', 'Thành Trì Đổ Nát')">
                <div class="gallery-art art-3">
                    <div class="gallery-caption">
                        <h4>Giọt Rượu Vong Hồn</h4>
                        <p>Hương vị ngọt ngào đầy độc tính</p>
                    </div>
                </div>
            </div>
            <div class="gallery-item" onclick="openLightbox('art-4', 'Bình Minh Tội Lỗi')">
                <div class="gallery-art art-4">
                    <div class="gallery-caption">
                        <h4>Lời Nguyện Cuối Cùng</h4>
                        <p>Khi kẻ phản diện biết lụy tình</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="vault" class="reveal">
        <h2 class="section-title">Tài Liệu Mật Hoàng Gia</h2>
        <p class="section-subtitle">Tự động giải mật khi tiến sâu vào thánh đường</p>

        <div class="vault-container">
            <div class="secret-document">
                <div class="document-info">
                    <h4>Hồ sơ số #0901 - Thử nghiệm cấm lý</h4>
                    <p>Bản thảo ghi chép lại nguồn gốc sức mạnh hắc ám và khế ước phong ấn linh hồn của dòng tộc Vance.</p>
                </div>
                <div class="lock-zone"><i class="fa-solid fa-lock"></i></div>
            </div>
            
            <div class="secret-document">
                <div class="document-info">
                    <h4>Nhật ký lưu đày - Ross và sự sụp đổ</h4>
                    <p>Kế hoạch thâu tóm gia sản hoàng gia thông qua các giao dịch ngầm xuyên lục địa.</p>
                </div>
                <div class="lock-zone"><i class="fa-solid fa-lock"></i></div>
            </div>

            <div class="secret-document">
                <div class="document-info">
                    <h4>Mật chỉ tối cao - Bản án tử hình hoãn thi hành</h4>
                    <p>Bằng chứng chứng minh các tội danh thanh trừng gia tộc lớn của thủ lĩnh Renato.</p>
                </div>
                <div class="lock-zone"><i class="fa-solid fa-lock"></i></div>
            </div>
        </div>
    </section>

    <section id="contact" class="reveal">
        <h2 class="section-title">Gửi Mật Thư</h2>
        <p class="section-subtitle">Để lại lời nhắn của bạn vào hư vô</p>

        <div class="form-container">
            <form onsubmit="event.preventDefault(); alert('Mật thư của bạn đã được mã hóa và gửi đi ẩn danh...');">
                <div class="form-group">
                    <input type="text" class="form-input" placeholder=" " required>
                    <label class="form-label">Danh Tính Của Bạn</label>
                </div>
                <div class="form-group">
                    <input type="email" class="form-input" placeholder=" " required>
                    <label class="form-label">Địa Chỉ Nhận Phản Hồi (Email)</label>
                </div>
                <div class="form-group">
                    <textarea class="form-input" rows="4" placeholder=" " required style="resize: none;"></textarea>
                    <label class="form-label">Lời Thì Thầm Chứa Bí Mật</label>
                </div>
                <button type="submit" class="submit-btn">Niêm Phong & Gửi Đi</button>
            </form>
        </div>
    </section>

    <div class="lightbox" id="lightboxWindow">
        <span class="lightbox-close" onclick="closeLightbox()">&times;</span>
        <div class="lightbox-content" id="lightboxBg"></div>
    </div>

    <footer>
        <p>© 2026 THÁNH ĐƯỜNG PHẢN DIỆN - KHO LƯU TRỮ HOÀNG GIA CẤM KỴ. ALL RIGHTS RESERVED.</p>
    </footer>

    <script>
        /* --- 1. Hiệu Ứng Hạt Ánh Sáng Bay (Particle system) --- */
        const canvas = document.getElementById('particle-canvas');
        const ctx = canvas.getContext('2d');
        
        let particlesArray = [];
        const numberOfParticles = 60;

        function setCanvasSize() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        setCanvasSize();
        window.addEventListener('resize', setCanvasSize);

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 2.5 + 0.5;
                this.speedX = Math.random() * 0.4 - 0.2;
                this.speedY = Math.random() * -0.5 - 0.2; // Hạt chuyển động nhẹ nhàng bay lên
                this.alpha = Math.random() * 0.5 + 0.2;
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                if (this.y < 0) {
                    this.y = canvas.height;
                    this.x = Math.random() * canvas.width;
                }
                if (this.x < 0 || this.x > canvas.width) {
                    this.speedX = -this.speedX;
                }
            }
            draw() {
                ctx.save();
                ctx.globalAlpha = this.alpha;
                ctx.shadowBlur = 8;
                ctx.shadowColor = "#fbcbc9"; // Phát sáng hồng nhạt Coquette
                ctx.fillStyle = '#f0e2d0'; // Champagne mềm
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        function initParticles() {
            particlesArray = [];
            for (let i = 0; i < numberOfParticles; i++) {
                particlesArray.push(new Particle());
            }
        }
        initParticles();

        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            for (let i = 0; i < particlesArray.length; i++) {
                particlesArray[i].update();
                particlesArray[i].draw();
            }
            requestAnimationFrame(animateParticles);
        }
        animateParticles();


        /* --- 2. Xử Lý Fade-In Khi Cuộn (Scroll Reveal) & Tự Động Mở Khóa Kho Lưu Trữ --- */
        const reveals = document.querySelectorAll('.reveal');
        const secretDocuments = document.querySelectorAll('.secret-document');

        function handleScrollEffects() {
            const windowHeight = window.innerHeight;

            // Xử lý hiện mượt các section
            reveals.forEach(reveal => {
                const elementTop = reveal.getBoundingClientRect().top;
                const elementVisible = 120;
                if (elementTop < windowHeight - elementVisible) {
                    reveal.classList.add('active');
                }
            });

            // Hiệu ứng điện ảnh: Cuộn trang tới đâu, tài liệu mật hoàng gia "bẻ khóa" tới đó
            secretDocuments.forEach(doc => {
                const docTop = doc.getBoundingClientRect().top;
                if (docTop < windowHeight - 100) {
                    if (!doc.classList.contains('unlocked')) {
                        doc.classList.add('unlocked');
                        const lockIcon = doc.querySelector('.lock-zone i');
                        lockIcon.classList.remove('fa-lock');
                        lockIcon.classList.add('fa-lock-open'); // Biến đổi biểu tượng mở khóa mượt mà
                    }
                }
            });
        }

        window.addEventListener('scroll', handleScrollEffects);
        // Chạy ngay lần đầu để quét các phần tử đang nằm sẵn trong màn hình
        handleScrollEffects();


        /* --- 3. Bộ Phóng To Ảnh Điện Ảnh (Lightbox) --- */
        const lightbox = document.getElementById('lightboxWindow');
        const lightboxBg = document.getElementById('lightboxBg');

        function openLightbox(artClass, titleText) {
            lightboxBg.className = 'lightbox-content ' + artClass;
            lightbox.classList.add('active');
        }

        function closeLightbox() {
            lightbox.classList.remove('active');
        }

        // Tự động đóng khi nhấn trúng khoảng không bên ngoài ảnh phóng to
        lightbox.addEventListener('click', function(e) {
            if (e.target === lightbox) {
                closeLightbox();
            }
        });
    </script>
</body>
</html>
