

# Bài 9: Tự động tra cứu bằng VLOOKUP

## Phần 1: Phân tích bài toán

### 1. Bảng thành phần VLOOKUP

Thành phần

Nội dung

Lookup_value

`TRIM(C2)` – Mã tác giả

Table_array

`'DanhMucTacGia'!$A$2:$E$81`

Col_index_num cột D

`2` – Tên tác giả

Col_index_num cột E

`4` – Phòng

Col_index_num cột F

`5` – Thù lao

### 2. Xử lý 3 bẫy dữ liệu

-   `TRIM`: Xóa khoảng trắng thừa.
    
-   `IFERROR`: Nếu lỗi, hiển thị “Chưa cập nhật”.
    
-   `$`: Cố định vùng tra cứu khi kéo công thức.
    

### 3. Các bước thực hiện

1.  Kiểm tra dữ liệu ở hai sheet.
    
2.  Nhập công thức vào D2, E2, F2.
    
3.  Kéo công thức xuống hàng 81.
    
4.  Kiểm tra các mã tác giả bị lỗi.
    

## Phần 2: Công thức và chống lỗi

### 4. Ô D2 – Tên tác giả

```
=IFERROR(VLOOKUP(TRIM(C2),'DanhMucTacGia'!$A$2:$E$81,2,FALSE),"Chưa cập nhật")
```

### 5. Ô E2 và F2

Ô E2 – Phòng:

```
=IFERROR(VLOOKUP(TRIM(C2),'DanhMucTacGia'!$A$2:$E$81,4,FALSE),"Chưa cập nhật")
```

Ô F2 – Thù lao:

```
=IFERROR(VLOOKUP(TRIM(C2),'DanhMucTacGia'!$A$2:$E$81,5,FALSE),"Chưa cập nhật")
```

Chỉ thay số `2`, `4`, `5` để lấy dữ liệu ở cột tương ứng.

### 6. Nếu bỏ dấu `$`

Khi kéo công thức từ D2 xuống D5:

-   D2: `A2:E81`
    
-   D3: `A3:E82`
    
-   D4: `A4:E83`
    
-   D5: `A5:E84`
