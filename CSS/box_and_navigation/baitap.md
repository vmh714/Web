### **Bài tập thực hành cho Giai đoạn 2**

#### **Bài tập 1: Tạo kiểu cho Nút bấm (Button Styling) (Dễ)**

- **Mục tiêu học tập:**
  - Hiểu và áp dụng các thuộc tính cơ bản của **Box Model**: `padding`, `border`, `margin`.
  - Làm quen với việc sử dụng `box-sizing: border-box` để kiểm soát kích thước.
- **Mô tả yêu cầu:**
  1.  Tạo hai thẻ `<a>` trong file HTML và đặt cho chúng `class="button"`.
  2.  Trong file CSS, hãy style cho class `.button` để nó trông giống một nút bấm thực sự:
      - Bỏ gạch chân mặc định (`text-decoration`).
      - Đặt màu nền (`background-color`) và màu chữ (`color`).
      - Sử dụng **`padding`** để tạo không gian bên trong nút, giúp chữ không bị dính vào viền (ví dụ: `10px` cho trên/dưới và `20px` cho trái/phải).
      - Thêm một đường viền (`border`) cho nút.
      - Sử dụng **`margin`** để tạo khoảng cách _giữa_ hai nút bấm với nhau.
  3.  **Thử thách:** Hãy thử thêm `width: 150px` cho nút. Quan sát sự khác biệt khi có và không có `box-sizing: border-box;`.

#### **Bài tập 2: Bố cục hai cột đơn giản (Trung bình)**

- **Mục tiêu học tập:**
  - Sử dụng **đơn vị tương đối** (`%` và `rem`) để tạo bố cục linh hoạt.
  - Kết hợp Box Model và các đơn vị để quản lý không gian hiệu quả.
- **Mô tả yêu cầu:**
  1.  Tạo một `div` cha có `class="container"`. Bên trong, tạo hai `div` con có `class="column"`.
  2.  Trong file CSS:
      - Đặt cho `.container` một chiều rộng cố định bằng `px` (ví dụ: `width: 900px;`) và `margin: auto;` để căn giữa nó trên trang.
      - Đặt cho `.column` thuộc tính `display: inline-block;` để chúng có thể đứng cạnh nhau.
      - Sử dụng đơn vị **`%`** để đặt chiều rộng cho mỗi `.column` (ví dụ: `width: 48%;`). Tại sao không phải 50%? Hãy thử và tìm hiểu!
      - Sử dụng đơn vị **`rem`** cho `font-size`, `padding` và `margin` bên trong các cột.
  3.  **Thử thách:** Hãy thử thay đổi `font-size` của thẻ `<html>`. Bạn có thấy tất cả `padding`, `margin` và `font-size` dùng `rem` đều thay đổi theo một cách nhất quán không? Đây chính là sức mạnh của `rem`.

#### **Bài tập 3: Thẻ sản phẩm với huy hiệu "Giảm giá" (Khó)**

- **Mục tiêu học tập:**
  - Làm chủ cặp đôi "thần thánh": **`position: relative` và `position: absolute`**.
  - Hiểu về "ngữ cảnh định vị" (positioning context).
  - Tổng hợp tất cả kiến thức của Giai đoạn 2.
- **Mô tả yêu cầu:**
  1.  Tạo một `div` với `class="product-card"`.
  2.  Bên trong `div` đó, đặt một thẻ `<img>` cho ảnh sản phẩm và một thẻ `<span>` với `class="sale-badge"` chứa chữ "SALE".
  3.  Trong file CSS:
      - Style cho `.product-card` có `width`, `border`, `padding`... theo ý bạn.
      - **Quan trọng nhất:** Đặt `position: relative;` cho `.product-card`. Bước này tạo ra một "khung tham chiếu" cho các phần tử con bên trong nó.
      - Bây giờ, style cho `.sale-badge`:
        - Đặt `position: absolute;`.
        - Sử dụng các thuộc tính `top` và `left` (hoặc `right`) để đặt huy hiệu này ở góc trên bên trái (hoặc phải) của thẻ sản phẩm. Ví dụ: `top: 10px; left: 10px;`.
        - Thêm `background-color` và `color` để huy hiệu nổi bật.

---

### **Mini Project Giai đoạn 2: Thanh điều hướng cố định (Fixed Navigation Bar)**

Project này sẽ giúp bạn tạo ra một thành phần cực kỳ phổ biến trên mọi trang web, áp dụng tất cả các khái niệm quan trọng của Giai đoạn 2.

- **Mô tả project:**
  Bạn sẽ xây dựng một thanh điều hướng (header/navbar) nằm cố định ở đầu trang. Khi người dùng cuộn trang, thanh điều hướng này sẽ luôn hiển thị.

- **Yêu cầu chi tiết:**

  1.  **Cố định trên cùng:** Thanh điều hướng phải luôn dính ở đầu trang.
      - **Kiến thức áp dụng:** `position: fixed;`, `top: 0;`, `left: 0;`, `width: 100%;`.
  2.  **Thứ tự hiển thị:** Thanh điều hướng phải luôn nằm trên các nội dung khác.
      - **Kiến thức áp dụng:** `z-index` (gợi ý: đặt một giá trị lớn như `z-index: 1000;`).
  3.  **Bố cục bên trong:**
      - Thanh điều hướng cần có chiều cao (`height`) và vùng đệm (`padding`) hợp lý.
      - Thêm một chút bóng đổ (`box-shadow`) để tạo cảm giác nó "nổi" lên trên nội dung.
  4.  **Nội dung:**
      - Bên trong thanh điều hướng, có một logo (thẻ `<a>` với `id="logo"`) và một danh sách các link điều hướng (`<ul>` với `class="main-nav"`).
  5.  **Đơn vị:** Sử dụng `rem` cho `height`, `padding`, `font-size` để dễ dàng thay đổi kích thước toàn cục.

- **Gợi ý cấu trúc HTML để bắt đầu:**

  ```html
  <!DOCTYPE html>
  <html lang="vi">
    <head>
      <meta charset="UTF-8" />
      <title>Fixed Navbar</title>
      <link rel="stylesheet" href="style.css" />
    </head>
    <body>
      <header class="main-header">
        <nav class="container">
          <a href="#" id="logo">LOGO</a>
          <ul class="main-nav">
            <li><a href="#">Trang chủ</a></li>
            <li><a href="#">Sản phẩm</a></li>
            <li><a href="#">Giới thiệu</a></li>
            <li><a href="#">Liên hệ</a></li>
          </ul>
        </nav>
      </header>

      <!-- Thêm nhiều nội dung vào đây để có thể cuộn trang -->
      <main class="content">
        <h1>Nội dung trang web</h1>
        <p>...</p>
        <!-- Lặp lại thẻ p nhiều lần -->
      </main>
    </body>
  </html>
  ```

- **Gợi ý file CSS ban đầu:**

  ```css
  /* Reset cơ bản và thiết lập box-sizing */
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  html {
    font-size: 16px; /* 1rem = 16px */
  }

  body {
    font-family: sans-serif;
    /* Quan trọng: Thêm padding-top cho body bằng chiều cao của header
         để nội dung đầu trang không bị header che mất. */
  }

  .content {
    /* Chỉ để tạo không gian cho trang */
    width: 80%;
    margin: 2rem auto;
    font-size: 1.2rem;
    line-height: 1.8;
  }

  /* 
  ========================================
  BẮT ĐẦU CODE CỦA BẠN TẠI ĐÂY
  ========================================
  */

  .main-header {
    /* Gợi ý: position, top, left, width, background-color, z-index, box-shadow */
  }

  .main-header .container {
    /* Đây là nơi bạn sẽ sắp xếp logo và nav */
    /* Gợi ý: có thể dùng tạm display: inline-block cho logo và ul */
  }

  /* Style cho logo và các link điều hướng... */
  ```
