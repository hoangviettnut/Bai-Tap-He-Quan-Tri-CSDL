# BÀI TẬP VỀ NHÀ 03 - MÔN HỆ QUẢN TRỊ CSDL
## Sinh Viên: Lương Hoàng Việt - K225480106073 

# DEADLINE: 23H59 NGÀY 30/03/2025

## ĐIỀU KIỆN: (ĐÃ LÀM XONG BÀI 2)

## BÀI TOÁN: Sửa bài 2 để có csdl như sau:
  + SinhVien(#MSSV,Hovaten,NgaySinh)
  + Lop(#maLop,tenLop)
  + GVCN(#@maLop,#@maGV,#HK)
  + LopSV(#@maLop,#@MSSV,ChucVu)
  + GiaoVien(#maGV,Hovaten,NgaySinh,@maBM)
  + BoMon(#maBM,tenBM,@maKhoa)
  + Khoa(#maKhoa,tenKhoa)
  + MonHoc(#maMon,tenMon,STC)
  + LopHP(#maLopHP,TenLopHP,HK,@maMon,@maGV)
  + DKMH(#id_dk, @maLopHP,@maSV,DiemThi,PhanTramThi)
  + Diem(#id, @id_dk, diem)

## YÊU CẦU:
1. Sửa bảng DKMH và bảng Điểm từ bài tập 2 để có các bảng như yêu cầu.
2. Nhập dữ liệu demo cho các bảng (nhập có kiểm soát từ tính năng Edit trên UI của mssm)
3. Viết lệnh truy vấn để: Tính được điểm thành phần của 1 sinh viên đang học tại 1 lớp học phần.

## HÌNH THỨC LÀM BÀI:
1. Tạo file bai_tap3.md trên cùng repository của bài tập 2:
   Nội dung chứa đề bài, và ảnh chụp quá trình thao tác các yêu cầu khác.
2. Chụp ảnh quá trình sửa bảng DKMH và quá trình thêm bảng Diem, chú ý @ là FK, và thêm CK cho trường điểm
3. Hình sau khi chụp paste trực tiếp vào file bai_tap3.md trên github, cần mô tả các phần trên ảnh để tỏ ra là hiểu hết!
4. dùng tính năng: Tasks -> Generate Scrips => sinh ra file: bai_tap_3_schema.sql  (chỉ chứa lệnh tạo cấu trúc của db)
5. dùng tính năng: Tasks -> Generate Scrips => advance => Check Data only => sinh ra file: bai_tap_3_data.sql  (chỉ chứa dữ liệu đã nhập demo vào db)
6. Tạo diagram mô tả các PK, FK của db. Chụp hình kết quả các bảng có các đường nối 1-->nhiều
7. upload 2 file  bai_tap_3_schema.sql và bai_tap_3_data.sql lên repository.
8. nhớ commit để save nội dung file bai_tap3.md

# BÀI LÀM
## 1.Sửa bảng DKMH: ![SuaBangDKMH](https://github.com/user-attachments/assets/42d130d4-44f1-416d-a9bf-97c4a55d4f7c)
Thêm bảng Diem vào Database: ![TableDiem](https://github.com/user-attachments/assets/5663af06-5fa3-4b4d-9775-d8e94701446c)
Diagram giữa các bảng sau khi sửa lại từ BTVN_02: ![image-2](https://github.com/user-attachments/assets/d2709633-54ba-448d-9064-9c09fd3fd6a3)
## 2. Nhập dữ liệu demo cho các bảng
1. Nhập dữ liệu cho bảng SinhVien: ![image](https://github.com/user-attachments/assets/12f23849-67ad-46a2-ae19-84c23d170025)
2. Nhập dữ liệu cho bảng Lop: ![image-3](https://github.com/user-attachments/assets/76d8830d-a345-4350-9a6e-4491fb047770)
3. Nhập dữ liệu cho bảng LopSV: ![NhapLopSV](https://github.com/user-attachments/assets/d5840014-9cdc-452b-a0d4-c700af6c9846)
4. Nhập dữ liệu cho bảng Khoa: ![image-4](https://github.com/user-attachments/assets/e88106e5-dfeb-4ab6-b8bc-98ea3d4b3e7e)
5. Nhập dữ liệu cho bảng BoMon: ![image-5](https://github.com/user-attachments/assets/2c7c6183-8de3-48a9-afcb-df5fd77c0fa3)
6. Nhập dữ liệu cho bảng GiaoVien: ![image-6](https://github.com/user-attachments/assets/4a6c9e12-31fd-45ee-a6f1-809c5fa917b7)
7. Nhập dữ liệu cho bảng GVCN: ![image-7](https://github.com/user-attachments/assets/ce6c48d6-5a43-4da8-b590-331744d4c83c)
8. Nhập dữ liệu cho bảng MonHoc![image-8](https://github.com/user-attachments/assets/39c0a40c-22aa-4c4a-bbb8-e5379bcdc53a)
9. Nhập dữ liệu cho bảng LopHP:![image-9](https://github.com/user-attachments/assets/f49afdb0-d54f-4f49-82e2-62709d676fb3)
10. Nhập dữ liệu cho bảng DKMH: ![image-10](https://github.com/user-attachments/assets/37ad4fcd-39cf-40d6-9624-cef495acde90)
11. Nhập dữ liệu cho bảng Diem: ![image-11](https://github.com/user-attachments/assets/0f3f63dc-f627-4c2b-93af-5144d1188f34)
## 3. Viết lệnh truy vấn
Bảng sau khi viết lệnh truy vấn: ![image-12](https://github.com/user-attachments/assets/849a70d7-8a27-4b15-8080-651646fda875)
### Code Truy vấn
Từ dòng 312 trong file Code BTVN03.sql
