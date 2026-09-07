# Chương 3: Đại số quan hệ
**Môn Cơ sở dữ liệu**

## Câu hỏi và bài tập
1. Các phép toán: hội, giao, trừ, tích Đề-các dựa trên cơ sở lý thuyết nào ?
2. Trình bày tính khả hợp trên 2 quan hệ.
3. Cho ví dụ mỗi phép toán: hội, giao, trừ, tích đề các trên 2 quan hệ.
4. Cho ví dụ minh hoạ cho mỗi phép toán: chọn, chiếu, kết tự nhiên, kết có điều kiện, chia.

## Bài tập chương 3
**5) Tính giá trị biểu thức đại số quan hệ:**

Cho hai quan hệ S và T:

**Quan hệ S:**

| A | B | C | D | E |
|---|---|---|---|---|
| a | 1 | b | 2 | a |
| b | 2 | b | 1 | c |
| a | 1 | c | 1 | d |
| c | 3 | a | 3 | d |
| c | 4 | d | 2 | b |

**Quan hệ T:**

| A | G | H |
|---|---|---|
| c | 5 | d |
| b | 2 | b |
| a | 7 | c |
| c | 3 | a |
| b | 4 | a |
| a | 3 | d |

**Thực hiện các phép toán:**
*   **a/** $\Pi_{ABC}(S) \cap T$
*   **b/** $S * T$
*   **c/** $S  owtie_{B>G} T$
*   **d/** $\Pi_{BC}(S) \cap \Pi_{DE}(S)$
*   **e/** $\Pi_{CDE}(\sigma_{B>1}(S)) - T$
*   **f/** $\Pi_{AB}(S) \cup \Pi_{AG}(\sigma_{G>4}(T))$
*   **g/** $\sigma_{B=D}(S) 	imes \sigma_{A='a'}(T)$
*   **h/** $T \div U$ với quan hệ U:
    
    | A | G |
    |---|---|
    | c | 5 |
    | a | 3 |

*   **k/** $T \div P$ với quan hệ P:

    | A | G |
    |---|---|
    | c | 3 |
    | b | 4 |

*   **l/** $\Pi_{ABC}(S) \div V$ với quan hệ V:

    | C |
    |---|
    | b |
    | c |

---

**6) Viết câu truy vấn bằng đại số quan hệ**

Cho các lược đồ quan hệ:
*   `LOP (MaLop, TenLop)`
*   `SINHVIEN(MaSV, HoTen, NgaySinh, Phai, MaLop)`
*   `MONHOC(MaMH, TenMH, SoTC)`
*   `KETQUA(MaSV, MaMH, Diem)`

**Yêu cầu:**
*   **a/** Cho biết mã và họ tên những sinh viên thuộc lớp có tên là 07DHTH
*   **a’/** Cho biết mã và họ tên những sinh viên thuộc lớp có mã là L01
*   **b/** Mã và tên những môn học nào có số tín chỉ < 2
*   **c/** Liệt kê danh sách những sinh viên (mã sinh viên, họ tên) học môn có mã là MH001
*   **d/** Liệt kê danh sách những sinh viên (mã sinh viên, họ tên) học môn có tên là Cơ sở dữ liệu
*   **e/** Cho biết danh sách môn học (mã mh, tên mh) mà sinh viên có mã sv001 học
*   **e’/** Cho biết danh sách môn học (mã mh) mà sinh viên có mã sv001 học
*   **f/** Cho biết mã và tên những môn học chưa có sinh viên nào học.
