Bài tập Chương 4: Cơ Sở Dữ Liệu & SQL

CÂU 1

1. Lược đồ cơ sở dữ liệu

KHOA(MaKhoa, TenKhoa)

LOP(MaLop, TenLop, MaKhoa)

SINHVIEN(MaSV, HoTen, NgaySinh, Phai, MaLop)

MONHOC(MaMH, TenMH, SoTC)

KETQUA(MaSV, MaMH, Diem)

2. Yêu cầu

a/ Định nghĩa dữ liệu (DDL)

Viết lệnh tạo các bảng dữ liệu, tạo khoá chính, khoá ngoại (nếu có).

b/ Truy vấn dữ liệu (SQL / DQL)

Cho biết mã và tên những lớp thuộc khoa có tên CNTT.

Cho biết mã và họ tên những sinh viên phái nam thuộc lớp có mã lớp là 'L001'.

Cho biết mã và họ tên những sinh viên phái nam thuộc lớp có mã lớp là 'L001' hoặc phái nữ học lớp có mã là 'L002'.

Cho biết mã và họ tên những sinh viên phái nam thuộc lớp có tên lớp là '08 Đại học tin học'.

Liệt kê danh sách những môn học (MaMH) do sinh viên có mã 'sv001' đã học.

Liệt kê danh sách những môn học (MaMH, TenMH) do sinh viên có mã 'sv001' đã học.

Liệt kê danh sách những sinh viên (MaSV) có học môn với mã môn là 'mh001'.

Liệt kê danh sách những sinh viên (MaSV, HoTen) có học môn với mã môn là 'mh001'.

Cho biết mã khoa, tên khoa và số lớp trong từng khoa.

Mã và tên những khoa nào có số lớp trên 5.

Mã và tên những khoa có nhiều lớp nhất.

Cho biết mã sinh viên và số môn học của từng sinh viên.

Cho biết mã, họ tên và số môn học của từng sinh viên.

Cho biết mã và họ tên những sinh viên học trên 5 môn học.

Cho biết mã, họ tên những sinh viên học nhiều môn nhất.

Cho biết mã môn học và số sinh viên học của từng môn.

Cho biết mã môn học, tên môn học và số lượng sinh viên học tương ứng.

Cho biết mã và tên những môn học có ít nhất 20 sinh viên học.

Cho biết mã và tên những môn học có nhiều sinh viên học nhất.

Mã và tên những môn học nào không có sinh viên học.

CÂU 2

1. Lược đồ cơ sở dữ liệu

KHACH(MaKH, TenKH, DiaChi, DienThoai)

HOADON(MaHD, NgayLap, MaKH)

HANGHOA(MaHG, TenHG, DVT, NhaSX, LoaiHang)

CHITIETHD(MaHD, MaHG, SoLuong, DonGia)

2. Yêu cầu

a/ Định nghĩa dữ liệu (DDL)

Viết lệnh tạo các bảng dữ liệu, tạo khoá chính, khoá ngoại (nếu có).

b/ Truy vấn dữ liệu (SQL / DQL)

Cho biết mã và tên những khách hàng có địa chỉ ở TPHCM hay Hà Nội.

Khách hàng nào có mua hàng trong ngày 12/11/2025?

Khách hàng nào không mua hàng trong ngày 12/11/2025?

Ngày 15/02/2025, khách hàng Trần Văn Minh mua những mặt hàng nào (MaHG, TenHG, DVT)?

Mã và tên những mặt hàng nào không bán ra trong ngày 12/11/2025?

Cho biết mã hàng, tên hàng và tổng số lượng mặt hàng được bán ra tương ứng.

Mã và tên những mặt hàng nào bán chạy nhất trong ngày 12/11/2025?

Hoá đơn nào có trị giá cao nhất. Thông tin liệt kê gồm: mã hoá đơn, ngày lập.

Câu 3: Sinh viên đọc kỹ, phân tích diagram bên dưới:
<img width="811" height="524" alt="image" src="https://github.com/user-attachments/assets/c6b625dd-fec1-4482-b7c1-cda12f14295f" />

Câu 3.1/ Thục hiện các truy vấn sau bằng đại số quan hệ và dùng Sql
<img width="805" height="608" alt="image" src="https://github.com/user-attachments/assets/7923faa1-b4be-4633-b1e3-25e28bdc4f6e" />

Câu 3.2
<img width="886" height="745" alt="image" src="https://github.com/user-attachments/assets/1c6140b0-0a20-467f-b85e-20011ba05a60" />

Câu 3.3
<img width="858" height="397" alt="image" src="https://github.com/user-attachments/assets/5342f634-ffb6-440a-8a52-bb20c9eb7569" />

Câu 4: thực hiện viết truy vấn bằng đại số quan hệ và viết SQL
<img width="975" height="607" alt="image" src="https://github.com/user-attachments/assets/ebb8074d-bfe8-450b-ad20-4d894699c3d9" />
