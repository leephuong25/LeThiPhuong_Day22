# Territorial Scope — Mẹ Âu Cơ (Adaptive Learning Assistant)
**Date:** 08/05/2026

## Câu hỏi 1: User EU?
- Có user EU hiện tại: 0 (Sản phẩm đặc thù Giáo dục THPT Việt Nam)
- Kế hoạch mở rộng EU 12 tháng: NO
- **Kết luận:** EU AI Act áp dụng = **NO** 
> *Note:* Hiện tại chúng ta an toàn với rào cản của EU. Tuy nhiên, nếu sau này có học sinh gốc Việt tại châu Âu sử dụng web/app của chúng ta, số lượng lớn, lúc đó mới cần quay lại rà soát EU AI Act.

## Câu hỏi 2: Dữ liệu Việt Nam?
### Loại dữ liệu cá nhân đang xử lý:
1. **Thông tin định danh:** Tên, Email, SĐT (dùng cho đăng nhập, khôi phục tài khoản).
2. **Hành vi học tập:** Lịch sử làm bài, số lần xin hint, thời gian giải bài, các lỗi sai thường gặp (Common Errors tracking).
3. **Định vị & Kỹ thuật:** Địa chỉ IP, thiết bị đăng nhập.
4. **Tài chính (sắp tới):** Dữ liệu giao dịch khi triển khai mô hình trả phí (Subscription).
5. **Dữ liệu Giáo viên** (tài liệu upload: PDF/PPTX/DOCX, cấu trúc lớp học, thông tin lớp)

### Có chuyển ra nước ngoài: YES
- Chúng ta gọi API của OpenAI / Anthropic (Data học sinh và câu hỏi Toán bị đưa sang server tại Mỹ).
- Hạ tầng Server/Database: Đang deploy trên Railway (hầu hết server đặt ở US/EU/Singapore).

### Kết luận: 
- PDPL áp dụng = **YES** (Chắc chắn 100%).
- **PDPL áp dụng:** YES — chắc chắn (dữ liệu người dùng Việt Nam, bao gồm trẻ vị thành niên)
- **CTIA (Cross-border Transfer Impact Assessment) bắt buộc:** **YES** — cho cả Anthropic API, OpenAI API, và VLM Service
- **Đồng ý của phụ huynh/người giám hộ:** **BẮT BUỘC** theo PDPL cho đối tượng dưới 18 tuổi
- **DPIA (Data Protection Impact Assessment):** Bắt buộc nộp trong **60 ngày** kể từ khi bắt đầu xử lý dữ liệu (Điều 30 PDPL)
- **DPA (Data Processing Agreement) với OpenAI và Anthropic:** PRD Section 12 đã ghi "DPA ký trước launch" — cần confirm đây đã thực hiện chưa

## Câu hỏi 3: Tầng rủi ro Luật AI VN?
### Phân tích

Mẹ Âu Cơ là hệ thống AI hoạt động trong **lĩnh vực giáo dục**, được Luật AI Việt Nam Điều 9 xếp vào nhóm ứng dụng **Tầng Cao** (High Risk).

**Lập luận phân loại:**

> Hệ thống AI của Mẹ Âu Cơ tự động phân loại nỗ lực học tập (genuine/fake/spam), tính Mastery Score, sinh hồ sơ năng lực cá nhân hóa (Error Taxonomy + effort profile), và cung cấp báo cáo dữ liệu cho giáo viên ra quyết định giảng dạy — tất cả tác động trực tiếp đến quá trình đánh giá và phát triển giáo dục của trẻ vị thành niên 15–16 tuổi, thuộc lĩnh vực "giáo dục" được liệt kê tường minh tại Điều 9 Khoản 1 Luật AI Việt Nam 134/2025/QH15.




  **Các feature cụ thể kích hoạt Tầng Cao:**

| Feature | Tại sao là High Risk |
|---|---|
| Effort Validation Engine (FR-02) | Phân loại hành vi học sinh (genuine/fake) ảnh hưởng trực tiếp đến việc học sinh có được hỗ trợ hay không |
| Mastery Score (Section 4.4.1) | Chỉ số đánh giá năng lực cá nhân của học sinh, được giáo viên sử dụng để đưa ra quyết định giảng dạy |
| Error Taxonomy + Heatmap (FR-07) | Hồ sơ điểm yếu kiến thức cá nhân hóa sâu, ảnh hưởng đến cách giáo viên xử lý từng học sinh |
| Stagnation Flag + Escape Hatch (FR-06) | AI gắn cờ "học sinh cần hỗ trợ đặc biệt" — hành động có tác động đến cơ hội học tập |

### Kết luận phân loại

- **Phân loại:** **TẦNG CAO (High Risk)**
- **Lĩnh vực:** Giáo dục (Điều 9 Khoản 1)

### Nghĩa vụ pháp lý theo Tầng Cao

| Nghĩa vụ | Mô tả | Deadline |
|---|---|---|
| **Đánh giá phù hợp (Conformity Assessment)** | Đánh giá rủi ro hệ thống AI trước khi đưa vào sử dụng | Trước launch |
| **Đăng ký CSDL AI quốc gia** | Đăng ký với Bộ KH&CN qua cổng AI quốc gia | Trước launch |
| **Giám sát con người (Human Oversight)** | Phải có cơ chế con người can thiệp được vào quyết định AI | Đã có một phần: Teacher Dashboard — cần document rõ hơn |
| **Báo cáo sự cố** | Quy trình báo cáo khi AI có lỗi nghiêm trọng | Cần build Incident Playbook |
| **Lưu log đầy đủ** | Log toàn bộ quyết định AI để có thể audit | SRS đề cập conversation history — cần confirm log retention policy |
| **Thông báo Bộ KH&CN** | Bắt buộc cho Tầng Cao trước khi deploy | Ngay khi chuẩn bị launch |

> **Lưu ý ân hạn:** Luật AI Việt Nam có ân hạn **18 tháng cho lĩnh vực giáo dục** (tính từ 1/3/2026 = deadline 1/9/2027). Tuy nhiên, đây không phải lý do để không chuẩn bị — ân hạn là để có thời gian build hồ sơ đúng, không phải để bỏ qua.

## 4 deadlines đã note vào Notion
- [x] 1/1/2026 — PDPL hiệu lực (đã qua - **Chúng ta đang vi phạm nếu chưa có Privacy Policy đúng chuẩn**)
- [x] 1/3/2026 — Luật AI VN hiệu lực (đã qua)
- [ ] 2/8/2026 — EU AI Act high-risk (3 tháng nữa - Không lo do áp dụng Câu 1 = NO)
- [ ] 1/3/2027 — Hết ân hạn (10 tháng nữa - Deadline để hoàn thành đăng ký AI Quốc gia)
