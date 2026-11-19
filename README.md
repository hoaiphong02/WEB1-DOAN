# 🛍️ ĐỒ ÁN MÔN HỌC: WEBSITE BÁN HÀNG THỜI TRANG (SHOPCLOTH)

## 📁 CẤU TRÚC THƯ MỤC & CÁC TỆP TIN TRONG DỰ ÁN

```text
WEB1-DOAN/
│
├── admin/                           # Khu vực dành riêng cho Quản trị viên
│   ├── index.html                   # Bảng điều khiển tổng quan (Dashboard thống kê)
│   ├── login.html                   # Trang đăng nhập dành cho Quản trị viên
│   ├── products.html                # Quản lý danh sách sản phẩm (CRUD sản phẩm, tồn kho)
│   ├── orders.html                  # Quản lý đơn hàng (xem, lọc, duyệt trạng thái đơn)
│   ├── order-detail.html            # Trang chi tiết đơn hàng quản trị (in hóa đơn, cập nhật)
│   └── users.html                   # Quản lý tài khoản người dùng và phân quyền
│
├── css/                             # Thư mục chứa mã nguồn định kiểu giao diện
│   ├── style.css                    # Toàn bộ CSS giao diện khách hàng (Modern Dark Theme)
│   └── admin.css                    # Toàn bộ CSS giao diện trang quản trị Admin
│
├── js/                              # Thư mục chứa mã nguồn xử lý logic JavaScript
│   ├── main.js                      # Xử lý logic phía khách hàng (giỏ hàng, đặt hàng, lọc, phân trang)
│   ├── admin.js                     # Xử lý logic các chức năng bên trong Admin Portal
│   └── products.js                  # Cơ sở dữ liệu mẫu & API lưu trữ sản phẩm cho Admin
│
├── images/                          # Thư mục tài nguyên hình ảnh sản phẩm & icon
│   ├── logo-cat.png                 # Logo biểu tượng thương hiệu
│   ├── product-jacket-black.png     # Ảnh sản phẩm: Áo khoác da lộn đen
│   ├── product-jacket-brown.png     # Ảnh sản phẩm: Áo bomber da bò nâu
│   ├── product-jacket-grey.png      # Ảnh sản phẩm: Áo khoác nỉ xám khói
│   ├── product-jacket-windbreaker.png # Ảnh sản phẩm: Áo khoác gió 2 lớp
│   ├── product-pant-baggy.png       # Ảnh sản phẩm: Quần tây Baggy công sở
│   ├── product-pant-jean.png        # Ảnh sản phẩm: Quần Jean Slimfit co giãn
│   ├── product-pant-khaki.png       # Ảnh sản phẩm: Quần Khaki túi hộp
│   ├── product-shirt-oxford.png     # Ảnh sản phẩm: Áo sơ mi Oxford
│   ├── product-shirt-polo.png       # Ảnh sản phẩm: Áo Polo nam phối cổ
│   └── product-shirt-tshirt.png     # Ảnh sản phẩm: Áo thun Cotton basic
│
├── index.html                       # Trang chủ dành cho khách (chưa đăng nhập)
├── logged-index.html                # Trang chủ sau khi khách hàng đã đăng nhập thành công
├── product-detail.html              # Trang chi tiết sản phẩm (chọn số lượng, thêm giỏ hàng)
├── cart.html                        # Trang giỏ hàng (tăng/giảm số lượng, xóa món, tính tổng tiền)
├── checkout.html                    # Trang đặt hàng & nhập thông tin thanh toán (COD / Chuyển khoản)
├── success.html                     # Trang thông báo đặt hàng thành công
├── order-detail.html                # Trang chi tiết đơn hàng riêng biệt phía khách hàng (không popup)
├── account.html                     # Trang quản lý tài khoản & lịch sử đơn hàng của khách
├── log-in.html                      # Trang đăng nhập riêng biệt
├── register.html                    # Trang đăng ký tài khoản mới riêng biệt
├── history.html                     # Trang xem lịch sử các đơn hàng đã mua
└── README.md                        # Tài liệu hướng dẫn và mô tả dự án
```

---

## 🌟 DANH SÁCH CHỨC NĂNG CHI TIẾT

### 1. Phân hệ Khách hàng (Storefront)
- **Duyệt & Tìm kiếm sản phẩm (`index.html`, `logged-index.html`):**
  - Thanh bộ lọc ngang hiện đại ở đầu trang: tìm kiếm nhanh theo tên sản phẩm theo thời gian thực.
  - Lọc sản phẩm theo danh mục (`Áo khoác`, `Áo sơ mi/Thun`, `Quần Jean/Khaki`).
  - Lọc sản phẩm theo khoảng giá tùy chỉnh (Giá từ - Giá đến).
  - Phân trang hiển thị sản phẩm linh hoạt.
- **Xem chi tiết sản phẩm (`product-detail.html`):**
  - Hiển thị hình ảnh kích thước lớn, thông tin mô tả chi tiết, giá tiền.
  - Tùy chỉnh số lượng mua và thêm sản phẩm vào giỏ hàng.
- **Quản lý giỏ hàng (`cart.html`):**
  - Thêm, bớt số lượng hoặc xóa từng mặt hàng trong giỏ.
  - Tự động cập nhật số lượng badge giỏ hàng trên Header.
  - Tự động tính toán tạm tính và tổng thanh toán.
- **Đặt hàng & Thanh toán (`checkout.html`, `success.html`):**
  - Nhập thông tin người nhận hàng: Họ tên, số điện thoại, địa chỉ, ghi chú.
  - Lựa chọn phương thức thanh toán (COD hoặc chuyển khoản qua ngân hàng).
  - Tự động sinh mã đơn hàng (dạng `ORD-XXXX`), đồng bộ đơn hàng trực tiếp sang hệ thống của Admin.
- **Trang chi tiết đơn hàng khách hàng (`order-detail.html`):**
  - Là **1 trang HTML độc lập (hoàn toàn không dùng popup)** theo đúng yêu cầu.
  - Xem lại chi tiết từng sản phẩm, số lượng, đơn giá, tổng tiền và trạng thái giao hàng.
- **Đăng ký & Đăng nhập (`account.html`, `log-in.html`, `register.html`):**
  - Đã loại bỏ toàn bộ các ràng buộc nhập liệu phức tạp (bấm là đăng nhập/đăng ký thành công ngay).
  - Hiển thị Avatar người dùng và tên viết tắt ở góc Header khi đã đăng nhập.
  - Quản lý lịch sử đơn hàng và chức năng Đăng xuất.

### 2. Phân hệ Quản trị (Admin Portal)
- **Menu điều hướng:** Được tích hợp thông qua nút 3 gạch (☰) ở góc Header trang chính dẫn vào `admin/login.html`.
- **Dashboard (`admin/index.html`):** Thống kê tổng số doanh thu, đơn hàng, sản phẩm và khách hàng.
- **Quản lý sản phẩm (`admin/products.html`):**
  - Hiển thị bảng danh sách sản phẩm với hình ảnh, giá bán, giá cũ và số lượng tồn kho.
  - Tìm kiếm, lọc sản phẩm theo danh mục, thêm mới, sửa thông tin và xóa sản phẩm.
- **Quản lý đơn hàng (`admin/orders.html`):**
  - Xem danh sách toàn bộ các đơn hàng do khách đặt từ trang chủ.
  - Bộ lọc đơn hàng theo trạng thái: *Chưa xác nhận, Đã xác nhận, Đang giao, Đã giao, Hủy đơn*.
  - Thay đổi trạng thái xử lý đơn hàng.
- **Trang chi tiết đơn hàng Admin (`admin/order-detail.html`):**
  - Là 1 trang HTML riêng biệt dành cho Admin để xem chi tiết đơn, thông tin giao hàng và in hóa đơn.
- **Quản lý người dùng (`admin/users.html`):**
  - Danh sách tài khoản khách hàng, khóa/mở khóa tài khoản, phân quyền.

