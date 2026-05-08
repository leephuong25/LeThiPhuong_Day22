# Compliance Audit v2 — Mẹ Âu Cơ (Adaptive Learning Assistant)

**Căn cứ pháp lý:**
- Luật AI Việt Nam 134/2025/QH15 (hiệu lực 1/3/2026)
- Luật Bảo vệ Dữ liệu Cá nhân 91/2025/QH15 — PDPL (hiệu lực 1/1/2026)
- Bộ luật Hình sự: Điều 174 (Lừa đảo), Điều 198 (Lừa dối khách hàng), Điều 324 (Rửa tiền)
- EU AI Act (2024/1689)

> **LỜI MỞ ĐẦU CỦA KIỂM TOÁN VIÊN:**
> Đây là văn bản đánh giá pháp lý thẳng thắn — không có "nhưng mà", không có "tuy nhiên sản phẩm rất tốt". Mục đích duy nhất là giúp founder nhìn rõ rủi ro trước khi cơ quan điều tra nhìn thấy trước. Mọi vi phạm dưới đây đều có bằng chứng trích dẫn từ tài liệu thật của startup. Không có vi phạm nào được bịa thêm. Không có vi phạm nào bị bỏ qua vì "nhạy cảm".

---

## PHẦN I — VI PHẠM MARKETING CLAIM (Điều 198 BLHS)

---

### VI PHẠM 1: Claim "AI không bao giờ cho đáp án" — Cam kết tuyệt đối không thể thực hiện

**Luật áp dụng:** Bộ luật Hình sự  
**Điều:** Điều 198 BLHS — Tội lừa dối khách hàng  
**Khoản:** Khoản 2 (gian lận có hệ thống, gây thiệt hại)

**Bằng chứng trong sản phẩm:**

> Trích từ `marketing_claims_audit.md` — Claim #4:
> *"AI không bao giờ cho đáp án trực tiếp, 100% an toàn cho tư duy của trẻ."*

> Trích từ PRD Section 6.1:
> *"Khi nào cho xem solution: KHÔNG BAO GIỜ trong MVP."*

> Trích từ PRD Section 11 — Risks:
> *"Tutor AI sinh hint sai kiến thức — Likelihood: Medium, Impact: High"*

**Phân tích vi phạm:**

Đây là vi phạm cấu trúc, không phải lỗi đánh máy. Startup đang đồng thời làm hai việc mâu thuẫn nhau:

1. **Marketing cam kết tuyệt đối:** "KHÔNG BAO GIỜ" và "100% an toàn" — không có ngoại lệ
2. **PRD thừa nhận rủi ro trung bình:** Tutor AI có thể sinh hint sai kiến thức ở mức "Medium Likelihood"

Khi một LLM (Claude Sonnet hoặc GPT-4o) sinh hint Level 3 micro-steps, không có cơ chế nào đảm bảo 100% hint không vô tình tiết lộ đáp án — đặc biệt ở Tier 1 bài đơn giản. Đây là giới hạn kỹ thuật của mọi LLM hiện tại, được Anthropic và OpenAI ghi rõ trong documentation.

Khi phụ huynh mua sản phẩm vì tin "AI không bao giờ cho đáp án" và sau đó học sinh nhận hint quá chi tiết → phụ huynh có đủ căn cứ kiện. Đây là **pattern Kẹo Kera chính xác**: cam kết công dụng tuyệt đối → thực tế không đạt → Điều 198.

**Pattern khớp với:** Vụ Kẹo Kera 11/2025 — claim "1 viên kẹo = 1 đĩa rau" không thể chứng minh khoa học → 3 KOL bị truy tố Điều 198.

**Hành động sửa (trong 1 tuần):**
1. Xóa ngay từ "không bao giờ" và "100%" khỏi mọi tài liệu marketing
2. Thay bằng: *"Hệ thống được thiết kế để ưu tiên gợi ý thay vì đáp án — guardrails được kiểm tra định kỳ và giáo viên có thể override bất kỳ lúc nào"*
3. Thêm disclaimer: *"Trong một số trường hợp ngoài corpus, AI có thể không hỗ trợ được — học sinh sẽ được chuyển sang giáo viên"*
4. Founder ký xác nhận marketing mới trước khi publish

**Deadline:** **Ngay lập tức** — claim này đang live trên tài liệu pitch/demo. Mỗi ngày pilot chạy với claim này là mỗi ngày tích lũy evidence cho Điều 198.

---

### VI PHẠM 2: Claim "Đảm bảo học sinh tăng 2–3 điểm Toán chỉ sau 1 tháng" — Cam kết kết quả không có evidence

**Luật áp dụng:** Bộ luật Hình sự  
**Điều:** Điều 198 BLHS — Tội lừa dối khách hàng  
**Khoản:** Khoản 1 (gian lận trong giao dịch thương mại)

**Bằng chứng trong sản phẩm:**

> Trích từ `marketing_claims_audit.md` — Claim #3:
> *"Đảm bảo học sinh hiểu bài và tăng 2–3 điểm môn Toán chỉ sau 1 tháng."*

> Trích từ PRD Section 9 — Metrics (đối chiếu):
> *"Điểm số bài kiểm tra — bị loại — Ngoài tầm kiểm soát của sản phẩm trong pilot ngắn."*

**Phân tích vi phạm:**

Đây là mâu thuẫn nội bộ nghiêm trọng nhất trong toàn bộ bộ tài liệu. Cùng một startup:
- **Marketing nói:** "Đảm bảo tăng 2–3 điểm sau 1 tháng"
- **PRD của chính họ nói:** Điểm số bài kiểm tra là metric "Ngoài tầm kiểm soát của sản phẩm"

Nếu cơ quan điều tra đọc cả hai file này cùng lúc, không cần chứng minh thêm bất kỳ điều gì. PRD tự thừa nhận claim marketing là không có cơ sở. Đây là trường hợp "founder biết rõ mình không thể thực hiện cam kết nhưng vẫn cam kết" — yếu tố chủ quan của Điều 198.

**Pattern khớp với:** Vụ Kẹo Kera 11/2025 — cam kết công dụng cụ thể (giảm X kg, tăng Y sức đề kháng) không có thử nghiệm lâm sàng.

**Hành động sửa (trong 1 tuần):**
1. **Xóa ngay** từ "đảm bảo" và con số "2–3 điểm" khỏi tất cả kênh
2. Không thay bằng bất kỳ cam kết kết quả nào cho đến khi có ít nhất 1 cohort data đầy đủ (≥30 học sinh, ≥4 tuần)
3. Định vị lại: *"Mẹ Âu Cơ giúp học sinh tự giải được nhiều bài hơn — cải thiện điểm số phụ thuộc vào thói quen học tập của từng học sinh"*

**Deadline:** **Ngay lập tức** — đây là claim nguy hiểm nhất, trực tiếp cam kết outcome bằng số.

---

### VI PHẠM 3: Claim "Thay thế hoàn toàn gia sư dạy kèm" — Mô tả sai tính năng sản phẩm

**Luật áp dụng:** Bộ luật Hình sự  
**Điều:** Điều 198 BLHS — Tội lừa dối khách hàng  
**Khoản:** Khoản 1

**Bằng chứng trong sản phẩm:**

> Trích từ `marketing_claims_audit.md` — Claim #2:
> *"Thay thế hoàn toàn gia sư dạy kèm, giúp phụ huynh nhàn tênh."*

> Trích từ PRD Section 4 — Non-Goals:
> *"Thay thế giáo viên — [đây là Non-Goal của sản phẩm]"*

> Trích từ PRD Section 8 — Hole 2:
> *"Học sinh kẹt sau 3 micro-steps Level 3 → async note to teacher → 'Mình đã ghi lại chỗ bạn đang kẹt để thầy/cô xem vào buổi học tới.'"*

**Phân tích vi phạm:**

Giống như VI PHẠM 2, đây là mâu thuẫn nội bộ được ghi thành văn bản. PRD ghi tường minh "Thay thế giáo viên = Non-Goal". Hơn nữa, toàn bộ Stagnation Fallback flow đều **phụ thuộc vào giáo viên** — khi AI không giúp được, học sinh được gửi về giáo viên. Nếu gia sư đã bị "thay thế hoàn toàn", thì Stagnation Fallback không có ai để fallback.

Phụ huynh mua vì tin sẽ không cần thuê gia sư nữa → trẻ vẫn cần giáo viên hỗ trợ → khiếu nại → Điều 198.

**Pattern khớp với:** Kẹo Kera — tuyên bố thay thế y tế truyền thống khi thực tế không thể.

**Hành động sửa (trong 1 tuần):**
1. Xóa "thay thế hoàn toàn" — không thể giữ bất kỳ phiên bản nào của claim này
2. Thay bằng positioning đúng thật: *"Trợ lý học tập sau giờ học — giúp học sinh tự vượt điểm kẹt mà không phải chờ đến sáng hôm sau hỏi thầy"* (đây là Job-to-be-done thật trong PRD Section 2)
3. Đây là positioning tốt hơn về marketing — honest positioning thường convert cao hơn overclaim với sản phẩm EdTech

**Deadline:** **Tuần này** — ưu tiên thấp hơn VI PHẠM 1 và 2 về hình sự, nhưng là claim xuất hiện nhiều nhất trên social media.

---

## PHẦN II — VI PHẠM DỮ LIỆU CÁ NHÂN (PDPL — Luật 91/2025/QH15)

---

### VI PHẠM 4: Chuyển dữ liệu học sinh vị thành niên ra nước ngoài không có CTIA — Vi phạm đang diễn ra

**Luật áp dụng:** Luật Bảo vệ Dữ liệu Cá nhân 91/2025/QH15  
**Điều:** Điều 30 — Chuyển dữ liệu cá nhân ra nước ngoài  
**Khoản:** Khoản 3 (bắt buộc CTIA trước khi chuyển)  
**Mức phạt nếu vi phạm:** Theo Điều 8 PDPL — phạt tối đa **10 lần doanh thu** từ hoạt động vi phạm

**Bằng chứng trong sản phẩm:**

> Trích từ PRD Section 7.1 (AI Architecture):
> *"Tutor AI — Model: Claude Sonnet hoặc GPT-4o — Input: conversation history + student work + hint_level từ Analyzer + corpus chunk"*

> Trích từ PRD Section 12:
> *"LLM API — Claude Sonnet (Tutor) + GPT-4o-mini (Analyzer). DPA ký trước launch."*

> Trích từ `territorial_scope.md`:
> *"Hạ tầng Server/Database: Đang deploy trên Railway (hầu hết server đặt ở US/EU/Singapore)"*

> Trích từ `document_trail.md`:
> *"DPIA / CTIA — Status: ✗ CHƯA CÓ — Deadline: Nộp chậm nhất 60 ngày sau Launch"*

**Phân tích vi phạm:**

Mỗi lần học sinh 15–16 tuổi bấm "Gợi ý bước tiếp theo", toàn bộ conversation history (bao gồm đề bài, lời giải đang làm, các hint đã nhận) được gửi sang server Anthropic tại Mỹ và/hoặc OpenAI tại Mỹ để sinh hint. Đây là hành vi **chuyển dữ liệu cá nhân của trẻ vị thành niên ra nước ngoài** theo định nghĩa của PDPL.

Điều 30 PDPL yêu cầu CTIA phải được thực hiện **trước khi bắt đầu chuyển dữ liệu**, không phải sau 60 ngày. "60 ngày sau launch" trong `document_trail.md` là cách hiểu sai — deadline 60 ngày là để **nộp báo cáo** lên cơ quan có thẩm quyền sau khi đã thực hiện CTIA. Bản thân CTIA phải xong trước ngày đầu tiên pilot.

**Thêm yếu tố aggravating:** Đây là dữ liệu của trẻ vị thành niên (15–16 tuổi) — theo PDPL Điều 2 Khoản 11, đây là **dữ liệu cá nhân nhạy cảm đặc biệt**, mức phạt và yêu cầu tuân thủ cao hơn dữ liệu người lớn.

**Hạ tầng Railway (US/EU/SG)** là thêm 1 luồng chuyển dữ liệu độc lập cần CTIA riêng.

**Pattern khớp với:** Vụ rò rỉ CIC 9/2025 — PDPL Điều 8 phạt 10x doanh thu. Mẹ Âu Cơ chưa có doanh thu lớn, nhưng khi có vụ rò rỉ dữ liệu học sinh (breach tại OpenAI hoặc Anthropic — đã xảy ra với các công ty khác) thì phạt tính trên toàn bộ doanh thu từ hoạt động xử lý dữ liệu đó.

**Hành động sửa (trong 1 tuần):**
1. **Dừng pilot** cho đến khi CTIA cho OpenAI API và Anthropic API được hoàn thành và ký — hoặc implement pseudonymization (xem bên dưới)
2. **Pseudonymization ngay:** Loại bỏ tên, email, mã học sinh khỏi payload gửi API — chỉ dùng `session_id` ẩn danh. Đây là biện pháp kỹ thuật giảm thiểu rủi ro có thể implement trong 1–2 ngày
3. **Xác nhận Zero Data Retention** với OpenAI (opt-out training) và Anthropic — ghi vào CTIA
4. Thuê luật sư soạn CTIA cho Railway (hạ tầng), OpenAI, Anthropic — 3 CTIA riêng biệt
5. Nộp DPIA cho cơ quan có thẩm quyền

**Deadline:** **Trước ngày đầu pilot** — không có ngoại lệ. Đây là vi phạm đang diễn ra, không phải rủi ro tương lai.

---

### VI PHẠM 5: Không có Parental Consent Flow cho dữ liệu trẻ vị thành niên

**Luật áp dụng:** Luật Bảo vệ Dữ liệu Cá nhân 91/2025/QH15  
**Điều:** Điều 11 — Đồng ý xử lý dữ liệu cá nhân; Điều 2 Khoản 11 — Dữ liệu đặc biệt nhạy cảm  
**Khoản:** Điều 11 Khoản 4 (người dưới 18 tuổi cần đồng ý từ cha mẹ/người giám hộ)

**Bằng chứng trong sản phẩm:**

> Trích từ PRD Section 5 — User Flow:
> *"[1] Học sinh vào app → Chọn lớp → Chọn bài tập được giao"*
> → Không có bước nào yêu cầu xác nhận tuổi, lấy đồng ý phụ huynh, hoặc xác minh người giám hộ.

> Trích từ PRD Section 2:
> *"Target User: Học sinh Toán 10 — 15–16 tuổi"*

> Trích từ PRD Section 4 — Out-of-Scope (MVP):
> *"Parent view → V2"*

> Trích từ PRD Section 11 — Risks:
> *"Privacy: dữ liệu học sinh vị thành niên — Likelihood: Low, Impact: Critical"*

**Phân tích vi phạm:**

PRD ghi rõ target user là 15–16 tuổi — tức là toàn bộ user base đều là trẻ vị thành niên theo PDPL. Tuy nhiên, toàn bộ onboarding flow không có bất kỳ bước nào:
- Thu thập đồng ý của cha mẹ/người giám hộ
- Thông báo cho phụ huynh về loại dữ liệu được thu thập
- Cho phụ huynh xem hoặc xóa dữ liệu của con

**"Parent view → V2"** trong Out-of-Scope là một quyết định thiết kế sản phẩm hợp lý — nhưng Parental Consent không phải tính năng UX, đó là nghĩa vụ pháp lý bắt buộc từ ngày đầu, không thể đưa vào V2.

**Thêm vấn đề:** PRD đánh giá Likelihood của rủi ro này là "Low" — đây là đánh giá sai về mặt pháp lý. Likelihood không phải là "xác suất xảy ra" — đây là **nghĩa vụ pháp lý bắt buộc**, không có xác suất. Đánh giá "Low Likelihood" có thể được dùng để lập luận rằng founder không nhận thức đủ về nghĩa vụ pháp lý, điều này gây bất lợi hơn thay vì có lợi trong tố tụng.

**Pattern khớp với:** Vụ rò rỉ CIC 9/2025 — thu thập và xử lý dữ liệu cá nhân không có cơ sở pháp lý đồng ý đúng chuẩn.

**Hành động sửa (trong 1 tuần):**
1. **Thêm Parental Consent Gate** vào onboarding flow — trước khi học sinh submit bất kỳ bài nào:
   - Option A (đơn giản hơn): Giáo viên/trường ký MOU thay mặt, trong đó có điều khoản phụ huynh được thông báo — document MOU này
   - Option B (chuẩn PDPL hơn): Form đồng ý phụ huynh gửi qua email trước khi học sinh active tài khoản
2. Sửa Risk Register trong PRD: đổi Likelihood từ "Low" thành "Certain" (vì đây là nghĩa vụ pháp lý, không phải rủi ro ngẫu nhiên)
3. Viết Privacy Notice riêng cho phụ huynh — liệt kê rõ loại dữ liệu, mục đích, bên thứ 3 nhận dữ liệu (OpenAI, Anthropic, Railway)

**Deadline:** **Trước ngày đầu pilot** — không có ân hạn cho nghĩa vụ đồng ý của người giám hộ với dữ liệu trẻ vị thành niên.

---

## PHẦN III — VI PHẠM PHÂN LOẠI RỦI RO AI (Luật AI VN 134/2025/QH15)

---

### VI PHẠM 6: Chưa đăng ký hệ thống AI Tầng Cao với Bộ KH&CN — Luật đã có hiệu lực từ 1/3/2026

**Luật áp dụng:** Luật AI Việt Nam 134/2025/QH15  
**Điều:** Điều 9 Khoản 1 (phân loại Tầng Cao); Điều 15 (nghĩa vụ đăng ký); Điều 19 (Conformity Assessment)  
**Khoản:** Điều 15 Khoản 1 — đăng ký vào CSDL AI quốc gia trước khi triển khai

**Bằng chứng trong sản phẩm:**

> Trích từ PRD Section 7.1:
> *"Analyzer AI — Classify lời giải: genuine effort / pattern matching / AI-generated / incoherent; Output: effort_state, hint_level, progress_flag"*

> Trích từ PRD Section 7 — System Design (implicit từ SRS):
> *Mastery Score, Error Taxonomy, Stagnation Flag, Effort Validation — tất cả ảnh hưởng trực tiếp đến cơ hội học tập của học sinh 15–16 tuổi*

> Trích từ `territorial_scope.md`:
> *"Phân loại: TẦNG CAO (High Risk) — Lĩnh vực: Giáo dục (Điều 9 Khoản 1)"*

> Trích từ `document_trail.md`:
> *"5/5 hồ sơ chưa có ✗"* — không có hồ sơ đăng ký Bộ KH&CN

**Phân tích vi phạm:**

Luật AI Việt Nam 134/2025/QH15 có hiệu lực từ **1/3/2026** — tức là đã có hiệu lực **68 ngày** tính đến ngày rà soát (08/05/2026). Mẹ Âu Cơ đang phát triển một hệ thống AI Tầng Cao trong lĩnh vực giáo dục và chưa thực hiện bất kỳ nghĩa vụ pháp lý nào theo Luật này.

**Các nghĩa vụ cụ thể đã bị bỏ qua:**

| Nghĩa vụ | Điều luật | Status | Ân hạn còn lại |
|---|---|---|---|
| Conformity Assessment (đánh giá phù hợp) | Điều 19 | ✗ Chưa có | ~16 tháng (đến 1/9/2027) |
| Đăng ký CSDL AI quốc gia | Điều 15 | ✗ Chưa có | ~16 tháng |
| Human Oversight Protocol | Điều 22 | Có một phần (Teacher Dashboard) nhưng chưa document | ~16 tháng |
| Incident Reporting Procedure | Điều 25 | ✗ Chưa có | ~16 tháng |
| Audit Log đủ chuẩn | Điều 23 | ✗ Chưa xác nhận | ~16 tháng |

**Lưu ý ân hạn 18 tháng:** Với lĩnh vực Giáo dục, ân hạn kéo dài đến **1/9/2027**. Đây là tin tốt — nhưng ân hạn không có nghĩa là không phải làm gì. Ân hạn cho phép startup có thời gian build hồ sơ đúng. **Nếu có sự cố xảy ra trong thời gian ân hạn** (ví dụ: AI sinh hint sai, học sinh học theo, điểm thi giảm), Luật AI vẫn áp dụng để điều tra và quy trách nhiệm — ân hạn chỉ cho phép chuẩn bị hồ sơ, không miễn trừ trách nhiệm khi có sự cố.

**Pattern khớp với:** Đây là vi phạm về không tuân thủ luật mới — chưa có vụ án mẫu tại Việt Nam, nhưng pattern tương tự với các startup fintech bị xử phạt vì thiếu giấy phép trung gian thanh toán (Điều 1 Nghị định 101/2012/NĐ-CP) trước khi có giấy phép.

**Hành động sửa (trong 1 tuần):**
1. **Tuần này:** Document Human Oversight Protocol — Teacher Dashboard có gì, giáo viên có thể override gì, học sinh có thể báo cáo AI sai như thế nào (Button "Hint này có vẻ sai" trong PRD Section 8 → cần document đây là Human Oversight mechanism)
2. **Tháng 6/2026:** Bắt đầu Conformity Assessment — thuê consultant hoặc tự làm theo hướng dẫn của Bộ KH&CN
3. **Tháng 8/2026:** Đăng ký CSDL AI quốc gia (để đủ thời gian buffer trước deadline)
4. **Ngay lập tức:** Build Incident Log — mỗi khi Tutor AI sinh hint sai và được flag, ghi lại. Đây vừa là yêu cầu Luật AI, vừa là bằng chứng human oversight đang hoạt động

**Deadline:** Ân hạn đến **1/9/2027** — nhưng bắt đầu từ tháng 6/2026 để có buffer.

---

## PHẦN IV — VI PHẠM VENDOR & PAYMENT (Điều 324 BLHS)

---

### VI PHẠM 7: Không có cơ chế giám sát giao dịch bất thường cho Subscription — Rủi ro Điều 324 khi scale

**Luật áp dụng:** Bộ luật Hình sự  
**Điều:** Điều 324 BLHS — Tội rửa tiền  
**Khoản:** Khoản 1 (thiếu kiểm soát giao dịch trong hoạt động kinh doanh có liên quan đến dòng tiền)  
**Luật bổ sung:** Luật Phòng chống rửa tiền 2022, Điều 17 — Nhận biết khách hàng (KYC)

**Bằng chứng trong sản phẩm:**

> Trích từ `document_trail.md`:
> *"Nhật ký giám sát giao dịch bất thường — Status: ✗ CHƯA CÓ — Tính năng Subscription sẽ dev ở Tuần 6"*

> Trích từ PRD Section 12:
> *"Budget: ~35 học sinh × 5 submit/ngày × 3 API calls/submit × $0.002 = ~$1/ngày cho pilot"*

> Trích từ PRD Section 4 — Out-of-Scope:
> *Không có hạng mục nào về payment compliance, KYC, hoặc AML monitoring*

**Phân tích vi phạm:**

Đây là **vi phạm tiềm năng, không phải vi phạm đang diễn ra** — vì Subscription chưa launch. Tuy nhiên, đây cần được flagged ở mức độ cao vì:

**Pattern Điều 324 không yêu cầu founder chủ động rửa tiền.** Điều 324 áp dụng khi:
1. Hệ thống thanh toán của startup được dùng để luân chuyển tiền bất hợp pháp
2. Startup **biết hoặc có thể biết** nhưng không có cơ chế phát hiện
3. Giao dịch bất thường xảy ra mà không có ai ghi nhận

Với mô hình Subscription cho học sinh/phụ huynh, các pattern rủi ro bao gồm:
- Tài khoản giả tạo với thẻ ngân hàng ăn cắp để test trước khi dùng cho gian lận lớn hơn
- Nhiều giao dịch nhỏ từ cùng 1 nguồn (smurfing)
- Refund abuse có tổ chức

**Pattern khớp với:** Vụ Shark Bình 2/2026 — không phải Shark Bình chủ động rửa tiền, mà hệ thống đầu tư của ông không có cơ chế phát hiện dòng tiền bất thường. Đây là lý do Điều 324 có thể áp dụng cho người vận hành nền tảng, không chỉ người rửa tiền trực tiếp.

**Hành động sửa (trước khi launch Subscription — Tuần 6):**
1. Chọn payment gateway có AML/fraud detection built-in — Stripe (có) hoặc VNPay Business (có giám sát theo quy định SBV)
2. Thiết lập threshold tự động: flag giao dịch >5 triệu VND/tháng từ 1 tài khoản hoặc >10 giao dịch/ngày từ 1 IP
3. Implement KYC cơ bản: xác minh email + SĐT thật trước khi cho phép giao dịch đầu tiên
4. Build Nhật ký giám sát giao dịch (hồ sơ #3) — có thể đơn giản là Google Sheet được cập nhật tự động từ webhook payment gateway, có người review hàng tuần

**Deadline:** **Trước khi launch tính năng Subscription (Tuần 6)** — không phải ngay lập tức, nhưng không thể bỏ qua.

---

## PHẦN V — VI PHẠM BỔ SUNG (Ngoài yêu cầu tối thiểu)

---

### VI PHẠM 8: Giáo viên upload tài liệu có bản quyền — Rủi ro Điều 225 BLHS (Xâm phạm quyền tác giả)

**Luật áp dụng:** Bộ luật Hình sự  
**Điều:** Điều 225 — Xâm phạm quyền tác giả, quyền liên quan  
**Khoản:** Khoản 1

**Bằng chứng trong sản phẩm:**

> Trích từ PRD Section 7.2:
> *"Corpus nguồn: Tài liệu giáo viên upload (PDF/Word → Markdown): lời giải mẫu, phân tích lỗi phổ biến, ghi chú pedagogy; SGK Toán 10 (public domain) làm tham chiếu nền"*

**Phân tích vi phạm:**

Khi giáo viên upload "lời giải mẫu" dưới dạng PDF — rất có khả năng đây là tài liệu từ sách tham khảo thương mại (Loigiaihay, Vietjack, sách bài tập của NXB Giáo dục). Khi startup chuyển tài liệu này thành Markdown, lưu trữ trong vector database, và dùng làm RAG corpus cho AI sinh hint → đây là hành vi **tái sản xuất và sử dụng tác phẩm bảo hộ** mà không có giấy phép.

PRD ghi "SGK Toán 10 (public domain)" — nhưng SGK hiện hành của NXB Giáo dục Việt Nam **không phải public domain**, chỉ có SGK trước năm 1975 mới có thể coi là public domain theo Luật SHTT Việt Nam.

**Hành động sửa:**
1. Thêm điều khoản ToS cho giáo viên: "Chỉ upload tài liệu do giáo viên tự soạn hoặc có giấy phép sử dụng"
2. Xác nhận lại với legal về SGK — cần giấy phép từ NXB Giáo dục Việt Nam nếu dùng làm corpus thương mại
3. Ưu tiên corpus do giáo viên tự tạo — an toàn hơn về bản quyền và tốt hơn về chất lượng pedagogy

**Deadline:** **Trước pilot** — vì corpus đã được setup từ trước launch.

---

## TỔNG KẾT — BẢNG XẾP HẠNG ƯU TIÊN

| # | Vi phạm | Luật | Mức độ nguy hiểm | Đang vi phạm? | Deadline sửa |
|---|---|---|---|---|---|
| 4 | Chuyển dữ liệu HS vị thành niên ra nước ngoài không có CTIA | PDPL Điều 30 | 🔴 NGAY LẬP TỨC | ✅ Đang diễn ra | Trước pilot ngày 1 |
| 5 | Không có Parental Consent Flow | PDPL Điều 11 | 🔴 NGAY LẬP TỨC | ✅ Đang diễn ra | Trước pilot ngày 1 |
| 2 | Claim "tăng 2–3 điểm — đảm bảo" | BLHS Điều 198 | 🔴 NGAY LẬP TỨC | ✅ Đang active | Xóa hôm nay |
| 1 | Claim "AI không bao giờ cho đáp án" | BLHS Điều 198 | 🔴 NGAY LẬP TỨC | ✅ Đang active | Xóa hôm nay |
| 3 | Claim "thay thế hoàn toàn gia sư" | BLHS Điều 198 | 🟠 Tuần này | ✅ Đang active | Tuần này |
| 8 | Corpus có tài liệu có bản quyền | BLHS Điều 225 | 🟠 Tuần này | Có thể đang diễn ra | Trước pilot |
| 6 | Chưa đăng ký hệ thống AI Tầng Cao | Luật AI Điều 15 | 🟡 Ân hạn còn | Chưa (ân hạn) | 1/9/2027 |
| 7 | Không có AML monitoring cho Subscription | BLHS Điều 324 | 🟡 Rủi ro tương lai | Chưa (Subscription chưa launch) | Trước Tuần 6 |

---

## HÀNH ĐỘNG 72 GIỜ TỚI (Founder cần làm ngay)

**Giờ 1–4:**
- [ ] Xóa/khóa toàn bộ tài liệu marketing có VI PHẠM 1 và 2 (claim "không bao giờ" và "tăng 2–3 điểm")
- [ ] Gọi điện cho Engineering: implement pseudonymization cho API payload ngay hôm nay (bỏ tên/email học sinh khỏi prompt gửi OpenAI/Anthropic)

**Giờ 4–24:**
- [ ] Liên hệ luật sư PDPL: đặt lịch soạn CTIA cho OpenAI + Anthropic + Railway
- [ ] Thiết kế Parental Consent Gate (có thể đơn giản: giáo viên ký MOU thay mặt phụ huynh — xác nhận với luật sư xem cách này có đủ không)

**Ngày 2–3:**
- [ ] Viết lại 4 marketing claims theo Honest Version đã có trong `marketing_claims_audit.md`
- [ ] Founder ký từng claim mới (hồ sơ #5 — phê duyệt marketing)
- [ ] Rà soát corpus giáo viên đã có: kiểm tra nguồn gốc bản quyền

---


