---
artifact: 5 — Solution Approach (phần khám phá)
bai-tap: Solution — tìm lời giải đã có sẵn trước khi tự xây
phase: Double Diamond vòng 2 · ◇ giãn (mở hết lựa chọn, chưa chốt)
time: ~8 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 01-frame/3-FINAL-problem-framing.md · 00-context.md · prompts/04-find-solutions.md
nop-cuoi: Không — file trung gian (bản chốt ở 2-FINAL-solution.md)
---

# 1 — Find existing solutions (đừng xây lại từ số 0)

Mục tiêu: trước khi quyết Build / Buy / Boost / Partner, nhóm phải biết bài này đã có ai giải ở chỗ khác chưa, và họ giải bằng cách nào. Đây là nửa "giãn ra" của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 2 — mở hết các lời giải đang tồn tại, chưa chốt cái nào.

Lý do làm bước này: đây là chỗ nhiều nhóm hỏng mà không biết. Hỏng vì nhảy thẳng vào "tự build" cho oai, trong khi 80–90% nhu cầu nội bộ chỉ cần Boost hoặc Buy. Hỏng vì không hỏi "ai làm rồi" nên đi lại từ số 0. Gần như bài nào cũng đã có người giải ở một ngành khác — không thấy thì phí cả pilot.

Quy tắc: **không có nguồn = giả định.** Mỗi cái AI/web nói ra, hỏi lại "lấy ở đâu?". Không chỉ được nguồn thì đánh dấu 🧮 (giả định để giảng), đừng xài như fact.

## Bước 0 — Bài này thực ra là dạng bài gì? (2 phút)

Bỏ context AI20k sang một bên. Mô tả Quick Win của nhóm như một bài toán chung — không có chữ "học viên / coach / Discord". Vài ví dụ cho dễ hình dung:

- "câu hỏi của user → câu trả lời kèm nguồn" → đây là bài Q&A có citation
- "một đống văn bản lộn xộn → data có cấu trúc" → bài extraction
- "bài nộp → nhận xét theo rubric" → bài rubric grading

Dạng bài (the pattern) đó gần như chắc chắn đã có người làm ở ngành khác. Tìm ra dạng bài → tìm ra người đã giải nó.

- **Quick Win của nhóm, viết lại thành 1 dạng bài chung (không có chữ domain)**: "artifact của người dùng + rubric đánh giá → feedback cá nhân hóa + danh sách tài liệu học tiếp theo phù hợp với lỗ hổng phát hiện được" — đây là bài **rubric-based gap analysis + personalized learning recommendation**
- **Input → output thực chất là gì**: Bài nộp text (3 file FINAL) + Rubric 5 Gate → Danh sách 3 concept/tài liệu cần xem lại (tên cụ thể + link + 1 câu giải thích)
- **Ràng buộc không bỏ được (lấy từ `00-context.md`)**: Privacy (cần consent), Human review (coach xem trước khi gửi), Citation (phải trỏ tài liệu thật trong khóa), Budget nhỏ (<$10 API)

## Quy trình 8 phút

```text
2 phút  — Bước 0: gọi tên dạng bài
4 phút  — Phần A: deep research 4 tầng "ai giải dạng bài này rồi"
2 phút  — Phần B: rút về 2–3 hướng khả thi, đánh dấu nguồn
```

---

## Phần A — Deep research: ai giải dạng bài này rồi, giải sao?

Không phải gõ 1 câu vào AI rồi chép. Chạy 4 tầng, **tầng sau lấy kết quả tầng trước làm input**. Khung câu lệnh ở `prompts/04-find-solutions.md`.

Câu hỏi phụ (tự trả lời — viết ra cái nhóm *tìm thấy*, không phải cái nhóm *đoán*):

- Dạng bài này giống bài nào ở một ngành hoàn toàn khác?
- Hướng nào AI gợi ý mà nhóm **không kiểm được nguồn** — vậy có nên tin không?
- Một ca thất bại của người đi trước dạy nhóm tránh đúng điều gì?
- Nhóm "đi từ mức mấy" — kế thừa được gì để khỏi bắt đầu từ 0?

### Trả lời — điền theo 4 tầng

| Tầng | Hỏi AI/web câu gì | Tìm được gì | Nguồn / 🧮 nếu là giả định |
|---|---|---|---|
| 1 · Map | "Bài rubric-based gap analysis + learning recommendation thường giải bằng hướng nào? 4-6 hướng." | (1) LLM với rubric làm system prompt — phân tích bài theo từng Gate, sinh gợi ý. (2) RAG: embed tài liệu khóa + query từ lỗi phát hiện → truy xuất đoạn liên quan. (3) Rule-based decision tree: map điểm rubric → nhóm tài liệu cố định. (4) Embedding similarity: so sánh bài nộp với "bài chuẩn" để phát hiện khoảng cách. (5) Fine-tuned classifier: train model nhận diện loại lỗi → đề xuất resource. | 🧮 Tổng hợp từ kiến thức AI/ML phổ biến; không có nguồn cụ thể cho từng hướng. |
| 2 · Tiền lệ | "Tổ chức giáo dục nào đã dùng AI phân tích bài nộp → gợi ý tài liệu cá nhân hóa?" | **Khan Academy Khanmigo** (2023): dùng GPT-4 làm gia sư, phân tích câu trả lời học sinh và đặt câu hỏi Socratic + gợi ý bài tập phù hợp — tương tự pattern nhưng tập trung vào Q&A hơn là artifact nộp. **Coursera AI Feedback** (2023): AI phân tích bài peer review theo rubric, gợi ý phần cần cải thiện — rất gần pattern của nhóm. **Carnegie Mellon OLI** (Open Learning Initiative): adaptive learning platform dựa trên phân tích lỗi → gợi ý module học bù. | Khan Academy + Coursera: nguồn báo chí (🧮 chi tiết kỹ thuật không verify được). CMU OLI: oli.cmu.edu là thật nhưng chi tiết triển khai là 🧮. |
| 3 · Phản chứng | "Ca nào dùng AI feedback theo rubric thất bại? Nguyên nhân gốc?" | **ETS e-rater essay scoring**: học sinh gaming rubric (viết câu dài/phức tạp mà không cần logic tốt vẫn được điểm cao) vì rubric quá đơn giản. **Automated grading ở MIT**: feedback AI nghe chuyên nghiệp nhưng không relate đến bài nộp cụ thể — copy từ template chung. **Recommendation engine bị bỏ qua**: nhiều hệ thống gợi ý tài liệu thất bại vì gợi ý quá nhiều (overload) hoặc gợi ý không liên quan trực tiếp đến lỗi vừa mắc. | 🧮 ETS e-rater là thật; chi tiết ca thất bại cụ thể là giả định tổng hợp từ nghiên cứu về AI grading failures. |
| 4 · Thu hẹp | "Với budget <$10, cần human review, cần citation trỏ tài liệu thật, pilot 2 tuần — hướng nào khả thi nhất?" | **Hướng 1 (LLM + rubric system prompt + mapping table)**: khả thi nhất — không cần train model, rubric D28 đã có, mapping table tự build 2-3 giờ, Claude API <$5 cho 80 bài. **Hướng 2 (RAG nhẹ)**: khả thi trong 6 tuần nếu embed tài liệu khóa — phức tạp hơn nhưng citation tốt hơn. **Hướng 3 (Rule-based)**: nhanh nhất nhưng kém cá nhân hóa, dễ thành "cá nhân hóa giả". Không khả thi: Fine-tuned model (cần data lớn, vượt budget); Embedding similarity (cần "bài chuẩn" chưa có). | 🧮 Ước tính cost và effort là giả định; cần test thật để confirm. |

---

## Phần B — Rút về 2–3 hướng khả thi

Câu hỏi phụ:

- Hướng nào *kế thừa được nhiều nhất* từ người đã làm?
- Hướng nào nghe hay nhưng nhóm **không có nguồn** để tin?

### Trả lời

| Hướng giải khả thi | Ai làm rồi (gần bài mình nhất) | Nguồn / 🧮 | Hợp ràng buộc `00-context`? |
|---|---|---|---|
| LLM (Claude API) + rubric D28 system prompt + mapping table lỗi→tài liệu | Coursera AI Feedback (phân tích bài theo rubric + gợi ý) | 🧮 chi tiết kỹ thuật Coursera | Có — budget <$10 ✓, human review ✓, citation trỏ tài liệu thật ✓ |
| RAG nhẹ: embed tài liệu khóa (slide+handbook) + query từ lỗi phát hiện | Khan Academy Khanmigo (RAG-based Q&A có citation) | 🧮 chi tiết kỹ thuật Khanmigo | Có — nhưng setup phức tạp hơn (2-3 ngày thay vì vài giờ), vẫn trong 2 tuần ✓ |
| Rule-based decision tree: Gate trượt → nhóm tài liệu cố định | CMU OLI (adaptive learning theo module) | 🧮 | Có — nhưng rủi ro "cá nhân hóa giả" cao (Red Flag #1 của track), không đủ cá nhân hóa ✗ |

**"Đi từ 5 lên" — nhóm kế thừa cụ thể cái gì** (1–2 câu):

```text
Kế thừa pattern của Coursera AI Feedback: dùng LLM làm lớp trung gian phân tích bài nộp
theo rubric, không cần train model mới. Thứ AI20k cần build thêm là mapping table riêng
(Gate/lỗi → tài liệu khóa cụ thể) — đây là phần domain-specific chưa ai làm sẵn.
```

---

## Phát hiện ban đầu

Ghi nhanh 2–3 cái đáng chú ý nhất (chưa phải quyết định — quyết định ở file FINAL):

- Ca thất bại của ETS e-rater dạy bài học quan trọng: mapping table phải dựa trên chất lượng lập luận, không chỉ hình thức văn bản — rubric D28 đã có cái này (Gate rõ ràng).
- Hướng Rule-based rất hấp dẫn vì đơn giản nhưng đúng là "cá nhân hóa giả" — Red Flag #1 của track. Loại.
- RAG có thể là Phase 2 sau khi LLM + rubric pilot thành công — không cần xây ngay.

## Câu hỏi mở (mang sang bước chốt)

- Mapping table lỗi→tài liệu nên có bao nhiêu entries là đủ? (5 Gate × 2-3 lỗi phổ biến/Gate = ~15 entries?)
- Claude model nào phù hợp nhất — Haiku (rẻ, nhanh) hay Sonnet (hiểu sắc thái hơn)?

---

## Tổng kiểm tra trước khi sang `2-FINAL-solution.md`

| Hạng mục | Xong? |
|---|---|
| Gọi được dạng bài trong 1 câu, không còn chữ domain | ✓ (rubric-based gap analysis + personalized learning recommendation) |
| Đủ 4 tầng deep research, tầng nào cũng có kết quả | ✓ |
| Mỗi kết quả có nguồn, hoặc đánh dấu 🧮 nếu là giả định | ✓ |
| Rút về 2–3 hướng + nói được "đi từ 5 lên" cái gì | ✓ (kế thừa pattern Coursera + thêm mapping table riêng) |

Hàng nào chưa xong → quay lại Phần A, đừng sang bước chốt vội.

Sau bước này, mở `2-FINAL-solution.md` — chốt Build/Buy/Boost/Partner + data & ai review + bản vẽ trực quan (đây là bản nộp của phase này).

*Liên quan: handbook §A5 · `prompts/04-find-solutions.md` · `00-context.md`*
