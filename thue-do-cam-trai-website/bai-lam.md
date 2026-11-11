


# BÀI LÀM – HACKATHON 02

  

-  **Mã đề:** 05

-  **Họ tên:** MAI HUY HOÀNG 

-  **Lớp:** CNTT1 

-  **Link repository:** https://github.com/maihuyhoang19012008-jpg/HNKS26CNTT1_NHAP-MON-CNTT_HACKATHON02-

-  **Hệ điều hành (Windows/macOS):** WIN

  

## 4.2. Thao tác máy tính cơ bản bằng CLI

  

### Các lệnh đã chạy

  

```shell
pwd 
cd thue-do-cam-trai-website
mkdir logs, evidence, data New-Item .env, .env.example, .gitignore, README.md 
-ItemType File 
Get-ChildItem
dir -Force
copy data\don_thue_thang_5.xlsx \backup
Remove-Item \*.tmp
`Set-Location logs``Get-ChildItem -Force``Set-Location \`
  

```


### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

  

```text

Get-ChildItem -Recurse -Force
  

```

  logs/, evidence/, data/ file ẩn .env, .gitignore, .env.example.

## 4.3. Lọc log truy cập website

  

### a) Lệnh lọc các dòng status=500

  

```shell

Select-String -Path .\logs\access.log -Pattern "status=500" | ForEach-Object { $_.Line } | Out-File .\logs\loi_500.txt -Encoding utf8 Get-Content .\logs\loi_500.txt -TotalCount 2

```

  

### 2 dòng đầu tiên trong logs/


```text
2026-05-28 08:17:12 POST /api/kho-do status=500
2026-05-28 08:20:23 POST /api/thue-do status=500
  

```

  

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
Select-String -Path .\logs\access.log -Pattern "status=404").Count

```

```text
4


```

  

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

  

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

  

```shell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass .\tong_hop.ps1
```

  

### Nội dung file logs/tong_hop.txt

```text
Get-Content .\logs\tong_hop.txt
  

```

  

## 4.5. README.md và bảo vệ thông tin bí mật

  

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

  

- [x] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote

- [x] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)

- [x] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

  

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

  

### Bảng lỗi

  

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 |Console |ReferenceError: ... is not defined (file app.js) |Kiểm tra lại tên biến , thứ tự load script trong HTML |
| 2 |Network  |style.css trả về 404 Not Found |Sửa đường dẫn href cho đúng, hoặc tạo file còn thiếu |

  

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

  !(console.jpg)[(console.1.png)]

### Báo cáo lỗi gửi trưởng nhóm

  

**Context**: Mở trang index.html bằng Live Server, trình duyệt Chrome bản mới nhất.
 **Expected**: Trang hiển thị đầy đủ CSS và chạy được chức năng nút bấm. 
 **Actual**: CSS không áp dụng, nút bấm không phản hồi. 
 **Log**: Failed to load resource: the server responded with a status of 404 (Not Found) — style.css; Uncaught TypeError: ... at app.js:15

  

### Câu tìm kiếm Google


```text

(Ghi câu tìm kiếm vào đây – xoá dòng này)

  

```

  

## 4.7. Excel

  

> Phần Excel được chấm trực tiếp trên file `data/dat_san_thang_10.xlsx`, không cần ghi vào đây.
