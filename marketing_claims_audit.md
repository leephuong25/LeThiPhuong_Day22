# Marketing Claims Audit — Mẹ Âu Cơ (Adaptive Learning Assistant)

**Ngày rà soát:** 08/05/2026
**Người rà soát:** AI Compliance Auditor
**Tài liệu nguồn:** SRS v2.0 – Nhóm A20 (23/04/2026)
**Phạm vi:** Tất cả tuyên bố về năng lực AI có thể xuất hiện trong marketing

> ⚠️ **Ghi chú phương pháp:** SRS là tài liệu kỹ thuật nội bộ, không phải landing page hay pitch deck.
> Tuy nhiên, nhiều câu trong SRS **sẽ được trích dẫn trực tiếp** vào slide, brochure, và livstream.
> Audit này rà soát các câu đó theo tiêu chuẩn Điều 198 BLHS — tức là đánh giá xem
> tuyên bố nào **có thể chứng minh được** nếu khách hàng (giáo viên/phụ huynh/nhà trường) yêu cầu.

---

## Bảng Claim Audit

| # | Câu gốc (trích từ SRS) | Vị trí trong SRS | Mức | Evidence hiện có | Honest Version | Action |
|---|------------------------|-------------------|-----|------------------|----------------|--------|
| 1 | *"AI Engine với kiến trúc Multi-Agent (Tutor AI + Analyzer AI) để phân tích nỗ lực, theo dõi tiến độ và sinh gợi ý thích ứng"* | §2.1 – Tầm nhìn sản phẩm | **B** | Kiến trúc đã thiết kế trong SRS; chưa có data thực tế về độ chính xác phân loại nỗ lực | *"Hệ thống sử dụng 2 lớp AI hỗ trợ học sinh — một xử lý real-time khi làm bài, một tổng hợp lịch sử bất đồng bộ. Tính năng đang trong giai đoạn xây dựng và kiểm thử."* | Fix trước khi dùng trong slide |
| 2 | *"Phân tích nỗ lực"* — AI tự phân loại submission thành `spam` / `fake_effort` / `genuine_effort` | §3.2 – FR-02 Effort Validation Engine | **B** | Logic phân loại đã được định nghĩa trong SRS; chưa có accuracy benchmark thực tế trên tập dữ liệu học sinh VN | *"Hệ thống cố gắng phân biệt nỗ lực thật và nỗ lực qua loa dựa trên logic lập luận. Độ chính xác phụ thuộc vào chất lượng bài làm — giáo viên vẫn là người kiểm tra cuối cùng."* | Cần pilot test đo accuracy trước khi công bố |
| 3 | *"AI Insights tóm tắt tự động: '80% học sinh vướng ở kỹ năng Phá Trị Tuyệt Đối'"* | §3.7 – Teacher Dashboard | **C** | Con số 80% là ví dụ minh họa trong SRS, **không phải kết quả thực tế**. Chưa có học sinh thật nào dùng hệ thống | *"Hệ thống sẽ hiển thị tỷ lệ lỗi phổ biến của lớp dựa trên dữ liệu thực học sinh nộp vào. Con số cụ thể phụ thuộc vào từng lớp học — không có con số mặc định."* | **Xóa ngay** con số 80% khỏi mọi tài liệu marketing |
| 4 | *"Valid Attempt Rate >= 70%"* — KPI mục tiêu | §7.1 – KPI Targets | **C** | Đây là **mục tiêu kỳ vọng**, không phải kết quả đã đạt. SRS không có dữ liệu pilot nào hỗ trợ con số này | *"Chúng tôi đặt mục tiêu ít nhất 70% lượt nộp bài có chất lượng lập luận. Con số này sẽ được đo thực tế sau giai đoạn pilot."* | Không được dùng như "kết quả" trong marketing; chỉ dùng như "mục tiêu" có gắn nhãn rõ ràng |
| 5 | *"Hệ thống tuyệt đối không cung cấp đáp án số cuối cùng — chỉ dẫn dắt học sinh tự tìm ra câu trả lời"* | §1.2 – Anti-Answer Policy | **B** | Policy được thiết kế chặt chẽ trong SRS (Escape Hatch, guardrails, jailbreak resistance); tuy nhiên chưa có kiểm thử thực tế khả năng bypass | *"Hệ thống được thiết kế để không đưa đáp án số cuối cùng. Có cơ chế bảo vệ nhiều lớp, nhưng không có hệ thống AI nào đảm bảo 100% chống mọi cách khai thác — giám sát của giáo viên vẫn cần thiết."* | Giữ claim nhưng bỏ từ "tuyệt đối" trong marketing |
| 6 | *"AI thông minh phát hiện học sinh đang hổng kiến thức nền và tự động rẽ nhánh sang bài phụ"* (ngụ ý từ FR-05 Sub-loop) | §3.5 – FR-05 | **B** | Logic kích hoạt Sub-loop khi phát hiện `Base Knowledge Gap` đã thiết kế; chưa có data về độ chính xác phát hiện gap thực tế | *"Khi AI nhận thấy dấu hiệu học sinh thiếu kiến thức nền, hệ thống gợi ý bài ôn tập phù hợp. Tính năng này phụ thuộc vào chất lượng tài liệu giáo viên cung cấp và độ rõ ràng của bài làm học sinh."* | Cần test trước khi quảng cáo |
| 7 | *"Grounding: Ép Tutor AI chỉ trả lời bám sát tài liệu giáo viên cung cấp"* | §6.2 – Guardrails | **B** | Cơ chế Grounding Pipeline được thiết kế; hiệu quả thực tế phụ thuộc vào chất lượng tài liệu và khả năng parse của VLM | *"AI sẽ ưu tiên trả lời trong phạm vi tài liệu giáo viên upload. Tuy nhiên chất lượng phụ thuộc vào định dạng và độ rõ ràng của tài liệu đầu vào — giáo viên nên review preview Markdown trước khi giao bài."* | Giữ, thêm điều kiện "phụ thuộc chất lượng tài liệu" |
| 8 | *"VLM nhận diện trực tiếp ảnh chụp bài viết tay"* | §3.1 – FR-01, §9.3 Risks | **B** | VLM được dùng nhưng SRS **tự thừa nhận rủi ro**: "VLM nhận diện kém chữ viết tay xấu" — có fallback LaTeX ảo | *"Hệ thống hỗ trợ nhận diện ảnh bài viết tay thông qua AI thị giác. Chữ viết quá xấu hoặc ảnh mờ có thể không được nhận diện chính xác — hệ thống sẽ hướng dẫn chụp lại hoặc nhập LaTeX thủ công."* | Phải nêu giới hạn này rõ trong marketing |
| 9 | *"Mastery Score phản ánh mức độ thành thạo thực chất"* | §4.4.1 | **C** | Công thức Mastery Score **chưa được xác định**: SRS ghi rõ *"trọng số cụ thể sẽ được xác định trong Technical Design Document"* | *"Hệ thống đang phát triển chỉ số đánh giá mức độ thành thạo dựa trên nỗ lực, thời gian suy nghĩ và mức độ tự lập. Công thức tính đang trong giai đoạn xây dựng và sẽ được điều chỉnh dựa trên dữ liệu thực."* | **Không dùng** trong marketing cho đến khi công thức finalize |
| 10 | *"Stagnation Rate <= 20%"* — KPI mục tiêu | §7.1 – KPI Targets | **C** | **Mục tiêu thiết kế**, không phải kết quả thực tế. Không có pilot data. | *"Mục tiêu chúng tôi hướng tới: dưới 20% học sinh rơi vào trạng thái bế tắc kéo dài. Chỉ số này sẽ được đo trong giai đoạn thử nghiệm thực tế."* | Chỉ dùng kèm nhãn "Mục tiêu MVP" — không trình bày như kết quả |
| 11 | *"Persona Mẹ Âu Cơ: bao dung, gần gũi, xưng hô Mẹ-Con để tạo môi trường học tập không phán xét"* | §2.1, §3.8 | **A** | Voice & Tone đã được thiết kế chi tiết trong SRS với ví dụ cụ thể; đây là thuộc tính UX có thể demo trực tiếp | *Giữ nguyên — có thể demo live.* | Giữ |
| 12 | *"AI Insights: '70% học sinh có Mastery Score < 40% ở kỹ năng Phá Trị Tuyệt Đối'"* | §4.4.1 – Nơi sử dụng | **C** | Con số 70% là ví dụ minh họa trong SRS, không có dữ liệu thực | *"Dashboard sẽ hiển thị phân bố Mastery Score theo từng kỹ năng của lớp. Con số thực phụ thuộc vào từng lớp học cụ thể."* | **Xóa ngay** mọi con số minh họa khỏi tài liệu marketing |
| 13 | *"Heatmap tự động hiển thị lỗi phổ biến cả lớp — giáo viên không cần tốn thời gian chấm tay"* (ngụ ý từ Teacher pain point) | §2.2 – Teacher Persona | **B** | Heatmap được thiết kế; độ chính xác phụ thuộc vào Error Taxonomy và khả năng phân loại của AI | *"Heatmap tổng hợp dữ liệu lỗi từ toàn bộ bài nộp của lớp, giúp giáo viên nhìn thấy xu hướng lỗi chung mà không cần đọc từng bài thủ công. Độ chính xác phụ thuộc vào chất lượng phân tích AI — giáo viên vẫn nên xác nhận bằng quan sát lớp học."* | Thêm disclaimer "hỗ trợ, không thay thế giáo viên" |

---

## Thống kê

- **Tổng số claim rà soát:** 13
- **Mức A (Chứng minh được):** 1 *(Persona UX — có thể demo)*
- **Mức B (Chưa chứng minh, có thể — cần test):** 7
- **Mức C (Thổi phồng — vùng nguy hiểm Điều 198):** 5

> 🚨 **Tỷ lệ rủi ro:** 38% claim hiện tại thuộc Mức C — cần xử lý **trước khi ra thị trường**.

---

## TOP 3 Priority Sửa Ngay

### 🔴 Priority 1 — Con số minh họa bị dùng như kết quả thực (Claim #3, #12)
**Câu nguy hiểm:** *"AI Insights: 80% học sinh vướng ở kỹ năng Phá Trị Tuyệt Đối"*

**Tại sao nguy hiểm:** Đây là con số **ví dụ trong SRS**, được viết để minh họa cách hệ thống trình bày — không phải kết quả thực. Nếu xuất hiện trong slide pitch hay brochure, đây là **lừa dối khách hàng điển hình theo pattern Kẹo Kera**: đưa con số cụ thể, không có nguồn gốc, tạo ảo giác về hiệu quả đã được chứng minh.

**Action:** Xóa toàn bộ con số % minh họa khỏi mọi tài liệu đối ngoại. Thay bằng *"[Số liệu sẽ cập nhật sau pilot]"*.

---

### 🔴 Priority 2 — KPI "mục tiêu" bị trình bày như "kết quả" (Claim #4, #10)
**Câu nguy hiểm:** *"Valid Attempt Rate >= 70%"*, *"Stagnation Rate <= 20%"*

**Tại sao nguy hiểm:** SRS §7.1 ghi rõ đây là **KPI Target** — mục tiêu kỳ vọng. Nhưng trong slide pitch deck hoặc báo cáo đầu tư, những con số này rất dễ bị đọc như "hệ thống đã đạt được". Không có một học sinh thật nào đã dùng hệ thống để xác nhận.

**Action:** Mọi KPI phải đi kèm nhãn rõ ràng: *"Mục tiêu MVP — chưa có dữ liệu thực tế"*. Nếu trình bày trong pitch: đặt vào slide riêng tiêu đề *"Target Metrics"*, không phải *"Results"*.

---

### 🔴 Priority 3 — Mastery Score được giới thiệu như tính năng hoàn chỉnh (Claim #9)
**Câu nguy hiểm:** *"Mastery Score phản ánh mức độ thành thạo thực chất của học sinh"*

**Tại sao nguy hiểm:** SRS §4.4.1 tự thừa nhận: *"Công thức chi tiết và trọng số cụ thể sẽ được xác định trong Technical Design Document"* — nghĩa là tính năng này **chưa tồn tại về mặt thuật toán**. Quảng cáo một tính năng chưa có công thức là vi phạm rõ ràng.

**Action:** Mastery Score chỉ được đề cập trong marketing sau khi công thức đã được finalize và kiểm thử. Trước đó chỉ được nói: *"Đang phát triển chỉ số đánh giá tiến bộ học sinh — sẽ ra mắt sau giai đoạn beta."*

---

## Khuyến nghị Bổ sung cho Startup

### ✅ Những gì có thể nói ngay (Safe Claims)
- Mô tả kiến trúc hệ thống (Multi-Agent, Grounding Pipeline) — đây là thiết kế, không phải kết quả
- Giải thích **Anti-Answer Policy** như một cam kết về triết lý sản phẩm
- Demo live Persona Mẹ Âu Cơ — đây là UX có thể thấy trực tiếp
- Mô tả các tính năng trong SRS như *"đang xây dựng"* hoặc *"thiết kế để..."*

### 📋 Cần làm trước khi ra thị trường
1. **Pilot test** với ít nhất 1 lớp thực (20-30 học sinh) để có accuracy data thực cho Effort Validation
2. **Finalize** công thức Mastery Score trong Technical Design Document
3. **Đo thực tế** KPI sau pilot để thay thế con số mục tiêu bằng con số thực
4. **Gắn disclaimer** vào mọi screenshot Dashboard: *"Dữ liệu mẫu — minh họa giao diện"*

### ⚖️ Lưu ý pháp lý
Theo **Điều 198 BLHS 2015** (Tội lừa dối khách hàng): hành vi *"đưa thông tin gian dối"* về sản phẩm có thể bị xử lý hình sự nếu gây thiệt hại. Trong ngữ cảnh EdTech bán cho nhà trường/phụ huynh, con số KPI giả hoặc minh họa được trình bày như kết quả thực là rủi ro pháp lý nghiêm trọng. Luôn để tên luật sư/đơn vị tư vấn pháp lý review tài liệu marketing trước khi gửi cho khách hàng B2B (trường học).

---

*Audit thực hiện bởi: AI Compliance Auditor | Dựa trên SRS v2.0 – Mẹ Âu Cơ – Nhóm A20*
*Ngày: 08/05/2026*
