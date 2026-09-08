# Chương 4: Ngôn ngữ truy vấn SQL
**Môn Cơ sở dữ liệu**

## Ngôn ngữ truy vấn SQL
* Giới thiệu ngôn ngữ SQL
* Các lệnh khai báo cấu trúc
* Các lệnh cập nhật dữ liệu
* Lệnh truy vấn dữ liệu

## Ngôn ngữ SQL là gì?
SQL (Structured Query Language) là ngôn ngữ hỏi đáp, có cấu trúc, được dùng để khai thác cơ sở dữ liệu quan hệ.
SQL có các tiêu chuẩn:
* ANSI (American National Standards Institute)
* SQL-92 (SQL2)
* SQL-99 (SQL3) mở rộng từ SQL2...
* SQL-23 (Mở rộng thêm XML, JSON...)

## Các lệnh khai báo cấu trúc
Lệnh tạo cấu trúc bảng:
```sql
CREATE TABLE <tên_bảng> (   
	<Tên cột 1> <kiểu dữ liệu> [null | not null],    
	<Tên cột 2> <kiểu dữ liệu> [null | not null],    
	…    
	<Tên cột N> <kiểu dữ liệu> [null | not null],    
	[constraint <tên ràng buộc khóa chính> primary key (khóa chính)],    
	[constraint <tên ràng buộc khóa ngoại> foreign key (khóa ngọai) references <bảng>]
)
```

### Diễn giải Lệnh Create Table
* **Tên bảng:** Là chuỗi ký tự bất kỳ không chứa khoảng trắng. Không trùng với các từ khóa.
* **Tên cột:** Là chuỗi ký tự bất kỳ không chứa khoảng trắng. Không trùng với tên cột khác bên trong bảng. Thứ tự các cột trong bảng là không quan trọng.
* **Giá trị Null:** Là giá trị rỗng, sẽ được áp dụng khi người dùng không nhập dữ liệu vào bảng. Thuộc tính khoá chính bị ràng buộc Not Null.
* **Kiểu dữ liệu:** Qui định dạng dữ liệu mà cột sẽ lưu trữ bên trong bảng. Một số kiểu dữ liệu thông dụng trong hệ quản trị CSDL SQL Server: Char, Varchar, Nchar, Nvarchar, int, float, Numeric, Datetime.

### Ví dụ lệnh tạo cấu trúc bảng
Cho lược đồ CSDL như sau:
* `LOP(MaLop, TenLop, Siso)`
* `SINHVIEN(MaSV, HoTen, NgaySinh, Phai, MaLop)`
* `MONHOC(MaMH, TenMH, SoTC)`
* `KETQUA(MaSV, MaMH, Diem)`

Viết lệnh tạo các bảng tương ứng cho bảng LOP:
```sql
CREATE TABLE LOP(
	MaLop NCHAR(10) Not Null,
	TenLop NVARCHAR(50),
	Siso int,
	Constraint PK_Lop Primary Key(MaLop)
)
```
*Lưu ý: Các ràng buộc khoá chính, khoá ngoại có thể tạo sau khi tạo bảng.*

Ví dụ tạo bảng SINHVIEN:
```sql
CREATE TABLE SINHVIEN(
	MaSV Nchar(10) Not Null,
	HoTen Nvarchar(50),
	NgaySinh DateTime,
	MaLop Nchar(10),
	Constraint PK_SV Primary Key(MaSV),
    Constraint FK_SV_Lop Foreign Key (MaLop) Refercences LOP(MaLop)
)
```
*Lưu ý: Khi tạo ràng buộc khoá ngoại trong bảng phải đảm bảo bảng chứa khoá chính tương ứng đã được tạo trước. MaLop là thuộc tính khoá ngoại nên kiểu dữ liệu và chiều dài phải giống hoàn toàn với MaLop trong bảng LOP.*

## Xác định kiểu dữ liệu
Việc xác định kiểu dữ liệu phù hợp cho các cột là rất quan trọng, tránh sự ảnh hưởng đến dữ liệu trong quá trình vận hành cơ sở dữ liệu. Kiểu dữ liệu được xác định dựa vào dữ liệu cần lưu trữ khảo sát trong thực tế. Chiều dài dữ liệu được xác định sao cho bao phủ được giá trị lớn nhất của dữ liệu trong tương lai nhưng không nên quá thừa.

### Kiểu dữ liệu chuỗi ký tự
* **Char, Nchar:** Cấp phát vùng nhớ tĩnh. Chiều dài cố định. Bộ nhớ được cấp phát ngay khi tạo bảng. (Ví dụ: Char(10): Dữ liệu nhập: ‘A001’. Vẫn cấp phát 10 ô nhớ để lưu trữ chuỗi). Tốc độ xử lý nhanh hơn kiểu Varchar.
* **Varchar, NVarchar:** Cấp phát vùng nhớ động. Chiều dài biến đổi. Bộ nhớ chỉ được cấp phát khi nhập dữ liệu. (Ví dụ: Varchar(10): Dữ liệu nhập ‘A001’ chỉ cấp phát 4 ô nhớ lưu trữ vừa đủ chuỗi). Tốc độ xử lý chậm hơn kiểu Char.
* **Char, Varchar:** Không sử dụng cho dữ liệu Unicode - Dữ liệu nhập đặt trong cặp dấu nháy. Ví dụ: ‘A001’.
* **Nchar, NVarchar:** Sử dụng cho dữ liệu Unicode. Ký tự đầu N(National): Dạng dữ liệu được thông hiểu trên thế giới. Dữ liệu nhập có ký tự N phía trước. Ví dụ: N‘A001’.

## Lệnh sửa cấu trúc bảng
Sử dụng lệnh `ALTER TABLE` để thay đổi cấu trúc bảng. Các thay đổi thông thường là: Thêm cột, Xoá cột, Sửa kiểu dữ liệu của cột, Thêm/xoá ràng buộc (khoá chính, khoá ngoại và các ràng buộc khác).

* **Lệnh thêm cột:** `ALTER TABLE <tên_bảng> ADD <tên_cột> <kiểu_dữ_liệu>`
  * Ví dụ: `ALTER TABLE SINHVIEN ADD GhiChu Nvarchar(100)`
* **Lệnh xoá cột:** `ALTER TABLE <tên_bảng> DROP COLUMN <tên_cột>`
  * Ví dụ: `ALTER TABLE SINHVIEN DROP COLUMN GhiChu`
* **Lệnh sửa cột:** `ALTER TABLE <Tên_bảng> ALTER COLUMN <Tên_cột> <Kiểu_dữ_liệu_mới>`
  * Ví dụ: `ALTER TABLE SINHVIEN ALTER COLUMN GhiChu NVARCHAR(150)`
* **Lệnh thêm ràng buộc:** `ALTER TABLE <Tên_bảng> ADD CONTRAINT <cấu trúc contraint 1>, ...`
  * Ví dụ: `ALTER TABLE SINHVIEN ADD Constraint FK_SV_Lop Foreign Key (MaLop) Refercences LOP(MaLop)`
* **Lệnh xoá ràng buộc:** `ALTER TABLE <Tên_bảng> DROP CONSTRAINT <tên constraint 1>, ...`
  * Ví dụ: `ALTER TABLE KETQUA DROP Constraint FK_SV, FK_MH`

## Các lệnh cập nhật dữ liệu
Cập nhật dữ liệu gồm các thao tác: Thêm dữ liệu, Xoá dữ liệu, Sửa dữ liệu. Các thao tác này làm cho dữ liệu trong cơ sở dữ liệu bị thay đổi.

* **Lệnh thêm dữ liệu:**
  `INSERT INTO TênBảng[(Danh sách cột)] VALUES(Danh sách giá trị)`
  * Ví dụ: Thêm dữ liệu vào bảng MONHOC
    ```sql
    INSERT INTO MONHOC(MaMH, TenMH, SoTC)
    VALUES('101001756', N'Cấu trúc dữ liệu', 4), ('101001757', N'Cơ sở dữ liệu', 4)
    ```

* **Lệnh xoá dữ liệu:**
  `DELETE FROM TênBảng [WHERE <Điều kiện xoá>]`
  * Ví dụ: Xoá môn học có mã số là ‘101001756’
    ```sql
    DELETE FROM MONHOC WHERE MaMH= '101001756'
    ```

* **Lệnh sửa dữ liệu:**
  `UPDATE <Tên Bảng> SET <Tên cột>=<giá trị> [WHERE <Điều kiện sửa>]`
  * Ví dụ: Sửa số tín chỉ của môn học mã số ‘101001756’ có giá trị mới là 4
    ```sql
    UPDATE MONHOC SET SoTC=4 WHERE MaMH= '101001756'
    ```

## Truy vấn dữ liệu
Cấu trúc lệnh truy vấn:
```sql
SELECT [* | DISTINCT] <danh_sách_cột>
FROM <danh_sách_bảng> 
[WHERE <biểu_thức_điều_kiện>] 
[GROUP BY <danh_sách_tên_nhóm>] 
[HAVING <biểu_thức_điều_kiện_nhóm>] 
[ORDER BY {tên_cột_thứ_tự | số_thứ_tự_cột | biểu thức} [ASC | DESC]]
```

### Áp dụng truy vấn đơn giản
Ví dụ: Cho biết Mã và họ tên những sinh viên lớp ‘07DHTH’ ?
```sql
SELECT MaSV, HoTen
FROM SINHVIEN
WHERE MaLop= '07DHTH'
```
*Lưu ý: Trong một câu truy vấn, mệnh đề SELECT và FROM bắt buộc phải có. Các mệnh đề khác có thể không có tuỳ thuộc vào câu truy vấn.*

### Biểu thức kết nối
Cú pháp: `TênBảng1.TênCột1 = TênBảng2.TênCột2`
Ví dụ: Kết nối 2 bảng SINHVIEN và LOP
`SINHVIEN.MaLop = LOP.MaLop` (Khoá ngoại = Khoá chính)

### Sử dụng từ khoá AS
Từ khoá AS được dùng để đổi tên cột, tên bảng trong câu truy vấn.
Ví dụ: Cho biết mã và họ tên những sinh viên học lớp Đại học CNTT khoá 07
```sql
SELECT MASV, HOTEN AS SV07
FROM SINHVIEN, LOP
WHERE SINHVIEN.MALOP=LOP.MALOP AND TENLOP= N'Đại học CNTT khoá 07'
```
Hoặc dùng AS cho tên bảng:
```sql
SELECT sv.MASV, sv.HOTEN AS SV07
FROM SINHVIEN AS sv, LOP 
WHERE sv.MaLop=LOP.MaLop AND TenLop= N'Đại học CNTT khoá 07'
```

### Sử dụng ký hiệu ‘*’ và ‘%’
* **Ký hiệu ‘*’:** được dùng để lấy tất cả các cột trên bảng. Cú pháp: `Select *` hay `Select TênBảng.*`
* **Ký hiệu ‘%’:** được dùng để thay thế cho một chuỗi con bất kỳ, sử dụng trong mệnh đề Where với LIKE.
  * Cú pháp: `TênCột LIKE '%chuỗi'`, `TênCột LIKE 'chuỗi%'`, `TênCột LIKE '%chuỗi%'`
  * Ví dụ liệt kê những sinh viên có họ Trần: `Select * From SINHVIEN Where HoTen LIKE N'Trần%'`

### Từ khoá DISTINCT và BETWEEN...AND
* **Từ khoá DISTINCT:** dùng để loại bỏ dòng trùng trong kết quả câu truy vấn.
  * Cú pháp: `Select DISTINCT DanhSáchCột`
  * Ví dụ: `Select DISTINCT MaMH From KETQUA Where MaSV= '2001180021'`
* **Từ khoá BETWEEN…AND:** Dùng để thiết lập điều kiện trong một khoảng cho trước.
  * Cú pháp: `TênCột Between GiáTrịĐầu AND GiáTrịCuối`
  * Ví dụ: `Select MaSV, MaMH From KETQUA Where Diem Between 6 And 8` (Tương đương `Diem >= 6 And Diem <= 8`).

### Mệnh đề ORDER BY
Dùng để sắp xếp thứ tự kết quả truy vấn. ASC (Ascending): Sắp xếp tăng dần, DESC (Descending): Sắp xếp giảm dần. Có thể sắp xếp cùng lúc nhiều cột, độ ưu tiên sắp xếp từ trái sang phải.
* Ví dụ: Liệt kê danh sách tất cả sinh viên, sắp xếp tăng dần theo họ tên sinh viên, nếu trùng tên thì sắp giảm dần theo ngày sinh.
```sql
SELECT * FROM SINHVIEN ORDER BY HOTEN ASC, NGSINH DESC
```

### Các hàm thống kê
* `SUM(TênCột)`: Tính tổng
* `MAX(TênCột)`: Lớn nhất
* `MIN(TênCột)`: Nhỏ nhất
* `AVG(TênCột)`: Trung bình
* `COUNT(TênCột|*)`: Đếm số lượng
*Lưu ý: Các hàm này chỉ được đặt tại SELECT hoặc HAVING. Không được đặt trực tiếp trong WHERE.*
* Ví dụ: Cho biết số lần thi môn ‘TRR’ của sinh viên có mã số = ‘2001180021’
```sql
SELECT COUNT(LanThi) AS SoLanThi FROM KETQUA WHERE MaSV= '2001180021' AND MaMH = 'TRR'
```

### Mệnh đề GROUP BY và HAVING
* **GROUP BY:** được sử dụng để gom nhóm các bộ có cùng thuộc tính trong quan hệ, mỗi nhóm bao gồm tập hợp các bộ có cùng giá trị trên các thuộc tính gom nhóm. *Tập thuộc tính trong mệnh đề SELECT phải thuộc Tập thuộc tính trong mệnh đề GROUP BY.*
  * Ví dụ: Cho biết mã lớp và số sinh viên trong từng lớp
    ```sql
    SELECT MaLop, Count(MaSV) AS SoSV FROM SINHVIEN GROUP BY MaLop
    ```
* **HAVING:** Sử dụng cho điều kiện lọc trên các nhóm. Cú pháp: `HAVING BiểuThứcĐiềuKiện`.
  * Ví dụ: Liệt kê danh sách những lớp (MaLop) có trên 2 sinh viên
    ```sql
    SELECT MaLop FROM SINHVIEN GROUP BY MaLop HAVING Count(MaSV)>2
    ```

### Truy vấn lồng/truy vấn con (Subquery)
Là dạng thức mà một truy vấn này được nhúng vào trong một truy vấn khác. Có 2 dạng truy vấn lồng:
* **Lồng phân cấp:** Truy vấn con thực thi trước, kết quả của truy vấn con sẽ trả về cho truy vấn lớn thực hiện tiếp theo.
* **Lồng tương quan:** Truy vấn con và truy vấn lớn thực thi song song.
Một số từ khoá cho truy vấn lồng: `IN/NOT IN`, `ALL`, `ANY/SOME`, `EXISTS/ NOT EXISTS`.

* **Ví dụ truy vấn lồng phân cấp (dùng ALL):** Cho biết mã và tên môn học có số tín chỉ lớn nhất.
```sql
SELECT MAMH, TENMH FROM MONHOC WHERE SOTC >= ALL (SELECT SOTC FROM MONHOC)
```

* **Ví dụ truy vấn lồng tương quan (dùng EXISTS):** Cho biết mã và tên những môn học mà chưa có sinh viên nào học ?
```sql
SELECT MAMH, TENMH FROM MONHOC 
WHERE NOT EXISTS (SELECT * FROM KETQUA WHERE MONHOC.MAMH = KETQUA.MAMH)
```

* **Ví dụ truy vấn lồng phân cấp (dùng NOT IN):** Cho biết mã và tên những môn học mà chưa có sinh viên nào học ?
```sql
SELECT MAMH, TENMH FROM MONHOC 
WHERE MAMH NOT IN (SELECT MAMH FROM KETQUA)
```
