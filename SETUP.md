# SETUP GUIDE — Content Social Pipeline

Hướng dẫn triển khai hệ thống sản xuất content cho một doanh nghiệp mới.
Thời gian ước tính: 2-4 giờ (chưa tính thời gian thu thập thông tin từ khách hàng).

---

## Yêu cầu trước khi bắt đầu

- [ ] Đã cài Claude Code (`npm install -g @anthropic-ai/claude-code`)
- [ ] Đã có tài khoản Claude (Pro hoặc Max plan) và đăng nhập Claude Code
- [ ] Đã clone hoặc copy repo này về máy
- [ ] Đã thu thập thông tin cần thiết từ khách hàng (xem Checklist thu thập bên dưới)

---

## Bước 1 — Clone repo và đổi tên

```bash
# Clone repo gốc
git clone https://github.com/hieupham1202/content-social-test.git [tên-công-ty-mới]
cd [tên-công-ty-mới]

# Xóa git history cũ, tạo repo mới
rm -rf .git
git init
git add .
git commit -m "init: content pipeline for [tên công ty]"
```

Nếu muốn push lên GitHub riêng:
```bash
git remote add origin [URL repo mới]
git push -u origin main
```

---

## Bước 2 — Xóa dữ liệu cũ

Xóa toàn bộ data của GMO, giữ lại cấu trúc folder và template:

```bash
# Xóa brand data cũ
rm knowledge-base/brand/brand-profile.md
rm knowledge-base/brand/brand-guideline.md

# Xóa product data cũ
rm knowledge-base/product/aikoai.md
rm knowledge-base/product/omnicare.md
rm knowledge-base/product/wowcrm.md

# Xóa competitive data cũ
rm knowledge-base/competitive/base-vn.md
rm knowledge-base/competitive/misa-crm.md
rm knowledge-base/competitive/salesforce-vietnam.md
rm knowledge-base/competitive/hubspot-vietnam.md
rm knowledge-base/competitive/microsoft-dynamics.md
rm knowledge-base/competitive/overview.md

# Xóa case studies cũ
rm -rf knowledge-base/case-studies/BFSI/
rm -rf knowledge-base/case-studies/san-xuat-co-khi/
# (giữ lại folder _template nếu có)

# Reset activities và reports
echo "" > knowledge-base/activities/events-log.md
```

---

## Bước 3 — Điền thông tin Brand

### 3a. Tạo brand-profile.md
Copy từ template và điền:

```
knowledge-base/brand/brand-profile.md
```

Thông tin cần có:
- Tên công ty, tập đoàn mẹ (nếu có)
- Sản phẩm/dịch vụ chính
- Định vị thương hiệu (1-2 câu)
- Target audience: chức danh, ngành, quy mô doanh nghiệp
- Tone of voice
- Những từ/cụm từ tuyệt đối tránh

### 3b. Tạo brand-guideline.md
Copy từ template và điền:

```
knowledge-base/brand/brand-guideline.md
```

Thông tin cần có:
- Màu sắc chính (HEX, RGB)
- Font chữ
- Quy tắc dùng logo
- Hướng dẫn visual cho social post

---

## Bước 4 — Điền thông tin Sản phẩm

Với mỗi sản phẩm/dịch vụ, copy `knowledge-base/product/_template.md` và điền:

```bash
cp knowledge-base/product/_template.md knowledge-base/product/[tên-sản-phẩm].md
```

Thông tin cần có cho mỗi sản phẩm:
- Mô tả ngắn và tính năng chính
- Khách hàng mục tiêu (ngành, chức danh, quy mô)
- Pain points giải quyết được
- Điểm khác biệt so với đối thủ
- Giá (nếu public)
- Angles content gợi ý

---

## Bước 5 — Điền thông tin Cạnh tranh

### 5a. Tạo overview.md
Vẽ bản đồ cạnh tranh tổng quan:
- Ai đang cạnh tranh trực tiếp?
- Ai cạnh tranh gián tiếp?
- Khoảng trống thị trường mà công ty có thể chiếm?

### 5b. Tạo profile từng đối thủ

```bash
cp knowledge-base/competitive/_template.md knowledge-base/competitive/[tên-đối-thủ].md
```

Ưu tiên điền: định vị, điểm mạnh/yếu, cách làm content, **điểm công ty có thể khai thác**.

---

## Bước 6 — Điền Case Studies

Với mỗi case study, tạo folder theo ngành và điền:

```bash
mkdir -p knowledge-base/case-studies/[ngành]/
cp knowledge-base/case-studies/BFSI/_template.md \
   knowledge-base/case-studies/[ngành]/[tên-khách-hàng]-[sản-phẩm]-[năm].md
```

**Lưu ý quan trọng:**
- Chỉ đưa vào case study đã được khách hàng cho phép public
- Đánh dấu rõ thông tin nào public / không public
- Ưu tiên case có: số liệu cụ thể + quote từ C-level

---

## Bước 7 — Cập nhật CLAUDE.md

Chỉnh 3 phần sau trong `CLAUDE.md`:

```markdown
## Tần suất & Tỷ lệ content

### Tần suất đăng bài
- Facebook: [X]/tuần       ← chỉnh theo kế hoạch thực tế
- LinkedIn: [X]/tuần       ← chỉnh theo kế hoạch thực tế

### Tỷ lệ Pillar 6 — Sản phẩm & Dịch vụ
- Facebook: [X]%           ← thường 10-20%
- LinkedIn: [X]%           ← thường 15-25%
```

---

## Bước 8 — Cập nhật Skill 02 (Competitor Audit)

Mở `skills/02-competitor-audit.md` và thay danh sách đối thủ cụ thể phù hợp với ngành mới.

---

## Bước 9 — Test pipeline

Chạy thử từ bước 1 để kiểm tra hệ thống hoạt động đúng:

```bash
cd [thư-mục-repo]
claude
```

Gõ lệnh test:
```
Chạy bước 1: phân tích thị trường [ngành của khách hàng] tháng này
```

Kiểm tra output:
- [ ] Claude đọc đúng brand-profile không?
- [ ] Output có đúng format không?
- [ ] Có bịa số liệu không? (nếu có → kiểm tra lại skill 01)

---

## Checklist thu thập thông tin từ khách hàng

Cần có trước khi bắt đầu setup:

**Brand:**
- [ ] Tên công ty, sản phẩm/dịch vụ chính
- [ ] File brand guideline (màu sắc, font, logo)
- [ ] Tone of voice và những điều tránh nói
- [ ] Website, social media hiện tại

**Audience:**
- [ ] Khách hàng mục tiêu là ai? (ngành, chức danh, quy mô)
- [ ] Insight về pain point của họ

**Sản phẩm:**
- [ ] Danh sách sản phẩm/dịch vụ đang bán
- [ ] USP và điểm khác biệt so với đối thủ
- [ ] Bảng giá (nếu public)

**Case Studies:**
- [ ] Danh sách khách hàng đã triển khai
- [ ] Kết quả đo được (số liệu cụ thể)
- [ ] Khách hàng nào cho phép public?
- [ ] Có quote từ C-level không?

**Cạnh tranh:**
- [ ] Đối thủ trực tiếp là ai?
- [ ] Điểm mạnh/yếu so với đối thủ theo góc nhìn của họ

**Kế hoạch:**
- [ ] Tần suất đăng bài mong muốn (FB/LI)
- [ ] Tỷ lệ bài sản phẩm/bán hàng mong muốn

---

## Cấu trúc file sau khi setup xong

```
[tên-công-ty]/
├── CLAUDE.md                    ✅ Đã cập nhật
├── SETUP.md                     ✅ File này
├── push.bat                     ✅ Giữ nguyên
├── skills/                      ✅ Giữ nguyên toàn bộ
│   ├── 01-market-analysis.md
│   ├── 02-competitor-audit.md   ✅ Đã cập nhật đối thủ
│   ├── 03-content-pillars.md
│   ├── 04-content-outline.md
│   └── 05-content-writer.md
├── knowledge-base/
│   ├── brand/
│   │   ├── brand-profile.md     ✅ Đã điền
│   │   └── brand-guideline.md   ✅ Đã điền
│   ├── competitive/
│   │   ├── overview.md          ✅ Đã điền
│   │   └── [đối-thủ].md         ✅ Đã điền
│   ├── product/
│   │   └── [sản-phẩm].md        ✅ Đã điền
│   ├── case-studies/
│   │   └── [ngành]/             ✅ Đã điền
│   ├── activities/
│   │   └── events-log.md        ✅ Sẵn sàng cập nhật
│   └── reports/                 ✅ Sẵn sàng cập nhật
└── outputs/                     ✅ Sẵn sàng nhận output
```
