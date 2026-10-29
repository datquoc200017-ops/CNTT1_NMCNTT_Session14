**# Bài Tập Về Nhà
## Bài 9: Tự Thiết Kế Hệ Thống Lưu Trữ và Phân Quyền Cho Dự Án CampusPay
### Bài Làm
## Phần 1: Phân tích bài toán

### 1. Đầu vào và Đầu ra

-   **Đầu vào:**
    
    -   **4 vai trò:** Ban Kỹ thuật, Ban Thiết kế, Ban Kinh doanh, Nhà đầu tư.
        
    -   **5 loại tài liệu:** Code & API Keys, Thiết kế UI & Đồ họa, Dữ liệu khách hàng & Đối tác, Business Plan, Slide Pitch.
        
-   **Đầu ra:**
    
    -   Cấu trúc thư mục Google Drive 2 cấp.
        
    -   Bảng phân quyền 6 cột theo nguyên tắc tối thiểu quyền.
        
    -   Giải pháp xử lý 3 bẫy dữ liệu.
        

### 2. Cấu trúc thư mục Google Drive 2 cấp

Lưu trực tiếp bằng Google Docs/Sheets/Slides trên Cloud để giữ lịch sử phiên bản trên 30 ngày:

Plaintext

```
📁 CampusPay_Project - Cấp 1: Thư mục dự án
 ├── 📁 01_KyThuat - Cấp 2: Chứa tài liệu test API, cấu hình và API Keys.
 ├── 📁 02_ThietKe - Cấp 2: Chứa file thiết kế UI và tài sản đồ họa.
 ├── 📁 03_KinhDoanh - Cấp 2: Chứa danh sách đối tác và dữ liệu khách hàng.
 ├── 📁 04_TaiLieuChung - Cấp 2: Chứa Business Plan và Business Summary làm chung.
 └── 📁 05_NhaDauTu - Cấp 2: Chứa bản đọc Business Plan và file PDF Slide Pitch.

```

### 3. Các bước cấu hình hệ thống

-   **Bước 1 — Tạo thư mục:** Tạo thư mục gốc `CampusPay_Project` và 5 thư mục con.
    
-   **Bước 2 — Đặt tên:** Đặt tên theo số thứ tự và tên bộ phận để dễ quản lý.
    
-   **Bước 3 — Cấp quyền:** Chuyển tất cả về chế độ Restricted, thêm đúng email từng thành viên vào thư mục tương ứng, thiết lập hạn truy cập 14 ngày cho Nhà đầu tư.
    
-   **Bước 4 — Kiểm tra:** Rà soát mục Quản lý quyền truy cập để đảm bảo không có link nào mở công khai.
    
-   **Bước 5 — Thu hồi / Cập nhật:** Xóa quyền ngay khi có thành viên nghỉ việc hoặc hết hạn hợp tác.
    

## Phần 2: Triển khai & Chống lỗi

### 4. Bảng phân quyền

Loại tài liệu

Ban KT

Ban TK

Ban KD

Nhà đầu tư

Ghi chú bảo mật

**1. Code, API & API Keys**

Editor

Không có quyền

Không có quyền

Không có quyền

Restricted. Tắt quyền tải, in, sao chép và chia sẻ lại.

**2. Thiết kế UI & Đồ họa**

Viewer

Editor

Không có quyền

Không có quyền

Restricted. Ban KT chỉ xem và tải hình ảnh để code giao diện.

**3. Dữ liệu khách hàng & Đối tác**

Không có quyền

Không có quyền

Editor

Không có quyền

Restricted. Dữ liệu nhạy cảm, tắt quyền tải, in, sao chép.

**4. Business Plan**

Viewer

Viewer

Editor

Viewer

Restricted. Tắt tải, in, sao chép. Nhà đầu tư hết hạn sau 14 ngày.

**5. Slide Pitch bản PDF**

Viewer

Editor

Editor

Viewer

Xuất file PDF riêng cho Nhà đầu tư, cho phép tải, hết hạn sau 14 ngày.

### 5. Trả lời 3 bẫy dữ liệu

-   **Bẫy 1: Chia sẻ Business Plan cho Ban Kỹ thuật đọc nhưng không cho sửa**
    
    -   **Quyền cấp:** Viewer hoặc Commenter trực tiếp trên file Business Plan.
        
    -   **Tính năng tắt:** Tắt tính năng cho phép người xem tải xuống, in và sao chép.
        
    -   **Lý do:** Giúp Ban Kỹ thuật đọc hiểu nghiệp vụ nhưng không thể chỉnh sửa nội dung gốc hay tải file mật về máy.
        
-   **Bẫy 2: Nhà đầu tư muốn tải PDF Slide Pitch nhưng không được sửa**
    
    -   **Quyền cấp:** Xuất Slide Pitch ra file PDF riêng, cấp quyền Viewer cho Nhà đầu tư kèm thời hạn 14 ngày.
        
    -   **Tính năng bật/tắt:** Không tắt tính năng _"Viewers can download"_ trên file PDF này, nhưng tắt trên file Slide gốc.
        
    -   **Lý do:** File PDF không thể chỉnh sửa như file gốc nên an toàn để tải về trình chiếu offline. Nếu tắt tính năng tải xuống, Nhà đầu tư sẽ không tải được file PDF.
        
-   **Bẫy 3: Thành viên nghỉ việc cần chặn truy cập ngay lập tức**
    
    -   **Thao tác:** Xóa email người đó khỏi toàn bộ thư mục dự án, chuyển quyền sở hữu các file họ đã tạo sang cho Trưởng nhóm, đồng thời đổi mới toàn bộ API Keys và mật khẩu hệ thống.
