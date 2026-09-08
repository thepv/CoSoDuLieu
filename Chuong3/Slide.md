# Chương 3: Đại số quan hệ
**Môn Cơ sở dữ liệu**
▶️ [Xem video Chương 3 Đại Số Quan Hệ](https://www.youtube.com/watch?v=UR69-9VGDyE)
## Đại số quan hệ
* Các phép toán tập hợp: Hội, giao, trừ, tích đề-các
* Các phép toán quan hệ: Chọn, chiếu, kết, đổi tên, chia
* Tính giá trị biểu thức đại số quan hệ
* Viết biểu thức truy vấn bằng đại số quan hệ.

## Các phép toán tập hợp
### Tính khả hợp:
Hai quan hệ có cùng bậc (cùng số thuộc tính) và miền giá trị của mỗi thuộc tính tương ứng trên 2 quan hệ phải giống nhau.
* **Ví dụ:** Các quan hệ khả hợp: r, s. Quan hệ không khả hợp: r và p; s và p.
    * `r (A, B)`: (a, 1), (a, 2), (b, 1)
    * `s (A, B)`: (a, 2), (b, 3)
    * `p (A, B, C)`: (b, 1, c), (a, 3, c)

### Phép hội (Union)
Xét 2 quan hệ khả hợp: r và s
`r ∪ s = {t | t ∈ r ∨ t ∈ s}`
* **Ví dụ:**
    * `r` có (a,1), (a,2), (b,1). `s` có (a,2), (b,3).
    * `r ∪ s` sẽ là (a,1), (a,2), (b,1), (b,3).
* **Ví dụ phép hội (Danh sách sinh viên thuộc cả 2 lớp A và B):**
    * SV_A (MaSV, HoTen): Gồm các SV lớp A.
    * SV_B (MaSV, HoTen): Gồm các SV lớp B.
    * Kết quả `SV_A ∪ SV_B` là danh sách gộp tất cả sinh viên của cả 2 lớp.

### Phép giao (Intersection)
Xét 2 quan hệ khả hợp: r và s
`r ∩ s = { t | t ∈ r ∧ t ∈ s }`
* **Ví dụ:**
    * `r (A,B,C)`: (a,1,b), (a,2,c), (b,1,a), (c,2,d), (b,3,a).
    * `s (A,B,C)`: (a,1,b), (b,3,d), (c,2,d).
    * `r ∩ s` sẽ là các bộ chung: (a,1,b), (c,2,d).
* **Ví dụ phép giao:**
    * Cho biết danh sách sinh viên học vừa học môn Cơ sở dữ liệu, vừa học môn Toán rời rạc. Kết quả `SV_CSDL ∩ SV_TRR` lấy những sinh viên có ở cả hai danh sách.

### Phép trừ (Difference)
Xét 2 quan hệ khả hợp: r và s
`r - s = { t | t ∈ r và t ∉ s}`
* **Ví dụ:**
    * `r (A,B,C)`: (a,1,b), (a,2,c), (b,1,a), (c,2,d), (b,3,a).
    * `s (A,B,C)`: (a,1,b), (b,3,d), (c,2,d).
    * `r - s` sẽ giữ lại các bộ có trong r nhưng không có trong s: (a,2,c), (b,1,a), (b,3,a).
* **Ví dụ phép trừ:**
    * Câu hỏi: Những sinh viên nào học lớp 03CNTT không là đoàn viên?
    * Giải: `03CNTT - DoanVien`. Kết quả trả về các sinh viên có trong lớp 03CNTT nhưng không có tên trong bảng DoanVien.

### Phép tích Đề-các (Cartesian Product)
R có m thuộc tính A1, A2, …, Am và p bộ. S có n thuộc tính B1, B2, …, Bn và q bộ.
`R x S` có m+n thuộc tính (A1, A2, …, Am, B1, B2, …, Bn) và có p x q bộ.
* **Ví dụ:**
    * `r(A,B)` có 3 bộ, `s(C,D,E)` có 2 bộ.
    * `r x s` sẽ tạo ra một bảng mới (A,B,C,D,E) với 3 x 2 = 6 bộ dữ liệu.

## Các phép toán quan hệ
### Phép chọn (Selection)
`σP(R) = {t | P(t) đúng}`
Chọn các bộ trên quan hệ R thỏa điều kiện P. Biểu thức điều kiện có thể sử dụng các phép toán: =, <, ≤, >, ≥, ∧, ∨, ¬
* **Ví dụ:** `σ(A='a') ∨ (B>2) (r)` sẽ lọc ra các dòng thỏa mãn A='a' hoặc B>2.
* **Ví dụ phép chọn:**
    * Cho bảng `NHANVIEN(MANV, HOTEN, TUOI, PHAI, PHONG)`.
    * Câu hỏi: Hãy cho biết những nhân viên nào thuộc phòng Kinh doanh có tuổi trên 25?
    * Giải: `σ(PHONG='Kinh doanh') ∧ (TUOI>25) (NHANVIEN)`.

### Phép chiếu (Projection)
`ΠX(r) = {t[X] | t ∈ r}`
t[X] là giá trị của bộ t trên tập thuộc tính X. Phép chiếu dùng để chọn ra các cột.
* **Ví dụ:** Cho bảng `MONHOC(MAMH, TENMH, TINCHI, LOAI)`.
    * Yêu cầu: `ΠTENMH, TINCHI(MONHOC)` sẽ tạo ra bảng mới chỉ gồm 2 cột TENMH và TINCHI.

### Ví dụ kết hợp phép chọn và phép chiếu
* **Câu hỏi:** Cho biết mã và tên những môn học có số tín chỉ lớn hơn 2 ?
* **Giải (2 bước):**
    1. Phép chọn: `σTINCHI > 2(MONHOC)`
    2. Phép chiếu trên kết quả của phép chọn: `ΠMAMH, TENMH (σTINCHI > 2(MONHOC))`

### Phép kết (Join)
#### Phép kết có điều kiện (Theta join)
`r ⋈P s = {t(A1, A2, …, Am, B1, B2, …, Bn) | P(t) thỏa}`
Trong đó:
* P là điều kiện dạng `Ai θ Bj` với Ai ∈ {A1, A2, …, Am}, Bj ∈ {B1, B2, …, Bn}.
* θ là một trong các phép so sánh =, <, ≤, >, ≥, ≠.
* **Ví dụ:** `r ⋈A=C ∧ B<D s` sẽ nối bảng r và s lại với nhau dựa trên điều kiện A=C và B<D.

#### Phép kết tự nhiên (Natural join)
Là phép kết có điều kiện so sánh ‘=’ giữa một hoặc tập các thuộc tính chung của 2 quan hệ tham gia. Ký hiệu là `*`.
* **Ví dụ:**
    * Bảng `NHANVIEN(MANV, HOTEN, PHAI, MAPH)`.
    * Bảng `PHONGBAN(MAPH, TENPHONG)`.
    * Phép kết tự nhiên: `NHANVIEN * PHONGBAN` sẽ tự động nối dữ liệu dựa trên thuộc tính chung là `MAPH`. (Cho biết thông tin nhân viên và phòng ban mà nhân viên đó trực thuộc).

#### Ví dụ phép chọn, chiếu, kết kết hợp
* **Câu hỏi:** Mã và họ tên những nhân viên thuộc phòng Quản trị?
* **Giải:** `ΠMANV, HOTEN (σTENPHONG='Quản trị' (NHANVIEN * PHONGBAN))`

### Phép chia (Division)
`R(X) ÷ S(Y) = V(X – Y)`
Chọn ra một số bộ trong quan hệ R sao cho thỏa với tất cả các bộ trong quan hệ S.
* **Ví dụ:**
    * Câu hỏi: Nhân viên nào được phân công vào tất cả các đề án?
    * Cho bảng `PHANCONG(NhanVien, DeAn)`.
    * `P ← ΠDeAn(PHANCONG)` (Tạo bảng P chứa tất cả các đề án có trong bảng phân công).
    * Lấy `PHANCONG ÷ P` sẽ trả về NhanVien (Bình, Châu) đã tham gia đủ tất cả các đề án.

### Phép đổi tên (Rename)
`R ← A`: Đổi tên quan hệ A thành R.
* **Ví dụ:** Gán kết quả của phép chiếu vào một quan hệ tạm.
    * `P ← ΠAB(R)`
    * Sau đó thực hiện tiếp `P * S`.
