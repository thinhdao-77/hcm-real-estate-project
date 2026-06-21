hcm-real-estate-project/
│
├── data/                           # Thư mục chứa dữ liệu
│   ├── raw/                        # Chứa file gốc tải từ Kaggle chưa qua xử lý
│   └── processed/                  # Chứa file dữ liệu đã được làm sạch (xuất ra từ notebook)
│
├── notebooks/                      # Không gian làm việc, nháp và tiền xử lý dữ liệu
│   ├── 01_data_exploration.ipynb   # File khám phá, xem xét cấu trúc dữ liệu (EDA)
│   ├── 02_data_cleaning.ipynb      # File code làm sạch dữ liệu, xử lý missing values
│   └── 03_testing_charts.ipynb     # (Tùy chọn) Chạy thử các biểu đồ
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
│
└── README.md                       # File hướng dẫn chạy project