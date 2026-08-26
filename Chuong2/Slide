
# Chương 2: Các mô hình dữ liệu
**Môn Cơ sở dữ liệu**

## Mô hình thực thể kết hợp
Entity Relationship Model gọi tắt là ER hay ERD là mô hình dữ liệu được dùng để thiết kế cơ sở dữ liệu mức quan niệm.
**Các khái niệm chính:**
* Thực thể
* Kiểu thực thể
* Thuộc tính
* Mối kết hợp
* Phân loại kiểu thực thể
* Phân loại thuộc tính

## Thực thể (Entity)
Là một đối tượng trong thế giới thực, tồn tại một cách cụ thể hay tồn tại quan niệm.
Ví dụ: trong một lớp học gồm các thực thể:
* **Tồn tại cụ thể:** Huyền, Châu, Tuấn, Mai, Long.
* **Tồn tại quan niệm:** môn Toán, môn Lý, môn Hóa.

## Kiểu thực thể (Entity types)
Một tập các thực thể có cùng các thuộc tính.
* Biểu diễn: Tên kiểu thực thể
* Ví dụ:
    * Các thực thể: Châu, Huyền, Mai, Tuấn, Long thuộc kiểu thực thể **SINH_VIEN**.
    * Các thực thể: Lập trình C, Cấu trúc rời rạc, Cơ sở dữ liệu, Lập trình Web thuộc kiểu thực thể **MON_HOC**.

## Thuộc tính (Attribute)
Mô tả đặc trưng của thực thể.
* **Ví dụ 1:** Thực thể Huyền, Mai, Châu, Tuấn, Long đều có các thuộc tính là Mã sinh viên, Họ tên, Ngày sinh, Giới tính, Tuổi.
* **Ví dụ 2:** Thực thể Toán rời rạc, CSDL, Lập trình C, Lập trình Web đều có các thuộc tính là Mã môn học, tên môn học, số tín chỉ.

## Thuộc tính và kiểu thực thể
Quan hệ giữa thuộc tính và kiểu thực thể được biểu diễn bằng một trong hai cách:
* (Biểu diễn qua sơ đồ cho kiểu thực thể SINH_VIEN với các thuộc tính MaSV, HoTen, NgaySinh, GioiTinh).

## Mối kết hợp (Relationship)
Thể hiện sự liên kết giữa 2 thực thể, phản ánh một thực tế về quản lý.
Có 3 loại mối kết hợp:
* Một – Nhiều (1 – N)
* Một – Một (1 – 1)
* Nhiều – Nhiều (N – N)

### Mối kết hợp Một – Nhiều
* **Cách 1:**
    * Biểu diễn: E -> F
    * Mô tả: Mỗi thực thể thuộc kiểu thực thể E có thể liên kết với một hoặc nhiều thực thể thuộc kiểu thực thể F. Ngược lại, mỗi thực thể kiểu F có liên kết với nhiều nhất một thực thể kiểu E.
* **Cách 2: sử dụng cặp chỉ số (min, max)**
    * Biểu diễn: E (1,N) ---- (1,1) F
    * Mô tả: Mỗi thực thể thuộc kiểu thực thể E có liên kết với ít nhất 1 và nhiều nhất N thực thể thuộc kiểu thực thể F. Ngược lại, Mỗi thực thể thuộc kiểu thực thể F có liên kết với ít nhất 1 và nhiều nhất 1 thực thể thuộc kiểu thực thể E.
    * Các chỉ số min, max có thể thay đổi như: 0, 1, 30,… tùy thuộc vào yêu cầu thực tế.

**Ví dụ mối kết hợp 1 – N:**
* Sinh viên (Châu, Huyền, Mai, Tuấn, Long) và Lớp (Lop01, Lop02, Lop03).
* LOP (MaLop, TenLop, Siso) liên kết (1,n) - (1,1) với SINH_VIEN (MaSV, HoTen, NgaySinh, GioiTinh).

### Mối kết hợp Một – Một
* **Cách 1:**
    * Biểu diễn: E -> F
    * Mô tả: Mỗi thực thể thuộc kiểu thực thể E có liên kết với nhiều nhất một thực thể thuộc kiểu thực thể F. Ngược lại, mỗi thực thể kiểu F có liên kết với nhiều nhất một thực thể kiểu E.
* **Cách 2: sử dụng cặp chỉ số (min, max)**
    * Biểu diễn: E (1,1) ---- (1,1) F
    * Mô tả: Mỗi thực thể thuộc kiểu thực thể E có liên kết với ít nhất 1 và nhiều nhất 1 thực thể thuộc kiểu thực thể F. Ngược lại, Mỗi thực thể thuộc kiểu thực thể F có liên kết với ít nhất 1 và nhiều nhất 1 thực thể thuộc kiểu thực thể E. Các chỉ số min, max có thể thay đổi tùy thuộc vào yêu cầu thực tế.

**Ví dụ mối kết hợp Một – Một:**
* Giả sử rằng quan hệ giữa phòng ban và trưởng phòng như sau: 
* Trưởng phòng (Huyền, Mai, Tuấn) và Phòng ban (P.Kế toán, P.Kinh Doanh, P.Quản trị).
* PHONGBAN (MaPH, TenPH, DiaDiem) liên kết (1,1) - (1,1) với TR_PHONG (MaTP, HoTen, NgaySinh, GioiTinh).

### Mối kết hợp Nhiều – Nhiều
* **Cách 1:**
    * Biểu diễn: E -> F
    * Mô tả: Mỗi thực thể thuộc kiểu thực thể E có liên kết với một hoặc nhiều thực thể thuộc kiểu thực thể F. Ngược lại, Mỗi thực thể thuộc kiểu thực thể F có thể liên kết với một hoặc nhiều thực thể thuộc kiểu thực thể E.
* **Cách 2: sử dụng cặp chỉ số (min, max)**
    * Biểu diễn: E (1,N) ---- (1,N) F
    * Mô tả: Mỗi thực thể thuộc kiểu thực thể E có liên kết với ít nhất 1 và nhiều nhất N thực thể thuộc kiểu thực thể F. Ngược lại, Mỗi thực thể thuộc kiểu thực thể F có liên kết với ít nhất 1 và nhiều nhất N thực thể thuộc kiểu thực thể E.

**Ví dụ mối kết hợp Nhiều – Nhiều:**
* Sinh viên (Châu, Huyền, Tuấn, Long) và Môn học (CSDL, ToanCC, LTC).
* MON_HOC (MaMH, TenMH, SoTC) liên kết (1,n) - (1,n) với SINH_VIEN (MaSV, HoTen, NgaySinh, GioiTinh) thông qua KETQUA (Diem).

## Phân loại thuộc tính
* Thuộc tính khóa (định danh)
* Thuộc tính đơn trị
* Thuộc tính đa trị
* Thuộc tính gộp
* Thuộc tính dẫn xuất

### 1. Thuộc tính khóa (định danh)
Dùng để xác định duy nhất một thực thể trong một kiểu thực thể. Ký hiệu gạch dưới tên thuộc tính.
* Ví dụ: MaSV là khóa trong kiểu thực thể SINH_VIEN, MaMH là khóa trong kiểu thực thể MON_HOC.

### 2. Thuộc tính đơn trị
Có giá trị đơn (nguyên tử) nghĩa là không thể chia nhỏ giá trị thành các phần có ý nghĩa.
* Ví dụ: Thuộc tính Tuoi có giá trị 20. Thuộc tính GioiTinh có giá trị Nam.

### 3. Thuộc tính đa trị
Có chứa nhiều giá trị.
* Ví dụ: Một nhân viên có 2 bằng cấp chuyên môn là Kỹ sư Công nghệ thông tin và Cử nhân ngoại ngữ. Vậy thuộc tính BangCap của nhân viên là đa trị vì có thể chứa nhiều giá trị.
* Biểu diễn: Bằng vòng bầu dục nét đôi (ví dụ: BangCap).

### 4. Thuộc tính gộp
Giá trị có thể phân tách thành nhiều phần có ý nghĩa.
* Ví dụ: HoTen có thể tách thành 2 phần là Họ, Tên. DiaChi có thể tách thành Số nhà, Đường, Quận, Thành phố.

### 5. Thuộc tính dẫn xuất
Có giá trị được tính toán từ các giá trị của các thuộc tính khác.
Trong thiết kế cơ sở dữ liệu có thể loại bỏ những thuộc tính dẫn xuất để tối ưu bộ nhớ lưu trữ.
* Ví dụ: ThanhTien có giá trị được tính từ 2 thuộc tính là SoLuong và DonGia.

## Phân loại kiểu thực thể
* Kiểu thực thể mạnh (Strong Entity Types)
* Kiểu thực thể yếu (Weak Entity Types)

### Kiểu thực thể mạnh
Là kiểu thực thể có thuộc tính khóa định danh. Tồn tại độc lập mà không phụ thuộc vào sự tồn tại của thực thể khác.
* Ví dụ: Các kiểu thực thể mạnh: NhanVien, PhongBan, DeAn.

### Kiểu thực thể yếu
Là kiểu thực thể không có thuộc tính định danh riêng. Tồn tại phụ thuộc vào sự tồn tại của thực thể khác.
* Ví dụ: Kiểu thực thể yếu ThanNhan phụ thuộc vào kiểu thực thể NhanVien. ThanNhan chỉ tồn tại khi có sự tồn tại của NhanVien.
* Biểu diễn: Vòng chữ nhật nét đôi (ví dụ: ThanNhan).


## Mô hình quan hệ
Được E.F.Cold đề xuất vào năm 1970. Dựa trên nền tảng lý thuyết tập hợp.
**Các khái niệm chính:**
* Quan hệ (Relation)
* Thuộc tính (Attribute)
* Miền giá trị (Domain)
* Bộ (Tupe)
* Lược đồ quan hệ (Schema)
* Thể hiện quan hệ (Instance)
* Khóa (Key)

### Quan hệ (Relation)
Là đối tượng để trình bày dữ liệu được biểu diễn bằng bảng 2 chiều.
* Ví dụ: Tên quan hệ NHAN_VIEN với các thuộc tính (MA_SO, HO_TEN, NAM_SINH, LUONG) và các bộ dữ liệu tương ứng.

### Thuộc tính, miền
Mô tả tính chất đặt trưng riêng cho mỗi đối tượng cần được quản lý và lưu trữ trong cơ sở dữ liệu.
* Ví dụ: Các thuộc tính của đối tượng SinhVien gồm: Mã sinh viên, họ tên, ngày sinh,…
* Tập các giá trị cho phép của thuộc tính gọi là miền giá trị (Domain) của thuộc tính.
* Giá trị của thuộc tính thường là nguyên tử (atomic). Thuộc tính có thể chứa giá trị rỗng (Null).

### Bộ (Tupe)
Một bộ là một dòng dữ liệu biểu diễn thông tin của một đối tượng cụ thể trong quan hệ.
* Không có 2 bộ trùng nhau trong một quan hệ.
* Các bộ trong quan hệ là không có thứ tự.

### Lược đồ quan hệ (Relation Schema)
Biểu diễn cấu trúc của quan hệ gồm tên và tập các thuộc tính của quan hệ.
* Ví dụ: quan hệ SINHVIEN và lược đồ tương ứng: SINHVIEN(MaSV, HoTen, GioiTinh, MaLop).

### Thể hiện quan hệ (Instance)
Một thể hiện quan hệ (Relation Instance) là giá trị của quan hệ tại một thời điểm cụ thể.
* Ví dụ: Thể hiện quan hệ sinh viên tại thời điểm 1 và Thể hiện quan hệ sinh viên tại thời điểm 2.

### Khóa (Key)
Gọi U là tập tất cả các thuộc tính của R; t1, t2 là 2 bộ bất kỳ trên R. Tập thuộc tính K  U được gọi là khóa của R nếu:
* ∀t1, t2 ∈ R, t1[K] ≠ t2 [K]
* ∀ K’ ⊂ K đều không thỏa tính chất trên.
* Ví dụ: Quan hệ KETQUA có một khóa là {MaSV, MaMH}.

### Siêu khóa (Super key)
Là tập thuộc tính chứa hoặc bằng khóa.
* Ví dụ: Quan hệ KETQUA có 2 siêu khóa là: S1={MaSV, MaMH}, S2={MaSV, MaMH, DiemThi}.

### Khóa chính (Primary key)
Là khóa được chọn từ tập các khóa của quan hệ.
* Ví dụ: Quan hệ NHANVIEN có 3 khóa là MANV, EMAIL và SOCMND. Trong 3 khóa này, ta có thể chọn MANV làm khóa chính.

### Khóa ngoại (Foreign key)
Là tập các thuộc tính tham chiếu đến một khóa chính trên quan hệ. Quan hệ được tham chiếu đến có thể cùng hoặc khác quan hệ chứa khóa ngoại.
* Ví dụ: MaPH trên quan hệ NHANVIEN là khóa ngoại tham chiếu đến PHONGBAN.

**Ví dụ khóa ngoại:**
Cho các lược đồ quan hệ:
* NHANVIEN(MANV, HOTEN, PHAI, TUOI)
* KYNANG(MANV, MAKN)
* DEAN(MADA, TENDA, NGAYBD, NGAYKT)
* PHANCONG(MANV, MAKN, MADA, NGAYPC)
* Mô tả: Với tính chất của đề án, Việc phân công đề án cho nhân viên phải dựa vào kỹ năng của nhân viên có phù hợp hay không.
* Yêu cầu: Hãy xác định khóa ngoại có trên các quan hệ KYNANG, PHANCONG.

## Chuyển mô hình ER sang mô hình quan hệ
### Mối kết hợp 1 – N
* E(A, B, C) liên kết 1-N với F(D, G).
* Lược đồ: E(A, B, C) và F(D, G, A) (Thuộc tính khóa A của E làm khóa ngoại trong F).

### Mối kết hợp 1 – 1
* E(A, B, C) liên kết 1-1 với F(D, G).
* TH1: E(A, B, C) và F(D, G, A)
* TH2: F(D, G) và E(A, B, C, D)
* Lưu ý: Tùy vào gốc độ quản lý sẽ chọn trường hợp 1 hay trường hợp 2.
* Ví dụ: Hãy chuyển sang lược đồ quan hệ. Từ đó xác định chọn trường hợp nào phù hợp với thực tế quản lý giữa SINHVIEN (MASV, HOTEN, PHAI) và THESV (SOTHE, NGAYLAP).

### Mối kết hợp Nhiều – Nhiều
* E(A, B, C) liên kết N-N với F(D, G) qua thuộc tính P.
* Lược đồ: E(A, B, C), F(D, G) và T(A, D, P) (với A, D là khóa ngoại tham chiếu đến E và F).
* Ví dụ 1: Chuyển sang lược đồ quan hệ giữa SINH_VIEN (MaSV, HoTen, NgaySinh, GioiTinh) và MON_HOC (MaMH, TenMH, SoTC) qua kết quả (Diem).
* Ví dụ 2: Chuyển sang lược đồ quan hệ giữa HOADON (MAHD, NGAYLAP) và HANGHOA (MAHG, TENHG, DVT, DONGIA) qua chi tiết (SOLUONG).
* Ví dụ 3: Chuyển sang lược đồ quan hệ. (Lưu ý: KETQUA được biểu diễn dạng kiểu thực thể yếu) giữa SINHVIEN (MASV, HOTEN, NGAYSINH) và MONHOC (MAMH, TENMH, SOTC) qua KETQUA (LANTHI, DIEM).

## Câu hỏi và bài tập Chương 2
1. Trong một hệ thống quản lý thư viện, hãy liệt kê các thực thể, thuộc tính, mối kết hợp có thể có.
2. Trình bày 2 thực thể yếu có trong một hệ thống tùy chọn. Diễn giải cụ thể.
3. Trình bày 2 thuộc tính đa trị tồn tại trong thực tế của một hệ thống cụ thể. Diễn giải.
4. Trình bày 2 ví dụ về mối kết hợp 1 – 1 giữa 2 kiểu thực thể trong hệ thống cụ thể.
5. Việc thể hiện cặp chỉ số (min, max) trên mối kết hợp có lợi ích gì? Hãy nêu một số trường hợp mối kết hợp có chỉ số min khác 1.
6. Hãy đưa ra 3 quy tắc khi thiết kế mô hình thực thể kết hợp.
7. Phân biệt khóa, siêu khóa, khóa chính, khóa ngoại. Cho ví dụ minh họa.
8. Hãy cho biết thứ tự nhập và xóa dữ liệu trên 2 quan hệ có tham chiếu khóa chính – khóa ngoại.
9. Thiết kế mô hình thực thể kết hợp của hệ thống quản lý thư viện dựa vào các đối tượng liệt kê ở câu 1. Chuyển sang lược đồ quan hệ.
Chuong_2_Cac_mo_hinh_du_lieu.md
Displaying Chuong_2_Cac_mo_hinh_du_lieu.md.
