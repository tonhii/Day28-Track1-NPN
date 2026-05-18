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

- **Cách làm chốt**: **Boost** — Claude API (model sẵn) + data riêng (rubric D28 + mapping table tự build)
- **Lý do CẦN (không phải thích), 2–3 câu**: Bài toán phân tích text theo rubric và sinh gợi ý là việc LLM hiện tại làm tốt mà không cần train thêm. Chỉ cần bổ sung context domain-specific (rubric 5 Gate + mapping lỗi→tài liệu khóa) qua system prompt và context window — đây là Boost, không cần Build model mới hay mua tool sẵn.
- **Vì sao KHÔNG "Build từ số 0"**: Không phải lợi thế cạnh tranh cốt lõi của AI20k, không có AI engineer trong nhóm, timeline 2 tuần không đủ cho custom model, và LLM off-the-shelf đã đủ tốt cho task này.
- **Tool / API / vendor cần + ước lượng chi phí thô**:
  - Claude API (claude-haiku-4-5 hoặc claude-sonnet-4-6): ~$3–8 cho 80 bài (🧮 ước tính ~2,500 tokens/bài)
  - Google Sheets (mapping table lỗi→tài liệu): $0
  - Discord webhook hoặc LMS notification (gửi gợi ý): $0
  - Tổng cash: **<$10**; effort: ~12 giờ người (xây mapping table 3h + viết prompt 3h + test 4h + setup delivery 2h)

## Phần B — Data & ai review (cách làm này cần gì để chạy được)

| Cần gì | Có sẵn trong AI20k? | Trong lab dùng (mẫu/giả định) | Privacy? |
|---|---|---|---|
| Data: Bài nộp D28 FINAL (3 file/học viên: problem-framing.md, solution.md, pitch.md) | Có sau buổi hôm nay (cần consent từ học viên) | 5 bài mẫu giả định cho test | Nhạy cảm — cần opt-in consent |
| Data: Rubric 5 Gate D28 | Có (templates/rubric-gate-sheet.md) | Dùng nguyên file thật | Public — không vấn đề |
| Data: Mapping table Gate/lỗi → tài liệu khóa | Chưa có, cần tự xây | Xây thử ~15 entries (5 Gate × 3 lỗi phổ biến) | Public — không vấn đề |
| Data: Danh sách tài liệu khóa (slide, handbook, template) | Có (trong repo D28) | Dùng tên + link thật từ repo | Public — không vấn đề |

- **Output nào rủi ro cao**: Gợi ý tài liệu sai (AI trỏ tài liệu không tồn tại hoặc không liên quan) → học viên mất thời gian, mất tin tưởng vào hệ thống.
- **Ai review + bao nhiêu mẫu + pass/fail theo gì**: 1–2 coach track Product review 100% output trước khi gửi học viên (Phase 1: review 5 mẫu test; Phase 2: review tất cả 80 output — ước tính ~45 giây/output = ~1 giờ tổng). Pass: tài liệu tồn tại trong khóa + liên quan đến lỗi phát hiện. Fail: bịa tài liệu / gợi ý chung chung không bám lỗi cụ thể.
- **Có cần citation / nói "không biết" khi thiếu nguồn không**: CÓ — bắt buộc. System prompt phải yêu cầu AI chỉ gợi ý tài liệu có trong mapping table; nếu không map được lỗi cụ thể → ghi "Không tìm thấy tài liệu phù hợp, liên hệ coach" thay vì bịa.

## Phần C — Bản vẽ trực quan (BẮT BUỘC)

Chọn **1** dạng nhẹ nhất đủ rõ (xem `templates/demo-examples.md`): mockup 2–3 màn hình · user flow trước/sau · prompt flow · agent flow · 1 cặp input–output thật. Vẽ tay / ASCII / bảng đều được.

```text
=== PROMPT FLOW: AI D28 Gap Analyzer ===

TRƯỚC (hiện tại):
[Học viên nộp bài D28]
        │
        ▼
[Nhận feedback nhóm chung sau pitch]
        │
        ▼  ← không có gợi ý cá nhân
[Vào 6 tuần thực chiến với lỗ hổng chưa biết]


SAU (với Quick Win):
[Học viên nộp bài D28]
        │
        ▼
[3 file FINAL: problem-framing.md + solution.md + pitch.md]
        │
        ▼
┌─────────────────────────────────────────────────┐
│  SYSTEM PROMPT (Claude API)                      │
│  • Rubric 5 Gate D28 (tiêu chí đạt/không đạt)  │
│  • Mapping table: Gate lỗi → tên tài liệu + link│
│  • Instruction: chỉ gợi ý tài liệu có trong     │
│    mapping table; nếu không map được → nói rõ   │
└─────────────────────────────────────────────────┘
        │
        ▼
[Claude phân tích từng Gate → phát hiện lỗ hổng]
        │
        ▼
┌─────────────────────────────────────────────────┐
│  OUTPUT cá nhân hóa (draft):                    │
│  "Bài của bạn đạt Gate 1, 2. Cần xem lại:      │
│  1. [Tên tài liệu] — lý do: Gate 3 thiếu số    │
│  2. [Tên tài liệu] — lý do: Gate 5 thiếu exit  │
│  3. [Tên tài liệu] — lý do: ..."               │
└─────────────────────────────────────────────────┘
        │
        ▼
[⚠️ COACH REVIEW — chỗ con người review ⚠️]
  Coach xem: tài liệu có tồn tại? gợi ý đúng lỗi?
  → Approve / Edit / Reject
        │ approve
        ▼
[Gửi cho học viên qua Discord DM / LMS]
        │
        ▼
[Học viên nhận, click tài liệu, học lại trước sprint]


=== CẶP INPUT–OUTPUT MẪU ===

INPUT (trích từ bài nộp giả định):
  "Exit criteria: nếu pilot thất bại thì dừng"

OUTPUT AI (draft):
  Gate 5 — Pilot Plan: Exit criteria thiếu ngưỡng cụ thể
  và chưa ghi ai có quyền dừng.
  → Xem lại: "templates/ai-pilot-plan-core.md" (mục Exit Criteria)
     + "handbook/d28-student-handbook.md" §A8

Chỗ con người review (output rủi ro cao) nằm ở:
  Bước "COACH REVIEW" — trước khi gửi cho học viên.
  Coach kiểm tra: (1) tài liệu gợi ý có trong khóa không?
                  (2) lý do gợi ý có khớp với lỗi thật không?
```

Câu hỏi phụ — một người đóng vai stakeholder nhìn 20 giây: *hiểu user làm gì, nhận lại gì, không cần giải thích thêm không? Có chỗ nào "đẹp nhưng rỗng" không?*

---

## Tổng kiểm tra trước khi sang `../03-pilot-plan/`

| Hạng mục | Xong? |
|---|---|
| Cách làm có lý do CẦN, không phải "mặc định tự build" | ✓ (Boost vì LLM đủ tốt, không phải core advantage) |
| Nói rõ data cần + ai review output rủi ro cao | ✓ (coach review 100% trước khi gửi) |
| Có ≥1 bản vẽ trực quan, người ngoài hiểu trong ~20 giây | ✓ (prompt flow + trước/sau + cặp I/O mẫu) |
| Có đánh dấu chỗ con người review | ✓ (⚠️ COACH REVIEW trong flow) |

⚑ Coach kiểm tra ở Mốc 3: *"Stakeholder nhìn vào đâu để hiểu flow? Mockup/sketch/demo đâu?"* Chỉ nói bằng chữ = chưa qua.

Sau bước này, mở `../03-pilot-plan/1-pilot-plan.md`.

*Liên quan: handbook §A5+§A6 · `templates/demo-examples.md` · `prompts/05-demo-challenge.md`*
