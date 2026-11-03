# GIẢI PHÁP QUẢN TRỊ ĐA PROFILE VÀ BẢO MẬT TRÌNH DUYỆT — GREENLOGISTICS



## PHẦN 1. PHÂN TÍCH: INCOGNITO MODE VÀ DEDICATED PROFILE

| Tiêu chí | Incognito Mode (Chế độ Ẩn danh) | Dedicated Profile (Profile riêng biệt) |
| --- | --- | --- |
| **Bản chất lưu trữ trạng thái** | **Tạm thời trên RAM / Bộ nhớ biến động:** Không lưu vết dữ liệu vào ổ cứng sau khi đóng cửa sổ. | **Lâu dài trên ổ cứng (Persistent):** Lưu trữ trong một thư mục định danh riêng (`User Data Directory`) trên thiết bị. |
| **Khả năng lưu giữ Bookmark / Tiện ích** | Không lưu giữ (mọi bookmark, extension hay cài đặt cá nhân sẽ biến mất hoàn toàn khi tắt cửa sổ). | Lưu trữ vĩnh viễn, ổn định qua các lần khởi động lại máy hoặc đóng/mở trình duyệt. |
| **Mục đích sử dụng tối ưu** | Kiểm tra nhanh, tra cứu thông tin tạm thời hoặc đăng nhập một lần không để lại lịch sử trên máy lạ. | Phục vụ công việc lâu dài, duy trì các phiên đăng nhập ổn định, đồng bộ hóa tài nguyên cá nhân/công việc. |

---

## PHẦN 2. TRIỂN KHAI: QUY TRÌNH TẠO PROFILE VÀ ĐỒNG BỘ CLOUD SYNC

Để thiết lập mô hình 3 Profile (`Personal`, `GreenLog Work`, `Sandbox`) và đảm bảo tài nguyên không bị mất khi đổi máy tính, thực hiện theo quy trình chuẩn:

### 1. Quy trình tạo các Dedicated Profile độc lập

1. Mở trình duyệt Chrome, nhấp vào **biểu tượng Profile** ở góc trên cùng bên phải.
2. Chọn **Thêm (Add)** ở cuối menu thả xuống.
3. Nhọn **Đăng nhập** (nếu muốn gắn với tài khoản Google) hoặc chọn **Tiếp tục mà không cần tài khoản** (đối với Sandbox).
4. Đặt tên Profile rõ ràng (Ví dụ: `GreenLog_Work`) và chọn màu sắc chủ đạo (Theme) để phân biệt trực quan, tránh nhầm lẫn khi thao tác.

### 2. Thiết lập Đồng bộ hóa Cloud Sync bảo vệ Bookmark

1. Truy cập vào Profile cần đồng bộ (`GreenLog Work`).
2. Vào **Cài đặt (Settings)** > Chọn **Bạn và Google (You and Google)**.
3. Bật tính năng **Đồng bộ hóa (Turn on sync)** bằng tài khoản email công ty.
4. Tùy chỉnh chọn đồng bộ các mục quan trọng: **Dấu trang (Bookmarks)**, **Mật khẩu (Passwords)**, và **Tiện ích (Extensions)**.
*Lợi ích:* Khi đổi sang máy tính mới, chỉ cần đăng nhập lại tài khoản công ty trên Profile tương ứng, toàn bộ cây thư mục Bookmark và cấu hình sẽ tự động kéo về mà không sợ thất lạc.

---

## PHẦN 3. KIỂM THỬ: QUY TẮC SỬ DỤNG GUEST PROFILE TRÊN MÁY TÍNH CÔNG CỘNG

Khi làm việc hoặc mượn tạm máy tính công cộng / thiết bị dùng chung, việc sử dụng **Guest Profile (Khách)** thay vì tài khoản cá nhân tuân thủ các quy tắc bảo mật nghiêm ngặt sau:

1. **Luôn sử dụng tùy chọn "Browse as guest" (Duyệt với tư cách khách):**
* *Cơ chế:* Chế độ khách tạo ra một không gian hoàn toàn cách ly, không có quyền truy cập vào bất kỳ Profile cá nhân nào khác đang có trên máy, đồng thời ẩn đi lịch sử và dữ liệu của các người dùng trước đó.


2. **Cơ chế tự hủy dữ liệu:**
* Ngay khi đóng cửa sổ Guest Profile, toàn bộ lịch sử duyệt web, cookie, tệp tải xuống và các phiên đăng nhập sẽ **tự động bị xóa sạch hoàn toàn**, không để lại bất kỳ dấu vết rác hay rò rỉ thông tin nào.


3. **Cảnh báo an toàn tuyệt đối:**
* Tuyệt đối **không đăng nhập tài khoản Google cá nhân** hay bật tính năng Cloud Sync trên máy tính công cộng. Việc này nhằm ngăn chặn nguy cơ lưu trữ mật khẩu, thông tin nhạy cảm hoặc đồng bộ nhầm dữ liệu cá nhân lên thiết bị không đáng tin cậy.