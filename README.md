[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574001&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** sang.phan2409@gmail.com
**Name:** Phan Thanh Sang

---

## Mo ta

Bai lab xay dung ETL pipeline tu file JSON -> CSV gom 4 buoc: extract, validate,
transform, load. Pipeline loai bo record khong hop le (price <= 0, category rong),
them discounted_price (giam 10%), chuan hoa category ve Title Case va them cot
processed_at de theo doi thoi diem xu ly. Ngoai ra, da thuc hien stress test Agent
voi clean data vs garbage data de quan sat tac dong cua data quality den do chinh xac.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python solution.py
python generate_garbage.py
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- Input tu `raw_data.json`: 5 records
- Sau validation: 3 valid records, 2 errors bi loai
- Output: tao `processed_data.csv` voi 3 records
- Stress test Agent:
	- Clean data tra loi hop ly: Laptop at $1200
	- Garbage data bi nhieu boi outlier: Nuclear Reactor at $999999
- Local test: `pytest` dat 9/9 test
