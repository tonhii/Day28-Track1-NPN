---
artifact: 5 — Solution Approach + 6 — Demo/Mockup/Flow (bản nộp phase Solution)
bai-tap: Solution — chốt cách làm + cho stakeholder nhìn thấy
phase: Double Diamond vòng 2 · ◆ siết (chốt 1 cách làm + 1 artifact trực quan)
time: ~12 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 1-find-existing-solutions.md · 00-context.md · templates/demo-examples.md · prompts/05-demo-challenge.md
nop-cuoi: Có — bản nộp của phase Solution (Part B + C · A3 mục Solution Approach + Demo/Mockup/Flow)
---

# 2 — FINAL: Solution Approach + Demo/Mockup/Flow

Mục tiêu: chốt cách làm cho Quick Win (Build / Buy / Boost / Partner), nói rõ data & ai review cần có, và tạo 1 bản vẽ trực quan để stakeholder *nhìn* được. Đây là nửa "siết lại" của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 2 và là bản nộp của phase Solution.

Lý do làm bước này: hai cái bẫy. Một, "tự build" cho oai — trong khi 80–90% nhu cầu nội bộ chỉ cần Boost/Buy; tự build là quyết định khó rút lại nhất. Hai, chỉ nói bằng chữ — stakeholder không duyệt một đoạn văn, họ duyệt khi *nhìn thấy* flow. Không có bản vẽ → trượt Gate 4 dù lập luận tốt.

Quy tắc: **bản vẽ trực quan là BẮT BUỘC; demo chạy được chỉ là điểm cộng.** *Demo đơn giản + lập luận chặt > demo đẹp + lập luận yếu.*

## Quy trình 12 phút

```text
4 phút  — Phần A: chốt Build/Buy/Boost/Partner (decision tree + ego check)
3 phút  — Phần B: data & ai review cần có
5 phút  — Phần C: vẽ 1 artifact trực quan + đánh dấu chỗ người review
```

---

## Phần A — Chốt cách làm

Đi decision tree, đừng chọn theo cảm giác:

```text
Bài này có phải LỢI THẾ CẠNH TRANH CỐT LÕI không?
 ├─ CÓ  → đội có AI engineer mạnh? CÓ → Build · KHÔNG → Boost
 └─ KHÔNG (chỉ là productivity layer) → có tool sẵn?
          CÓ → Buy · KHÔNG → Boost (model sẵn + data riêng)
```

Câu hỏi phụ:

- Nhóm chọn cách này vì *cần* hay vì *thích tự build*? Một câu thành thật.
- Hướng nào ở file `1` (đã tìm được người làm rồi) khớp với cách này — "đi từ 5 lên"?

### Trả lời

- **Cách làm chốt**: **Boost** — Claude API (claude-haiku-4-5) + handbook D28 làm context (context stuffing) + system prompt strict với instruction citation và fallback "không biết"
- **Lý do CẦN (không phải thích), 2–3 câu**: Bài toán scope-limited Q&A với grounded citation là việc LLM hiện tại làm tốt mà không cần train thêm — chỉ cần cung cấp đúng corpus và instruction. Handbook D28 (~40-60 trang) vừa trong context window Claude → không cần RAG setup phức tạp. Đây là Boost, không phải Build: chỉ thêm data riêng (handbook D28) và instruction domain-specific vào model off-the-shelf.
- **Vì sao KHÔNG "Build từ số 0"**: Không phải lợi thế cạnh tranh cốt lõi của AI20k — nhiều tổ chức đã làm pattern này (Notion AI Q&A); không có AI engineer trong nhóm; timeline 1 tuần không đủ; LLM off-the-shelf với đúng context đã đủ tốt cho bài này.
- **Vì sao KHÔNG RAG**: Corpus nhỏ (~40-60 trang) vừa context window → RAG overkill; setup phức tạp hơn 3-5× mà không cải thiện đáng kể cho scale này; để RAG cho Phase 2 khi cần index nhiều ngày khóa học.
- **Tool / API / vendor cần + ước lượng chi phí thô**:
  - Claude API (claude-haiku-4-5): ~$1–3 cho ước tính 500 câu hỏi/tuần × ~500 tokens/câu (**🧮 ước tính**)
  - Hosting: Python script đơn giản hoặc Claude.ai Projects: $0
  - Tổng cash: **<$5**; effort: ~6 giờ người (đọc + format handbook 2h + viết system prompt 2h + test 10 câu mẫu 2h)

## Phần B — Data & ai review (cách làm này cần gì để chạy được)

| Cần gì | Có sẵn trong AI20k? | Trong lab dùng (mẫu/giả định) | Privacy? |
|---|---|---|---|
| Data: Handbook D28 (handbook/d28-student-handbook.md) | Có (trong repo D28) | Dùng nguyên file thật | Public — không vấn đề |
| Data: Slide skeleton D28 | Có (trong LMS) | Dùng phần có trong repo | Public — không vấn đề |
| Data: Danh sách section/anchor trong handbook (để citation chính xác) | Có (tên section trong file markdown) | Dùng tên section thật | Public — không vấn đề |
| Input: Câu hỏi học viên (trong pilot) | Chưa có — cần collect trong buổi | 10 câu hỏi mẫu giả định cho test | Cần consent nếu log để cải thiện |

- **Output nào rủi ro cao**: Câu trả lời trỏ sai section (section không tồn tại hoặc không liên quan) → học viên đọc sai chỗ, mất thời gian, mất tin tưởng vào chatbot.
- **Ai review + bao nhiêu mẫu + pass/fail theo gì**: 1 coach track Product review 10 câu test trước khi deploy cho 80 học viên (~30 phút). Pass: câu trả lời trỏ đúng section tồn tại trong handbook + nội dung phù hợp câu hỏi. Fail: trỏ section không tồn tại (hallucination) HOẶC trả lời câu hỏi ngoài phạm vi D28 mà không nói "không biết".
- **Có cần citation / nói "không biết" khi thiếu nguồn không**: CÓ — bắt buộc. System prompt phải yêu cầu: (1) mọi câu trả lời kèm "— Nguồn: handbook §X" hoặc "— Nguồn: slide §Y"; (2) nếu không tìm thấy section liên quan trong tài liệu → "Câu hỏi này nằm ngoài phạm vi tài liệu D28. Vui lòng hỏi coach trên Discord." Không được generate câu trả lời mà không có nguồn.

## Phần C — Bản vẽ trực quan (BẮT BUỘC)

Chọn **1** dạng nhẹ nhất đủ rõ (xem `templates/demo-examples.md`): mockup 2–3 màn hình · user flow trước/sau · prompt flow · agent flow · 1 cặp input–output thật. Vẽ tay / ASCII / bảng đều được.

```text
=== PROMPT FLOW: Chatbot Gia Sư D28 ===

TRƯỚC (hiện tại):
[Học viên đọc handbook D28]
        │
        ▼  ← gặp concept không hiểu (Exit Criteria, Double Diamond vòng 2...)
[Post câu hỏi lên Discord]
        │
        ▼  ← đợi 30–60 phút
[Coach hoặc bạn trả lời (nếu có)]
        │
        ▼  ← hoặc bỏ qua, vào lab với concept mơ hồ
[Vào lab / làm bài nộp]


SAU (với Quick Win):
[Học viên đọc handbook D28]
        │
        ▼  ← gặp concept không hiểu
[Hỏi Chatbot Gia Sư D28 (link/bot)]
        │
        ▼
┌────────────────────────────────────────────────────────┐
│  SYSTEM PROMPT (Claude Haiku API)                       │
│  • Toàn bộ handbook D28 (context stuffed)              │
│  • Instruction: chỉ trả lời từ tài liệu D28           │
│  • Format bắt buộc: [Trả lời] — Nguồn: handbook §X    │
│  • Fallback bắt buộc: nếu không thấy section liên quan │
│    → "Ngoài phạm vi D28, hỏi coach trên Discord"      │
└────────────────────────────────────────────────────────┘
        │
        ▼
[Claude phân tích câu hỏi → tìm section liên quan trong handbook]
        │
        ├─── Tìm thấy section → sinh câu trả lời kèm nguồn
        │
        └─── Không tìm thấy → fallback "ngoài phạm vi"
        │
        ▼
[⚠️ COACH REVIEW (trước lần đầu deploy) ⚠️]
  Coach kiểm tra 10 câu test: section có tồn tại? nội dung phù hợp?
  → Pass / Fail
        │ pass
        ▼
[Deploy cho 80 học viên track Product]
        │
        ▼
[Học viên nhận câu trả lời trong ~5 giây, đọc lại section, hiểu concept]


=== CẶP INPUT–OUTPUT MẪU ===

INPUT (câu hỏi học viên):
  "Exit criteria là gì? Khác gì với KPI bình thường?"

OUTPUT Chatbot (draft):
  Exit criteria là điều kiện được đặt TRƯỚC khi chạy pilot, xác định
  ngưỡng cụ thể mà nếu không đạt → dừng pilot ngay, không cần thảo luận.
  Khác KPI ở chỗ: KPI đo hiệu quả chung, exit criteria là điểm dừng rõ ràng
  có người có quyền thực thi.

  — Nguồn: handbook/d28-student-handbook.md §A8 (mục Exit Criteria)

---

INPUT (câu hỏi ngoài phạm vi):
  "Tôi nên chọn ngành gì để học AI?"

OUTPUT Chatbot:
  Câu hỏi này nằm ngoài phạm vi tài liệu D28.
  Vui lòng hỏi coach trên Discord để được tư vấn phù hợp với bạn.

Chỗ con người review (output rủi ro cao) nằm ở:
  Bước "COACH REVIEW" — trước lần đầu deploy.
  Coach kiểm tra: (1) section trong "— Nguồn:" có tồn tại trong handbook?
                  (2) nội dung câu trả lời có khớp với câu hỏi không?
```

Câu hỏi phụ — một người đóng vai stakeholder nhìn 20 giây: *hiểu user làm gì, nhận lại gì, không cần giải thích thêm không? Có chỗ nào "đẹp nhưng rỗng" không?*

---

## Tổng kiểm tra trước khi sang `../03-pilot-plan/`

| Hạng mục | Xong? |
|---|---|
| Cách làm có lý do CẦN, không phải "mặc định tự build" | ✓ (Boost vì LLM đủ tốt + corpus nhỏ vừa context, không phải core advantage) |
| Nói rõ data cần + ai review output rủi ro cao | ✓ (coach review 10 câu test trước deploy) |
| Có ≥1 bản vẽ trực quan, người ngoài hiểu trong ~20 giây | ✓ (prompt flow + trước/sau + 2 cặp I/O mẫu) |
| Có đánh dấu chỗ con người review | ✓ (⚠️ COACH REVIEW trong flow) |

⚑ Coach kiểm tra ở Mốc 3: *"Stakeholder nhìn vào đâu để hiểu flow? Mockup/sketch/demo đâu?"* Chỉ nói bằng chữ = chưa qua.

Sau bước này, mở `../03-pilot-plan/1-pilot-plan.md`.

*Liên quan: handbook §A5+§A6 · `templates/demo-examples.md` · `prompts/05-demo-challenge.md`*
