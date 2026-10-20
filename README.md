# Chăm Sóc Xe - Website Dịch Vụ Chăm Sóc Ô Tô & Xe Cộ

> **Đề thi Giữa kỳ môn Thiết Kế Web - Trường Đại học Lạc Hồng (LHU) - Khoa Công Nghệ Thông Tin**  
> **Sinh viên thực hiện:** Nguyễn Tấn Thuận - **MSSV:** 125000770  
> **Repository:** https://github.com/NguyenTanThuan1/Thuan_NguyenTan_125000770.git  
> **Live Preview (GitHub Pages):** https://nguyentanthuan1.github.io/Thuan_NguyenTan_125000770/  
> **Hình thức thi:** Đề thi mở (Vibe Coding)

---

## 📌 Cấu Trúc Repository Theo Yêu Cầu

```text
Ten_Ho_MSSV/
│
├── index.html          # File HTML5 chuẩn ngữ nghĩa Semantic
├── style.css           # File CSS3, CSS Variables (:root), Flexbox & Grid
├── PROMPT_LOG.md       # Nhật ký Prompt Engineering (Vibe Coding Log - 3.0 điểm)
├── README.md           # Hướng dẫn nộp bài và chạy dự án
└── assets/             # Thư mục chứa tài nguyên phụ trợ (nếu có)
```

---

## 🚀 Tính Năng & Tiêu Chí Kỹ Thuật Đạt Chuẩn 10/10

1. **Chuẩn Semantic HTML5 (2.0 điểm):**
   - Đầy đủ các thẻ ngữ nghĩa: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`.
   - Tuyệt đối không lạm dụng thẻ `<div>` vô nghĩa. Mỗi dịch vụ, bước quy trình, bảng giá, testimonial đều dùng thẻ `<article>`.
2. **Kỹ thuật CSS & CSS Variables (2.5 điểm):**
   - Khai báo và sử dụng hệ thống biến `:root` (`--primary-color`, `--bg-dark`, `--font-family`, `--spacing-*`,...).
   - Bố cục hiện đại: phối hợp hài hòa giữa **CSS Flexbox** và **CSS Grid**.
   - Thiết kế Responsive chuẩn trên Mobile, Tablet, Laptop và Desktop.
   - UI/UX phong cách Dark Luxury sang trọng cho trung tâm Detailing & Car Care.
3. **Hiệu ứng & Thư viện (100% Thuần HTML5 & CSS3):**
   - Tích hợp **Animate.css** (thư viện CSS thuần) cho Hero section, tiêu đề và nút CTA.
   - Cơ chế đóng/mở Mobile Menu hoàn toàn bằng **CSS Checkbox Hack** (`:checked`) không cần JavaScript.
   - Tự viết các hiệu ứng `:hover`, `:focus`, `:active` mượt mà cho nút bấm, thẻ bài viết và form nhập liệu.
4. **Nhật ký Prompt Engineering `PROMPT_LOG.md` (3.0 điểm):**
   - Trình bày đúng cấu trúc biểu mẫu của Khoa CNTT LHU.
   - Ghi lại chi tiết các vòng lặp (iterations), prompt ban đầu, thách thức & cách debug, cùng 2 câu hỏi đánh giá cá nhân.

---

## 🛠 Hướng Dẫn Đẩy Code Lên GitHub & Bật GitHub Pages (1.0 điểm)

### Bước 1: Đổi tên thư mục thành đúng cú pháp
Tên thư mục / repository trên GitHub phải đặt theo định dạng:  
**`Ten_Ho_MSSV`**  
*(Ví dụ: Bạn tên Nguyễn Văn Nam, MSSV là 20110001 thì đặt là: `Nam_NguyenVan_20110001`)*

### Bước 2: Khởi tạo Git và Push lên GitHub
Mở Terminal/PowerShell tại thư mục này và chạy các lệnh:

```bash
# 1. Khởi tạo kho Git
git init

# 2. Thêm tất cả các file
git add .

# 3. Tạo commit đầu tiên
git commit -m "feat: Khoi tao du an website Cham Soc Xe voi 100% HTML5 semantic va CSS3 thuan"

# 4. Đổi nhánh chính thành main
git branch -M main

# 5. Liên kết tới repository GitHub của bạn (thay username và ten_repo)
git remote add origin https://github.com/<YOUR_GITHUB_USERNAME>/<Ten_Ho_MSSV>.git

# 6. Đẩy code lên GitHub
git push -u origin main
```

### Bước 3: Kích hoạt GitHub Pages để Giảng viên xem Live
1. Truy cập vào Repository của bạn trên GitHub.
2. Nhấn vào tab **Settings** (Cài đặt) ở thanh menu trên cùng.
3. Ở menu bên trái, chọn mục **Pages**.
4. Tại phần **Build and deployment** > **Branch**:
   - Chọn nhánh: **`main`**
   - Chọn thư mục: **`/(root)`**
   - Nhấn **Save**.
5. Đợi khoảng 1 - 2 phút, GitHub sẽ hiển thị đường link trang web trực tiếp (ví dụ: `https://<username>.github.io/<Ten_Ho_MSSV>/`).
6. **Quan trọng:** Quay lại trang chủ của Repository, nhấn vào biểu tượng bánh răng ⚙️ ở góc phải mục **About**, dán link GitHub Pages vào ô **Website** để Giảng viên bấm vào xem trực tiếp.
