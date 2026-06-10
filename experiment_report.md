# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600614
**Name:** Nguyễn Ngọc Hải
**Date:** 10/6/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario                          | Agent Response                                                          | Accuracy (1-10) | Notes                                                                 |
| --------------------------------- | ----------------------------------------------------------------------- | --------------- | --------------------------------------------------------------------- |
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200.           | 9               | Hop ly vi du lieu da duoc lam sach va khong con record gia tri bat thuong. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2               | Sai ve mat ngu canh, bi anh huong boi outlier gia qua lon trong du lieu ban. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi dung clean data, agent tra loi on dinh va hop ly vi tap du lieu da qua buoc validation nen loai bo duoc cac record khong hop le. Nguoc lai, garbage data chua nhieu van de chat luong nhu duplicate ID, sai kieu du lieu, gia tri null va dac biet la outlier gia rat lon. Logic truy van trong agent dang tim san pham co gia cao nhat trong nhom electronics, nen bi record "Nuclear Reactor" chi phoi. Dieu nay cho thay neu khong co data quality control thi agent co the dua ra cau tra loi sai nghiem trong, du prompt co viet tot den dau.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y.

Prompt tot giup agent dien dat va suy luan ro rang hon, nhung khong the sua du lieu dau vao bi sai. Neu du lieu ban, ket qua van se lech huong. Vi vay, trong he thong AI thuc te, dam bao data quality va observability la dieu kien tien quyet truoc khi toi uu prompt.
