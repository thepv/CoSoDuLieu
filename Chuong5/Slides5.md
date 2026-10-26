# 📚 Cơ sở dữ liệu — Chương 5: Ràng buộc toàn vẹn

## 🧭 Nội dung

- [Giới thiệu môn học](#-giới-thiệu-môn-học)
- [Chuẩn đầu ra, tài liệu và đánh giá](#-chuẩn-đầu-ra-tài-liệu-và-đánh-giá)
- [Chương 5: Ràng buộc toàn vẹn](#-chương-5-ràng-buộc-toàn-vẹn)
  - [1. Khái niệm](#1--khái-niệm-ràng-buộc-toàn-vẹn)
  - [2. Đặc trưng](#2--đặc-trưng-của-ràng-buộc-toàn-vẹn)
  - [3. Phân loại](#3--phân-loại-ràng-buộc-toàn-vẹn)
  - [4. Các loại ràng buộc và ví dụ](#4--các-loại-ràng-buộc-và-ví-dụ)
- [Bài tập chương 5](#-bài-tập-chương-5)

---

## 🎓 Giới thiệu môn học

- **Tên môn học:** Cơ sở dữ liệu (*Database*)
- **Ngành:** Công nghệ thông tin, Khoa học dữ liệu, An toàn thông tin và Trí tuệ nhân tạo
- **Số tín chỉ:** 3 (3,0)
- **Thời lượng:** 45 tiết lý thuyết trên lớp + 90 tiết học ở nhà
- **Môn học song hành:** Thực hành cơ sở dữ liệu
- **Vị trí:** Học kỳ 3
- **Khối kiến thức:** Cơ sở ngành
- **Nội dung kiến thức:** Cơ sở dữ liệu quan hệ

## 🗂️ Chuẩn đầu ra, tài liệu và đánh giá

Slide giới thiệu các mục **Chuẩn đầu ra môn học**, **Tài liệu tham khảo** và **Phương pháp đánh giá**  

---

## 🛡️ Chương 5: Ràng buộc toàn vẹn

### 1. 🔎 Khái niệm ràng buộc toàn vẹn

**Ràng buộc toàn vẹn (Integrity Constraints)** là các quy tắc, điều kiện được thiết lập trên cơ sở dữ liệu nhằm đảm bảo tính đúng đắn của cơ sở dữ liệu trong quá trình người dùng tương tác.

Các thao tác cập nhật dữ liệu có thể làm thay đổi dữ liệu trong CSDL:

- ➕ **Thêm dữ liệu**
- 🗑️ **Xóa dữ liệu**
- ✏️ **Sửa dữ liệu**

### 2. 🧩 Đặc trưng của ràng buộc toàn vẹn

| Đặc trưng | Ý nghĩa |
|---|---|
| **Bối cảnh** | Các quan hệ mà ràng buộc toàn vẹn có thể bị vi phạm khi có thao tác cập nhật dữ liệu trên các quan hệ đó. |
| **Nội dung** | Mô tả hoặc biểu diễn hình thức các quy tắc, điều kiện không được vi phạm trong CSDL. |
| **Tầm ảnh hưởng** | Cho biết thao tác cập nhật có thể làm vi phạm ràng buộc hay không: `+` là có thể vi phạm; `−` là không vi phạm. |

### 3. 🧭 Phân loại ràng buộc toàn vẹn

**Ràng buộc trên một quan hệ**
- 🔗 Ràng buộc liên bộ
- 🎯 Ràng buộc miền giá trị
- 🔀 Ràng buộc liên thuộc tính

**Ràng buộc trên nhiều quan hệ**
- 🧷 Ràng buộc tham chiếu
- 🔗 Ràng buộc liên bộ – liên quan hệ
- 🔀 Ràng buộc liên thuộc tính – liên quan hệ

### 4. 🧪 Các loại ràng buộc và ví dụ

#### 4.1. 🔗 Ràng buộc liên bộ

Là ràng buộc giữa các bộ giá trị trong cùng một quan hệ. Sự tồn tại của một hay nhiều bộ có thể phụ thuộc vào sự tồn tại của một hay nhiều bộ khác trong cùng quan hệ. Ràng buộc toàn vẹn về khóa là một trường hợp của ràng buộc liên bộ.

**Ví dụ — quan hệ môn học**

```text
MONHOC(MaMH, TenMH, SoTC)
```

Hai bộ khác nhau bất kỳ phải có mã môn học khác nhau.

**Biểu diễn hình thức**

```text
∀ t1, t2 ∈ MONHOC, nếu t1 ≠ t2 thì t1.MaMH ≠ t2.MaMH
```

**Bối cảnh:** `MONHOC`

| Quan hệ | Thêm | Xóa | Sửa |
|---|:---:|:---:|---|
| `MONHOC` | + | − | +(MaMH) |

#### 4.2. 🎯 Ràng buộc miền giá trị

Quy định các giá trị mà một thuộc tính có thể nhận.

**Ví dụ:** Số tín chỉ của môn học phải lớn hơn hoặc bằng 1.

```text
MONHOC(MaMH, TenMH, SoTC)
∀ t ∈ MONHOC: t.SoTC ≥ 1
```

**Bối cảnh:** `MONHOC`

| Quan hệ | Thêm | Xóa | Sửa |
|---|:---:|:---:|---|
| `MONHOC` | + | − | +(SoTC) |

#### 4.3. 🔀 Ràng buộc liên thuộc tính

Là ràng buộc giữa các thuộc tính trong cùng một quan hệ.

**Ví dụ — quan hệ khóa học**

```text
KHOAHOC(MaKH, TenKH, NgayBD, NgayKT)
∀ t ∈ KHOAHOC: t.NgayKT > t.NgayBD
```

Mỗi khóa học phải có ngày kết thúc sau ngày bắt đầu.

**Bối cảnh:** `KHOAHOC`

| Quan hệ | Thêm | Xóa | Sửa |
|---|:---:|:---:|---|
| `KHOAHOC` | + | − | +(NgayBD, NgayKT) |

#### 4.4. 🧷 Ràng buộc tham chiếu

Là ràng buộc về phụ thuộc tồn tại hoặc ràng buộc về khóa ngoại. Loại ràng buộc này phổ biến vì các quan hệ trong CSDL có mối liên hệ mật thiết với nhau. Một bộ được thêm vào một quan hệ là hợp lệ khi tồn tại bộ tương ứng ở quan hệ khác.

**Ví dụ — lớp và sinh viên**

```text
LOP(MaLop, TenLop)
SINHVIEN(MaSV, HoTen, Phai, MaLop)
```

Mỗi sinh viên phải thuộc về một lớp đã tồn tại.

**Biểu diễn hình thức**

```text
∀ t ∈ SINHVIEN, ∃ u ∈ LOP: t.MaLop = u.MaLop
```

**Bối cảnh:** `LOP`, `SINHVIEN`

| Quan hệ | Thêm | Xóa | Sửa |
|---|:---:|:---:|---|
| `LOP` | − | + | +(MaLop) |
| `SINHVIEN` | + | − | +(MaLop) |

#### 4.5. 🔗 Ràng buộc liên bộ – liên quan hệ

Là ràng buộc xảy ra giữa các bộ trên nhiều quan hệ khác nhau.

**Ví dụ — hóa đơn và chi tiết hóa đơn**

```text
HOADON(MaHD, NgayLap, KH)
CHITIETHD(MaHD, MaHG, SoLuong, DonGia)
```

Mỗi hóa đơn phải có ít nhất một mặt hàng.

**Biểu diễn hình thức**

```text
∀ t ∈ HOADON, ∃ u ∈ CHITIETHD: t.MaHD = u.MaHD
```

**Bối cảnh:** `HOADON`, `CHITIETHD`

| Quan hệ | Thêm | Xóa | Sửa |
|---|:---:|:---:|---|
| `HOADON` | + | − | +(MaHD) |
| `CHITIETHD` | − | + | +(MaHD) |

#### 4.6. 🔀 Ràng buộc liên thuộc tính – liên quan hệ

Là ràng buộc xảy ra giữa các thuộc tính trên nhiều quan hệ khác nhau.

**Ví dụ — đặt hàng và giao hàng**

```text
DATHANG(MaDH, MaKH, NgayDH)
GIAOHANG(MaGH, MaDH, NgayGH)
```

Mỗi phiếu giao hàng có ngày giao hàng sau hoặc cùng ngày đặt hàng.

**Biểu diễn hình thức**

```text
∀ t ∈ GIAOHANG, ∃ u ∈ DATHANG:
    t.MaDH = u.MaDH ∧ t.NgayGH ≥ u.NgayDH
```

**Bối cảnh:** `DATHANG`, `GIAOHANG`

| Quan hệ | Thêm | Xóa | Sửa |
|---|:---:|:---:|---|
| `GIAOHANG` | + | − | +(MaDH, NgayGH) |
| `DATHANG` | − | + | +(MaDH, NgayDH) |

---

## 📝 Bài tập chương 5

Cho lược đồ cơ sở dữ liệu:

```text
PHONGBAN(MaPH, TenPH, DiaDiem)
NHANVIEN(MaNV, HoTen, Tuoi, Phai, Luong, MaPH)
DEAN(MaDA, TenDA, NgayBD, NgayKT)
PHANCONG(MaNV, MaDA, NgayPC)
```

Hãy biểu diễn các ràng buộc toàn vẹn sau:

1. Các ràng buộc liên bộ có trên mỗi quan hệ.
2. Các ràng buộc tham chiếu có trên `NHANVIEN`, `PHANCONG`.
3. Ràng buộc miền giá trị có trên `NHANVIEN`.
4. Ràng buộc liên thuộc tính có trên `DEAN`.
5. Ràng buộc liên thuộc tính – liên quan hệ có trên `DEAN`, `PHANCONG`.
6. Mỗi đề án được phân công cho ít nhất một nhân viên.

---
