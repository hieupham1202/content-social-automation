# Content Social Production System — GMO Runsystem

## Mô tả hệ thống
Pipeline sản xuất content tự động cho Facebook và LinkedIn,
tập trung vào sản phẩm CRM tích hợp AI của GMO Runsystem.

## Cách sử dụng pipeline
Chạy tuần tự theo thứ tự. Mỗi bước đọc skill tương ứng trong /skills/:

1. Phân tích thị trường   → đọc skills/01-market-analysis.md
2. Audit đối thủ          → đọc skills/02-competitor-audit.md
3. Đề xuất pillar & angle → đọc skills/03-content-pillars.md
4. Làm dàn ý              → đọc skills/04-content-outline.md
5. Viết bài               → đọc skills/05-content-writer.md

Thông tin brand cố định: xem /knowledge-base/brand/brand-profile.md
Kết quả lưu tại: /outputs/YYYY-MM-DD/

## Tần suất & Tỷ lệ content

### Tần suất đăng bài
- Facebook: 3/tuần
- LinkedIn: 3/tuần
- Chu kỳ lên lịch: 1 tháng

### Tỷ lệ Pillar 6 — Sản phẩm & Dịch vụ
Chỉnh 2 con số dưới đây để thay đổi tỷ lệ bài thuần sản phẩm/bán hàng:
- Facebook: 20%   
- LinkedIn: 20%  

Phần trăm còn lại tự động phân bổ đều cho các pillar 1-5.
Nếu để 0%: bỏ hoàn toàn Pillar 6 khỏi lịch content kỳ đó.

## Knowledge Base — Quy tắc sử dụng

### Vị trí
Toàn bộ tài liệu tham khảo nằm trong /knowledge-base/:
- /knowledge-base/brand/          — Brand profile, brand guideline (màu sắc, font, logo)
- /knowledge-base/competitive/    — Hồ sơ đối thủ cạnh tranh + bản đồ thị trường
- /knowledge-base/case-studies/   — Case study thực tế theo ngành
- /knowledge-base/product/        — Thông tin sản phẩm GMO (WOWCRM, OmniCare, AikoAI)
- /knowledge-base/reports/        — Báo cáo thị trường, nội bộ
- /knowledge-base/activities/     — Sự kiện, hoạt động thực tế của GMO

### Khi nào cần đọc knowledge-base

**Bước 1 (Market Analysis) & Bước 2 (Competitor Audit):**
- BẮT BUỘC đọc /knowledge-base/competitive/overview.md trước khi research
- Đọc file đối thủ liên quan nếu cần đi sâu vào từng tên cụ thể
- Sau khi research xong: nếu có thông tin mới hoặc thay đổi so với file hiện có,
  ghi chú vào phần "Ghi chú cần verify" của file đối thủ tương ứng để cập nhật sau

**Bước 3 (Pillar & Angle):**
- Pillar 5: Đọc /knowledge-base/activities/events-log.md để tìm nội dung thực tế
- Pillar 3 & 4: Liệt kê case study trong /knowledge-base/case-studies/ để gợi ý angle

**Bước 4 (Outline):**

| Pillar | Hành động |
|--------|-----------|
| Pillar 1 — AI & Future of Sales | Không cần scan. Bài thiên về góc nhìn/xu hướng |
| Pillar 2 — Thực chiến CRM | Không cần scan. Bài thiên về tips/how-to |
| Pillar 3 — Business Impact | **BẮT BUỘC scan** case-studies/ — số liệu là xương sống bài |
| Pillar 4 — Ngành chuyên sâu | **BẮT BUỘC scan** case-studies/ theo đúng ngành (BFSI/BĐS...) |
| Pillar 5 — GMO thực tế | **BẮT BUỘC đọc** events-log.md + case study liên quan |
| Pillar 6 — Sản phẩm & Dịch vụ | **BẮT BUỘC đọc** file sản phẩm liên quan trong knowledge-base/product/ |

Nếu scan Pillar 3/4/5 mà không tìm thấy case phù hợp: ghi "[cần case study]" vào outline, không tự bịa.

**Bước 5 (Viết bài):**
- Pillar 3/4/5: Đọc lại file case study đã xác định ở Bước 4 trước khi viết
- Mọi pillar: Kiểm tra /knowledge-base/product/features.md khi đề cập tính năng sản phẩm
- Mọi pillar: Kiểm tra /knowledge-base/reports/ nếu cần số liệu thị trường
- Không dùng số liệu nào không có trong knowledge-base hoặc do người dùng cung cấp

### Ưu tiên sử dụng case study
1. Cao nhất: Case có số liệu cụ thể + quote C-level (ví dụ: GMO Ad Marketing, ABBank)
2. Trung bình: Case có số liệu cụ thể, không có quote (Miza, BaAn, Apec Securities)
3. Thấp hơn: Case thiếu số liệu công khai → chỉ dùng tên khách hàng, không dùng con số

## Tiêu chuẩn chất lượng xuyên suốt pipeline
Mỗi bước output phải đạt 4 tiêu chí sau:
- **Clarity**: bước này tạo ra decision gì cho bước tiếp theo? Phải trả lời được câu hỏi đó.
- **Specificity**: càng cụ thể càng tốt — tránh mô tả mơ hồ, tránh insight chung chung
- **Actionability**: người chạy bước tiếp theo dùng được ngay, không cần giải thích thêm
- **Consistency**: logic nhất quán từ market analysis đến draft cuối — angle, persona, key message không được lệch nhau giữa các bước

## Quy tắc bắt buộc
- Luôn đọc /knowledge-base/brand/brand-profile.md trước khi bắt đầu bất kỳ bước nào
- Bước 5 (viết bài): đọc thêm /knowledge-base/brand/brand-guideline.md để gợi ý visual đúng màu sắc, font
- Output mỗi bước phải lưu thành file riêng trước khi sang bước tiếp
- Không bịa số liệu — chỉ dùng data từ knowledge-base hoặc do người dùng cung cấp
- Nếu thiếu số liệu: ghi [cần bổ sung] vào đúng chỗ đó trong bài, không ước lượng
- Mỗi bài viết phải ghi rõ: kênh (FB/LI), format, target persona

## Cấu trúc output
outputs/
└── YYYY-MM-DD/
    ├── 01-market-analysis.md
    ├── 02-competitor-audit.md
    ├── 03-pillars-angles.md
    ├── 04-outline-[tên-angle].md
    └── 05-post-[tên-angle-rút-gọn].md