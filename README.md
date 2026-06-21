# HCM Real Estate Project

Dự án ứng dụng trực quan sử dụng dashboard để phân tích dữ liệu bất động sản tại Việt Nam.

## 1. Cấu trúc thư mục (Folder Structure)
```text
hcm-real-estate-project/
│
├── data/                           # Thư mục chứa dữ liệu
│   ├── raw/                        # Chứa file gốc tải từ Kaggle chưa qua xử lý
│   └── processed/                  # Chứa file dữ liệu đã được làm sạch (xuất ra từ notebook)
│
├── notebooks/                      # Không gian làm việc, nháp và tiền xử lý dữ liệu
│   ├── data_exploration.ipynb      # File khám phá, xem xét cấu trúc dữ liệu (EDA)
│   ├── data_cleaning.ipynb         # File code làm sạch dữ liệu, xử lý missing values
│   └── testing_charts.ipynb        # (Tùy chọn) Chạy thử các biểu đồ
│
├── src/                            # Trung tâm chứa mã nguồn thực thi
│   ├── backend/                    # Phần API xử lý logic AI và Code (Bắt buộc)
│   │   ├── api_server.py           
│   │   └── requirements_api.txt    
│   ├── dashboard/                  # Phần Giao diện & Tương tác người dùng (Frontend)
│   │   ├── app.py                  
│   │   └── requirements_ui.txt     
│   └── logs/                       # Hệ thống lưu trữ lịch sử
│       └── history_logs.json       
├── GUIDE.md                        # File hướng dẫn chạy dự án
└── README.md                       # File README dự án
```

## 2. Tổng quan dự án
- Trình bày một dự án ứng dụng trực quan sử dụng dashboard để phân tích dữ liệu.
- Ngữ cảnh của dữ liệu là **Việt Nam**.
- Các nhóm sẽ trình bày trong buổi vấn đáp.

## 3. Yêu cầu về dữ liệu
- Dữ liệu là **dữ liệu thật** có liên quan đến đất nước Việt Nam.
- Dữ liệu phải có tối thiểu **7 biến độc lập** và tối thiểu **2000 dòng**.
- Tổng số dữ liệu liên quan đến Việt Nam phải trên **50% dữ liệu**.

## 4. Các tiêu chí để đánh giá
1. **Kết hợp nguồn dữ liệu đáng tin cậy:**
   - Nguồn dữ liệu phải đáng tin cậy và minh bạch.
   - Không có thiếu sót trong quy trình xử lý dữ liệu.
2. **Phù hợp với mục đích:**
   - Trực quan hóa phải phản ánh mục đích cụ thể (VD: biểu đồ cột so sánh dữ liệu, biểu đồ đường theo dõi xu hướng).
   - Phù hợp với đối tượng mục tiêu.
3. **Rõ ràng và dễ hiểu:**
   - Truyền đạt thông điệp rõ ràng, dễ hiểu.
   - Người xem có thể nhanh chóng nhận thức thông tin từ biểu đồ và đồ thị.
4. **Sự tích hợp và liên kết:**
   - Đảm bảo sự liên kết, tích hợp giữa các biểu đồ.
   - Mối quan hệ giữa các phần trực quan hóa phải được làm rõ.
5. **Tương tác và điều hướng:**
   - Sự tương tác tích hợp hợp lý để thăm dò dữ liệu.
   - Hệ thống điều hướng dễ sử dụng.
6. **Thiết kế hấp dẫn:**
   - Thiết kế, màu sắc hấp dẫn, thu hút sự chú ý nhưng không gây quá tải màu sắc.
7. **Phân tích dữ liệu:**
   - Thể hiện sự thay đổi/xu hướng theo thời gian.
   - Mối quan hệ giữa các biến rõ ràng.
   - Kết luận và câu chuyện rút ra từ dữ liệu.

## 5. Tích hợp AI: Thiết kế và vận hành
Dự án yêu cầu tích hợp tính năng AI vào phân tích dữ liệu (có thể là ứng dụng độc lập, tích hợp vào dashboard hoặc tạo API để các ứng dụng khác sử dụng).

### 5.1. Nguyên tắc cơ bản
- **Vai trò của AI:**
  - Trợ giúp đề xuất ý tưởng.
  - Viết code dựa vào yêu cầu của người dùng.
  - Trình bày kết quả phân tích với số liệu/hình ảnh do con người cung cấp (AI không tự ý thêm số liệu/hình ảnh khác).
- **Vai trò của con người:**
  - Định hướng, đề xuất yêu cầu, ra quyết định thực thi code.
  - Xin gợi ý từ AI nếu chưa có ý tưởng phân tích.
- **Thực thi code:** Code do AI sinh ra phải được thực thi trên môi trường **local**, không thực thi trên môi trường online.

### 5.2. Nguyên tắc "Không thực thi ngầm"
AI không được tự ý thay đổi dữ liệu gốc hay âm thầm chạy thuật toán.
- **Hiển thị code bắt buộc:** Mọi code AI tạo ra phải hiển thị rõ ràng.
- **Giải thích bằng ngôn ngữ tự nhiên:** Mỗi đoạn code phải có comment giải thích rõ ràng bằng ngôn ngữ tự nhiên ngay trên code đó (VD: `"Đoạn code này sẽ xóa 15 dòng có giá trị NULL ở cột Doanh Thu, sử dụng hàm dropna() của Pandas."`).

### 5.3. Nguyên tắc phê duyệt (Vai trò "Người quyết định")
- **Trạng thái chờ:** Code AI sinh ra ban đầu ở trạng thái "Chờ duyệt".
- **Chỉnh sửa:** Người dùng có quyền can thiệp, chỉnh sửa các tham số trong code AI vừa viết.
- **Chấp nhận & thực thi:** Đoạn code chỉ được chạy và trả về kết quả/biểu đồ khi con người nhấn chấp thuận.

### 5.4. Nguyên tắc lưu trữ
Hệ thống phải lưu trữ **tất cả** yêu cầu, mã nguồn, kết quả phân tích và giải thích để có thể truy xuất lại.

## 6. Gợi ý thiết kế (Kiến trúc hệ thống)
Hệ thống nên phân chia rõ ràng giữa API và Frontend.

### 6.1. Phần Giao diện & Tương tác người dùng (Frontend)
Công nghệ phát triển là tùy chọn (Streamlit, Gradio, React,...). Cần đảm bảo các chức năng:
- **Nhận yêu cầu:** Ô chat hoặc form để người dùng gửi yêu cầu phân tích/viết code.
- **Xem & chỉnh sửa mã nguồn:** Cho phép xem và sửa đoạn code do AI trả về.
- **Phê duyệt:** Nút xác nhận cho phép chạy code (Accept & Run).
- **Hiển thị kết quả:** Trình bày bảng dữ liệu, biểu đồ sau khi thực thi.

### 6.2. Phần API
- **API AI (Bắt buộc):** Tiếp nhận yêu cầu từ Frontend, gửi ngữ cảnh cho mô hình AI (chạy local) và trả về code + giải thích.
- **API Thực thi (Bắt buộc):** Tiếp nhận mã đã được phê duyệt từ Frontend, chạy code trực tiếp trên dữ liệu máy (local), thu thập kết quả và trả về cho Frontend hiển thị.
- **API Logs (Bắt buộc):** Lưu trữ lịch sử toàn bộ các yêu cầu, mã nguồn sinh ra, kết quả và giải thích.

## 7. Trong báo cáo và vấn đáp
- **Vấn đáp:** Các nhóm sẽ sử dụng module AI đã phát triển để trả lời các câu hỏi phân tích từ hội đồng (dựa trên dữ liệu nhóm và câu hỏi chuẩn bị sẵn). Số lượng câu hỏi tối thiểu bằng số lượng thành viên nhóm.
- **Báo cáo:** Phải tóm tắt quá trình sử dụng AI, những yêu cầu đặt ra, kết quả nhận được, thay đổi đã thực hiện và nhận xét về AI.
