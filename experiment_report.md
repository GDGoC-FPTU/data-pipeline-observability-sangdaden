# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600280
**Name:** Phan Thanh Sang
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Data sau ETL sach, khong co gia tri loi, ket qua hop ly voi tap du lieu electronics hien co. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Outlier gia qua lon va record rac lam agent uu tien lua chon sai trong bo canh mua sam thong thuong. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi dung garbage data, agent de bi nhieu boi bo du lieu nhieu loi chat luong.
Duplicate IDs lam mat tinh nhat quan va kho xac dinh ban ghi nao la dung.
Wrong data types (vi du "ten dollars") co the gay sai khi tinh toan hoac so sanh.
Outlier gia qua cao (999999) keo logic chon "best" di lech hoan toan.
Null values o cot quan trong lam mat ngu canh, gay kho cho loc category.
Tong hop lai, model co prompt tot nhung neu data dau vao bi doc thi suy luan van sai.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Dong y. Prompt giup huong dan cach tra loi, nhung data quality quyet dinh tran kien
thuc de model dua tren do suy luan. Neu du lieu sai, trung lap, thieu hoac co outlier
manh, ket qua se sai lech du prompt rat ro rang. Vi vay can ETL va validation truoc
khi dua data vao agent.
