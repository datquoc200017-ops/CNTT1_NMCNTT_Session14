# Bài Tập Về Nhà 
## Bài 3 : Ngăn chặn quá tải lưu trữ khi đồng bộ mã nguồn
###  Bài Làm
**5. Yêu cầu đầu ra**

-   **Báo cáo phân tích (I/O):** Mô tả luồng dữ liệu từ lúc nhấn Ctrl+S đến khi xuất hiện tích xanh trên file. 
1. Khi lập trình viên lưu file thì sẽ ghi nhận trực tiếp xuống SSD Local, hệ điều hành ghi nhận và cập nhật dữ liệu vào thư mục dự án trên ổ đĩa, khi lập trình viên bật tiến trình theo dõi đám mây rồi và thấy sự thay đổi của file và tự động sao lưu, và khi server cloud xác nhận nhận dữ liệu thành công  phần mềm trả lại trạng thái tích xanh ở giao diện.


    
-   **Thiết kế:** Sơ đồ tổ chức thư mục Cloud chuẩn cho một lập trình viên (bao gồm phân loại: Code, Docs, Assets).
📁 Cloud_Workspace/
├── 📁 Code/                   
│   ├── 📁 startup-project-js/
│   └── 📁 practice-exercises/
├── 📁 Docs/                  
│   ├── 📄 IT108_Session15_Report.md
│   └── 📄 Architecture_Design.pdf
└── 📁 Assets/         
    ├── 📁 images/
    └── 📁 branding/

