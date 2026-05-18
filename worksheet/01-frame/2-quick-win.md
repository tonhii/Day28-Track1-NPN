---
artifact: 3 — Quick Win Selection
bai-tap: Frame — chọn lát cắt làm trước
phase: Double Diamond vòng 1 · ◆ siết (hội tụ về 1 lựa chọn)
time: ~10 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 1-intake-breakdown.md · prompts/02-quick-win-challenge.md
nop-cuoi: Không — file trung gian (bản chốt phase này ở 3-FINAL-problem-framing.md)
---

# 2 — Quick Win: chọn lát cắt làm trước

Mục tiêu: từ 5–8 use case ở file `1`, chấm điểm nhanh và chốt **1 Quick Win** để pilot đầu tiên — kèm lý do chọn và lý do *không* chọn các phần khác. Đây là nửa "siết lại" của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 1.

Lý do làm bước này: đây là quyết định quan trọng nhất của phase Frame. Quick Win **không phải** phần dễ nhất hay nghe hay nhất — là phần *chứng minh được giá trị nhanh và có người ủng hộ*. Chọn sai → pilot fail → mất uy tín → khó xin pilot tiếp. Nhóm phải chọn được *và bảo vệ được bằng lý do*, không bằng cảm tính.

Quy tắc: **điểm số chỉ là gợi ý, không phải đáp án.** Đừng để con số quyết thay nhóm — nó chỉ giúp so sánh.

## Bước 0 — Lấy 4–6 use case mạnh nhất từ file `1` (1 phút)

## Quy trình 10 phút

```text
1 phút  — Bước 0: chọn 4–6 ứng viên
5 phút  — Phần A: chấm điểm 4 trục
3 phút  — Phần B: 1 lý do nên / 1 lý do không cho top 2
1 phút  — Phần C: chốt + ai ủng hộ + cái KHÔNG chọn
```

---

## Phần A — Chấm điểm 4 trục (1–5 mỗi trục)

Câu hỏi phụ (tự trả lời):

- "Risk" ở đây là *sai thì mất gì* — chọn đúng việc chính của user (task centrality) thì sai cũng đỡ đau; chọn việc lớn nhất thì sai rất đắt. Use case nào risk thấp thật?
- Use case nào có sẵn data + có người trong AI20k thật sự muốn dùng?

| Use case | Impact | Feasibility | Evidence nhanh | Risk (cao = an toàn) | Tổng |
|---|:--:|:--:|:--:|:--:|:--:|
| UC1: Chatbot Q&A D28 — trả lời câu hỏi về handbook D28 kèm nguồn cụ thể | 5 | 5 | 5 | 4 | **19** |
| UC3: Mini practice 5 câu sau mỗi phần D28 (Frame/Solution/Pilot Plan) | 4 | 5 | 4 | 5 | **18** |
| UC2: Gia sư Socratic — hỏi ngược thay vì cho đáp án thẳng | 4 | 4 | 3 | 4 | **15** |
| UC4: Giải thích concept theo 3 level (cơ bản/áp dụng/nâng cao) | 3 | 4 | 3 | 5 | **15** |
| UC6: Dashboard instructor — concept nào bị hỏi nhiều | 3 | 2 | 2 | 3 | **10** |

(Thang điểm chi tiết: `templates/quick-win-scoring.md`.)

## Phần B — 1 lý do nên / 1 lý do không, cho top 2

**Ứng viên A — UC1: Chatbot Q&A D28 có nguồn**

```text
Nên chọn vì: Data có sẵn ngay (handbook D28 + slide skeleton trong repo), deploy được
             trong 1 ngày, evidence rõ trong 1 tuần (đếm % câu trả lời đúng nguồn),
             giải quyết đúng pain thật — học viên hỏi Discord đợi 30-60 phút.
Không nên vì: Rủi ro hallucination nếu prompt không đủ strict; cần guard
              "nói không biết" cho câu hỏi ngoài phạm vi, không thì bịa.
```

**Ứng viên B — UC3: Mini practice 5 câu sau mỗi phần D28**

```text
Nên chọn vì: Risk thấp nhất (câu hỏi practice sai không gây hại bằng Q&A sai),
             evidence nhanh (học viên làm xong thấy ngay bản thân hiểu chỗ nào sai).
Không nên vì: Impact thứ hai so với UC1 — học viên cần hiểu trước, rồi mới practice;
             nếu Q&A (UC1) chưa có thì practice mà không hiểu concept vẫn không ăn thua.
```

## Phần C — Chốt Quick Win

- **Quick Win nhóm chọn**: Chatbot gia sư D28 — học viên hỏi về nội dung handbook D28 → nhận câu trả lời kèm nguồn cụ thể (tên section + đoạn trích). Nếu câu hỏi nằm ngoài phạm vi handbook D28 → nói "Câu hỏi này nằm ngoài phạm vi tài liệu D28, hỏi thêm coach trên Discord."
- **Vì sao chọn cái này trước** (2–4 câu, bám điểm + impact + evidence nhanh): Tổng điểm 19/20 — cao nhất trong 5 ứng viên. Data có sẵn ngay (handbook D28 + slide trong repo, vừa context window Claude). Evidence nhanh: test được trong 1 ngày với 10 câu hỏi mẫu trước khi deploy. Giải quyết pain thật nhất — học viên đang đợi Discord 30-60 phút cho câu hỏi mà chatbot có thể trả lời trong 5 giây từ tài liệu có sẵn.
- **Ai trong AI20k sẽ ủng hộ pilot này** (và vì sao họ care): Coach track Product — muốn giảm câu hỏi lặp lại trên Discord (hiện chiếm nhiều thời gian coach mà câu trả lời chỉ là "đọc handbook §X"). Instructor D28 — muốn học viên đọc tài liệu chủ động hơn trước khi vào lab.
- **Nhóm KHÔNG chọn gì + vì sao**: 1. UC2 (Socratic) — phức tạp hơn nhiều về prompt engineering, khó đo "gia sư Socratic có hiệu quả không" trong 1 tuần; đây là Phase 2 sau khi UC1 chạy ổn. 2. UC6 (Dashboard instructor) — phụ thuộc hoàn toàn vào UC1 (cần log câu hỏi thật từ học viên trước), không thể pilot độc lập.

---

## Phát hiện ban đầu

- UC1 vượt trội nhờ 3 yếu tố cùng lúc: data sẵn (handbook có ngay) + evidence nhanh (đếm được nguồn đúng/sai) + giải quyết pain hiện hữu (Discord lag).
- UC3 (mini practice) là bước đi tự nhiên tiếp theo sau UC1 — khi học viên đã có chỗ hỏi, thêm cơ chế tự kiểm tra sẽ rất logic; để Phase 2.

## Câu hỏi mở (mang sang Problem Framing)

- Kênh deploy chatbot nào phù hợp nhất — trong LMS, Discord bot, hay link standalone — cái nào học viên thật sự click vào?
- Cần bao nhiêu câu hỏi test để confirm chatbot đủ tốt trước khi mở cho 80 học viên?

---

## Tổng kiểm tra trước khi sang `3-FINAL-problem-framing.md`

| Hạng mục | Xong? |
|---|---|
| Có bảng chấm 4 trục cho ≥4 use case | ✓ (5 use case) |
| Chốt 1 Quick Win, lý do bám số/impact (không "nghe hay") | ✓ |
| Nêu rõ ai ủng hộ pilot này | ✓ (Coach track Product + Instructor D28) |
| Ghi rõ ≥2 phần KHÔNG chọn + lý do | ✓ (UC2 và UC6) |

⚑ Đây là phần coach kiểm tra ở Mốc 1: *"Vì sao không làm full tool? Vì sao chọn lát cắt này trước?"*

Sau bước này, mở `3-FINAL-problem-framing.md` — đóng khung vấn đề thật (bản nộp của phase Frame).

*Liên quan: handbook §A3 · `templates/quick-win-scoring.md` · `prompts/02-quick-win-challenge.md`*
