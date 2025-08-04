### **Chủ đề 1: Giới thiệu & Cú pháp CSS**

#### 1. Khái niệm

Hãy tưởng tượng HTML là bộ xương của một ngôi nhà, nó xác định cấu trúc: đây là phòng khách, đây là phòng ngủ, đây là cửa sổ. Thì **CSS (Cascading Style Sheets)** chính là kiến trúc sư nội thất và thợ sơn. CSS quyết định màu sơn của tường, loại rèm cửa, kiểu dáng của đồ đạc.

Nói cách khác, **CSS là ngôn ngữ dùng để tạo phong cách và định dạng cho các tài liệu viết bằng ngôn ngữ đánh dấu (như HTML)**. Nó quyết định giao diện, màu sắc, bố cục và mọi thứ liên quan đến "vẻ ngoài" của trang web.

Có 3 cách để thêm CSS vào HTML:

- **External (Bên ngoài - Tốt nhất):** Tạo một file `.css` riêng và liên kết nó với file HTML bằng thẻ `<link>`. Đây là cách chuyên nghiệp và được khuyến khích nhất vì nó giúp tách biệt rõ ràng giữa cấu trúc (HTML) và trình bày (CSS), dễ quản lý và tái sử dụng.
- **Internal (Bên trong):** Viết code CSS bên trong cặp thẻ `<style>` đặt ở phần `<head>` của file HTML. Hữu ích khi bạn chỉ muốn style cho một trang duy nhất.
- **Inline (Nội tuyến):** Viết CSS trực tiếp vào thuộc tính `style` của một thẻ HTML. Cách này nên hạn chế tối đa vì nó làm code khó đọc, khó bảo trì và vi phạm nguyên tắc tách biệt.

#### 2. Thành phần quan trọng

Cú pháp CSS cơ bản vô cùng đơn giản và bao gồm 3 phần chính:

`selector { property: value; }`

- **Selector (Bộ chọn):** "Chọn ai?" - Đây là phần nhắm đến (các) phần tử HTML mà bạn muốn áp dụng style.
- **Property (Thuộc tính):** "Thay đổi cái gì?" - Đây là đặc tính bạn muốn thay đổi, ví dụ: `color` (màu chữ), `font-size` (cỡ chữ), `background-color` (màu nền).
- **Value (Giá trị):** "Thay đổi thành gì?" - Đây là giá trị cụ thể bạn gán cho thuộc tính, ví dụ: `red`, `16px`, `#ffffff`.

Ngoài ra, **comment (ghi chú)** trong CSS được viết giữa `/*` và `*/`.

#### 3. Ví dụ minh họa

**HTML (`index.html`)**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Trang của tôi</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <p>Đây là một đoạn văn bản sẽ được làm đẹp bằng CSS.</p>
  </body>
</html>
```

**CSS (`style.css`)**

```css
/* Đây là một comment trong CSS */

p {
  /* p là selector */
  color: blue; /* color là property, blue là value */
  font-size: 18px; /* Kết thúc mỗi dòng khai báo bằng dấu chấm phẩy ; */
}
```

**Kết quả:** Đoạn văn bản trên trang web sẽ có màu xanh dương và cỡ chữ 18px.

#### 4. Lỗi phổ biến của người mới

- **Quên dấu chấm phẩy (`;`)** ở cuối một dòng khai báo. Điều này sẽ làm cho thuộc tính tiếp theo bị lỗi.
- **Quên dấu ngoặc nhọn đóng (`}`)**.
- **Sai đường dẫn file CSS** trong thẻ `<link>`. Ví dụ: `href="styles.css"` trong khi tên file là `style.css`.
- **Viết sai tên thuộc tính:** Ví dụ: `background-colorr` thay vì `background-color`.

#### 5. Áp dụng thực tế

Mọi trang web bạn thấy đều sử dụng CSS. Từ việc đổi màu một nút bấm, thay đổi font chữ của một bài báo, cho đến việc tạo bố cục phức tạp cho các trang thương mại điện tử như Tiki, Shopee.

---

### **Chủ đề 2: Selectors (Bộ chọn) cơ bản**

#### 1. Khái niệm

Selector là "hệ thống định vị" của CSS. Nó cho phép bạn chỉ định chính xác phần tử HTML nào bạn muốn trang trí. Nếu không có selector, bạn sẽ không thể áp dụng bất kỳ style nào.

#### 2. Các bộ chọn quan trọng

- **Element Selector (Bộ chọn phần tử):** Chọn tất cả các phần tử có cùng tên thẻ.
  - Cú pháp: `ten_the` (ví dụ: `p`, `h1`, `div`)
- **Class Selector (Bộ chọn lớp):** Chọn tất cả các phần tử có cùng thuộc tính `class`. Đây là bộ chọn linh hoạt và được sử dụng nhiều nhất. Một phần tử có thể có nhiều class, và nhiều phần tử có thể dùng chung một class.
  - Cú pháp: `.ten_class` (ví dụ: `.button`, `.product-title`)
- **ID Selector (Bộ chọn định danh):** Chọn một phần tử duy nhất có thuộc tính `id`. Mỗi `id` phải là duy nhất trên một trang.
  - Cú pháp: `#ten_id` (ví dụ: `#main-header`, `#contact-form`)
- **Grouping Selector (Bộ chọn nhóm):** Áp dụng cùng một bộ quy tắc cho nhiều bộ chọn khác nhau, giúp code ngắn gọn hơn.
  - Cú pháp: `selector1, selector2, ...` (ví dụ: `h1, h2, h3`)

#### 3. Ví dụ minh họa

**HTML (`index.html`)**

```html
<h1 id="main-title">Tiêu đề chính của trang</h1>
<p class="highlight">Đoạn văn này được làm nổi bật.</p>
<p>Đây là một đoạn văn bình thường.</p>
<div>
  <h2 class="highlight">Tiêu đề phụ cũng được làm nổi bật</h2>
</div>
```

**CSS (`style.css`)**

```css
/* Element selector: áp dụng cho tất cả thẻ p */
p {
  font-family: sans-serif;
}

/* ID selector: chỉ áp dụng cho phần tử có id="main-title" */
#main-title {
  color: navy;
}

/* Class selector: áp dụng cho tất cả phần tử có class="highlight" */
.highlight {
  background-color: yellow;
  font-weight: bold;
}

/* Grouping selector: áp dụng cho cả h1 và h2 */
h1,
h2 {
  text-decoration: underline;
}
```

#### 4. Lỗi phổ biến của người mới

- **Nhầm lẫn giữa `.` và `#`**: Dùng `#` cho class và ngược lại.
- **Đặt tên class/id có khoảng trắng**: Ví dụ `class="my button"`. Đúng phải là `class="my-button"` hoặc `class="myButton"`.
- **Sử dụng một ID cho nhiều phần tử**: Vi phạm quy tắc "ID là duy nhất".
- **Quên dấu `.` hoặc `#`** trước tên class/id trong file CSS.

#### 5. Áp dụng thực tế

- Dùng **class** `.button` để style cho tất cả các nút bấm trên trang web có giao diện giống nhau.
- Dùng **ID** `#header` để style cho phần đầu trang duy nhất của website.
- Dùng **element selector** `p` để thiết lập một cỡ chữ và khoảng cách dòng mặc định cho tất cả các đoạn văn.

---

### **Chủ đề 3: Màu sắc & Nền (Colors & Backgrounds)**

#### 1. Khái niệm

Đây là nhóm thuộc tính giúp thổi hồn vào trang web, làm cho nó trở nên sống động và có cảm xúc. Bạn có thể thay đổi màu của chữ, màu nền của một khối, hoặc thậm chí dùng hình ảnh làm nền.

#### 2. Các thuộc tính quan trọng

- `color`: Quy định màu của văn bản.
- `background-color`: Quy định màu nền cho một phần tử.
- `background-image`: Đặt một hình ảnh làm nền. Giá trị thường là `url('duong_dan_den_anh.jpg')`.
- `background-size`: Kiểm soát kích thước của ảnh nền. Giá trị `cover` rất phổ biến, giúp ảnh lấp đầy phần tử mà không bị méo.
- `background-position`: Căn vị trí của ảnh nền (ví dụ: `center`).
- `background-repeat`: Quy định ảnh nền có lặp lại hay không (ví dụ: `no-repeat`).

**Các hệ màu:**

- **Tên màu (Keywords):** `red`, `blue`, `black`... (dễ dùng nhưng hạn chế).
- **HEX:** `#RRGGBB` (ví dụ: `#FFFFFF` là màu trắng). Đây là hệ màu phổ biến nhất.
- **RGB:** `rgb(red, green, blue)` (ví dụ: `rgb(255, 0, 0)` là màu đỏ).
- **RGBA:** Giống RGB nhưng có thêm kênh Alpha (độ trong suốt), từ 0 (trong suốt) đến 1 (không trong suốt). Ví dụ: `rgba(0, 0, 0, 0.5)` là màu đen bán trong suốt.

#### 3. Ví dụ minh họa

**HTML (`index.html`)**

```html
<div class="promo-banner">
  <h1>Ưu đãi đặc biệt!</h1>
  <p>Giảm giá 50% cho tất cả sản phẩm.</p>
</div>
```

**CSS (`style.css`)**

```css
.promo-banner {
  background-image: url("banner-image.jpg");
  background-size: cover;
  background-position: center;

  /* Lớp phủ màu đen bán trong suốt để chữ dễ đọc hơn */
  background-color: rgba(0, 0, 0, 0.4);
  background-blend-mode: multiply; /* Kỹ thuật nâng cao để trộn màu nền và ảnh nền */

  color: #ffffff; /* Màu chữ trắng */
  text-align: center;
}
```

#### 4. Lỗi phổ biến của người mới

- **Đường dẫn ảnh sai** trong `url()`.
- **Văn bản khó đọc** vì màu chữ và màu nền/ảnh nền có độ tương phản thấp.
- **Ảnh nền bị lặp lại** ngoài ý muốn (do giá trị mặc định của `background-repeat` là `repeat`).
- Quên dấu ngoặc đơn hoặc dấu nháy trong `url()`.

#### 5. Áp dụng thực tế

- Tạo các **banner quảng cáo** với ảnh nền bắt mắt.
- Tạo các **thẻ sản phẩm (card)** có màu nền riêng biệt.
- Làm nổi bật một đoạn văn bản quan trọng bằng cách thay đổi `background-color` của nó.

---

### **Chủ đề 4: Typography (Kiểu chữ)**

#### 1. Khái niệm

Typography là nghệ thuật và kỹ thuật sắp xếp chữ viết sao cho dễ đọc, dễ hiểu và hấp dẫn về mặt thị giác. Trong web, typography quyết định "giọng nói" của trang web: nó trang trọng, vui tươi, hay hiện đại?

#### 2. Các thuộc tính quan trọng

- `font-family`: Chọn font chữ. Bạn nên cung cấp một danh sách các font (font stack), bắt đầu bằng font bạn muốn và kết thúc bằng một font chung (ví dụ: `sans-serif`) để phòng trường hợp font đầu tiên không có sẵn trên máy người dùng.
- `font-size`: Kích thước của chữ (ví dụ: `16px`, `1.2rem`).
- `font-weight`: Độ đậm của chữ (`normal`, `bold`, hoặc các giá trị số như `400`, `700`).
- `font-style`: Kiểu chữ, phổ biến nhất là `italic` (in nghiêng).
- `text-align`: Căn lề cho văn bản (`left`, `right`, `center`, `justify`).
- `line-height`: Khoảng cách giữa các dòng văn bản. Đây là thuộc tính cực kỳ quan trọng để cải thiện khả năng đọc.
- `text-decoration`: Thêm hoặc bỏ các đường trang trí như gạch chân (`underline`). Rất hay dùng để bỏ gạch chân mặc định của thẻ `<a>`.

#### 3. Ví dụ minh họa

**HTML (`index.html`)**

```html
<article>
  <h1>Cách học CSS hiệu quả</h1>
  <p>
    Để học tốt CSS, bạn cần nắm vững nền tảng và thực hành liên tục. Khoảng cách
    dòng hợp lý sẽ giúp người đọc dễ theo dõi hơn.
  </p>
  <a href="#">Đọc thêm</a>
</article>
```

**CSS (`style.css`)**

```css
/* Thiết lập font chữ chung cho toàn bộ trang */
body {
  font-family: "Helvetica Neue", Arial, sans-serif;
}

h1 {
  font-size: 32px;
  font-weight: 700; /* Tương đương bold */
}

p {
  font-size: 16px;
  line-height: 1.6; /* Gấp 1.6 lần cỡ chữ, không có đơn vị */
}

a {
  color: #007bff;
  text-decoration: none; /* Bỏ gạch chân mặc định */
}
```

#### 4. Lỗi phổ biến của người mới

- **Tên font có khoảng trắng nhưng không đặt trong dấu nháy kép**: `font-family: Times New Roman;` (sai) -> `font-family: "Times New Roman";` (đúng).
- **`line-height` quá thấp**: Khiến các dòng chữ dính vào nhau, rất khó đọc.
- **Quên không bỏ gạch chân** cho các link trong menu điều hướng, làm mất thẩm mỹ.
- Sử dụng quá nhiều font chữ khác nhau trên một trang, gây rối mắt.

#### 5. Áp dụng thực tế

- Định dạng **tiêu đề bài viết** to, đậm để thu hút sự chú ý.
- Tăng `line-height` cho các **khối văn bản dài** (bài blog, mô tả sản phẩm) để người dùng không bị mỏi mắt.
- Tạo phong cách riêng cho các **đường link** để người dùng biết đó là yếu tố có thể tương tác.

---
