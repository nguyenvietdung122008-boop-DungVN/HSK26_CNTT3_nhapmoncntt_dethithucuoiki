# BÀI LÀM –(CHỦ ĐỀ QUẢN LÝ MODEL AI)

- **Mã đề:**
- **Họ tên:**Nguyễn Việt Dũng
- **Lớp:**CNTT3
- **Link repository:**
- **Hệ điều hành (Windows/macOS):**windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
# PS C:\dung\MiniPrjoect> ls


    Directory: C:\dung\MiniPrjoect


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/10/2026   1:50 PM                starter-kit
-a----        11/10/2026   1:42 PM        2671444 mini_project.docx
-a----        11/10/2026   1:41 PM          10876 mini_project.md


PS C:\dung\MiniPrjoect> cd starter-kit
PS C:\dung\MiniPrjoect\starter-kit> ls


    Directory: C:\dung\MiniPrjoect\starter-kit


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/10/2026   1:49 PM                quan-ly-model-ai
-a----        11/10/2026   1:41 PM           2665 bai_lam.md


PS C:\dung\MiniPrjoect\starter-kit> cd quan-ly-model-ai
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> Move-Item -Path "tai_lieu_ban_giao.txt" -Destination "docs"
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> mkdir "backup"


    Directory: C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/10/2026   1:57 PM                backup


PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> copy-item "data\chi_phi_model_thang_11.xlsx" "backup\chi_phi_model_thang_11_xlsx"

PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> Remove-Item "*.tmp"

PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> cd "logs"
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\logs> pwd

Path
----
C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\logs


PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\logs> ls
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\logs> pwd

Path
----
C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\logs


PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\logs> ls


    Directory: C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026   1:41 PM           1234 Inference.log


PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\logs> cd..
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> Get-ChildItem -Recurse -Force

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
( Directory: C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/10/2026   2:08 PM                backup
d-----        11/10/2026   2:06 PM                data
d-----        11/10/2026   1:56 PM                docs
d-----        11/10/2026   1:48 PM                evidence
d-----        11/10/2026   2:11 PM                logs
d-----        11/10/2026   1:41 PM                web
-a----        11/10/2026   1:41 PM             96 .env
-a----        11/10/2026   1:41 PM           2665 bai_lam.md


    Directory: C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026   1:45 PM          11417 chi_phi_model_thang_11.xl
                                                  sx


    Directory: C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026   1:45 PM          11417 Chi_Phi_Model_Thang_11.xl
                                                  sx


    Directory: C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026   1:41 PM            204 tai_lieu_ban_giao.txt


    Directory: C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026   1:41 PM           1234 Inference.log


    Directory: C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/10/2026   1:41 PM                images
-a----        11/10/2026   1:41 PM            644 app.js
-a----        11/10/2026   1:41 PM            567 index.html
-a----        11/10/2026   1:41 PM            460 style.css


    Directory: C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026   1:41 PM            339 logo-ai-hub.png)

```

## 4.3. Lọc log vận hành Model AI

### a) Lệnh lọc các dòng ERROR

```shell
# Ghi lệnh vào đây (PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> Select-String -Path "logs\inference.log" -Pattern "ERROR" | Select-Object -ExpandProperty Line > "logs\loi_model.txt")

```

### 2 dòng đầu tiên trong logs/loi_model.txt

```text
(PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> Get-Content "logs\loi_model.txt" -TotalCount 2
2026-11-10 08:27:45 ERROR POST /v1/chat/completions model=CLAUDE-35
2026-11-10 08:31:12 ERROR POST /v1/audio/transcriptions model=WHISPER-V3)

```

### b) Lệnh đếm số dòng WARNING và kết quả

```shell
# Ghi lệnh vào đây (xoá dòng này)

```

```text
(PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> (Select-String -Path "logs\inference.log" -Pattern "WARNING").Count
5)

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
# Ghi lệnh vào đây (PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> # ==========================================
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> # Tên script: tao_bao_cao.ps1
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> # Tác giả: Nguyễn Việt Dũng
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> # Ngày tạo: 10/11/2026
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> # Mô tả: Đọc log inference, tổng hợp và ghi ra file tong_hop.txt
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> # ==========================================
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai>
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> $OutputFile = "logs\tong_hop.txt"
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> $LogFile = "logs\inference.log"
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai>
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> # 1. Dòng đầu tiên theo yêu cầu
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> "=== BAO CAO VAN HANH MODEL AI ===" | Out-File -FilePath $OutputFile -Encoding utf8
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai>
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> # 2. Tiếp theo là các dòng chứa WARNING
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> Get-Content $LogFile | Select-String "WARNING" | Select-Object -ExpandProperty Line | Add-Content -Path $OutputFile -Encoding utf8
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai>
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> # 3. Cuối cùng là số dòng chứa ERROR
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> $ErrorCount = (Get-Content $LogFile | Select-String "ERROR").Count
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai> "So dong chua ERROR: $ErrorCount" | Add-Content -Path $OutputFile -Encoding utf8
PS C:\dung\MiniPrjoect\starter-kit\quan-ly-model-ai>)

```

### Nội dung file logs/tong_hop.txt

```text
(Dán nội dung file vào đây – xoá dòng này)

```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] README.md: Heading 1, hình ảnh (`![Alt](path)`), mô tả có **in đậm**, _in nghiêng_ và `inline code`, bảng, code block, task list, blockquote
- [ ] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [ ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | -------------------------- | --------------------------- | -------------- |
| 1   |                            |                             |                |
| 2   |                            |                             |                |

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

> Phần Excel được chấm trực tiếp trên file `data/chi_phi_model_thang_11.xlsx`, không cần ghi vào đây.
