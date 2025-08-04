### **Bài tập thực hành cho Giai đoạn 1**

#### **Bài tập 1: Danh thiếp đơn giản (Dễ)**

- **Mục tiêu học tập:**
  - Luyện tập sử dụng các bộ chọn (selector) cơ bản: `element`, `class`, và `id`.
  - Thực hành áp dụng các thuộc tính màu sắc (`color`, `background-color`).
  - Làm quen với việc nhúng CSS vào file HTML.
- **Mô tả yêu cầu:**
  1.  Tạo một file `index.html` và một file `style.css`
  2.  Trong file HTML, hãy tạo một `div` với `id="business-card"`.
  3.  Bên trong `div` đó, tạo các phần tử sau:
      - Một thẻ `h2` cho tên của bạn.
      - Một thẻ `p` với `class="job-title"` cho chức danh (ví dụ: "Front-end Developer Tương Lai").
      - Một thẻ `p` với `class="contact-info"` cho email hoặc số điện thoại.
  4.  Trong file CSS:
      - Sử dụng **ID selector** để chọn `#business-card` và cho nó một màu nền (`background-color`) bạn thích và một đường viền (`border`).
      - Sử dụng **element selector** để chọn thẻ `h2` và đổi màu chữ (`color`) của nó.
      - Sử dụng **class selector** để chọn `.job-title` và làm cho chữ in nghiêng (`font-style: italic`).
      - Sử dụng **class selector** để chọn `.contact-info` và đổi màu chữ của nó thành một màu khác.

#### **Bài tập 2: Menu nhà hàng (Trung bình)**k

- **Mục tiêu học tập:**
  - Thành thạo các thuộc tính `Typography` (`font-family`, `font-size`, `font-weight`, `line-height`).
  - Sử dụng bộ chọn nhóm (grouping selector) để áp dụng style cho nhiều phần tử cùng lúc.
  - Kết hợp các kiến thức về màu sắc và kiểu chữ để tạo ra sự phân cấp thông tin rõ ràng.
- **Mô tả yêu cầu:**
  1.  Tạo cấu trúc HTML cho một menu nhỏ gồm:
      - Một thẻ `h1` là tên nhà hàng.
      - Một thẻ `h2` là tên danh mục (ví dụ: "Món chính").
      - Ba "món ăn", mỗi món ăn nằm trong một `div`. Mỗi `div` chứa:
        - Một thẻ `h3` cho tên món ăn.
        - Một thẻ `p` cho mô tả món ăn.
        - Một thẻ `p` khác với `class="price"` cho giá tiền.
  2.  Trong file CSS:
      - Chọn `h1`, `h2`, `h3` và đặt cho chúng cùng một `font-family` (ví dụ: "Georgia, serif").
      - Style cho `h1` (tên nhà hàng) có `font-size` lớn nhất và căn giữa (`text-align: center`).
      - Style cho `h2` (tên danh mục) có màu khác biệt và có một đường gạch chân bên dưới (`text-decoration: underline`).
      - Style cho `h3` (tên món ăn) được in đậm (`font-weight: bold`).
      - Style cho `.price` có màu nổi bật (ví dụ: màu đỏ) và in đậm.
      - Tăng khoảng cách giữa các dòng trong đoạn mô tả món ăn bằng `line-height`.

#### **Bài tập 3: Hero Banner cho trang Blog (Khó)**

- **Mục tiêu học tập:**
  - Làm chủ các thuộc tính về nền (`background-image`, `background-size`, `background-position`).
  - Hiểu cách làm cho văn bản nổi bật trên một ảnh nền phức tạp.
  - Kết hợp nhiều kiến thức đã học để tạo ra một thành phần giao diện hoàn chỉnh.
- **Mô tả yêu cầu:**
  1.  Tìm một ảnh nền đẹp, chất lượng cao trên các trang như Unsplash, Pexels.
  2.  Tạo một thẻ `<section>` với `id="hero-banner"`. Bên trong chứa một thẻ `h1` (tiêu đề bài viết) và một thẻ `p` (mô tả ngắn).
  3.  Trong file CSS:
      - Chọn `#hero-banner` và đặt chiều cao cố định cho nó (ví dụ: `height: 400px`).
      - Sử dụng `background-image` để chèn ảnh bạn đã tìm.
      - Sử dụng `background-size: cover;` để ảnh luôn lấp đầy banner mà không bị méo.
      - Sử dụng `background-position: center;` để phần trung tâm của ảnh luôn được hiển thị.
      - Style cho `h1` và `p` bên trong banner có màu chữ là màu trắng (`color: white;`) để dễ đọc.
      - **Thử thách:** Làm thế nào để văn bản dễ đọc hơn nữa? Gợi ý: Tạo một lớp phủ màu tối bán trong suốt lên trên ảnh nền. (Bạn có thể tìm hiểu về `linear-gradient` trong `background-image`).

---

### **Mini Project Giai đoạn 1: Thẻ Công thức nấu ăn (Recipe Card)**

Đây là project nhỏ giúp bạn tổng hợp tất cả kiến thức của Giai đoạn 1 để tạo ra một sản phẩm hoàn chỉnh, đẹp mắt.

- **Mô tả project:**
  Bạn sẽ tạo một "thẻ công thức" (recipe card) cho một món ăn bạn yêu thích. Thẻ này sẽ bao gồm hình ảnh, tên món ăn, mô tả, thời gian chuẩn bị và các bước thực hiện.

- **Yêu cầu chi tiết:**

  1.  **Container chính:** Toàn bộ thẻ nằm trong một `div` có `class="recipe-card"`. `div` này nên có một đường viền (`border`) và một chút bóng đổ (`box-shadow` - bạn có thể tự tìm hiểu thuộc tính này, rất thú vị!) để tạo cảm giác "nổi" lên trên trang.
  2.  **Hình ảnh:** Phần trên cùng của thẻ là một hình ảnh món ăn (`img`).
  3.  **Phần nội dung:**
      - **Tên món ăn (`h2`):** Phải to, rõ ràng, sử dụng một font chữ đẹp (Gợi ý: tìm trên Google Fonts và nhúng vào).
      - **Mô tả ngắn (`p`):** Một đoạn văn ngắn, có thể in nghiêng.
      - **Thông tin thời gian (`div`):** Một khu vực nhỏ chứa thời gian chuẩn bị và thời gian nấu, sử dụng các thẻ `span` để định dạng riêng cho nhãn (ví dụ: "Thời gian chuẩn bị:") và giá trị (ví dụ: "15 phút").
      - **Nguyên liệu & Hướng dẫn (`h3`):** Sử dụng thẻ `h3` cho các tiêu đề "Nguyên liệu" và "Hướng dẫn".
      - **Danh sách (`ul`, `ol`):** Dùng danh sách không có thứ tự (`<ul><li>...</li></ul>`) cho nguyên liệu và danh sách có thứ tự (`<ol><li>...</li></ol>`) cho các bước hướng dẫn.

- **Gợi ý cấu trúc HTML để bắt đầu:**

  ```html
  <!DOCTYPE html>
  <html lang="vi">
    <head>
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>Thẻ Công thức</title>
      <link rel="stylesheet" href="style.css" />
      <!-- Gợi ý: Nhúng font từ Google Fonts vào đây -->
    </head>
    <body>
      <div class="recipe-card">
        <img src="https://via.placeholder.com/400x200" alt="Hình ảnh món ăn" />

        <div class="card-content">
          <h2>Tên Món Ăn Hấp Dẫn</h2>
          <p class="description">
            Một mô tả ngắn gọn, ngon miệng về món ăn này.
          </p>

          <div class="time-info">
            <p><strong>Thời gian chuẩn bị:</strong> 15 phút</p>
            <p><strong>Thời gian nấu:</strong> 25 phút</p>
          </div>

          <h3>Nguyên liệu</h3>
          <ul>
            <li>Nguyên liệu 1</li>
            <li>Nguyên liệu 2</li>
            <li>Nguyên liệu 3</li>
          </ul>

          <h3>Hướng dẫn</h3>
          <ol>
            <li>Bước 1: Sơ chế nguyên liệu.</li>
            <li>Bước 2: Tiến hành nấu theo công thức.</li>
            <li>Bước 3: Trình bày và thưởng thức.</li>
          </ol>
        </div>
      </div>
    </body>
  </html>
  ```

- **Gợi ý file CSS ban đầu:**

  ```css
  /* Gợi ý: Nhập font từ Google Fonts ở đây */
  /* @import url('https://fonts.googleapis.com/css2?family=YourChosenFont&display=swap'); */

  body {
    background-color: #f0f0f0; /* Một màu nền nhẹ cho trang */
    font-family: sans-serif; /* Font chữ mặc định */
    /* Gợi ý: Dùng font bạn đã nhập */
    /* font-family: 'YourChosenFont', sans-serif; */
  }

  /* 
  ========================================
  BẮT ĐẦU CODE CỦA BẠN TẠI ĐÂY
  ========================================
  */

  .recipe-card {
    /* Style cho thẻ chính ở đây */
    /* Gợi ý: width, background-color, border, margin: auto để căn giữa */
  }

  .recipe-card img {
    /* Style cho ảnh */
    /* Gợi ý: width: 100% để ảnh vừa với thẻ */
  }

  .card-content {
    /* Style cho phần nội dung */
    /* Gợi ý: padding để tạo khoảng trống */
  }

  /* Style cho các thẻ h2, p, ul, ol... bên trong */
  ```
