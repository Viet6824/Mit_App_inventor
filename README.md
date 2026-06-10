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

### Viewer (Màn hình mô phỏng)

Hiển thị giao diện điện thoại, cho phép kéo thả và sắp xếp các thành phần trực quan.

### Components (Danh sách linh kiện)

Quản lý toàn bộ các thành phần đã sử dụng dưới dạng cây phân cấp.

Cho phép:

* Đổi tên linh kiện (Rename)
* Xóa linh kiện
* Sắp xếp thứ tự hiển thị

### Properties (Thuộc tính)

Dùng để thay đổi:

* Kích thước
* Màu sắc
* Font chữ
* Căn lề
* Nội dung hiển thị

---

## 2. Kéo thả linh kiện và thay đổi thuộc tính

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

> Chèn ảnh Designer của Screen1 tại đây.

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

> Chèn ảnh Blocks Screen1 tại đây.
