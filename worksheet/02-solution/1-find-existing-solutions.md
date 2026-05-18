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

- **Quick Win của nhóm, viết lại thành 1 dạng bài chung (không có chữ domain)**: "câu hỏi tự nhiên về tài liệu học → câu trả lời kèm nguồn cụ thể, giới hạn trong corpus đã định, nói không biết nếu ngoài phạm vi" — đây là bài **scope-limited Q&A với grounded citation (RAG hoặc context-stuffed LLM)**
- **Input → output thực chất là gì**: Câu hỏi text của học viên → câu trả lời ngắn + tên section/đoạn trích từ handbook D28; HOẶC "ngoài phạm vi, hỏi coach"
- **Ràng buộc không bỏ được (lấy từ `00-context.md`)**: Citation (phải trỏ section thật), Budget nhỏ (<$5), Human review (coach kiểm 10 câu test trước deploy), Ranh giới gia sư/đáp án (hỗ trợ đọc, không làm bài thay)

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
| 1 · Map | "Bài scope-limited Q&A với grounded citation thường giải bằng hướng nào? 4-6 hướng." | (1) Context stuffing: nhét toàn bộ tài liệu vào context window LLM + prompt strict "chỉ trả lời từ tài liệu này, cite section, nói không biết nếu không thấy". (2) RAG (Retrieval-Augmented Generation): embed tài liệu → vector search → lấy top đoạn liên quan → generate answer kèm citation. (3) Keyword/semantic search thuần: không generate, chỉ tìm và trả về đoạn văn có sẵn. (4) Fine-tuned model trên FAQ domain. (5) Rule-based FAQ matching: câu hỏi khớp pattern → trả lời cố định. | 🧮 Tổng hợp từ kiến thức LLM/RAG phổ biến; không có nguồn cụ thể cho từng hướng. |
| 2 · Tiền lệ | "Công cụ hay tổ chức nào đã xây scope-limited Q&A từ tài liệu nội bộ có citation?" | **Notion AI Q&A** (2023): hỏi về nội dung workspace Notion riêng, trả lời với citation trỏ đúng page → rất gần pattern của nhóm (corpus giới hạn + citation). **Perplexity AI** (2023): Q&A kèm citation từ web — pattern giống nhưng corpus mở, không giới hạn. **Langchain + ChromaDB docs chatbot**: tutorial phổ biến — embed PDF tài liệu nội bộ + Q&A kèm nguồn. **Stanford HAI DocsBot**: chatbot từ tài liệu khóa học, giới hạn trong scope. | Notion AI + Perplexity: nguồn báo chí (🧮 chi tiết kỹ thuật không verify được). Langchain tutorial: thật, có trên docs.langchain.com. Stanford HAI: 🧮 chi tiết triển khai. |
| 3 · Phản chứng | "Ca nào dùng LLM Q&A từ tài liệu bị thất bại? Nguyên nhân gốc?" | **Harvey AI hallucination (legal)**: AI trích dẫn án lệ không tồn tại — luật sư tin theo, nộp lên tòa, bị phát hiện → mất uy tín toàn hệ thống. Lesson: citation sai 1 lần = mất trust lâu dài. **EdTech chatbot thay thế đọc tài liệu**: học viên hỏi bot thay vì đọc sách → comprehension giảm (MIT study 🧮); bot nghe hay nhưng không thay được quá trình đọc. **Scope creep**: nhiều chatbot bắt đầu "chỉ trả lời từ tài liệu" rồi drift sang general knowledge khi prompt không đủ strict → Red Flag #1 của track. | Harvey AI: thật (Reuters 2023). MIT study EdTech: 🧮 tổng hợp. Scope creep: 🧮 pattern quan sát. |
| 4 · Thu hẹp | "Với handbook D28 ~40-60 trang, budget <$5, cần citation trỏ section, pilot 1 tuần — hướng nào khả thi nhất?" | **Hướng 1 (Context stuffing + Claude API)**: handbook D28 vừa trong context window Claude (~100K tokens) → nhét toàn bộ vào system prompt + instruction strict → không cần vector DB, không cần RAG setup, cost thấp nhất. **Hướng 2 (RAG nhẹ)**: embed handbook bằng OpenAI/Claude embeddings + ChromaDB → retrieval → generate. Phức tạp hơn nhưng scale tốt hơn khi tài liệu lớn hoặc nhiều ngày. **Hướng 3 (Rule-based FAQ)**: 30-40 câu hỏi phổ biến + câu trả lời cố định. Nhanh nhất, không hallucinate, nhưng không tương tác thật — chỉ trả lời câu đã dự đoán trước. | 🧮 Ước tính context size và cost; cần test thật để confirm. |

---

## Phần B — Rút về 2–3 hướng khả thi

Câu hỏi phụ:

- Hướng nào *kế thừa được nhiều nhất* từ người đã làm?
- Hướng nào nghe hay nhưng nhóm **không có nguồn** để tin?

### Trả lời

| Hướng giải khả thi | Ai làm rồi (gần bài mình nhất) | Nguồn / 🧮 | Hợp ràng buộc `00-context`? |
|---|---|---|---|
| Context stuffing: handbook D28 → system prompt Claude API + instruction strict citation + fallback "không biết" | Notion AI Q&A (corpus giới hạn + citation theo page) | 🧮 chi tiết kỹ thuật Notion | Có — budget <$5 ✓, không cần infra phức tạp ✓, citation section ✓, deploy nhanh ✓ |
| RAG nhẹ: embed handbook D28 + slide → ChromaDB → query → generate với citation | Langchain + ChromaDB docs chatbot tutorial | Thật (docs.langchain.com) | Có — nhưng setup 1-2 ngày thay vì vài giờ; overkill cho corpus nhỏ (~40-60 trang) ✗ tương đối |
| Rule-based FAQ: 30-40 câu hỏi phổ biến → câu trả lời cố định từ handbook | N/A | N/A | Có về budget — nhưng không tương tác thật, không cover câu hỏi mới, Red Flag ranh giới ✗ |

**"Đi từ 5 lên" — nhóm kế thừa cụ thể cái gì** (1–2 câu):

```text
Kế thừa pattern context-stuffed Q&A từ Notion AI + Harvey AI lesson (citation sai = mất trust):
chỉ cần viết đúng system prompt với instruction strict (cite section, nói không biết, không bịa)
và nhét handbook D28 vào context. Thứ AI20k cần build thêm là instruction guard cụ thể
cho context khóa học — phần domain-specific chưa ai làm sẵn cho AI Thực Chiến.
```

---

## Phát hiện ban đầu

Ghi nhanh 2–3 cái đáng chú ý nhất (chưa phải quyết định — quyết định ở file FINAL):

- Bài học Harvey AI là quan trọng nhất: 1 citation sai = mất trust toàn hệ thống. System prompt phải có guard "nếu không tìm thấy section cụ thể → nói không biết, không đoán mò."
- Context stuffing đơn giản hơn RAG rất nhiều cho corpus nhỏ — handbook D28 vừa trong 100K token. Không cần xây infra phức tạp cho pilot 1 tuần.
- Rule-based FAQ bị loại vì không tương tác thật (không trả lời câu hỏi mới) và dễ thành gia sư giả — Red Flag #2 của track.

## Câu hỏi mở (mang sang bước chốt)

- Cần instruction guard gì trong system prompt để ngăn chatbot drift sang general knowledge ngoài D28?
- Slide skeleton và handbook D28 khác nhau về format — cần pre-process trước khi nhét vào context không?

---

## Tổng kiểm tra trước khi sang `2-FINAL-solution.md`

| Hạng mục | Xong? |
|---|---|
| Gọi được dạng bài trong 1 câu, không còn chữ domain | ✓ (scope-limited Q&A với grounded citation) |
| Đủ 4 tầng deep research, tầng nào cũng có kết quả | ✓ |
| Mỗi kết quả có nguồn, hoặc đánh dấu 🧮 nếu là giả định | ✓ |
| Rút về 2–3 hướng + nói được "đi từ 5 lên" cái gì | ✓ (kế thừa Notion Q&A pattern + bài học Harvey AI về citation guard) |

Hàng nào chưa xong → quay lại Phần A, đừng sang bước chốt vội.

Sau bước này, mở `2-FINAL-solution.md` — chốt Build/Buy/Boost/Partner + data & ai review + bản vẽ trực quan (đây là bản nộp của phase này).

*Liên quan: handbook §A5 · `prompts/04-find-solutions.md` · `00-context.md`*
