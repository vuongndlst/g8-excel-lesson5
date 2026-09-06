# Kết luận thổi phồng – Báo cáo phân tích

Website tĩnh dành cho GitHub Pages. Bài 5 của chuỗi Excel & Phân tích dữ liệu, khối 8 — bài chốt.

## Đưa lên GitHub Pages
1. Tạo repository mới trên GitHub và upload `index.html` vào thư mục gốc.
2. Settings → Pages → Deploy from a branch → nhánh **main**, thư mục **/(root)**.

## Điều kiện sử dụng
File **LSTS_KhaoSat_K8_2026_AnDanh_Cleaned.xlsx**, sheet `Clean_Data`, vùng hàng 3 → hàng 300.
Mỗi chặng dựng một phần của báo cáo.

## Nội dung
- Chặng 1: Câu hỏi nghiên cứu — lọc 5 câu hỏi theo ba tiêu chí
- Chặng 2: Mô tả mẫu — 298 · 293 · 293 · **288** · 10 bạn bị loại
- Chặng 3: Kết quả — bảng bốn nhóm giờ ngủ kèm n và tỉ lệ
- Chặng 4: Diễn giải đúng mức — ba loại từ nói quá
- Chặng 5: Giới hạn của nghiên cứu — bốn giới hạn, trong đó có biến gây nhiễu
- Kiểm tra cuối: 10 câu ngẫu nhiên rút từ ngân hàng 20 câu **tổng hợp cả năm buổi**

## Đáp án các chặng (dành cho giáo viên)

| Chặng | Nội dung | Kết quả |
|---|---|---|
| 2 | `=COUNTA(A3:A300)` | 298 |
| 2 | `=COUNT(B3:B300)` · `=COUNT(H3:H300)` | 293 · 293 |
| 2 | `=COUNTIFS(B3:B300;">=0";H3:H300;">=0")` | **288** |
| 2 | Số bạn bị loại | **10** |
| 3 | `=COUNTIFS(B3:B300;"<6";H3:H300;">=0")` | 30 |
| 3 | `=COUNTIFS(B3:B300;">=8";H3:H300;">=0")` | 69 |
| 3 | `=AVERAGEIFS(H3:H300;B3:B300;">=8")` | 8.36 |
| 3 | Tỉ lệ nhóm 7–8 giờ trên 288 | 38.5% |
| 5 | `=AVERAGEIF(B3:B300;"<6";C3:C300)` | **4.65** |
| 5 | `=AVERAGEIF(B3:B300;">=8";C3:C300)` | **2.26** |

Bảng kết quả đầy đủ của báo cáo mẫu: <6 giờ 5.77 (n=30, 10.4%) · 6–7 giờ 6.84 (n=78, 27.1%) ·
7–8 giờ 7.32 (n=111, 38.5%) · ≥8 giờ 8.36 (n=69, 24.0%).

## Lưu ý kỹ thuật
- Phần nhiệm vụ **không in sẵn công thức**. Sai ô nào thì ô đó tô đỏ và chỉ ô đó hiện gợi ý.
- Họ tên và lớp lưu trong `localStorage` (khóa `excelReport5Student`).
- Ô tỉ lệ phần trăm chấp nhận cả dạng `38.5` lẫn `0.385`.
- Ngân hàng câu hỏi cuối bài rút từ **cả năm buổi**, dùng được làm đề ôn cho bài kiểm tra Buổi 6.
