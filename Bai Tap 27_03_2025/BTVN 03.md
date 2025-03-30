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
## 1.Sửa bảng DKMH: ![alt text](SuaBangDKM.png)
Thêm bảng Diem vào Database: ![alt text](TableDiem.png)
Diagram giữa các bảng sau khi sửa lại từ BTVN_02: ![alt text](image-2.png)
## 2. Nhập dữ liệu demo cho các bảng
1. Nhập dữ liệu cho bảng SinhVien: ![alt text](image.png)
2. Nhập dữ liệu cho bảng Lop: ![alt text](image-3.png)
3. Nhập dữ liệu cho bảng LopSV: ![alt text](image-1.png)
4. Nhập dữ liệu cho bảng Khoa: ![alt text](image-4.png)
5. Nhập dữ liệu cho bảng BoMon: ![alt text](image-5.png)
6. Nhập dữ liệu cho bảng GiaoVien: ![alt text](image-6.png)
7. Nhập dữ liệu cho bảng GVCN: ![alt text](image-7.png)
8. Nhập dữ liệu cho bảng MonHoc![alt text](image-8.png)
9. Nhập dữ liệu cho bảng LopHP:![alt text](image-9.png)
10. Nhập dữ liệu cho bảng DKMH: ![alt text](image-10.png)
11. Nhập dữ liệu cho bảng Diem: ![alt text](image-11.png)
## 3. Viết lệnh truy vấn
Bảng sau khi viết lệnh truy vấn: ![alt text](image-12.png)
### Code Truy vấn
SELECT 
    sv.MSSV,
    sv.Hovaten AS TenSinhVien,
    lhp.maLopHP,
    lhp.TenLopHP,
    mh.tenMon AS MonHoc,
    gv.Hovaten AS TenGiaoVien,
    d.diem AS DiemThanhPhan,
    dkmh.DiemThi,
    dkmh.PhanTramThi
FROM 
    SinhVien sv
JOIN 
    DKMH dkmh ON sv.MSSV = dkmh.MSSV
JOIN 
    Diem d ON dkmh.id_dk = d.id_dk
JOIN 
    LopHP lhp ON dkmh.maLopHP = lhp.maLopHP
JOIN 
    MonHoc mh ON lhp.maMon = mh.maMon
JOIN 
    GiaoVien gv ON lhp.maGV = gv.maGV
WHERE 
    (sv.MSSV = 'K1' AND lhp.maLopHP = 'LHP1')
    OR (sv.MSSV = 'K2' AND lhp.maLopHP = 'LHP2')
    OR (sv.MSSV = 'K3' AND lhp.maLopHP = 'LHP3');
