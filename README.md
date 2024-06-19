# Bai_tap_lon_HQTCSDL
# Pham Thi Hong Nhung K215480106063
## Các bước tạo csdl
## Tạo database
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/e550a90f-f71b-4dcc-b528-12b801f602f4)
```
•	nhân viên: 🔑Id , mã nhân viên, họ tên , ngày sinh , giới tính, số điện thoại , địa chỉ , số căn cước công dân . 
•	khách hàng : 🔑Id , mã khách hàng, họ tên , ngày sinh , giới tính, số điện thoại 
•	sân : 🔑Id , mã sân , tên sân , tình trạng sân, giá mỗi giờ
•	Đăng ký sân: 🔑Id , mã khách hàng , tên khách hàng , mã sân ,ngày , thời gian bắt đầu , thời gian kết thúc.
•	Lịch sân: 🔑Id , mã nhân viên, mã khách hàng, mã sân, ngày , giờ bắt đầu , giờ kết thúc . 
```
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/e73d80de-1612-43b6-8953-8a3dcfa6e7ba)
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/a9d5a9f4-4835-45a7-8802-68e97145e34c)
## Thêm cột giá mỗi giờ vào bảng sân
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/57a06040-b5ea-435a-bdcb-ad7eb6926fb2)
```
## Bảng Đăng nhập
-	Id: INT PRIMARY KEY IDENTITY
•	Khóa chính (PRIMARY KEY): Đảm bảo mỗi bản ghi là duy nhất.
•	IDENTITY: Tự động tăng giá trị cho mỗi bản ghi mới.
•	Kiểu dữ liệu INT: Sử dụng kiểu số nguyên để tiết kiệm không gian lưu trữ và tăng hiệu suất truy vấn.
-	Username: VARCHAR(50) UNIQUE
•	UNIQUE: Đảm bảo không có hai tên đăng nhập nào trùng nhau.
•	VARCHAR(50): Kiểu chuỗi ký tự có độ dài tối đa 50 ký tự, đủ để lưu trữ tên đăng nhập.
-	Password: VARCHAR(100): Kiểu chuỗi ký tự có độ dài tối đa 100 ký tự, đủ để lưu trữ mật khẩu mã hóa.
```
## Bảng Đăng ký sân
```
-	Id: INT PRIMARY KEY IDENTITY
•	Khóa chính (PRIMARY KEY): Đảm bảo mỗi bản ghi là duy nhất.
•	IDENTITY: Tự động tăng giá trị cho mỗi bản ghi mới.
•	Kiểu dữ liệu INT: Sử dụng kiểu số nguyên.
-	MaKhachHang: VARCHAR(50): Kiểu chuỗi ký tự để lưu mã khách hàng.
-	TenKhachHang: NVARCHAR(100) Kiểu chuỗi ký tự hỗ trợ Unicode để lưu tên khách hàng có dấu.
-	  MaSan: VARCHAR(50)  Kiểu chuỗi ký tự để lưu mã sân.
-	  Ngay: DATE :Kiểu dữ liệu ngày tháng để lưu ngày đặt sân.
-	  ThoiGianBatDau: TIME : Kiểu dữ liệu giờ phút để lưu thời gian bắt đầu.
-	  ThoiGianKetThuc: TIME : Kiểu dữ liệu giờ phút để lưu thời gian kết thúc.
-	  FOREIGN KEY (MaKhachHang) REFERENCES KhachHang(MaKhachHang)
•	FOREIGN KEY: Đảm bảo tính toàn vẹn dữ liệu, liên kết tới bảng KhachHang.
-	  FOREIGN KEY (MaSan) REFERENCES San(MaSan)
•	FOREIGN KEY: Đảm bảo tính toàn vẹn dữ liệu, liên kết tới bảng San.
```
## Bảng Lịch sân
```
Id: INT PRIMARY KEY IDENTITY
•	Khóa chính (PRIMARY KEY): Đảm bảo mỗi bản ghi là duy nhất.
•	IDENTITY: Tự động tăng giá trị cho mỗi bản ghi mới.
•	Kiểu dữ liệu INT: Sử dụng kiểu số nguyên.
-	  MaNhanVien: INT : Kiểu số nguyên để lưu mã nhân viên.
-	  MaKhachHang: INT : Kiểu số nguyên để lưu mã khách hàng.
-	  MaSan: INT : Kiểu số nguyên để lưu mã sân.
-	  Ngay: DATE : Kiểu dữ liệu ngày tháng để lưu ngày đặt sân.
-	  GioBatDau: TIME : Kiểu dữ liệu giờ phút để lưu giờ bắt đầu.
-	  GioKetThuc: TIME : Kiểu dữ liệu giờ phút để lưu giờ kết thúc.
-	  FOREIGN KEY (MaNhanVien) REFERENCES NhanVien(Id)
•	FOREIGN KEY: Đảm bảo tính toàn vẹn dữ liệu, liên kết tới bảng NhanVien.
-	 FOREIGN KEY (MaKhachHang) REFERENCES KhachHang(Id)
•	FOREIGN KEY: Đảm bảo tính toàn vẹn dữ liệu, liên kết tới bảng KhachHang.
-	  FOREIGN KEY (MaSan) REFERENCES San(Id)
•	FOREIGN KEY: Đảm bảo tính toàn vẹn dữ liệu, liên kết tới bảng San.
```
## Bảng Nhân viên
```
Id: INT PRIMARY KEY IDENTITY
•	Khóa chính (PRIMARY KEY): Đảm bảo mỗi bản ghi là duy nhất.
•	IDENTITY: Tự động tăng giá trị cho mỗi bản ghi mới.
•	Kiểu dữ liệu INT: Sử dụng kiểu số nguyên.
-	  MaNhanVien: VARCHAR(50) UNIQUE : Kiểu chuỗi ký tự và duy nhất để lưu mã nhân viên.
-	  HoTen: NVARCHAR(100): Kiểu chuỗi ký tự hỗ trợ Unicode để lưu tên nhân viên.
-	  NgaySinh: DATE : Kiểu dữ liệu ngày tháng để lưu ngày sinh.
-	  GioiTinh: NVARCHAR(10) : Kiểu chuỗi ký tự hỗ trợ Unicode để lưu giới tính.
-	  SoDienThoai: VARCHAR(20) : Kiểu chuỗi ký tự để lưu số điện thoại.
-	  DiaChi: NVARCHAR(MAX): Kiểu chuỗi ký tự hỗ trợ Unicode để lưu địa chỉ.
-	  SoCCCD: VARCHAR(20): Kiểu chuỗi ký tự để lưu số căn cước công dân.
```
## Bảng Khách hàng
```
Id: INT PRIMARY KEY IDENTITY
•	Khóa chính (PRIMARY KEY): Đảm bảo mỗi bản ghi là duy nhất.
•	IDENTITY: Tự động tăng giá trị cho mỗi bản ghi mới.
•	Kiểu dữ liệu INT: Sử dụng kiểu số nguyên.
-	  MaKhachHang: VARCHAR(50) UNIQUE : Kiểu chuỗi ký tự và duy nhất để lưu mã khách hàng.
-	  HoTen: NVARCHAR(100) : Kiểu chuỗi ký tự hỗ trợ Unicode để lưu tên khách hàng.
-	  NgaySinh: DATE: Kiểu dữ liệu ngày tháng để lưu ngày sinh.
-	  GioiTinh: NVARCHAR(10): Kiểu chuỗi ký tự hỗ trợ Unicode để lưu giới tính.
-	  SoDienThoai: VARCHAR(20) : Kiểu chuỗi ký tự để lưu số điện thoại.
```
## Bảng Sân
```
Id: INT PRIMARY KEY IDENTITY
•	Khóa chính (PRIMARY KEY): Đảm bảo mỗi bản ghi là duy nhất.
•	IDENTITY: Tự động tăng giá trị cho mỗi bản ghi mới.
•	Kiểu dữ liệu INT: Sử dụng kiểu số nguyên.
-	  MaSan: VARCHAR(50) UNIQUE : Kiểu chuỗi ký tự và duy nhất để lưu mã sân.
-	  TenSan: NVARCHAR(100): Kiểu chuỗi ký tự hỗ trợ Unicode để lưu tên sân.
-	  TinhTrangSan: NVARCHAR(50) : Kiểu chuỗi ký tự hỗ trợ Unicode để lưu tình trạng sân.
-	  Gia_gio: FLOAT: Kiểu số thực để lưu giá thuê sân theo giờ.
```

# Thêm dữ liệu vào bảng
#1. Bảng Nhân viên
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/69b64106-5bdf-443c-a648-b2655483a87a)
#2. Bảng Khách hàng
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/371e9a83-ae17-4b24-a961-c62262b6efab)
#3. Bảng Sân
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/8c557113-f612-4023-9b02-7fc2b8428fcd)
#4. Bảng Đăng ký sân
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/60a0c696-516c-4fb6-a5c8-39c4fac2211d)
#5. Bảng Lịch sân
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/da11d437-70e3-47d6-9680-9d074359b0fb)
------------------
# Function tính tiền cho khách hàng đang sử dụng sân
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/1767087d-c9df-40bb-ad92-76bdfa681d6d)
# Function kiểm tra lịch đặt sân 
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/145e92e1-a571-4683-9e24-39a122462a9d)
# Test ví dụ 
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/7aad82eb-99fc-45ad-8441-17282a0173e6)
# Function đặt lịch sân
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/899a35b5-0798-470a-aa4c-2a5d70548821)
# Kiểm tra lịch đặt thử
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/0c3b2b3d-aa11-4658-ace7-916dd77dacec)
# Funtion kiểm tra số lần đặt lịch sân 
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/3a8aece7-334c-4e90-af02-e7b828db023c)
# Nâng cấp funtion tính tiền sân kết hợp với đặt lịch sẫn để giảm giá
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/035ce848-bc3e-4864-9333-533c7a0335f6)
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/f4947759-a27c-4fda-a101-e72bf55d5ec1)
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/108c167d-9ced-4a8e-b9ca-0de8fe914a8c)
# Funtion tìm kiếm thông tin khách hàng 
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/e8f904c3-4d3a-4482-9a2c-f11b7c73e61a)
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/a7fc9881-4d75-4796-9e4b-e20f53d21b7b)
# Funtion tính tổng tiền sân trong 1 ngày 
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/1af94f98-737b-44d3-b615-e508c5a095ac)
![image](https://github.com/PhamThiHongNhungKMT/Bai_tap_lon_HQTCSDL/assets/173180776/e103b7cf-43c8-4d71-8c2b-7f3c208d39a6)





