# BÀI TẬP VỀ NHÀ SỐ 2: MSSV K225480106088 - TẠ PHẠM ĐÌNH HÒA - MÔN HỆ QUẢN TRỊ CƠ SỞ DỮ LIỆU

# DEADLINE: 23H59 NGÀY 25/03/2025
# ĐỀ BÀI
## BÀI TOÁN
- Tạo csdl quan hệ với tên QLSV gồm các bảng sau:
  + SinhVien(#masv,hoten,NgaySinh)
  + Lop(#maLop,tenLop)
  + GVCN(#@maLop,#@magv,#HK)
  + LopSV(#@maLop,#@maSV,ChucVu)
  + GiaoVien(#magv,hoten,NgaySinh,@maBM)
  + BoMon(#MaBM,tenBM,@maKhoa)
  + Khoa(#maKhoa,tenKhoa)
  + MonHoc(#mamon,Tenmon,STC)
  + LopHP(#maLopHP,TenLopHP,HK,@maMon,@maGV)
  + DKMH(#@maLopHP,#@maSV,DiemTP,DiemThi,PhanTramThi)
## YÊU CẦU
1. Thực hiện các hành động sau trên giao diện đồ hoạ để tạo cơ sở dữ liệu cho bài toán:
  + Tạo database mới, mô tả các tham số(nếu có) trong quá trình.
  + Tạo các bảng dữ liệu với các trường như mô tả, chọn kiểu dữ liệu phù hợp với thực tế (tự tìm hiểu)
  + Mỗi bảng cần thiết lập PK, FK(s) và CK(s) nếu cần thiết. (chú ý dấu # và @: # là chỉ PK, @ chỉ FK)
2. Chuyển các thao tác đồ hoạ trên thành lệnh SQL tương đương. lưu tất cả các lệnh SQL trong file: Script_DML.sql
# BÀI LÀM
## THỰC HIỆN TẠO CSDL BÀI TOÁN BẰNG UI
1. Tạo database mới, mô tả các tham số(nếu có) trong quá trình
   Tạo database mới tên QLSV:
   ![Screenshot 2025-03-24 202358](https://github.com/user-attachments/assets/b7c0d535-e8cb-48fa-828d-fb9fd663405f)

3. Tạo các bảng dữ liệu với các trường như mô tả, chọn kiểu dữ liệu phù hợp với thực tế
   Tạo các bảng và đặt khóa chính:
   
   ![Screenshot 2025-03-24 205008](https://github.com/user-attachments/assets/2548b0f2-b220-4351-b507-fc9d507c18aa)
   ![Screenshot 2025-03-24 205102](https://github.com/user-attachments/assets/34bb096e-65ce-4991-9e8b-ee2a2a53d6ef)
   ![Screenshot 2025-03-24 205206](https://github.com/user-attachments/assets/a2e23625-6bb6-4cd1-a390-e01f72ab3e90)
   ![Screenshot 2025-03-24 205224](https://github.com/user-attachments/assets/38b49b62-ddee-413f-805d-81da2a4f2a89)
   ![Screenshot 2025-03-24 205248](https://github.com/user-attachments/assets/e9d86ad2-2595-4a8d-9197-921b53bb7460)
   ![Screenshot 2025-03-24 205306](https://github.com/user-attachments/assets/4f687da6-c127-48c6-a88b-c2006312e3b8)
   ![Screenshot 2025-03-24 205321](https://github.com/user-attachments/assets/1380608d-1b6f-4389-a264-79c6df40cf16)
   ![Screenshot 2025-03-24 205335](https://github.com/user-attachments/assets/d6bd8b76-5302-4083-a484-97cbe5fa0f50)
   ![Screenshot 2025-03-24 205351](https://github.com/user-attachments/assets/5b0e10cd-2d3c-458a-85c2-33f2abc0d49c)
   
   Liên kết các khóa ngoại:
   
   ![Screenshot 2025-03-24 205151](https://github.com/user-attachments/assets/9d9691b8-8004-4793-9538-45a3f519e3f3)
   ![Screenshot 2025-03-24 205217](https://github.com/user-attachments/assets/adbda7cd-3ba0-4c80-b6e7-98c92fb7f217)
   ![Screenshot 2025-03-24 205235](https://github.com/user-attachments/assets/db7fe267-2107-4907-82cc-5e91d3bfa502)
   ![Screenshot 2025-03-24 205255](https://github.com/user-attachments/assets/d097e226-0b0e-449b-a08c-7fa84348f5e8)
   ![Screenshot 2025-03-24 205312](https://github.com/user-attachments/assets/1c041e1e-f5ef-4117-b0e0-66455370c292)
   ![Screenshot 2025-03-24 205328](https://github.com/user-attachments/assets/e4801a54-216e-4011-830e-6b4cb60fde3d)
   ![Screenshot 2025-03-24 205343](https://github.com/user-attachments/assets/e9cad4c3-f3e7-43eb-9242-b821a7095e54)
   ![Screenshot 2025-03-24 205402](https://github.com/user-attachments/assets/bc05976b-5c66-4449-ab0f-7e5c1d217d0d)
5. Thiết lập các khóa cho các bảng
## THỰC HIỆN TẠO CSDL TƯƠNG ĐƯƠNG BẰNG LỆNH SQL
CREATE DATABASE QLSV;
GO

USE QLSV;
GO

CREATE TABLE SinhVien (
    MaSV VARCHAR(13) PRIMARY KEY,
    TenSV NVARCHAR(50) NOT NULL,
    NgaySinh DATE,
);
GO

CREATE TABLE MonHoc (
    MaMon VARCHAR(20) PRIMARY KEY,
    TenMon NVARCHAR(50),
    STC INT
);
GO

CREATE TABLE Lop (
    MaLop VARCHAR(20) PRIMARY KEY,
    TenLop NVARCHAR(50),
);
GO

CREATE TABLE Khoa (
    MaKhoa VARCHAR(20) PRIMARY KEY,
    TenKhoa NVARCHAR(50) NOT NULL,
);
GO

CREATE TABLE BoMon (
    MaBM VARCHAR(20) PRIMARY KEY,
    TenBM NVARCHAR(50),
    MaKhoa VARCHAR(20) NOT NULL,
	FOREIGN KEY (MaKhoa) REFERENCES Khoa(MaKhoa)
);
GO

CREATE TABLE LopSV (
    MaLop VARCHAR(20),
    MaSV VARCHAR(13),
	ChucVu NVARCHAR(30),
    PRIMARY KEY (MaLop, MaSV),
    FOREIGN KEY (MaLop) REFERENCES Lop(MaLop),
    FOREIGN KEY (MaSV) REFERENCES SinhVien(MaSV)
);
GO

CREATE TABLE GiaoVien (
    MaGV VARCHAR(20) PRIMARY KEY,
    TenGV NVARCHAR(50),
	NgaySinh DATE,
    MaBM VARCHAR(20),
    FOREIGN KEY (MaBM) REFERENCES BoMon(MaBM)
);
GO

CREATE TABLE GVCN (
    MaGV VARCHAR(20),
    MaLop VARCHAR(20),
	HK INT,
	PRIMARY KEY (MaLop, MaGV, HK),
    FOREIGN KEY (MaLop) REFERENCES Lop(MaLop),
	FOREIGN KEY (MaGV) REFERENCES GiaoVien(MaGV)
);
GO

CREATE TABLE LopHP (
    MaLopHP VARCHAR(20) PRIMARY KEY,
    TenLopHP VARCHAR(20),
    HK INT,
	MaMon VARCHAR(20) NOT NULL,
	MaGV VARCHAR(20) NOT NULL,
    FOREIGN KEY (MaMon) REFERENCES MonHoc(MaMon),
    FOREIGN KEY (MaGV) REFERENCES GiaoVien(MaGV)
);
GO

CREATE TABLE DKMH (
    MaLopHP VARCHAR(20) PRIMARY KEY,
    MaSV VARCHAR(13) NOT NULL,
    DiemTP FLOAT,
	DiemThi FLOAT,
	PhanTramThi FLOAT,
    FOREIGN KEY (MaLopHP) REFERENCES LopHP(MaLopHP),
    FOREIGN KEY (MaSV) REFERENCES SinhVien(MaSV)
);
GO
