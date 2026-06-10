# BÁO CÁO BÀI TẬP LỚN

# XÂY DỰNG ỨNG DỤNG DI ĐỘNG ĐA MÀN HÌNH TRÊN NỀN TẢNG MIT APP INVENTOR

---

# PHẦN I: TỔNG QUAN VỀ CÔNG CỤ VÀ QUY TRÌNH PHÁT TRIỂN

Quy trình phát triển một ứng dụng trên MIT App Inventor gồm ba giai đoạn chính:

```text
Thiết kế giao diện (Designer)
            ↓
Lập trình logic (Blocks)
            ↓
Kiểm thử và đóng gói ứng dụng (Build)
```

## 1. Cấu trúc giao diện Designer

Giao diện làm việc chính của MIT App Inventor được chia thành bốn khu vực:

### Palette (Bảng linh kiện)

Chứa toàn bộ các thành phần được phân loại theo từng nhóm:

* User Interface
* Layout
* Media
* Connectivity
* Sensors
* Drawing and Animation

Đây là nơi cung cấp các thành phần để xây dựng ứng dụng.

<img width="388" height="835" alt="image" src="https://github.com/user-attachments/assets/8aa780fa-7df1-47f0-920a-bf0ac03e9ccf" />

### Viewer (Màn hình mô phỏng)

<img width="420" height="674" alt="image" src="https://github.com/user-attachments/assets/22221816-c9c4-4a69-82d1-7e4f0545cbf4" />

Hiển thị giao diện điện thoại, cho phép kéo thả và sắp xếp các thành phần trực quan.

### Components (Danh sách linh kiện)

<img width="271" height="696" alt="image" src="https://github.com/user-attachments/assets/d6745226-3d85-471d-b978-6c77c0cfc0f8" />

Quản lý toàn bộ các thành phần đã sử dụng dưới dạng cây phân cấp.

Cho phép:

* Đổi tên linh kiện (Rename)
* Xóa linh kiện
* Sắp xếp thứ tự hiển thị

### Properties (Thuộc tính)

<img width="264" height="649" alt="image" src="https://github.com/user-attachments/assets/6b83e40e-a44e-4d2e-85a2-a8fe261add23" />

Dùng để thay đổi:

* Kích thước
* Màu sắc
* Font chữ
* Căn lề
* Nội dung hiển thị

---

## 2. Kéo thả linh kiện và thay đổi thuộc tính

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3e890870-a064-4fad-bc27-0206fddfd3a2" />

### Cách thực hiện

* Chọn linh kiện từ mục Palette.
* Kéo vào khu vực Viewer.
* Chọn linh kiện vừa tạo.
* Điều chỉnh các thuộc tính trong bảng Properties.

### Mục đích

#### Xây dựng giao diện người dùng (UI)

Thiết kế bố cục trực quan mà không cần viết mã XML hay HTML/CSS.

#### Thiết lập trạng thái ban đầu

Ví dụ:

* Width = Fill Parent
* Height = Automatic
* Visible = False
* NumbersOnly = True

Những thuộc tính này giúp đơn giản hóa quá trình xử lý logic sau này.

---

# PHẦN II: BẢN CHẤT CỦA CÔNG NGHỆ LẬP TRÌNH KHỐI

## 1. Bản chất của việc kéo thả Block

MIT App Inventor sử dụng phương pháp lập trình trực quan (Visual Programming) dựa trên sự kiện (Event-Driven Programming).

Các khối lệnh đại diện cho:

* Biến
* Toán học
* Điều kiện
* Văn bản
* Vòng lặp
* Danh sách

<img width="277" height="642" alt="image" src="https://github.com/user-attachments/assets/10a09e89-0a86-4568-bf05-a71bdb6c4d06" />

Các block hoạt động giống như những mảnh ghép Lego.

Hệ thống sẽ không cho phép ghép sai kiểu dữ liệu, giúp hạn chế lỗi cú pháp.

---

## 2. Ưu điểm và nhược điểm

| Tiêu chí   | Lập trình khối            | Viết code truyền thống            |
| ---------- | ------------------------- | --------------------------------- |
| Ưu điểm    | Không xảy ra lỗi cú pháp  | Hiệu năng cao                     |
|            | Trực quan hóa luồng xử lý | Linh hoạt hơn                     |
|            | Dễ tiếp cận cho người mới | Có thể can thiệp sâu vào hệ thống |
| Nhược điểm | Khó quản lý dự án lớn     | Đòi hỏi ghi nhớ cú pháp           |
|            | Giới hạn tính năng        | Dễ phát sinh lỗi cú pháp          |

---

## 3. Sao chép khối lệnh bằng Backpack

MIT App Inventor cung cấp công cụ Backpack để tái sử dụng block giữa các màn hình.

### Lưu block vào Backpack

```text
Kéo block
     ↓
Thả vào biểu tượng Backpack
     ↓
Block được lưu lại
```

### Sử dụng lại block

```text
Chuyển sang Screen khác
      ↓
Mở Backpack
      ↓
Kéo block ra vùng làm việc
```

---

# PHẦN III: THIẾT KẾ VÀ LẬP TRÌNH ỨNG DỤNG

Ứng dụng gồm ba màn hình:

1. Screen1 – Giới thiệu bản thân và điều hướng.
2. Screen2 – Giải phương trình bậc nhất.
3. Screen3 – Hiển thị Website bằng WebViewer.

---

# MÀN HÌNH 1: ABOUT ME VÀ ĐIỀU HƯỚNG

## 1. Thiết kế giao diện (Designer)

### Cấu hình Screen1

```text
Title = Trang Chủ - Giới Thiệu
AlignHorizontal = Center
```

### Các thành phần sử dụng

#### Label

Tên:

```text
Lbl_ThongTin
```

Hiển thị:

* Họ tên
* MSSV
* Lớp

Thuộc tính:

```text
FontSize = 20
FontBold = True
```

#### Button chuyển màn hình

Nút thứ nhất:

```text
Btn_ToScreen2
Text = Giải Toán Bậc Nhất
```

Nút thứ hai:

```text
Btn_ToScreen3
Text = Xem Website
```

<img width="1919" height="915" alt="image" src="https://github.com/user-attachments/assets/6b1a86e3-62f3-4aa5-be72-92868bd72d3e" />

---



## 2. Khối lệnh (Blocks)

Sử dụng sự kiện:

```text
when Btn_ToScreen2.Click
```

Gọi:

```text
open another screen with screenName
```

Truyền vào:

```text
"Screen2"
```

Tương tự đối với:

```text
Btn_ToScreen3
```

với:

```text
"Screen3"
```

<img width="1919" height="931" alt="image" src="https://github.com/user-attachments/assets/539794de-afeb-41b1-9f0f-2b0b49c3be5d" />

# MÀN HÌNH 2: GIẢI PHƯƠNG TRÌNH BẬC NHẤT

## 1. Thiết kế giao diện (Designer)

Screen2 được xây dựng để giải phương trình bậc nhất dạng:

[
ax+b=0
]

### Cấu hình Screen2

```text
Title = Giải Phương Trình Bậc Nhất
```

### Nhập hệ số a

Kéo một `HorizontalArrangement`, bên trong gồm:

* Label

```text
Text = Nhập a:
```

* TextBox

```text
Tên: Txt_A
NumbersOnly = True
```

### Nhập hệ số b

Kéo một `HorizontalArrangement` thứ hai, bên trong gồm:

* Label

```text
Text = Nhập b:
```

* TextBox

```text
Tên: Txt_B
NumbersOnly = True
```

### Nút tính toán

```text
Tên: Btn_Tinh
Text = Tính nghiệm
```

### Hiển thị kết quả

Label:

```text
Tên: Lbl_KetQua
Text = ""
TextColor = Red
```

### Nút quay lại

Button:

```text
Tên: Btn_Back
Text = Quay lại
```

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ae9f0331-c771-4103-9b5b-90d1fcedb369" />

---

## 2. Khối lệnh (Blocks)

Ứng dụng thực hiện biện luận phương trình:

[
ax+b=0
]

Theo các trường hợp:

* Nếu a = 0 và b = 0 → Phương trình vô số nghiệm.
* Nếu a = 0 và b ≠ 0 → Phương trình vô nghiệm.
* Nếu a ≠ 0 → Phương trình có nghiệm:

[
x=\frac{-b}{a}
]

### Thuật toán

```text
Nếu a = 0
    Nếu b = 0
        Vô số nghiệm
    Ngược lại
        Vô nghiệm
Ngược lại
    x = -b/a
```

### Cấu trúc khối lệnh

Sử dụng:

* if then else
* toán tử "="
* phép chia "/"
* phép nhân "*"
* khối join của Text

Ví dụ kết quả:

```text
Nghiệm x = 2
```

được tạo bằng cách nối:

```text
"Nghiệm x = "
+
(-1 × b)/a
```

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/17360811-9d2b-469f-898c-ba6328057d23" />

---

# MÀN HÌNH 3: HIỂN THỊ WEBSITE BẰNG WEBVIEWER

## 1. Thiết kế giao diện (Designer)

Screen3 dùng để hiển thị một trang web trực tiếp trên điện thoại.

### Thêm WebViewer

Từ nhóm User Interface kéo linh kiện:

```text
WebViewer
```

Thiết lập:

```text
Width = Fill Parent
Height = Fill Parent
```

### Cấu hình HomeUrl

Ví dụ:

```text
https://en.m.wikipedia.org
```

Khi mở Screen3, trang web sẽ được tải tự động.

### Nút quay lại

Button:

```text
Tên: Btn_Back
Text = Quay lại
```

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/509e5f2e-cb7c-4d8f-ae1e-57d510dac765" />

---

## 2. Khối lệnh (Blocks)

Sự kiện:

```text
when Btn_Back.Click
```

gọi:

```text
close screen
```

hoặc:

```text
open another screen with screenName
```

và truyền:

```text
"Screen1"
```

Linh kiện WebViewer không cần lập trình thêm khối lệnh để tải trang vì URL đã được khai báo trong thuộc tính `HomeUrl`.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b4ed32b8-a861-47f0-91fd-bac5a2354b0a" />

---

# PHẦN IV: ĐÁNH GIÁ VÀ KẾT LUẬN

## 1. Kết quả

### Screen 1:
<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/344b1888-c436-4837-8b00-248a5b864b08" />

### Screen 2:
<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/5ebea19e-1d0b-4349-99f7-ceb0ca5bb8fa" />

### Screen 3:
<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/34bfde7e-cfd7-4de5-91c5-e651e2e9cbf4" />

## 2. Kết quả đạt được

Sau khi hoàn thành bài tập lớn, ứng dụng đã đáp ứng được các yêu cầu đặt ra:

* Xây dựng thành công ứng dụng gồm ba màn hình độc lập.
* Chuyển đổi giữa các màn hình ổn định.
* Giải chính xác phương trình bậc nhất với đầy đủ các trường hợp đặc biệt.
* Hiển thị được trang web trực tiếp thông qua WebViewer.
* Giao diện đơn giản, trực quan và dễ sử dụng.

---

## 3. Kết luận

Thông qua bài tập lớn này, có thể thấy MIT App Inventor là một công cụ phù hợp cho việc học và phát triển ứng dụng di động ở mức cơ bản. Cơ chế kéo thả giao diện kết hợp với lập trình khối giúp giảm đáng kể độ phức tạp của cú pháp, đồng thời hỗ trợ người học tập trung vào tư duy thuật toán và thiết kế ứng dụng. Qua quá trình thực hiện, người học đã nắm được quy trình xây dựng một ứng dụng đa màn hình hoàn chỉnh, từ thiết kế giao diện, xử lý sự kiện đến kiểm thử và đóng gói sản phẩm.
