### **Chủ đề 5: Box Model (Mô hình hộp)**

#### 1. Khái niệm

Đây là **khái niệm nền tảng và quan trọng nhất trong CSS**. Hãy hình dung mọi phần tử HTML trên trang (một đoạn văn, một bức ảnh, một nút bấm) đều được đặt bên trong một chiếc hộp chữ nhật vô hình. Mô hình hộp mô tả cách chiếc hộp đó được cấu tạo và chiếm không gian.

Chiếc hộp này có 4 lớp, đi từ trong ra ngoài:

1.  **Content (Nội dung):** Khu vực chứa nội dung thực sự của bạn (văn bản, hình ảnh...). Kích thước của nó được quyết định bởi thuộc tính `width` và `height`.
2.  **Padding (Vùng đệm):** Là khoảng không gian trong suốt _bên trong_ đường viền, nằm giữa nội dung và đường viền. Nó giống như lớp đệm của một cái hộp, đẩy nội dung vào trong. Vùng đệm sẽ có màu nền của phần tử.
3.  **Border (Đường viền):** Là đường bao quanh vùng đệm và nội dung. Bạn có thể tùy chỉnh độ dày, kiểu và màu sắc của nó.
4.  **Margin (Lề):** Là khoảng không gian trong suốt _bên ngoài_ đường viền. Nó dùng để tạo khoảng cách giữa chiếc hộp này với các chiếc hộp (phần tử) khác.

**Một thuộc tính "thần thánh": `box-sizing: border-box;`**
Mặc định, khi bạn đặt `width: 200px`, đó chỉ là chiều rộng của `content`. Nếu bạn thêm `padding` và `border`, chiều rộng tổng thể của hộp sẽ lớn hơn 200px, gây khó khăn khi tính toán bố cục.
Khi bạn dùng `box-sizing: border-box;`, trình duyệt sẽ tính toán lại: `width` bạn đặt sẽ là chiều rộng tổng thể của hộp (bao gồm cả `padding` và `border`). Điều này làm cho việc xây dựng layout trở nên trực quan và dễ dàng hơn rất nhiều. **Hầu hết các lập trình viên đều đặt thuộc tính này cho tất cả các phần tử ngay từ đầu.**

#### 2. Các thuộc tính quan trọng

- `width`, `height`: Thiết lập chiều rộng và chiều cao cho vùng `content`.
- `padding`: Thiết lập vùng đệm. (Ví dụ: `padding: 10px;` hoặc `padding-top: 5px;`)
- `border`: Thiết lập đường viền. (Ví dụ: `border: 1px solid black;`)
- `margin`: Thiết lập lề. (Ví dụ: `margin: 15px;` hoặc `margin-bottom: 20px;`)
- `box-sizing`: Thay đổi cách trình duyệt tính toán kích thước của hộp.

#### 3. Ví dụ minh họa

**HTML (`index.html`)**

```html
<div class="card">Đây là nội dung của thẻ.</div>
```

**CSS (`style.css`)**

```css
/* Áp dụng box-sizing cho tất cả các phần tử để dễ làm việc */
* {
  box-sizing: border-box;
}

.card {
  width: 300px; /* Chiều rộng tổng thể của thẻ là 300px */
  background-color: #f0f0f0;

  /* 20px đệm ở mọi phía bên trong đường viền */
  padding: 20px;

  /* Đường viền dày 2px, nét liền, màu xám */
  border: 2px solid #ccc;

  /* 15px lề bên ngoài để tạo khoảng cách với các phần tử khác */
  margin: 15px;
}
```

#### 4. Lỗi phổ biến của người mới

- **Nhầm lẫn giữa `padding` và `margin`**: Đây là lỗi phổ biến nhất. Hãy nhớ: **Padding là không gian bên trong, Margin là không gian bên ngoài**. Muốn đẩy nội dung vào trong -> dùng `padding`. Muốn đẩy cả cái hộp ra xa các hộp khác -> dùng `margin`.
- **Kích thước phần tử lớn hơn dự kiến**: Do không sử dụng `box-sizing: border-box;`. Khi thêm `padding` và `border`, phần tử bị "phình" to ra, làm vỡ bố cục.
- **Margin bị "sụp" (Margin Collapsing)**: Khi hai phần tử đặt dọc có `margin-top` và `margin-bottom` chạm nhau, chúng sẽ không cộng dồn mà chỉ lấy giá trị lớn hơn. Đây là một hành vi của CSS, bạn chỉ cần biết để không bị bối rối.

#### 5. Áp dụng thực tế

- Tạo một **nút bấm (button)**: Dùng `padding` để tạo không gian xung quanh chữ bên trong nút, dùng `margin` để tạo khoảng cách giữa nút đó và các phần tử khác.
- Tạo một **thẻ sản phẩm (product card)**: Dùng `width` để giới hạn kích thước, `padding` cho nội dung bên trong, `border` để tạo khung, và `margin` để các thẻ không dính vào nhau.
- Tạo khoảng cách giữa các **đoạn văn**: Dùng `margin-bottom` cho thẻ `<p>`.

---

### **Chủ đề 6: Các đơn vị trong CSS**

#### 1. Khái niệm

Đơn vị trong CSS dùng để xác định giá trị cho các thuộc tính như `width`, `font-size`, `margin`... Chúng cho trình duyệt biết "to bao nhiêu", "dài bao nhiêu". Các đơn vị được chia thành hai loại chính:

- **Đơn vị tuyệt đối (Absolute Units):** Có kích thước cố định, không thay đổi theo bất kỳ yếu tố nào khác.
  - `px` (pixel): Là đơn vị phổ biến nhất. 1px tương ứng với một điểm ảnh trên màn hình. Nó dễ hình dung nhưng thiếu linh hoạt cho thiết kế đáp ứng (responsive).
- **Đơn vị tương đối (Relative Units):** Có kích thước thay đổi dựa trên một giá trị khác. Đây là chìa khóa để xây dựng các trang web linh hoạt và đáp ứng.
  - `%` (phần trăm): Tương đối so với kích thước của **phần tử cha**.
  - `rem` (root em): Tương đối so với kích thước font chữ của **phần tử gốc (`<html>`)**. Đây là đơn vị **được khuyến khích nhất** cho `font-size`, `padding`, `margin` vì nó giúp toàn bộ giao diện có thể co giãn một cách nhất quán và tốt cho khả năng truy cập (accessibility).
  - `em`: Tương đối so với kích thước font chữ của **chính phần tử đó**. Có thể gây rắc rối khi các phần tử lồng vào nhau.
  - `vw`, `vh` (viewport width/height): 1vw = 1% chiều rộng của khung nhìn (cửa sổ trình duyệt). 1vh = 1% chiều cao của khung nhìn.

#### 2. Các đơn vị quan trọng

- **Tuyệt đối:** `px`
- **Tương đối:** `%`, `rem` (rất quan trọng), `vw`, `vh`

#### 3. Ví dụ minh họa

**HTML (`index.html`)**

```html
<div class="parent">
  <p class="text-px">Chữ này có kích thước 16px.</p>
  <p class="text-rem">Chữ này có kích thước 1.5rem.</p>
</div>
```

**CSS (`style.css`)**

```css
/* Thiết lập font-size gốc cho toàn bộ trang */
html {
  font-size: 16px; /* Đây là giá trị mặc định của hầu hết trình duyệt */
}

.parent {
  width: 50%; /* Rộng bằng 50% chiều rộng của thẻ body */
  font-size: 20px; /* Font-size của thẻ cha */
}

.text-px {
  font-size: 16px; /* Luôn luôn là 16px, không đổi */
}

.text-rem {
  /* 1.5 * font-size của gốc (html) = 1.5 * 16px = 24px */
  font-size: 1.5rem;
}
```

#### 4. Lỗi phổ biến của người mới

- **Lạm dụng `px` cho mọi thứ**: Khiến trang web trở nên cứng nhắc, khó co giãn trên các màn hình khác nhau.
- **Nhầm lẫn giữa `em` và `rem`**: Dùng `em` cho các phần tử lồng nhau có thể tạo ra hiệu ứng "cộng dồn" không mong muốn (font chữ ngày càng to hoặc nhỏ hơn). `rem` giải quyết triệt để vấn đề này.
- **Sử dụng `%` cho `padding` hoặc `margin` dọc**: `padding-top: 5%` sẽ tính 5% dựa trên **chiều rộng** của phần tử cha, không phải chiều cao. Điều này thường gây bất ngờ.

#### 5. Áp dụng thực tế

- Dùng `px` cho những thứ có kích thước rất nhỏ và cố định, như `border-width: 1px;`.
- Dùng `%` để chia bố cục cột, ví dụ: sidebar `30%`, nội dung chính `70%`.
- Dùng `rem` cho hầu hết mọi thứ khác: `font-size`, `padding`, `margin`, `width`, `height` của các thành phần để tạo ra một giao diện nhất quán, dễ dàng thay đổi tỷ lệ.
- Dùng `vh` để tạo một **hero banner** chiếm toàn bộ chiều cao màn hình: `height: 100vh;`.

---

### **Chủ đề 7: Position (Định vị)**

#### 1. Khái niệm

Mặc định, các phần tử HTML được sắp xếp theo một "luồng" bình thường (normal flow) - các phần tử khối (như `div`, `p`) xếp chồng lên nhau, các phần tử nội tuyến (như `span`, `a`) xếp trên cùng một dòng. Thuộc tính `position` cho phép bạn **phá vỡ luồng bình thường này** và định vị một phần tử một cách chính xác.

#### 2. Các giá trị quan trọng

- `static`: Giá trị mặc định. Phần tử nằm trong luồng bình thường. Các thuộc tính `top`, `right`, `bottom`, `left` không có tác dụng.
- `relative`: Phần tử vẫn nằm trong luồng và chiếm không gian như bình thường, nhưng bây giờ bạn có thể "dịch chuyển" nó so với vị trí ban đầu bằng `top`, `right`, `bottom`, `left`. Quan trọng nhất: nó tạo ra một **ngữ cảnh định vị (positioning context)** cho các phần tử con có `position: absolute`.
- `absolute`: Phần tử bị **nhấc hoàn toàn ra khỏi luồng bình thường**. Các phần tử khác sẽ hành xử như thể nó không tồn tại. Vị trí của nó được xác định bởi `top`, `right`, `bottom`, `left` so với **tổ tiên được định vị gần nhất** (tức là tổ tiên có `position` khác `static`). Nếu không có tổ tiên nào như vậy, nó sẽ được định vị so với thẻ `<body>`.
- `fixed`: Tương tự `absolute`, nó cũng bị nhấc ra khỏi luồng. Nhưng nó được định vị so với **khung nhìn của trình duyệt (viewport)**. Nó sẽ đứng yên một chỗ ngay cả khi bạn cuộn trang.
- `sticky`: Là sự kết hợp giữa `relative` và `fixed`. Nó hoạt động như `relative` cho đến khi bạn cuộn trang đến một ngưỡng nhất định (được xác định bởi `top`), sau đó nó sẽ "dính" lại và hoạt động như `fixed`.

#### 3. Ví dụ minh họa

**HTML (`index.html`)**

```html
<div class="product-card">
  <img src="product.jpg" alt="Sản phẩm" />
  <span class="badge">Mới</span>
</div>
```

**CSS (`style.css`)**

```css
.product-card {
  width: 200px;
  border: 1px solid #ccc;
  position: relative; /* BẮT BUỘC: Tạo ngữ cảnh định vị cho .badge */
}

.badge {
  position: absolute; /* Nhấc badge ra khỏi luồng */
  top: 10px; /* Cách cạnh trên của .product-card 10px */
  right: 10px; /* Cách cạnh phải của .product-card 10px */

  background-color: red;
  color: white;
  padding: 5px;
}
```

**Kết quả:** Huy hiệu "Mới" sẽ nằm ở góc trên bên phải của ảnh sản phẩm, bất kể nội dung khác như thế nào.

#### 4. Lỗi phổ biến của người mới

- **Dùng `position: absolute` mà quên đặt `position: relative` cho thẻ cha**: Đây là lỗi kinh điển. Phần tử sẽ bị định vị theo thẻ `<body>` và "bay" đến một vị trí không mong muốn trên trang, thay vì nằm trong thẻ cha của nó.
- **Phần tử `absolute` che lấp nội dung khác**: Vì nó bị nhấc ra khỏi luồng, các phần tử khác không "nhường chỗ" cho nó, dẫn đến việc chúng bị che khuất.
- **`z-index` không hoạt động**: Thuộc tính `z-index` (để kiểm soát thứ tự xếp chồng) chỉ có tác dụng trên các phần tử đã được định vị (có `position` khác `static`).

#### 5. Áp dụng thực tế

- **`relative` + `absolute`**: Cặp đôi hoàn hảo để tạo các **huy hiệu (badge)** trên ảnh, đặt **icon** bên trong ô input, tạo các **menu thả xuống (dropdown)**.
- **`fixed`**: Dùng cho **thanh điều hướng cố định** ở đầu trang, nút "Cuộn lên đầu trang", các banner quảng cáo/cookie luôn hiển thị.
- **`sticky`**: Dùng cho **thanh điều hướng** mà bạn muốn nó dính lại sau khi người dùng cuộn qua phần banner, hoặc **tiêu đề của một bảng dữ liệu dài**.
