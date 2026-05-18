---
artifact: 8 — 5-slide Pitch + AI Support Log (bản nộp cuối lab)
bai-tap: Pilot Plan — dồn thành pitch, sẵn sàng phản biện
phase: Double Diamond vòng 2 · ◆ output (bản nộp cuối + present)
time: ~5 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 1-pilot-plan.md + toàn bộ 01-frame + 02-solution · templates/5-slide-pitch.md
nop-cuoi: Có — bản nộp cuối lab (Part E · 5-slide Pitch + AI Support Log)
---

# 2 — FINAL: 5-slide Pitch + AI Support Log

Mục tiêu: dồn cả A3 Working Canvas thành 5 slide pitch (5 phút), chuẩn bị trả lời 3 câu phản biện, và ghi AI Support Log. Đây là bản nộp cuối cùng của lab.

Lý do làm bước này: nguyên tắc *demo đơn giản + lập luận chặt > demo đẹp + lập luận yếu*. Slide đẹp mà không trả lời được "số này lấy ở đâu" thì hỏng. Pitch không phải kể chuyện — là đưa evidence để stakeholder ra được một quyết định.

Quy tắc: **slide cuối phải là một lời xin rõ ràng** (xin gì · đổi lại hứa gì). Không có lời xin = stakeholder không biết approve cái gì.

## Quy trình 5 phút

```text
3 phút  — Dồn 5 slide (mỗi slide 1 thông điệp)
1 phút  — Chuẩn bị 3 câu phản biện
1 phút  — AI Support Log
```

---

## Phần A — 5 slide (mỗi slide 1 thông điệp)

Kéo nguyên liệu từ các file đã làm, đừng viết mới. Khung đầy đủ: `templates/5-slide-pitch.md`.

| # | Slide | Lấy từ | Nội dung 1–2 gạch đầu dòng | Ai nói |
|---|---|---|---|---|
| 1 | Problem & user | 01-frame/3-FINAL | • 80 học viên track Product sau D28 không biết mình yếu concept nào trước 6 tuần thực chiến. • Không có gợi ý cá nhân — coach mất 🧮~6.7 giờ/cohort nếu làm thủ công, không khả thi. | Lê Thị Phương |
| 2 | Breakdown & Quick Win | 01-frame/1,2 | • Track 1 có 7 use case — không build hết cùng lúc. Chọn 1 Quick Win: "AI phân tích bài D28 → sinh gợi ý 3 tài liệu cần xem lại" (điểm 19/20). • Không chọn: chẩn đoán quiz (đã qua thời điểm) · dashboard tiến độ (phụ thuộc upstream). | Trần Thị Kim Ngân |
| 3 | Solution + bản vẽ trực quan | 02-solution/2-FINAL | • Boost — Claude API + rubric D28 system prompt + mapping table. Không tự build vì không phải core advantage, LLM đủ tốt. • Flow: [bài nộp] → [Claude+rubric+mapping] → [3 gợi ý draft] → [⚠️ coach review] → [học viên nhận]. | Hồ Thị Tố Nhi |
| 4 | AI Pilot Plan | 03-pilot-plan/1 | • Scope: 80 học viên · 2 tuần · 2 phase (build+test → run+deliver). • Budget: <$10 API + 12 giờ người + 2 giờ coach review. Người quyết dừng: Program Lead. | Trần Thị Kim Ngân |
| 5 | Metric · exit criteria · **lời xin** | 03-pilot-plan/1 | • Metric: ≥70% coach chấp nhận gợi ý · ≥50% học viên click tài liệu trong 1 tuần. Dừng nếu: AI bịa tài liệu HOẶC <50% coach accept sau Phase 1. • **Lời xin**: Xin consent bài nộp D28 + 2 giờ coach review + $10 API budget. Hứa: evidence trong 2 tuần, chấp nhận dừng nếu fail metric. | Hồ Thị Tố Nhi |

## Phần B — Chuẩn bị 3 câu phản biện

Business owner/instructor sẽ hỏi mỗi nhóm 1–2 câu. Viết sẵn câu trả lời:

1. *"Số liệu / giả định này lấy ở đâu?"* → Hai con số chính (~60% học viên trượt Gate; ~5 phút/học viên của coach) là **🧮 giả định** — đánh dấu rõ trong bài. Số thật có ngay: bài nộp D28 + rubric 5 Gate của 80 học viên có sau buổi hôm nay. Trước Phase 2, nhóm đếm thực tế từ 10 bài mẫu để replace số giả định.

2. *"Nếu giả định quan trọng nhất của bạn sai thì sao?"* → Giả định quan trọng nhất: coach có thể review 80 output AI trong ~1 giờ. Nếu sai (mất >3 giờ, coach từ chối) → thu hẹp scope Phase 2 xuống 20 học viên tình nguyện trước; scale sau khi đã streamline quy trình review.

3. *"Tình huống nào sẽ khiến bạn dừng pilot?"* → Hai tình huống dừng ngay, không bàn cãi: (1) AI trỏ tài liệu không tồn tại trong khóa — citation sai là mất trust cả hệ thống. (2) Dưới 50% coach chấp nhận gợi ý sau test 5 mẫu Phase 1 — tức là output chưa đủ chất lượng để gửi học viên thật.

## Phần C — AI Support Log

| Câu hỏi | Trả lời |
|---|---|
| AI giúp được gì trong lab này? | Dựng nháp toàn bộ worksheet (intake breakdown, quick win scoring, problem framing, deep research 4 tầng, solution approach, pilot plan, pitch). Gợi ý các tiền lệ thực tế (Khan Academy Khanmigo, Coursera AI Feedback, CMU OLI). Đặt câu hỏi phản biện giúp nhóm kiểm tra logic. |
| AI đưa output nào nghe hợp lý nhưng nhóm phải sửa? | Số giả định (~60% học viên trượt Gate, ~5 phút/học viên của coach) — AI đưa ra nghe có lý nhưng không có nguồn thật; nhóm đánh dấu 🧮 rõ thay vì dùng như fact. Chi tiết kỹ thuật của Coursera/Khan Academy — AI mô tả nghe chuyên nghiệp nhưng không verify được nguồn cụ thể; nhóm đánh dấu 🧮. |
| Phần nào nhóm tự lập luận, KHÔNG copy AI? | Quyết định chọn Quick Win UC2/UC3 (thay vì UC1 có impact cao hơn) với lý do timing và data sẵn có. Lý do loại UC7 (phụ thuộc upstream — AI không tự nhận ra điều này). Exit criteria Mức Nghiêm trọng — đặc biệt phần "ai có quyền dừng là Program Lead, không phải nhóm build" để tránh conflict of interest. |

---

## Tổng kiểm tra trước khi nộp

| Hạng mục | Xong? |
|---|---|
| 5 slide, mỗi slide 1 thông điệp, đã phân ai nói slide nào | ✓ |
| Slide 5 có lời xin rõ ràng (xin gì · hứa gì) | ✓ (consent + 2h coach + $10 API; hứa evidence 2 tuần + accept dừng) |
| Có câu trả lời sẵn cho cả 3 câu phản biện | ✓ |
| AI Support Log điền đủ 3 dòng | ✓ |
| Tất cả file worksheet/ đã commit + push, link dán vào Discord | ⬜ (cần push lên GitHub) |

Đây là file cuối. Pitch 5 phút + nhận phản biện theo bảng 5 Gate (`templates/rubric-gate-sheet.md`).

*Liên quan: handbook §A9 · `templates/5-slide-pitch.md` · `templates/ai-support-log.md`*
