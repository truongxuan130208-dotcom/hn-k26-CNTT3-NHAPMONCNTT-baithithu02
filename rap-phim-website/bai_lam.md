# BÀI LÀM – (ĐỀ LUYỆN TẬP SỐ 02)

- **Mã đề:** 02
- **Họ tên:phạm xuân trường**
- **Lớp:cntt3**
- **Link repository:**
- **Hệ điều hành (Windows/macOS):windows**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -Force  
                                                                   mv .\bien_ban_ban_giao.txt .\docs\                                           
                                   mkdir backup                                                        cp .\data\bang_ve_thang_11.xlsx .\backup\ 
                                     rm .\cache_991.tmp     
                                     cd .\logs\
                                     ls
                                     cd..


```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
                                                                                                                                                            
Mode                 LastWriteTime         Length Name                                                                                                      
----                 -------------         ------ ----                                                                                                      
d-----        11/10/2026   1:04 AM                backup                                                                                                    
d-----         11/9/2026   6:37 PM                data                                                                                                      
d-----         11/9/2026   6:39 PM                docs                                                                                                      
d-----         11/9/2026   6:35 PM                evidence                                                                                                  
d-----         11/9/2026  11:34 PM                logs                                                                                                      
d-----         11/9/2026   3:40 PM                web                                                                                                       
-a----         11/9/2026   3:40 PM             82 .env                                                                                                      
-a----        11/10/2026  12:38 AM             39 .env.example                                                                                              
-a----        11/10/2026  12:36 AM              4 .gitignore                                                                                                
-a----         11/9/2026   3:40 PM           2611 bai_lam.md                                                                                                
-a----        11/10/2026  12:25 AM            251 README.md                                                                                                 
-a----         11/9/2026  11:34 PM            366 tong_hop.ps1                                                                                              
                                                                                                                                                            
                                                                                                                                                            
    Directory: C:\Users\tTRUONG\Downloads\Luyen_Tap_11_9\starter-kit\rap-phim-website\backup                                                                
                                                                                                                                                            
                                                                                                                                                            
Mode                 LastWriteTime         Length Name                                                                                                      
----                 -------------         ------ ----                                                                                                      
-a----        11/10/2026   1:04 AM          11407 bang_ve_thang_11.xlsx                                                                                     
-a-h--        11/10/2026  12:53 AM            165 ~$bang_ve_thang_11.xlsx                                                                                   
                                                                                                                                                            
                                                                                                                                                            
    Directory: C:\Users\tTRUONG\Downloads\Luyen_Tap_11_9\starter-kit\rap-phim-website\data                                                                  
                                                                                                                                                            
                                                                                                                                                            
Mode                 LastWriteTime         Length Name                                                                                                      
----                 -------------         ------ ----                                                                                                      
-a----         11/9/2026   3:40 PM           5693 bang_ve_thang_11.xlsx                                                                                     
                                                                                                                                                            
                                                                                                                                                            
    Directory: C:\Users\tTRUONG\Downloads\Luyen_Tap_11_9\starter-kit\rap-phim-website\docs                                                                  
                                                                                                                                                            
                                                                                                                                                            
Mode                 LastWriteTime         Length Name                                                                                                      
----                 -------------         ------ ----                                                                                                      
-a----         11/9/2026   3:40 PM            172 bien_ban_ban_giao.txt                                                                                     
                                                                                                                                                            
                                                                                                                                                            
    Directory: C:\Users\tTRUONG\Downloads\Luyen_Tap_11_9\starter-kit\rap-phim-website\logs                                                                  
                                                                                                                                                            
                                                                                                                                                            
Mode                 LastWriteTime         Length Name                                                                                                      
----                 -------------         ------ ----                                                                                                      
-a----         11/9/2026   6:42 PM            572 loi_error.txt                                                                                             
-a----         11/9/2026   3:40 PM            893 server.log                                                                                                
-a----         11/9/2026  11:37 PM            766 tong_hop.txt                                                                                              
                                                                                                                                                            
                                                                                                                                                            
    Directory: C:\Users\tTRUONG\Downloads\Luyen_Tap_11_9\starter-kit\rap-phim-website\web                                                                   
                                                                                                                                                            
                                                                                                                                                            
Mode                 LastWriteTime         Length Name                                                                                                      
----                 -------------         ------ ----                                                                                                      
d-----         11/9/2026   3:40 PM                images                                                                                                    
-a----        11/10/2026  12:51 AM            620 app.js                                                                                                    
-a----        11/10/2026  12:46 AM            553 index.html                                                                                                
-a----         11/9/2026   3:40 PM            460 style.css                                                                                                 
                                                                                                                                                            
                                                                                                                                                            
    Directory: C:\Users\tTRUONG\Downloads\Luyen_Tap_11_9\starter-kit\rap-phim-website\web\images                                                            
                                                                                                                                                            
                                                                                                                                                            
Mode                 LastWriteTime         Length Name                                                                                                      
----                 -------------         ------ ----                                                                                                      
-a----         11/9/2026   3:40 PM            342 logo-cinebox.png                                                                              
                                                            

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng ERROR

```shell
gc .\logs\server.log |Select-String "ERROR" > .\logs\Loi_error.txt                                                                                   

```

### 2 dòng đầu tiên trong logs/loi_error.txt

```text
2026-11-01 09:25:40 ERROR POST /api/mua-ve
2026-11-01 09:29:11 ERROR POST /api/thanh-toan-qr


```

### b) Lệnh đếm số dòng WARNING và kết quả

```shell
 (gc .\logs\server.log |Select-String "WARNING").COUNT                                                                                              

```

```text
5
```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
 Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass         .\tong_hop.ps1                                                                                    

```

### Nội dung file logs/tong_hop.txt

```text
Dang tao bao cao...                                                                                             
Hoan thanh!         

```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] README.md: Heading 1, mô tả có **in đậm** và _in nghiêng_, bảng, code block, task list, blockquote
- [ ] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [ ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | -------------------------- | --------------------------- | -------------- |
| 1   |           network          |    Tên file ảnh sai                     |     Sửa tên file ảnh cho đúng           |
| 2   |            Console                |          app.js:18 Uncaught ReferenceError: hienThiBangGia is not defined                   |       Đổi tên dòng 18 thành hienThiBangGiaVe         |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:**
- **Expected:**
- **Actual:**
- **Log:**

### Câu tìm kiếm Google

```text
(Ghi câu tìm kiếm vào đây – xoá dòng này)

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/ban_ve_thang_11.xlsx`, không cần ghi vào đây.
