<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Tacotek</title>
    <link rel="icon" href="log.jpg" type="image/png">
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    <link rel="stylesheet" href="tacotek.css">
</head>
<body>
    <style>
        :root {
    --primary: #dc3545; /* Đỏ tươi */
    --secondary: #28a745; /* Xanh lá đậm */
    --bg: #ffffff; /* Nền trắng */
    --card: #f8f9fa; /* Nền card trắng xám nhạt */
    --text: #212529; /* Chữ đen */
    --subtext: #6c757d; /* Chữ xám đậm */
}
* {
    margin: 0; padding: 0; box-sizing: border-box;
    font-family: 'Roboto', sans-serif;
    transition: all 0.3s ease;
}
html {
    scroll-behavior: smooth;
}
body {
    background: var(--bg);
    color: var(--text);
    line-height: 1.6;
}
header {
    background: var(--card);
    padding: 1rem 3rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    position: sticky;
    top: 0;
    z-index: 1000;
}
.logo-container {
    display: flex;
    align-items: center;
    gap: 10px;
}
.logo-container h1 {
    color: var(--primary);
    font-size: 1.8rem;
    font-weight: 900;
    letter-spacing: 1px;
    text-transform: uppercase;
}
.logo-container i {
    font-size: 2rem;
    color: var(--secondary);
}
nav {
    display: flex;
    align-items: center;
}
nav a {
    color: var(--subtext);
    text-decoration: none;
    margin: 0 1rem;
    font-weight: 500;
    position: relative;
    padding: 0.5rem 0.8rem;
    border-radius: 8px;
}
nav a::after {
    content: '';
    position: absolute;
    width: 0;
    height: 2px;
    background: var(--primary);
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    transition: width 0.3s ease;
}
nav a:hover, nav a.active {
    color: var(--text);
}
nav a:hover::after {
    width: 80%;
}
.user-actions {
    display: flex;
    align-items: center;
    gap: 1rem;
}
.user-actions a {
    color: var(--subtext);
    text-decoration: none;
    font-weight: 500;
    padding: 0.5rem 0.8rem;
    border-radius: 8px;
}
.user-actions a.btn-login, .user-actions a.btn-register {
    border: 2px solid var(--primary);
    color: var(--primary);
    font-weight: bold;
}
.user-actions a.btn-register {
    background-color: var(--primary);
    color: white;
    border-color: var(--primary);
}
.user-actions a:hover {
    transform: scale(1.05);
}
.user-info {
    display: flex;
    align-items: center;
    gap: 10px;
}
.user-info .profile-link {
    display: flex;
    align-items: center;
    gap: 5px;
    font-weight: bold;
    color: var(--text);
}
.user-info .profile-link i {
    font-size: 1.5rem;
    color: var(--secondary);
}
.user-info .btn-logout {
    background: none;
    border: 2px solid var(--primary);
    color: var(--primary);
    font-weight: bold;
    padding: 8px 15px;
    border-radius: 30px;
}
.hero {
    position: relative;
    width: 100%;
    height: 110vh;
    overflow: hidden;
}
.hero img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
    animation: fadeIn 1s ease-in-out;
}
section {
    padding: 80px 20px;
    max-width: 1200px;
    margin: auto;
}
h2 {
    font-size: 2.5rem;
    margin-bottom: 40px;
    color: var(--primary);
    text-align: center;
    position: relative;
    animation: slideInDown 0.8s ease-in-out;
}
h2::after {
    content: '';
    width: 80px;
    height: 4px;
    background: var(--primary);
    position: absolute;
    bottom: -15px;
    left: 50%;
    transform: translateX(-50%);
    border-radius: 2px;
}
.products {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
}
.card {
    background: var(--card);
    padding: 25px;
    border-radius: 16px;
    box-shadow: 0 6px 16px rgba(0,0,0,0.1);
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    border: 1px solid #e9ecef;
    position: relative;
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.6s ease-out, transform 0.6s ease-out, box-shadow 0.3s ease;
}
.card.visible {
    opacity: 1;
    transform: translateY(0);
}
.card:hover {
    transform: translateY(-8px) scale(1.02);
    box-shadow: 0 15px 30px rgba(220,53,69,0.2);
    border-color: var(--primary);
}
.card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
    border-radius: 12px;
    margin-bottom: 15px;
}
.card h3 {
    font-size: 1.5rem;
    margin-top: 10px;
    color: var(--text);
    font-weight: 700;
}
.card p {
    color: var(--subtext);
    margin: 10px 0;
}
.card strong {
    color: var(--primary);
    font-size: 1.2rem;
    font-weight: 700;
}
.card .btn-group {
    display: flex;
    gap: 10px;
    margin-top: 20px;
}
.card button {
    background: var(--primary);
    color: white;
    border: none;
    padding: 12px 24px;
    border-radius: 30px;
    cursor: pointer;
    font-weight: bold;
    font-size: 1rem;
    box-shadow: 0 4px 10px rgba(220,53,69,0.4);
}
.card button.secondary {
    background: none;
    border: 2px solid var(--primary);
    color: var(--primary);
    box-shadow: none;
}
.card button:hover {
    transform: scale(1.05);
    background: var(--secondary);
    color: white;
    box-shadow: 0 4px 10px rgba(40, 167, 69, 0.4);
}
.card button.secondary:hover {
    background: rgba(220, 53, 69, 0.1);
    color: var(--primary);
}
.info-block {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
    margin-top: 40px;
}
.info-item {
    background: var(--card);
    padding: 30px;
    border-radius: 12px;
    text-align: center;
    border: 1px solid #e9ecef;
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.6s ease-out, transform 0.6s ease-out;
    box-shadow: 0 4px 12px rgba(0,0,0,0.05);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
.info-item.visible {
    opacity: 1;
    transform: translateY(0);
}
.info-item i {
    font-size: 3rem;
    color: var(--secondary);
    margin-bottom: 15px;
    animation: pulse 1.5s infinite;
}
.info-item h3 {
    font-size: 1.4rem;
    color: var(--text);
    margin-bottom: 10px;
}
.info-item p {
    flex-grow: 1;
    margin-bottom: 20px;
}
.info-item .info-button {
    background: none;
    border: 2px solid var(--primary);
    color: var(--primary);
    padding: 12px 24px;
    border-radius: 30px;
    font-weight: bold;
    font-size: 1rem;
    cursor: pointer;
    width: 100%;
}
.info-item .info-button:hover {
    background: var(--primary);
    color: white;
    transform: scale(1.05);
}
form {
    background: var(--card);
    padding: 40px;
    border-radius: 16px;
    box-shadow: 0 0 20px rgba(220, 53, 69, 0.1);
    display: flex;
    flex-direction: column;
    gap: 15px;
    animation: fadeIn 1s ease-in-out;
}
form input, form textarea {
    width: 100%;
    padding: 15px;
    border: 1px solid #ced4da;
    border-radius: 8px;
    background: #f1f3f5;
    color: var(--text);
    font-size: 1rem;
    transition: border-color 0.3s;
}
form input:focus, form textarea:focus {
    outline: none;
    border-color: var(--primary);
}
form input::placeholder, form textarea::placeholder {
    color: #adb5bd;
}
form button {
    background: var(--primary);
    color: white;
    border: none;
    padding: 15px 30px;
    border-radius: 10px;
    cursor: pointer;
    font-weight: bold;
    font-size: 1.1rem;
    margin-top: 10px;
    box-shadow: 0 4px 10px rgba(220,53,69,0.4);
}
form button:hover {
    background: var(--secondary);
    color: white;
    transform: scale(1.05);
    box-shadow: 0 4px 10px rgba(40, 167, 69, 0.4);
}
footer {
    background: #e9ecef;
    text-align: center;
    padding: 30px;
    color: var(--subtext);
    font-size: 1rem;
    border-top: 1px solid #dee2e6;
}
.contact-info {
    display: flex;
    justify-content: center;
    gap: 40px;
    margin-bottom: 20px;
}
.contact-info a {
    color: var(--subtext);
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 10px;
}
.contact-info a:hover {
    color: var(--primary);
}
#cart-count {
    background: var(--secondary);
    color: white;
    padding: 4px 10px;
    border-radius: 50%;
    font-size: 0.8rem;
    font-weight: bold;
    position: absolute;
    top: -5px;
    right: -10px;
}
.cart-link {
    position: relative;
}
.modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.5);
    display: none;
    justify-content: center;
    align-items: center;
    z-index: 2000;
}
.modal-content {
    background: var(--card);
    padding: 30px;
    border-radius: 16px;
    width: 90%;
    max-width: 500px;
    position: relative;
    box-shadow: 0 10px 30px rgba(0,0,0,0.2);
    border: 1px solid var(--primary);
    animation: scaleIn 0.4s cubic-bezier(0.68, -0.55, 0.27, 1.55);
}
.modal-content form {
    box-shadow: none;
    background: transparent;
    padding: 0;
}
.modal-content form button {
    width: 100%;
}
.modal-content p a {
    color: var(--primary);
    text-decoration: none;
    font-weight: bold;
}
#product-detail-box img {
    width: 100%;
    max-height: 250px;
    object-fit: cover;
    border-radius: 12px;
    margin-bottom: 15px;
}
#product-detail-box h3 {
    font-size: 1.8rem;
    color: var(--primary);
}
#product-detail-box p {
    margin: 10px 0;
    color: var(--subtext);
}
.close-btn {
    position: absolute;
    top: 15px;
    right: 20px;
    font-size: 2rem;
    cursor: pointer;
    color: var(--primary);
}
.cart-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 0;
    border-bottom: 1px solid #dee2e6;
}
.cart-item:last-child {
    border-bottom: none;
}
.cart-item span {
    font-size: 1.1rem;
}
#cart-total {
    font-size: 1.4rem;
    font-weight: bold;
    text-align: right;
    margin-top: 20px;
    color: var(--primary);
}
#checkout-btn {
    width: 100%;
    background: var(--primary);
    color: white;
    border: none;
    padding: 15px;
    border-radius: 10px;
    cursor: pointer;
    font-size: 1.2rem;
    margin-top: 20px;
    box-shadow: 0 4px 10px rgba(220,53,69,0.4);
}
#checkout-btn:hover {
    background: var(--secondary);
    color: white;
    box-shadow: 0 4px 10px rgba(40, 167, 69, 0.4);
}
@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}
@keyframes slideInDown {
    from { transform: translateY(-30px); opacity: 0; }
    to { transform: translateY(0); opacity: 1; }
}
@keyframes pulse {
    0% { transform: scale(1); }
    50% { transform: scale(1.05); }
    100% { transform: scale(1); }
}
@keyframes scaleIn {
    from { transform: scale(0.8); opacity: 0; }
    to { transform: scale(1); opacity: 1; }
}
@media (max-width: 768px) {
    header {
        flex-direction: column;
        gap: 15px;
        padding: 1rem 1rem;
    }
    nav {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    }
    nav a {
        margin: 0.5rem;
    }
    .user-actions {
        width: 100%;
        justify-content: center;
        margin-top: 1rem;
    }
    .hero {
        font-size: 2rem;
        padding: 80px 10px;
    }
    h2 {
        font-size: 2rem;
    }
}

#pagination button {
  background-color: white;
  border: 1px solid var(--primary);
  color: var(--primary);
  padding: 8px 12px;
  margin: 0 4px;
  cursor: pointer;
  border-radius: 5px;
  font-weight: bold;
  transition: 0.3s;
}

#pagination button:hover {
  background-color: var(--primary);
  color: white;
}

#pagination button.active {
  background-color: var(--primary);
  color: white;
}

    </style>
    <header>
        <div class="logo-container">
            <i class="fas fa-fire-extinguisher"></i>
            <h1>TACOTEK</h1>
        </div>
        <nav>
            <a href="#gioithieu">Giới Thiệu</a>
            <a href="#sanpham">Sản Phẩm</a>
            <a href="#dichvu">Dịch Vụ</a>
            <a href="#duan">Dự Án</a>
            <a href="#hotro">Hỗ Trợ</a>
            <a href="#lienhe">Liên Hệ</a>
        </nav>
        <div class="user-actions">
            <div id="auth-buttons">
                <a href="#" onclick="showLoginModal()" class="btn-login">Đăng nhập</a>
                <a href="#" onclick="showRegisterModal()" class="btn-register">Đăng ký</a>
            </div>
            <div id="profile-info" class="user-info" style="display: none;">
                <a href="#" class="profile-link">
                    <i class="fas fa-user-circle"></i>
                    <span id="user-name"></span>
                </a>
                <a href="#" onclick="logout()" class="btn-logout">Đăng xuất</a>
            </div>
            <a href="#" onclick="showCart()" class="cart-link">
                <i class="fas fa-shopping-cart"></i> Giỏ Hàng <span id="cart-count">0</span>
            </a>
        </div>
    </header>

    <div class="hero">
        <img src="5.jpg" alt="Hình ảnh"/>
    </div>

    <section id="gioithieu">
        <h2>Giới Thiệu Về Chúng Tôi</h2>
        <p style="text-align: center; max-width: 800px; margin: 0 auto 50px;" class="animated-element">
            Chúng tôi là đơn vị hàng đầu trong lĩnh vực phòng cháy chữa cháy, chuyên cung cấp các giải pháp an toàn tối ưu cho mọi công trình. Với đội ngũ kỹ sư giàu kinh nghiệm, chúng tôi cam kết mang đến sự an tâm tuyệt đối cho khách hàng.
        </p>
        <div class="info-block">
            <div class="info-item animated-element">
                <i class="fas fa-handshake"></i>
                <h3>Đội Ngũ Chuyên Nghiệp</h3>
                <p>Kỹ sư PCCC được đào tạo bài bản, nhiều kinh nghiệm thực chiến.</p>
                <button class="info-button" onclick="location.href = '#doingu';">Tìm Hiểu Thêm</button>
            </div>
            <div class="info-item animated-element">
                <i class="fas fa-certificate"></i>
                <h3>Sản Phẩm Chính Hãng</h3>
                <p>Thiết bị được kiểm định chất lượng, đạt chuẩn quốc tế.</p>
                <button class="info-button" onclick="location.href = '#sanpham';">Tìm Hiểu Thêm</button>
            </div>
            <div class="info-item animated-element">
                <i class="fas fa-headset"></i>
                <h3>Hỗ Trợ 24/7</h3>
                <p>Luôn sẵn sàng tư vấn và hỗ trợ kỹ thuật mọi lúc, mọi nơi.</p>
                <button class="info-button" onclick="location.href = '#hotro';">Tìm Hiểu Thêm</button>
            </div>
        </div>
    </section>
    
    <hr style="border: none; border-top: 1px solid #dee2e6; margin: 40px auto; max-width: 90%;">

    <section id="doingu">
        <h2>Đội Ngũ Của Chúng Tôi</h2>
        <p style="text-align: center; max-width: 800px; margin: 0 auto 50px;">
            Đội ngũ kỹ sư của chúng tôi đều là những chuyên gia PCCC với nhiều năm kinh nghiệm, được cấp chứng chỉ hành nghề theo đúng quy định của Nhà nước. Chúng tôi luôn sẵn sàng tư vấn, thiết kế và thi công các dự án PCCC một cách chuyên nghiệp và hiệu quả nhất.
        </p>
        <div class="info-block">
            <div class="card animated-element">
                <img src="5.jpg" alt="Đội ngũ kỹ sư PCCC" />
                <h3>Chuyên Nghiệp & Tận Tâm</h3>
                <p>Được đào tạo và cập nhật kiến thức liên tục để đáp ứng mọi tiêu chuẩn an toàn.</p>
            </div>
            <div class="card animated-element">
                <img src="5.jpg" alt="Hội thảo PCCC" />
                <h3>Kinh Nghiệm Thực Chiến</h3>
                <p>Hơn 1000 dự án PCCC lớn nhỏ đã được triển khai thành công trên toàn quốc.</p>
            </div>
            <div class="card animated-element">
                <img src="5.jpg" alt="Lắp đặt hệ thống PCCC" />
                <h3>Công Nghệ Hiện Đại</h3>
                <p>Sử dụng các công nghệ và thiết bị tiên tiến nhất để đảm bảo an toàn tối đa.</p>
            </div>
        </div>
    </section>

    <hr style="border: none; border-top: 1px solid #dee2e6; margin: 40px auto; max-width: 90%;">

    <section id="dichvu">
        <h2>Dịch Vụ Chính</h2>
        <div class="products">
            <div class="card animated-element">
                <i class="fas fa-hard-hat" style="font-size: 4rem; color: var(--secondary); margin-bottom: 20px;"></i>
                <h3>Thi Công Hệ Thống PCCC</h3>
                <p>Thiết kế và lắp đặt hệ thống báo cháy, chữa cháy tự động theo tiêu chuẩn mới nhất.</p>
            </div>
            <div class="card animated-element">
                <i class="fas fa-file-contract" style="font-size: 4rem; color: var(--secondary); margin-bottom: 20px;"></i>
                <h3>Tư Vấn & Thiết Kế</h3>
                <p>Lập bản vẽ, hoàn thiện hồ sơ và xin cấp phép PCCC cho mọi loại công trình.</p>
            </div>
            <div class="card animated-element">
                <i class="fas fa-tools" style="font-size: 4rem; color: var(--secondary); margin-bottom: 20px;"></i>
                <h3>Bảo Trì & Sửa Chữa</h3>
                <p>Kiểm tra, bảo dưỡng định kỳ, đảm bảo hệ thống luôn hoạt động hiệu quả.</p>
            </div>
        </div>
    </section>
    
    <hr style="border: none; border-top: 1px solid #dee2e6; margin: 40px auto; max-width: 90%;">

    <section id="sanpham">
        <h2>Sản Phẩm Nổi Bật</h2>
        <div class="products" id="product-list"></div>
    </section>

    <hr style="border: none; border-top: 1px solid #dee2e6; margin: 40px auto; max-width: 90%;">

    <section id="duan">
        <h2>Dự Án Tiêu Biểu</h2>
        <p style="text-align: center; max-width: 800px; margin: 0 auto 50px;" class="animated-element">
            Chúng tôi tự hào đã trở thành đối tác tin cậy của nhiều doanh nghiệp lớn tại Việt Nam, góp phần xây dựng môi trường làm việc an toàn và chuyên nghiệp.
        </p>
        <div class="products">
            <div class="card animated-element">
                <img src="logo.jpg" alt="Dự án Trường Đại Học Đồng Tháp" />
                <h3>Trường Đại Học Đồng Tháp</h3>
                <p>Thi công hệ thống báo cháy tự động cho nhà máy sản xuất.</p>
            </div>
            <div class="card animated-element">
                <img src="logo.jpg" alt="Dự án tòa nhà văn phòng" />
                <h3>Tòa Nhà VinGroup</h3>
                <p>Lắp đặt hệ thống PCCC hiện đại cho khu văn phòng và thương mại.</p>
            </div>
            <div class="card animated-element">
                <img src="logo.jpg" alt="Dự án khu dân cư" />
                <h3>Khu Dân Cư Cao Cấp</h3>
                <p>Giải pháp phòng cháy toàn diện cho khu dân cư, đảm bảo an toàn cho cư dân.</p>
            </div>
        </div>
    </section>

    <hr style="border: none; border-top: 1px solid #dee2e6; margin: 40px auto; max-width: 90%;">

    <section id="hotro">
        <h2>Bạn Cần Hỗ Trợ?</h2>
        <form onsubmit="submitSupport(event)" class="animated-element">
            <input type="text" placeholder="Họ và tên" required />
            <input type="email" placeholder="Email liên hệ" required />
            <input type="tel" placeholder="Số điện thoại" required />
            <textarea rows="5" placeholder="Nội dung yêu cầu hỗ trợ..."></textarea>
            <button type="submit">Gửi Yêu Cầu Của Bạn</button>
        </form>
    </section>

    <section id="lienhe">
        <h2>Liên Hệ Với Chúng Tôi</h2>
        <div style="text-align: center;" class="animated-element">
            <p><strong>Địa chỉ:</strong>Trụ sở : 464/21/15 và 15A Nguyễn Văn Quá, P.Đông Hưng Thuận, Tp.HCM ; Xưởng kho hàng & Bảo trì bình chữa cháy : 464/27/5 Nguyễn Văn Quá, P.Đông Hưng Thuận, Tp.HCM.</p>
            <p><strong>Hotline:</strong> <a href="tel:0936114144" style="color: var(--primary); text-decoration: none;">0386 114 114</a></p>
            <p><strong>Email:</strong> <a href="mailto:thietkephongchay@gmail.com" style="color: var(--primary); text-decoration: none;"></a>thietkephongchay@gmail.com</p>
        </div>
    </section>

    <footer>
        <div class="contact-info">
            <a href="tel:0386114114"><i class="fas fa-phone-alt"></i>0386 114 114</a>
            <a href="mailto:thietkephongchay@gmail.com"><i class="fas fa-envelope"></i>thietkephongchay@gmail.com</a>
        </div>
        <p>&copy; 2025 PCCC TACOTEK - Bảo vệ mọi khoảnh khắc.</p>
    </footer>

    <div id="cart-modal" class="modal">
        <div class="modal-content" id="cart-box">
            <span class="close-btn" onclick="hideCart()">&times;</span>
            <h3>Giỏ Hàng Của Bạn</h3>
            <div id="cart-items"></div>
            <div id="cart-total"></div>
            <button id="checkout-btn" onclick="checkout()">THANH TOÁN</button>
        </div>
    </div>
    
    <div id="product-detail-modal" class="modal">
        <div class="modal-content" id="product-detail-box">
            <span class="close-btn" onclick="hideProductDetail()">&times;</span>
            <img id="detail-image" src="" alt="Product Image" />
            <h3 id="detail-name"></h3>
            <p id="detail-description"></p>
            <p>Giá: <strong id="detail-price"></strong></p>
        </div>
    </div>

    <div id="login-modal" class="modal">
        <div class="modal-content">
            <span class="close-btn" onclick="hideLoginModal()">&times;</span>
            <h3>Đăng nhập</h3>
            <form onsubmit="handleLogin(event)">
                <input type="email" placeholder="Email của bạn" required />
                <input type="password" placeholder="Mật khẩu" required />
                <button type="submit">Đăng nhập</button>
            </form>
            <p style="text-align: center; margin-top: 20px;">
                Chưa có tài khoản? <a href="#" onclick="showRegisterModal()">Đăng ký ngay</a>
            </p>
        </div>
    </div>

    <div id="register-modal" class="modal">
        <div class="modal-content">
            <span class="close-btn" onclick="hideRegisterModal()">&times;</span>
            <h3>Đăng ký</h3>
            <form onsubmit="handleRegister(event)">
                <input type="text" placeholder="Họ và tên" id="reg-name" required />
                <input type="email" placeholder="Email của bạn" required />
                <input type="password" placeholder="Mật khẩu" required />
                <button type="submit">Đăng ký</button>
            </form>
            <p style="text-align: center; margin-top: 20px;">
                Đã có tài khoản? <a href="#" onclick="showLoginModal()">Đăng nhập</a>
            </p>
        </div>
    </div>

    <script>
        const products = [
    { name: "Bình Chữa Cháy MFZ4", price: 350000, image: "logo.jpg", description: "Bình bột chữa cháy 4kg, hiệu quả với đám cháy loại A, B, C. Phù hợp sử dụng trong văn phòng, nhà ở và nhà xưởng nhỏ." },
    { name: "Đầu Báo Khói Quang", price: 290000, image: "logo.jpg", description: "Thiết bị báo khói cảm ứng nhanh, chính xác cho mọi không gian. Có đèn LED báo trạng thái và còi báo động tích hợp." },
    { name: "Tủ Trung Tâm Báo Cháy 10 kênh", price: 1450000, image: "logo.jpg", description: "Tủ điều khiển trung tâm 10 kênh, dễ dàng lắp đặt và quản lý hệ thống. Hỗ trợ kết nối với nhiều loại thiết bị báo cháy." },
];
let cart = [];
let isLoggedIn = false;
let userName = "Khách Hàng";

function formatCurrency(n) {
    return n.toLocaleString('vi-VN') + ' VNĐ';
}

function renderProducts() {
    const list = document.getElementById("product-list");
    list.innerHTML = "";
    products.forEach((p, i) => {
        list.innerHTML += `
            <div class="card animated-element">
                <img src="${p.image}" alt="${p.name}" />
                <h3>${p.name}</h3>
                <p>${p.description}</p>
                <p>Giá: <strong>${formatCurrency(p.price)}</strong></p>
                <div class="btn-group">
                    <button onclick="addToCart(${i})">MUA NGAY</button>
                    <button class="secondary" onclick="showProductDetail(${i})">Xem Chi Tiết</button>
                </div>
            </div>`;
    });
}

function addToCart(index) {
    cart.push(products[index]);
    document.getElementById("cart-count").textContent = cart.length;
    alert(`Đã thêm sản phẩm "${products[index].name}" vào giỏ hàng!`);
}

function showCart() {
    const cartItemsContainer = document.getElementById("cart-items");
    const cartTotalContainer = document.getElementById("cart-total");
    cartItemsContainer.innerHTML = "";
    
    if (cart.length === 0) {
        cartItemsContainer.innerHTML = "<p style='text-align:center;'>Giỏ hàng của bạn đang trống.</p>";
        cartTotalContainer.textContent = "Tổng cộng: 0 VNĐ";
        document.getElementById("checkout-btn").disabled = true;
    } else {
        let total = 0;
        cart.forEach(item => {
            cartItemsContainer.innerHTML += `
                <div class='cart-item'>
                    <span>${item.name}</span>
                    <span>${formatCurrency(item.price)}</span>
                </div>`;
            total += item.price;
        });
        cartTotalContainer.textContent = `Tổng cộng: ${formatCurrency(total)}`;
        document.getElementById("checkout-btn").disabled = false;
    }
    document.getElementById("cart-modal").style.display = "flex";
}

function hideCart() {
    document.getElementById("cart-modal").style.display = "none";
}

function showProductDetail(index) {
    const product = products[index];
    document.getElementById("detail-image").src = product.image;
    document.getElementById("detail-name").textContent = product.name;
    document.getElementById("detail-description").textContent = product.description;
    document.getElementById("detail-price").textContent = formatCurrency(product.price);
    document.getElementById("product-detail-modal").style.display = "flex";
}

function hideProductDetail() {
    document.getElementById("product-detail-modal").style.display = "none";
}

function checkout() {
    if (cart.length > 0) {
        alert("Đơn hàng của bạn đã được tiếp nhận. Chúng tôi sẽ liên hệ để xác nhận!");
        cart = [];
        document.getElementById("cart-count").textContent = 0;
        hideCart();
    }
}

function submitSupport(e) {
    e.preventDefault();
    alert("Cảm ơn bạn đã gửi yêu cầu hỗ trợ. Chúng tôi sẽ liên hệ với bạn trong thời gian sớm nhất!");
    e.target.reset();
}

function handleAnimations() {
    const elements = document.querySelectorAll('.animated-element, .card, .info-item');
    elements.forEach(element => {
        const rect = element.getBoundingClientRect();
        const isVisible = (rect.top < window.innerHeight && rect.bottom >= 0);
        if (isVisible) {
            element.classList.add('visible');
        }
    });
}

function updateHeaderUI() {
    const authButtons = document.getElementById('auth-buttons');
    const profileInfo = document.getElementById('profile-info');
    const userNameElement = document.getElementById('user-name');

    if (isLoggedIn) {
        authButtons.style.display = 'none';
        profileInfo.style.display = 'flex';
        userNameElement.textContent = userName;
    } else {
        authButtons.style.display = 'flex';
        profileInfo.style.display = 'none';
    }
}

function showLoginModal() {
    hideRegisterModal();
    document.getElementById("login-modal").style.display = "flex";
}
function hideLoginModal() {
    document.getElementById("login-modal").style.display = "none";
}
function showRegisterModal() {
    hideLoginModal();
    document.getElementById("register-modal").style.display = "flex";
}
function hideRegisterModal() {
    document.getElementById("register-modal").style.display = "none";
}

function handleLogin(e) {
    e.preventDefault();
    const email = e.target.querySelector('input[type="email"]').value;
    userName = email.split('@')[0];
    
    isLoggedIn = true;
    updateHeaderUI();
    hideLoginModal();
    alert("Đăng nhập thành công! Chào mừng bạn quay trở lại.");
}

function handleRegister(e) {
    e.preventDefault();
    userName = e.target.querySelector('#reg-name').value;

    isLoggedIn = true;
    updateHeaderUI();
    hideRegisterModal();
    alert("Đăng ký thành công! Chào mừng bạn, " + userName + ".");
}

function logout() {
    isLoggedIn = false;
    userName = "Khách Hàng";
    updateHeaderUI();
    alert("Bạn đã đăng xuất thành công.");
}

document.addEventListener('DOMContentLoaded', () => {
    renderProducts();
    handleAnimations();
    updateHeaderUI();
});

window.addEventListener('scroll', handleAnimations);
    </script>
</body>
</html>
