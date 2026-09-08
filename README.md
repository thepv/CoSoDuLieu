# Bài giảng môn Cơ sở dữ liệu (Database) - Update 2026

Chào mừng bạn đến với tài liệu học tập môn **Cơ sở dữ liệu**. Thư mục này chứa toàn bộ nội dung bài giảng, lý thuyết và bài tập thực hành được biên soạn lại dưới định dạng Markdown để tiện theo dõi, lưu trữ và tra cứu.

## 📚 Mục lục tài liệu

Dưới đây là danh sách các tệp tài liệu tương ứng với từng chương của môn học:

*   **[Chương 1: Khái niệm và kiến trúc hệ CSDL](Chuong_1_Khai_niem_va_kien_truc_he_CSDL.md)**
    *   Khái niệm về dữ liệu, Cơ sở dữ liệu (CSDL) và Hệ quản trị CSDL (DBMS).
    *   Kiến trúc 3 mức của hệ CSDL.
    *   Các ngôn ngữ của DBMS (DDL, DML, SQL, DCL) và các đối tượng sử dụng.
    *   Tổng quan về các mô hình dữ liệu (Cổ điển và NoSQL hiện đại như Document, Wide Column, Graph, Key-Value, Vector).

*   **[Chương 2: Các mô hình dữ liệu](Chuong_2_Cac_mo_hinh_du_lieu.md)**
    *   **Mô hình thực thể kết hợp (ER/ERD):** Thực thể, thuộc tính, mối kết hợp (1-1, 1-N, N-N).
    *   **Mô hình quan hệ:** Quan hệ, bộ (tuple), thuộc tính, miền giá trị, các loại khóa (khóa chính, khóa ngoại, siêu khóa).
    *   Hướng dẫn quy tắc chuyển đổi từ Mô hình ER sang Mô hình quan hệ.

*   **[Chương 3: Đại số quan hệ](Chuong_3_Dai_so_quan_he.md)**
    *   Các phép toán tập hợp: Hội, Giao, Trừ, Tích Đề-các.
    *   Các phép toán quan hệ: Chọn, Chiếu, Kết (có điều kiện, tự nhiên), Chia, Đổi tên.
    *   Ví dụ minh họa chi tiết cho từng phép toán.

*   **[Bài tập Chương 3: Đại số quan hệ](Chuong_3_Cau_hoi_va_bai_tap_Dai_so_quan_he.md)**
    *   Tổng hợp các câu hỏi lý thuyết ôn tập chương.
    *   Bài tập tính toán giá trị biểu thức đại số quan hệ trên các bảng dữ liệu cho trước.
    *   Bài tập thực hành chuyển đổi yêu cầu truy vấn tự nhiên sang biểu thức đại số quan hệ.

*   **[Chương 4: Ngôn ngữ truy vấn SQL](Chuong_4_Ngon_ngu_truy_van_SQL.md)**
    *   Giới thiệu ngôn ngữ SQL và các tiêu chuẩn.
    *   **Lệnh khai báo cấu trúc (DDL):** `CREATE TABLE`, `ALTER TABLE`, quản lý ràng buộc (Constraint) và định nghĩa kiểu dữ liệu.
    *   **Lệnh cập nhật dữ liệu (DML):** `INSERT`, `UPDATE`, `DELETE`.
    *   **Lệnh truy vấn dữ liệu (DQL):** Cú pháp `SELECT`, các toán tử, `DISTINCT`, `BETWEEN`, `LIKE`, hàm thống kê, `GROUP BY`, `HAVING`, `ORDER BY`.
    *   Các loại truy vấn lồng (Subquery): Phân cấp và Tương quan (`IN`, `EXISTS`, `ALL`).

## 🛠 Hướng dẫn sử dụng

1.  **Lộ trình học tập:** Nên đọc tài liệu theo thứ tự từ Chương 1 đến Chương 4 để nắm vững từ khái niệm cơ bản, cách thiết kế mô hình dữ liệu, nền tảng toán học (Đại số quan hệ) cho đến ngôn ngữ lập trình thực tế (SQL).
2.  **Thực hành:** Sau khi hoàn thành lý thuyết Chương 3 và Chương 4, hãy bắt tay vào làm [Bài tập Chương 3](Chuong_3_Cau_hoi_va_bai_tap_Dai_so_quan_he.md) và tự viết các câu lệnh SQL tương ứng để đối chiếu.
3.  **Công cụ hỗ trợ:** Để thực hành lệnh SQL (Chương 4), bạn có thể cài đặt các Hệ quản trị CSDL thông dụng như MS SQL Server, MySQL hoặc PostgreSQL.
