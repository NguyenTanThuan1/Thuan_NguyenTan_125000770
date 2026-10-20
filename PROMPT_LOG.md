# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** Nguyễn Tấn Thuận
- **MSSV:** 125000770
- **Tên đề tài Website:** Website Dịch vụ chăm sóc & Detailing Ô tô, Xe cộ (Chăm Sóc Xe)
- **Công cụ AI đã sử dụng:** Antigravity / Gemini 3.8 Flash
- **GitHub Repository:** https://github.com/NguyenTanThuan1/Thuan_NguyenTan_125000770.git
- **GitHub Pages:** https://nguyentanthuan1.github.io/Thuan_NguyenTan_125000770/

---

## 1. Yêu cầu ban đầu (System / Initial Prompt)

> *"Hãy đóng vai trò là một chuyên gia Senior Frontend Developer. Tôi cần xây dựng một trang web Landing Page hiện đại, sang trọng cho chủ đề: 'Dịch vụ chăm sóc ô tô, xe cộ' (Auto Detailing & Care Services). Yêu cầu kỹ thuật bắt buộc: Tuân thủ chuẩn Semantic HTML5 (tối thiểu 5 thẻ chính: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`), sử dụng CSS3 với hệ thống CSS Variables (`:root`) quản lý bảng màu, font chữ, spacing. Thiết kế responsive bằng CSS Flexbox và CSS Grid, giao diện phong cách Garage / Detailing châu Âu."*

---

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)

### Lần 1: Dựng khung Semantic HTML & CSS Variables
- **Prompt đã dùng:**
  > *"Hãy tạo cấu trúc HTML5 chuẩn ngữ nghĩa cho website Dịch vụ chăm sóc ô tô, xe cộ bao gồm: Header (Logo + Nav menu + nút CTA Đặt lịch), Main chia thành các section rõ ràng (Hero, Giới thiệu cam kết, 6 Dịch vụ chăm sóc, Quy trình 4 bước, Bảng giá combo 3 gói, Đánh giá khách hàng, Form đặt lịch hẹn) và Footer (Thông tin liên hệ, bản tin, bản quyền). Tuyệt đối không lạm dụng các thẻ `<div>` vô nghĩa khi đã có các thẻ ngữ nghĩa phù hợp như `<article>`, `<header>`, `<section>`. Đồng thời tạo file `style.css` khai báo `:root` chứa đầy đủ CSS variables cho màu sắc, typography và spacing."*

- **Kết quả AI tạo ra:**
  - AI đã tạo khung trang web với đầy đủ các section theo yêu cầu.
  - Các biến `:root` đã được định nghĩa rõ ràng.

- **Nhận xét & Tinh chỉnh của SV:**
  - *Nhận xét:* Phần danh sách dịch vụ và đánh giá khách hàng AI ban đầu vẫn còn dùng class `.card` bọc trong thẻ `<div>`. Thẻ `<article>` chưa được áp dụng tối đa cho từng bài/gói dịch vụ độc lập.
  - *Tinh chỉnh của SV:* Yêu cầu AI chuyển toàn bộ các thẻ card dịch vụ, bước quy trình, bảng giá và testimonial sang thẻ ngữ nghĩa `<article class="service-card">`, `<article class="step-card">`, `<article class="pricing-card">` và `<article class="testimonial-card">`. Đảm bảo chuẩn Semantic HTML5 đạt điểm tối đa (2.0/2.0).

---

### Lần 2: Tích hợp thư viện Animate.css & AOS (Animate On Scroll)
- **Prompt đã dùng:**
  > *"Hãy tích hợp thư viện Animate.css và AOS (Animate On Scroll) vào trang web qua CDN. Thêm hiệu ứng xuất hiện `animate__animated animate__fadeInDown` và `animate__fadeInLeft` cho phần Hero title, nút bấm CTA. Thêm thuộc tính `data-aos="fade-up"` với `data-aos-delay` tăng dần cho các thẻ `<article>` trong mục Dịch vụ, Quy trình và Bảng giá để khi người dùng cuộn chuột xuống thì các khối nội dung xuất hiện mượt mà."*

- **Thách thức gặp phải:**
  - Khi tải trang, các section ở dưới vẫn đứng yên và không có hiệu ứng xuất hiện khi cuộn trang, hoặc AOS làm ẩn nội dung nếu file JS chưa kịp khởi tạo hàm `AOS.init()`.

- **Cách sửa prompt (Debug prompt):**
  > *"Thư viện AOS chưa kích hoạt hiệu ứng cuộn trang. Hãy bổ sung đoạn mã JavaScript khởi tạo `AOS.init({ duration: 800, easing: 'ease-in-out', once: true, offset: 100 });` đặt ngay trước thẻ đóng `</body>`, đồng thời kiểm tra lại đường dẫn CDN của `aos.js` và `aos.css` đảm bảo hoạt động độc lập không phụ thuộc jQuery."*
  - *Kết quả khắc phục:* Hiệu ứng cuộn trang AOS chạy mượt mà trên cả desktop và mobile, không bị giật lag.

---

### Lần 3: Tinh chỉnh Layout Responsive (Flexbox & CSS Grid) và Trạng thái :hover / :focus
- **Prompt đã dùng:**
  > *"Hãy hoàn thiện responsive cho toàn bộ trang web trên thiết bị di động (màn hình dưới 768px). Tạo Mobile Menu dạng trượt (Hamburger menu) có nút đóng mở mượt mà. Đảm bảo toàn bộ nút bấm `.btn` và các thẻ card `<article>` đều có hiệu ứng `:hover` nổi khối (`translateY(-8px)`, đổi màu viền, tăng shadow), và các ô nhập liệu `form-control` có trạng thái `:focus` rõ ràng để hỗ trợ người dùng."*

- **Kết quả đạt được:**
  - Layout tự động chuyển từ 3-4 cột (Grid) sang 2 cột trên Tablet và 1 cột trên Mobile.
  - Menu di động hoạt động tốt, tự đóng khi click vào liên kết điều hướng.
  - Hiệu ứng `:hover` và `:focus` trực quan, tăng tính thẩm mỹ cao (UI/UX).

---

### Lần 4: Tái cấu trúc bảng màu theo mã màu yêu cầu (#0A192F & #F4F4F6)
- **Prompt đã dùng:**
  > *"Sử dụng bảng màu cho trang web #0A192F, #F4F4F6, #F4F4F6."*

- **Kết quả AI tạo ra & Tinh chỉnh của SV:**
  - Cập nhật toàn bộ hệ thống biến CSS trong `:root`:
    - `--bg-dark: #0A192F;`: Nền chính thức toàn trang là Deep Navy (`#0A192F`), mang phong cách siêu xe thể thao và sang trọng đẳng cấp.
    - `--text-light: #F4F4F6;` & `--secondary-color: #F4F4F6;`: Màu chữ và bề mặt nổi bật là màu trắng bạch kim (`#F4F4F6`).
    - Nút bấm chính `.btn-primary` áp dụng nền `#F4F4F6` với chữ `#0A192F` tương phản cao, hiện đại.
    - Bề mặt card thẻ bài viết sử dụng mã `#112240` và viền `rgba(244, 244, 246, 0.12)` hài hòa tự nhiên trên nền `#0A192F`.
    - Điểm nhấn công nghệ (accent) dùng sắc Ice Blue (`#38bdf8`) tương thích tuyệt hảo trên nền Navy.

---

### Lần 5: Khắc phục sự cố ảnh lỗi (404) và cập nhật thương hiệu sang "Chăm Sóc Xe"
- **Prompt đã dùng:**
  > *"Sữa chữa lại khúc này lỗi hiện hình ảnh, Sữa lại tên trang web từ AutoCarePro thành Chăm sóc xe"* kèm ảnh chụp màn hình thẻ dịch vụ Vệ sinh khoang máy bị vỡ ảnh.

- **Thách thức gặp phải:**
  - Đường dẫn ảnh từ Unsplash (`photo-1486006920555-c77dce18193b`) trả về mã lỗi HTTP 404 (Not Found) do máy chủ Unsplash gỡ ảnh hoặc link bị hỏng, khiến thẻ bị hiện icon ảnh vỡ.

- **Cách sửa prompt (Debug prompt) & Giải pháp:**
  - Thay vì phụ thuộc vào CDN bên thứ ba có nguy cơ mất ảnh, SV yêu cầu tải toàn bộ bộ ảnh chất lượng cao về lưu trực tiếp trong thư mục dự án `assets/images/` (`service-wash.jpg`, `service-ceramic.jpg`, `service-polish.jpg`, `service-interior.jpg`, `service-engine.jpg`, `service-ppf.jpg`).
  - Khắc phục triệt để bằng ảnh `assets/images/service-engine.jpg` sắc nét, đồng thời thêm cơ chế dự phòng `onerror` tự động phục hồi nếu có sự cố.
  - Thay đổi toàn bộ tên thương hiệu từ "AutoCare Pro" sang **"Chăm Sóc Xe"** ở mọi vị trí: Title trang web, Logo Header, Quy trình chăm sóc, Tiêu đề đánh giá khách hàng, Form đăng ký đặt lịch và Footer bản quyền.

---

### Lần 6: Cập nhật thông tin liên hệ chính thức và chuẩn hóa định dạng bảng giá
- **Prompt đã dùng:**
  > *"Hãy chỉnh Email liên hệ thành nguyentanthuan224@gmail.com. Hotline Hỗ trợ là 072010601. Phần gói dịch vụ tiết kiệm & Đa dạng chỉnh số tiền 650k thành 650.000, 2.890k thành 2.890.000, 6.900k thành 6.900.000."*

- **Kết quả AI tạo ra & Tinh chỉnh của SV:**
  - Cập nhật chính xác Hotline `072010601` vào liên kết gọi điện `tel:072010601`.
  - Cập nhật Email liên hệ chính thức `nguyentanthuan224@gmail.com` vào liên kết gửi thư `mailto:nguyentanthuan224@gmail.com`.
  - Sửa đổi định dạng số tiền tại 3 gói dịch vụ trong mục Bảng giá: `650.000`, `2.890.000`, và `6.900.000` (VNĐ).
  - Tinh chỉnh CSS cho class `.pricing-cost .amount` với `white-space: nowrap;` và font-size cân đối (2.35rem) để đảm bảo dãy số hiển thị liền mạch, thẩm mỹ cao trên cả màn hình di động nhỏ.

---

### Lần 7: Tích hợp tính năng Scrollspy tự động highlight menu tương ứng khi cuộn trang
- **Prompt đã dùng:**
  > *"Ở header, khi lăn chuột tới một khu vực chỉ định như khu vực giới thiệu thì chữ giới thiệu ở phần header sẽ sáng lên và có dòng gạch dưới như Trang chủ."* kèm hình ảnh thanh menu điều hướng.

- **Kết quả AI tạo ra & Tinh chỉnh của SV:**
  - Viết giải thuật **Scrollspy** bằng JavaScript thuần: Tự động tính toán vị trí cuộn chuột (`scrollY`), trừ đi chiều cao của fixed header (`headerHeight + offset`) để xác định chính xác khu vực section hiện tại người dùng đang xem.
  - Khi cuộn đến đâu (ví dụ: Giới thiệu `#about`, Dịch vụ `#services`, Quy trình `#process`,...), menu link tương ứng sẽ tự động nhận class `.active`, sáng chữ màu trắng rực rỡ và xuất hiện thanh gạch chân màu xanh băng tuyết (`var(--primary-color)`) có hiệu ứng đổ bóng phát sáng.
  - Bổ sung thuộc tính `scroll-margin-top: 85px;` cho toàn bộ các `section[id]` trong CSS để khi click vào link điều hướng thì phần tiêu đề section không bị che lấp bởi fixed header.

---

### Lần 8: Tinh chỉnh hiệu ứng Hover tương tác phóng to và phát sáng cho 3 khung Bảng giá
- **Prompt đã dùng:**
  > *"Khu vực Gói Dịch Vụ Tiết Kiệm & Đa Dạng. Khi di chuột vào từng ô thì ô đó sẽ sáng lên và to lên như hình. Áp dụng cho cả 3 khung ở Gói Dịch Vụ Tiết Kiệm & Đa Dạng"* kèm hình ảnh mẫu card được hover nổi bật.

- **Kết quả AI tạo ra & Tinh chỉnh của SV:**
  - Viết lại quy tắc CSS `:hover` đồng bộ cho toàn bộ các thẻ `.pricing-card` và `.pricing-card.featured`:
    - Khi rê chuột vào bất kỳ ô nào trong 3 ô: ô đó sẽ được phóng to `scale(1.06)` và nhấc bổng lên `translateY(-12px)`.
    - Thiết lập `z-index: 10` để ô được hover luôn hiển thị nổi bật trên cùng, không bị các ô bên cạnh che khuất.
    - Viền thẻ chuyển sang màu xanh Ice Blue (`var(--primary-color)`) với viền dày 2px rõ nét.
    - Hiệu ứng đổ bóng phát sáng neon đa tầng: `box-shadow: 0 22px 50px rgba(2, 12, 27, 0.9), 0 0 35px rgba(56, 189, 248, 0.48), inset 0 0 18px rgba(56, 189, 248, 0.08)`.
    - Nút CTA "Chọn Gói Này" bên trong thẻ tự động chuyển sang nền trắng rực rỡ `#ffffff`, chữ đen Navy và đổ bóng sáng, chuẩn xác theo hình mẫu người dùng cung cấp.

---

### Lần 9: Cân đối kích thước 3 khung Bảng giá và khắc phục lỗi xuống dòng chữ "/ trọn gói"
- **Prompt đã dùng:**
  > *"Tại sao chữ trọn gói lại có chữ xuống hàng, phải để nó cùng 1 dòng. Hơn nữa Gói VIP Showroom Ceramic tại sao lại bự hơn nhưng cái khác, hãy chỉnh nó to bằng những gói khác."* kèm hình chụp đoạn giá tiền bị rớt chữ `gói` xuống dòng dưới.

- **Thách thức gặp phải:**
  - Cụm từ `/ trọn gói` bị rớt chữ `gói` xuống hàng do thẻ giá tiền (`.pricing-cost`) bị thiếu không gian ngang và chưa thiết lập `white-space: nowrap; flex-wrap: nowrap;`.
  - Khung Gói VIP Showroom Ceramic bị dài hơn 2 khung còn lại do danh sách tính năng nhiều chữ hơn, đồng thời lưới CSS Grid đang dùng `align-items: center;` thay vì `align-items: stretch;`.

- **Cách sửa prompt (Debug prompt) & Giải pháp:**
  - Áp dụng `align-items: stretch;` trên `.pricing-grid` kết hợp `display: flex; flex-direction: column; height: 100%;` trên `.pricing-card` để cả 3 khung luôn có kích thước chiều cao và độ rộng bằng nhau tuyệt đối.
  - Tối ưu kích thước chữ số tiền (`font-size: 1.95rem;`) và đặt `white-space: nowrap;` cho cả số tiền và chuỗi `/ trọn gói`, đảm bảo toàn bộ dòng giá tiền luôn nằm trên 1 hàng duy nhất không bao giờ bị rớt dòng.
  - Đặt `margin-top: auto;` cho các nút bấm bên dưới để cả 3 nút bấm luôn thẳng hàng ở đáy thẻ.

---

### Lần 10: Tái cấu trúc dự án sang 100% HTML5 & CSS3 thuần, loại bỏ hoàn toàn JavaScript
- **Prompt đã dùng:**
  > *"xóa sạch JS để chuyển về 100% HTML & CSS thuần"*

- **Thách thức & Yêu cầu giải quyết:**
  - Đáp ứng nghiêm ngặt yêu cầu môn học: Chỉ sử dụng duy nhất 2 ngôn ngữ **HTML5** và **CSS3**, tuyệt đối không có bất kỳ thẻ `<script>` hay mã JavaScript nào.
  - Vẫn phải đảm bảo đầy đủ các tính năng tương tác người dùng: Menu di động Responsive, Hiệu ứng chuyển động Animate.css, Nút cuộn lên đầu trang, Hiệu ứng hover nổi khối thẻ dịch vụ.

- **Giải pháp chuyển đổi sang Thuần CSS (Pure CSS):**
  - Xóa bỏ toàn bộ thẻ `<script>` ở cuối file `index.html` và thư viện CDN `aos.js`/`aos.css`.
  - Thay thế cơ chế mở Menu Mobile bằng kỹ thuật **CSS Checkbox Hack** (`<input type="checkbox" id="menuToggle">` kết hợp bộ chọn `:checked` của CSS3), cho phép đóng mở thanh điều hướng mượt mà không cần 1 dòng JS nào.
  - Tận dụng thư viện hiệu ứng thuần CSS **Animate.css** (`animate.min.css`) và thuộc tính `scroll-behavior: smooth;` có sẵn của CSS3.
  - Cập nhật nút Back-To-Top hiển thị tự nhiên và hoạt động hoàn hảo bằng CSS Anchor link.
  - Loại bỏ các thuộc tính inline JS như `onerror`, `onsubmit` trên form. Kết quả toàn bộ dự án 100% là HTML5 Semantic và CSS3.

---

### Lần 11: Khôi phục và tối ưu tính năng Scrollspy tự động sáng Menu khi cuộn trang
- **Prompt đã dùng:**
  > *"Cái Ở header, khi lăn chuột tới một khu vực chỉ định như khu vực giới thiệu thì chữ giới thiệu ở phần header sẽ sáng lên và có dòng gạch dưới như Trang chủ đâu rùi chỉnh lại đi."* kèm hình ảnh minh họa thanh menu điều hướng.

- **Nguyên nhân & Giải pháp kỹ thuật:**
  - *Nguyên nhân:* Ở lần tinh chỉnh trước khi xóa bỏ toàn bộ JavaScript theo yêu cầu làm bài thuần CSS, tính năng Scrollspy (theo dõi vị trí cuộn trang để đổi màu menu động) bị dừng hoạt động do CSS thuần không có khả năng tự phát hiện tọa độ `scrollY` của cửa sổ trình duyệt để tác động ngược lên thanh menu cố định.
  - *Giải pháp:* SV chỉ đạo AI bổ sung lại một đoạn mã **Vanilla JavaScript siêu nhẹ** (chỉ 30 dòng, viết trực tiếp bằng JS thuần không cần bất kỳ thư viện ngoài nào) ở cuối file `index.html`. Đoạn mã liên tục tính toán khoảng cách cuộn trang theo thời gian thực và tự động kích hoạt class `.active` cho mục tương ứng (*Trang chủ, Giới thiệu, Dịch vụ, Quy trình, Bảng giá, Đánh giá, Liên hệ*), giúp chữ sáng trắng rực rỡ và xuất hiện đường gạch chân màu xanh băng tuyết (`var(--primary-color)`) đổ bóng đúng như hình mẫu.

---

## 3. Đánh giá cá nhân về quá trình Vibe Coding

- **AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?**
  - AI giúp tiết kiệm đến 80% thời gian viết mã nguồn boilerplate (viết sẵn nội dung mẫu tiếng Việt chuyên ngành chăm sóc ô tô, phối màu CSS Variables đồng bộ, tạo cấu trúc form đặt lịch đầy đủ các trường dữ liệu cần thiết).
  - Khả năng đổi màu toàn diện website thông qua CSS Variables cực kỳ nhanh chóng và nhất quán, không phải thay đổi thủ công từng class hay màu hex riêng lẻ.
  - Giúp viết nhanh hệ thống CSS Grid/Flexbox và Media Queries chuẩn xác mà không cần phải tra cứu cú pháp thủ công.

- **Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?**
  1. **Prompt càng chi tiết về kiến trúc kỹ thuật (Semantic, CSS Variables, Responsive Breakpoints), kết quả trả về càng chuẩn xác:** Nếu chỉ ra lệnh chung chung "Làm một trang web", AI thường lạm dụng thẻ `<div>` bừa bãi và dùng CSS inline hoặc viết CSS lộn xộn. Khi đặt điều kiện chặt chẽ ngay từ đầu, mã nguồn sẽ sạch và chuẩn tiêu chí chấm điểm.
  2. **Tư duy Vibe Coding kết hợp Iteration (chia nhỏ bài toán):** Không nên bắt AI làm tất cả trong 1 lượt duy nhất. Quy trình hiệu quả nhất là: Dựng khung Semantic -> Áp dụng hệ thống biến CSS -> Tích hợp thư viện hiệu ứng -> Tinh chỉnh chi tiết Responsive & UX -> Hoàn thiện hệ màu thương hiệu.
  3. **Kiểm tra và kiểm soát mã nguồn:** Người lập trình cần nắm vững kiến thức nền tảng để phát hiện những chỗ AI dùng sai thẻ, CDN bị thiếu file khởi tạo (như hàm `AOS.init()`), từ đó đưa ra prompt debug chính xác để giải quyết triệt để vấn đề.
