# BÀI TẬP VỀ NHÀ - PHẠM QUỐC ĐẠT
## Phần 1 – Thiết lập Hybrid Workflow

### 1. Đánh giá sự cố mất file khi hỏng ổ cứng

-   **Sự cố có xảy ra không:** Không xảy ra.
    
-   **Lý do:** Với Hybrid Workflow kết hợp Auto Sync, ngay khi thành viên lưu file trên máy tính cá nhân, phần mềm đồng bộ đã tự động đẩy bản cập nhật mới nhất lên Cloud theo thời gian thực. Khi hỏng ổ cứng, nhóm chỉ cần đăng nhập Cloud tải lại file.
    

### 2. Ba bước thiết lập Auto Sync cho cả nhóm

1.  **Cài đặt ứng dụng:** Tải và cài đặt Google Drive for Desktop hoặc OneDrive lên máy tính, đăng nhập tài khoản email nhóm.
    
2.  **Tạo và chọn thư mục đồng bộ:** Tạo thư mục `SmartCampus_Project` trên ổ cứng máy tính, vào phần cài đặt ứng dụng chọn `Add folder` và tích chọn chế độ `Sync with Google Drive`.
    
3.  **Kiểm tra trạng thái:** Lưu thử 1 file vào thư mục và kiểm tra biểu tượng dấu tích xanh xuất hiện cạnh tên file để xác nhận đồng bộ tự động thành công.
    

### 3. Thao tác khôi phục 2 trang báo cáo bị xóa nhầm

-   Mở file `BaoCao_CuoiKy_SmartCampus.docx` trên Cloud -> Chọn menu `File` -> Chọn `Version history` -> Chọn `See version history` -> Tìm phiên bản cách đây hơn 10 phút trước khi bị xóa -> Nhấn `Restore this version`.
    

### 4. Hai sai lầm khi đồng bộ và cách xử lý

-   **Sai lầm 1:** Đồng bộ thư mục `node_modules` chứa hàng vạn file hệ thống nhỏ gây nghẽn tiến trình Auto Sync và treo máy.
    
    -   **Cách xử lý:** Đưa `node_modules` vào danh sách loại trừ đồng bộ hoặc chỉ đẩy file `package.json` lên GitHub.
        
-   **Sai lầm 2:** Đồng bộ file giải trí cá nhân dung lượng lớn như phim 4K làm đầy bộ nhớ Cloud của nhóm và tốn băng thông mạng.
    
    -   **Cách xử lý:** Xóa hoặc di chuyển toàn bộ file phim 4K ra thư mục cá nhân bên ngoài thư mục dự án `SmartCampus_Project`.
        

## Phần 2 – Phân quyền chia sẻ an toàn

### 1. Bảng phân quyền chia sẻ

**File**

**Mức quyền**

**Phạm vi chia sẻ**

**Giải thích**

**BaoCao_CuoiKy_SmartCampus.docx gửi giảng viên**

Viewer

Restricted

Giảng viên chỉ cần đọc để chấm điểm, tránh thao tác gõ nhầm làm thay đổi nội dung báo cáo.

**Slide_BaoCao.pptx cho 5 thành viên nhóm**

Editor

Restricted

Cả 5 thành viên trong nhóm đều cần quyền chỉnh sửa trực tiếp để kịp hoàn thiện slide.

**GopY_BanNhap.docx gửi anh khóa trên**

Commenter

Restricted

Cho phép anh khóa trên bôi đen và để lại bình luận góp ý nhưng không sửa đè vào văn bản gốc.

**ThongTin_CaNhan_NhomVien.xlsx**

Viewer / Editor nội bộ

Restricted

Chứa dữ liệu nhạy cảm nên chỉ cấp quyền truy cập đích danh cho thành viên nhóm và trưởng nhóm.

### 2. Quy tắc Cờ Đỏ Bảo mật với file ThongTin_CaNhan_NhomVien.xlsx

-   **Quy tắc Cờ Đỏ Bảo mật:** Dữ liệu nhạy cảm như CCCD, SĐT, mật khẩu tuyệt đối phải để ở chế độ `Restricted` và kiểm soát chặt chẽ người truy cập.
    
-   **Lý do không kết hợp Anyone with the link + Editor:** Tổ hợp này cho phép bất kỳ ai có đường link trên Internet đều xem được thông tin cá nhân và tự ý chỉnh sửa, xóa hoặc đánh cắp dữ liệu CCCD, SĐT của cả nhóm mà không cần đăng nhập.
    

### 3. Hai thao tác trong Settings của file Slide_BaoCao.pptx

1.  **Bỏ tích** ô `Editors can change permissions and share` để ngăn thành viên tự ý chia sẻ file hoặc thêm người lạ vào chỉnh sửa.
    
2.  **Bỏ tích** ô `Viewers and commenters can see the option to download, print, and copy` để kiểm soát việc phát tán bản nháp ra ngoài nhóm.
    

## Phần 3 – Tổ chức giao tiếp nhóm chuẩn doanh nghiệp

### 1. Ba vấn đề giao tiếp trong đoạn hội thoại Zalo

1.  **Lỗi No-Hello:** Lan nhắn _"có ai rảnh không"_,  _"giúp em cái này"_ mà không nêu thẳng vấn đề, làm mất thời gian chờ đợi qua lại.
    
2.  **Tin nhắn không phân luồng và lẫn lộn nội dung:** Gửi ảnh mèo và tán gẫu xen ngang luồng công việc đang gấp rút, không sử dụng Thread.
    
3.  **Spam @all ngoài giờ làm việc và thiếu ngữ cảnh:** Trưởng nhóm tag `@all` lúc 23:47 đêm gây làm phiền tất cả mọi người nhưng không chỉ rõ ai đang thiếu phần việc nào.
    

### 2. Đề xuất Channel/Topic trên Lark/Slack

-   `#thong-bao-deadline`: Chỉ dùng để đăng thông báo quan trọng, phân công nhiệm vụ và chốt hạn nộp bài.
    
-   `#cong-viec-do-an`: Dùng để trao đổi chuyên môn, gửi link tài liệu và giải đáp lỗi theo từng Thread.
    
-   `#giai-tri-tan-gau`: Dùng để trò chuyện ngoài lề, gửi ảnh vui vẻ mà không làm trôi tin nhắn công việc.
    

### 3. Viết lại tin nhắn của Lan theo tư duy Asynchronous

> "@Nam ơi, mình đang làm phần Thiết kế hệ thống trong file `BaoCao_CuoiKy_SmartCampus.docx` (trang 8) nhưng bị vướng chỗ vẽ sơ đồ Database. Khi nào Nam online thì xem giúp mình bảng dữ liệu đã đúng chuẩn chưa nhé. Link file tại đây: [Link]. Mình cần chốt trước 17h hôm nay để ghép vào báo cáo. Cảm ơn Nam!"

### 4. Viết lại tin nhắn của Trưởng nhóm (Hẹn giờ gửi 08:00 sáng hôm sau)

> **Schedule Send: 08:00 AM**
> 
> "Chào buổi sáng cả nhóm, hôm nay là hạn chót hoàn thiện nội dung trước khi nộp báo cáo cuối kỳ. Hiện tại phần của Nam, Hoa và Tuấn đã xong, còn 2 phần cần bổ sung gấp trước 15h chiều nay:
> 
> -   @Lan: Hoàn thiện nốt mục 3.2 trong file `BaoCao_CuoiKy_SmartCampus.docx`.
>     
> -   @Minh: Cập nhật 3 slide tổng kết vào file `Slide_BaoCao.pptx`.
>     
>     Hai bạn hoàn thành xong thì phản hồi trực tiếp vào Thread dưới tin nhắn này nhé!"
>     

## Phần 4 – Thông báo tổng hợp trên kênh #thong-bao

> **[CẬP NHẬT KHÔNG GIAN LÀM VIỆC & TIẾN ĐỘ NỘP ĐỒ ÁN SMARTCAMPUS]**
> 
> Chào cả nhóm, để tránh thất lạc dữ liệu và kịp hạn nộp bài trong 2 ngày tới, mình đã chuẩn hóa lại toàn bộ tài liệu dự án như sau:
> 
> 1.  **Đồng bộ dữ liệu:** Thư mục `SmartCampus_Project` đã được thiết lập **Auto Sync** lên Cloud kèm lịch sử phiên bản. Mọi người làm việc trực tiếp trên thư mục đồng bộ để dữ liệu tự động lưu an toàn.
>     
> 2.  **Phân quyền bảo mật:** File `BaoCao_CuoiKy_SmartCampus.docx` đã được thiết lập phạm vi **Restricted** và cấp quyền **Viewer** gửi trước cho giảng viên hướng dẫn theo dõi, đảm bảo không bị sửa đè nội dung.
>     
> 3.  **Nhiệm vụ cần hoàn thành trước 18h00 hôm nay:**
>     
>     -   @Lan: Kiểm tra lại định dạng bảng biểu chương 3 trong file báo cáo.
>         
>     -   @Tuan: Bổ sung số liệuCCCD và SĐT vào file `ThongTin_CaNhan_NhomVien.xlsx` để mình nộp thủ tục bảo vệ.
>         
> 
> @Lan và @Tuan xử lý xong vui lòng phản hồi trực tiếp vào **Thread** của tin nhắn này để mình tổng hợp nhé!
