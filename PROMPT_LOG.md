# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)
- Họ và tên:Trần Minh Bảo
- MSSV:426000129
- Tên đề tài Website: Portfolio cá nhân
- Công cụ AI đã sử dụng: Antigravity
## 1. Yêu cầu ban đầu (System/Initial Prompt)
Bạn là chuyên gia Front-end, hãy viết file index.html chuẩn Semantic HTML5 cho trang Portfolio cá nhân. Cấu trúc gồm: <header> (logo và <nav>), <main> chứa 3 section (Hero banner giới thiệu, Skills dàn hàng ngang, Projects dạng card) và <footer>. 
## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)
### Lần 1: Dựng khung Semantic HTML & CSS Variable
- Prompt đã dùng: Hãy viết CSS cho file HTML trên theo tư duy Mobile First. Khai báo biến :root gồm --primary-color, --secondary-color, --bg-color. Dùng Flexbox cho Nav & Skills, dùng CSS Grid cho Projects dạng 3 cột trên Desktop và 1 cột trên Mobile. Tạo file style.css
- Kết quả AI tạo ra: 
Mình tạo file style.css theo đúng tư duy Mobile First bạn yêu cầu:
Khai báo biến (:root): Đã thêm các biến màu sắc như --primary-color, --secondary-color, --bg-color ở đầu file để dễ dàng tái sử dụng và quản lý theme.
Tư duy Mobile First:
Mặc định CSS sẽ thiết kế cho màn hình nhỏ gọn (Mobile) trước: Header được xếp dọc (flex-direction: column), các kỹ năng tự động rớt dòng (flex-wrap: wrap) nếu quá dài, và phần Dự án (Projects) sẽ hiển thị ở dạng 1 cột (grid-template-columns: 1fr).
Media Query cho Desktop: Mình sử dụng @media (min-width: 768px) để điều chỉnh lại giao diện cho màn hình lớn hơn:
Header sẽ dàn hàng ngang (flex-direction: row).
Phần Dự án (Projects) sẽ tự động chia thành 3 cột bằng CSS Grid (grid-template-columns: repeat(3, 1fr)).
Bạn có thể mở file html trên trình duyệt và thử co giãn kích thước cửa sổ để xem sự thay đổi Responsive nhé!
### Lần 2: Tích hợp thư viện Animate.css & AOS
Hãy nhúng thư viện Animate.css vào thẻ <head> của file index.html qua CDN. Sau đó, thêm các class animate__animated animate__fadeInDown vào phần Header và animate__zoomIn vào nút bấm CTA chính ở Hero Section để tạo ấn tượng khi vừa truy cập trang.
### Lần 3
Viết CSS cho các thanh tiến trình (Progress bars) thể hiện mức độ kỹ năng (HTML 90%, CSS 85%, JS 75%). Khi trang web vừa tải xong, thanh màu bên trong sẽ tự động chạy từ 0% đến phần trăm mục tiêu trong 2 giây bằng @keyframes và giữ nguyên trạng thái bằng animation-fill-mode: forwards
### Lần 4: Tạo hiệu ứng lật thẻ
Tạo hiệu ứng lật thẻ 3D cho các Card dự án bằng CSS
. Mặt trước hiển thị hình ảnh dự án và tiêu đề; khi hover vào, thẻ sẽ xoay 180 độ theo trục Y lộ ra mặt sau chứa mô tả công nghệ và nút 'Xem Demo'
. Sử dụng transform-style: preserve-3d; và backface-visibility: hidden; để hiệu ứng mượt mà
### Lần 5: Giao diện Dark/Ligt Mode
hãy tạo tính năng chuyển đổi giao diện Sáng/Tối (Light/Dark Mode) hoàn toàn bằng HTML & CSS thuần (không sử dụng JavaScript) theo yêu cầu sau:
Cấu trúc HTML:
Sử dụng 1 thẻ <input type="checkbox" id="theme-toggle" hidden> ẩn.
Dùng thẻ <label for="theme-toggle"> làm nút bấm chứa 2 icon: Mặt trời ☀️ (cho Light Mode) và Mặt trăng 🌙 (cho Dark Mode) — có thể dùng Icon FontAwesome, SVG hoặc Emoji.
Xử lý CSS (Checkbox Hack & CSS Variables):
Khai báo bộ biến CSS tại :root cho giao diện Sáng (--bg-color, --text-color, --card-bg...).
Sử dụng CSS selector khi checkbox được tích :checked (#theme-toggle:checked ~ .wrapper hoặc :checked cấp cha) để đổi giá trị các biến :root sang tông màu Tối.
Chuyển đổi Icon: Khi ở chế độ Sáng thì hiện icon Mặt trăng 🌙 (ẩn Mặt trời ☀️); khi bấm chuyển sang Tối (:checked) thì ẩn Mặt trăng 🌙 và hiện icon Mặt trời ☀️.
Bổ sung transition: all 0.3s ease; để màu nền, màu chữ và icon chuyển đổi mượt mà.
### Lần 6: Menu
Ở giao diện Mobile, Menu biến mất vàthay bằng biểu tượng "3 gạch" (Hamburger Menu). Biến đổi biểu tượng 3 gạch ngang thành dấu "X" một cách mượt mà khi người dùng mở Menu (Sử dụng CSS Transitions).Yêu cầu viết bằng CSS, không dùng javascripts. Trên Desktop Menu nằm giữa màn hình.
### Lần 7: Nút tin nhăn
bỏ nút "Liên hệ với tôi" thay vào đó hãy tạo một nút tròn cố định ở góc dưới bên phải màn hình (position: fixed) chứa biểu tượng tin nhắn. Sử dụng CSS @keyframes pulse để tạo hiệu ứng 'phập phồng' co giãn từ scale(1) lên scale(1.1) liên tục và lan tỏa bóng nhẹ để thu hút sự chú ý.
## 3. Đánh giá cá nhân về quá trình Vibe Coding
- AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?
AI đã giúp bạn tiết kiệm thời gian ở phần Giao diện Dark/Ligt Mode
- Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?
Phải có yêu cầu rõ ràng khi đặt câu hỏi cho AI