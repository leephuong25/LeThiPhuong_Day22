# Document Trail — Mẹ Âu Cơ (A20-App-136 Adaptive Learning Assistant)
**Date:** 08/05/2026

## Bảng đối chiếu 5 loại hồ sơ chứng cứ

| # | Loại hồ sơ | Status | Link/Path hiện tại | Deadline build |
|---|------------|--------|--------------------|----------------|
| 1 | Nhật ký kiểm thử claim AI | ✗ | Đang draft tại `docs/evaluation_metrics.md` và file `data/test_math_reasoning.json` | Cuối Tuần 6 |
| 2 | Hồ sơ rà soát điều khoản vendor | ✗ | Chưa rà soát DPA của OpenAI / Anthropic | Cuối Tuần 6 |
| 3 | Nhật ký giám sát giao dịch bất thường | ✗ | Chưa làm (Tính năng Subscription sẽ dev ở Tuần 6) | Đầu Tuần 7 |
| 4 | DPIA / CTIA (Đánh giá tác động chuyển dữ liệu) | ✗ | Chưa có tài liệu nội bộ | Nộp chậm nhất 60 ngày sau Launch |
| 5 | Phê duyệt nội dung marketing | ✗ | Vừa làm file `marketing_claims_audit.md` (chưa có quy trình ký duyệt) | Tuần 6 |

## TOP 1 ưu tiên
**Loại:** #4 - DPIA / CTIA (Đánh giá tác động xử lý/chuyển dữ liệu xuyên biên giới).
**Lý do:** Mẹ Âu Cơ phục vụ đối tượng học sinh (dưới 18 tuổi - dữ liệu cực kỳ nhạy cảm) và liên tục đẩy prompt chứa hành vi học tập qua server OpenAI/Anthropic tại Mỹ. Đây là điểm rủi ro lớn nhất và dễ bị thanh tra nhất theo Điều 30 Luật Bảo vệ dữ liệu cá nhân (PDPL).


### Tần suất cập nhật: 1 lần trước Launch (và update khi đổi nhà cung cấp AI).
### Sample 3-5 dòng:

```markdown
# Bản Đánh giá Tác động Chuyển Dữ liệu ra Nước ngoài (CTIA) - Mẹ Âu Cơ
**1. Loại dữ liệu chuyển giao:** Lịch sử giải bài, text prompt của học sinh, thông số Effort Validation.
**2. Bên nhận dữ liệu:** OpenAI LLC (Mỹ) & Anthropic (Mỹ) qua đường API.
**3. Biện pháp bảo mật & Giảm thiểu rủi ro (Security by Design):**
- 100% Ẩn danh/Pseudonymize (Không truyền Tên, Email, SĐT của học sinh vào prompt).
- Thiết lập Zero Data Retention policy với OpenAI (Data truyền qua API không được dùng để train model của vendor).
**4. Đánh giá rủi ro rò rỉ:** Thấp (Do không chứa PII).
```
