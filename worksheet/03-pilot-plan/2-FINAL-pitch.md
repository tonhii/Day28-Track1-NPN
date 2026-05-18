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
| 1 | Problem & user | 01-frame/3-FINAL | • 80 học viên track Product đọc handbook D28 — gặp concept không hiểu, không có chỗ hỏi ngay. Đợi Discord 30-60 phút hoặc bỏ qua → vào lab với concept mơ hồ. • 🧮~50-80 câu hỏi/buổi trên Discord, ~40% có thể trả lời bằng 1 đoạn trong handbook có sẵn. | Lê Thị Phương |
| 2 | Breakdown & Quick Win | 01-frame/1,2 | • Track 2 có 7 use case — không build hết cùng lúc. Chọn 1 Quick Win: "Chatbot gia sư D28 Q&A có nguồn" (điểm 19/20). • Không chọn: Socratic (phức tạp, khó đo trong 1 tuần) · Dashboard instructor (phụ thuộc log câu hỏi thật, chưa có). | Trần Thị Kim Ngân |
| 3 | Solution + bản vẽ trực quan | 02-solution/2-FINAL | • Boost — Claude Haiku API + handbook D28 (context stuffing) + system prompt strict. Không Build vì không phải core advantage; không RAG vì corpus nhỏ vừa context. • Flow: [học viên hỏi] → [Claude + handbook] → [trả lời + nguồn §X] HOẶC ["ngoài phạm vi, hỏi coach"]. | Hồ Thị Tố Nhi |
| 4 | AI Pilot Plan | 03-pilot-plan/1 | • Scope: 80 học viên · 1 tuần · 2 phase (build+test → deploy+feedback). • Budget: <$5 API + 6 giờ người + 0.5 giờ coach review. Người quyết dừng: Program Lead. | Trần Thị Kim Ngân |
| 5 | Metric · exit criteria · **lời xin** | 03-pilot-plan/1 | • Metric: ≥80% câu trả lời đúng nguồn (coach confirm) · ≥40% học viên dùng ≥1 lần. Dừng nếu: AI trỏ section không tồn tại (citation hallucination). • **Lời xin**: Xin 30 phút coach review 10 câu test + $5 API budget + announce đầu buổi D28. Hứa: evidence trong 1 tuần, dừng ngay nếu citation sai. | Hồ Thị Tố Nhi |

## Phần B — Chuẩn bị 3 câu phản biện

Business owner/instructor sẽ hỏi mỗi nhóm 1–2 câu. Viết sẵn câu trả lời:

1. *"Số liệu / giả định này lấy ở đâu?"* → Ba con số chính (~50-80 câu hỏi/buổi Discord, ~40% có thể trả lời từ handbook, ~30 phút coach mất) là **🧮 giả định** — đánh dấu rõ trong bài. Số thật có ngay sau buổi D28: log Discord buổi hôm nay + thời gian coach đo. Trước Phase 2, nhóm đếm thực tế để replace số giả định.

2. *"Nếu giả định quan trọng nhất của bạn sai thì sao?"* → Giả định quan trọng nhất: handbook D28 đủ phủ các câu hỏi phổ biến của học viên (fallback rate ≤30%). Nếu sai (fallback rate cao hơn, học viên thấy chatbot không biết quá nhiều) → bổ sung slide skeleton vào context; thu top 20 câu hỏi Discord thật để thêm vào FAQ guard trong system prompt; ghi lesson learned.

3. *"Tình huống nào sẽ khiến bạn dừng pilot?"* → Hai tình huống dừng ngay, không bàn cãi: (1) Chatbot trỏ section không tồn tại trong handbook — citation hallucination 1 lần là mất trust toàn hệ thống, học viên không dùng nữa. (2) Dưới 8/10 câu test coach chấp nhận sau Phase 1 — tức là system prompt chưa đủ tốt, không deploy cho người thật.

## Phần C — AI Support Log

| Câu hỏi | Trả lời |
|---|---|
| AI giúp được gì trong lab này? | Dựng nháp toàn bộ worksheet Track 2 (intake breakdown, quick win scoring, problem framing, deep research 4 tầng, solution approach + prompt flow, pilot plan, pitch). Gợi ý tiền lệ thực tế (Notion AI Q&A, Harvey AI hallucination case, Langchain docs chatbot tutorial). Đặt câu hỏi phản biện về citation guard và adoption risk. |
| AI đưa output nào nghe hợp lý nhưng nhóm phải sửa? | Số giả định (~50-80 câu hỏi/buổi Discord, ~40% trả lời được từ handbook) — AI đưa ra nghe có lý nhưng không có nguồn thật; nhóm đánh dấu 🧮 rõ thay vì dùng như fact. Chi tiết kỹ thuật Notion AI Q&A — AI mô tả nghe chuyên nghiệp nhưng không verify được source cụ thể; nhóm đánh dấu 🧮. |
| Phần nào nhóm tự lập luận, KHÔNG copy AI? | Quyết định chọn Context stuffing thay vì RAG (corpus nhỏ vừa context → RAG overkill cho pilot 1 tuần) — AI gợi ý RAG nhưng nhóm lập luận không cần. Bài học từ Harvey AI case áp dụng vào exit criteria: "citation hallucination 1 lần = dừng ngay" thay vì có ngưỡng %. Adoption plan: "chatbot hỗ trợ đọc, không thay thế đọc" — nhóm tự thiết kế dựa trên Red Flag #2 của track. |

---

## Tổng kiểm tra trước khi nộp

| Hạng mục | Xong? |
|---|---|
| 5 slide, mỗi slide 1 thông điệp, đã phân ai nói slide nào | ✓ |
| Slide 5 có lời xin rõ ràng (xin gì · hứa gì) | ✓ (30 phút coach + $5 API + announce; hứa evidence 1 tuần + dừng nếu citation sai) |
| Có câu trả lời sẵn cho cả 3 câu phản biện | ✓ |
| AI Support Log điền đủ 3 dòng | ✓ |
| Tất cả file worksheet/ đã commit + push, link dán vào Discord | ⬜ (cần push lên GitHub) |

Đây là file cuối. Pitch 5 phút + nhận phản biện theo bảng 5 Gate (`templates/rubric-gate-sheet.md`).

*Liên quan: handbook §A9 · `templates/5-slide-pitch.md` · `templates/ai-support-log.md`*
