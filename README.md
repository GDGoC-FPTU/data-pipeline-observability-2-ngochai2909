[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112798&assignment_repo_type=AssignmentRepo)

# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** hainn29.dev@gmail.com
**Name:** Nguyễn Ngọc Hải

---

## Mô tả

Bài lab này xây dựng ETL pipeline có 4 bước: Extract -> Validate -> Transform -> Load.
Tôi đã hoàn thành `solution.py` với các chức năng:
- Đọc dữ liệu từ `raw_data.json`
- Loại bỏ record không hợp lệ (`price <= 0` hoặc `category` rỗng)
- Tính `discounted_price` (giảm 10%), chuẩn hóa `category` về Title Case
- Thêm timestamp `processed_at` và lưu ra `processed_data.csv`

Ngoài ra, tôi đã chạy stress test với clean data và garbage data để quan sát tác động của chất lượng dữ liệu đến câu trả lời của AI agent.

---

## Cách chạy (How to Run)

### Prerequisites

```bash
python3 -m venv venv
source venv/bin/activate
pip install pandas pytest
```

### Chạy ETL Pipeline

```bash
python3 solution.py
```

### Chạy Agent Simulation (Stress Test)

```bash
python3 generate_garbage.py
python3 agent_simulation.py
```

---

## Cấu trúc thư mục

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output của pipeline
├── experiment_report.md     # Báo cáo thí nghiệm
└── README.md                # File này
```

---

## Kết quả

- Tổng record đầu vào: 5
- Record hợp lệ sau validate: 3
- Record bị loại: 2 (1 record có `price <= 0`, 1 record có `category` rỗng)
- File output: `processed_data.csv` được tạo thành công
- Stress test:
  - Clean Data: Agent chọn `Laptop` giá `1200` (hợp lý)
  - Garbage Data: Agent chọn `Nuclear Reactor` giá `999999` (sai ngữ cảnh do outlier)
- Autograder local: `9/9 tests passed`
