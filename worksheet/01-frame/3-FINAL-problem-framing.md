---
artifact: 4 — Problem Framing (bản nộp phase Frame)
bai-tap: Frame — đóng khung vấn đề thật
phase: Double Diamond vòng 1 · ◆ output (chốt — owner xác nhận)
time: ~13 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 2-quick-win.md · prompts/03-problem-framing-challenge.md
nop-cuoi: Có — đây là bản nộp của phase Frame (Part A · A3 Working Canvas mục Problem Framing)
---

# 3 — FINAL: Problem Framing

Mục tiêu: đóng khung Quick Win đã chọn cho thật cụ thể. Đây **không phải** bản đề xuất giải pháp — là tài liệu trả lời đúng 1 câu: *"nhóm đã hiểu đúng vấn đề chưa?"*. Đây là output chốt của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 1, và là một mục trong A3 Working Canvas nộp cuối buổi.

Lý do làm bước này: một AI Pilot Plan cho vấn đề SAI — dù viết hay — vẫn sai. Đa số nhóm trượt Gate 3 vì khung chung chung ("học viên cần học tốt hơn", "coach quá tải") — câu đó không đo được, không ai chịu trách nhiệm, không biết khi nào thành công.

Quy tắc: **pain phải có số.** "Nhiều người phàn nàn" không phải evidence. "200 câu hỏi/tuần × 20 phút = 67 giờ/tuần" mới là evidence. Trong lab dùng số giả định cũng được, nhưng phải nói rõ số đến từ đâu.

## Quy trình 13 phút

```text
9 phút  — Điền 9 mục Problem Framing
3 phút  — Tự phản biện
1 phút  — Chốt: owner (giả định) có xác nhận đúng vấn đề không
```

---

## 9 mục Problem Framing

Câu hỏi phụ (tự trả lời trước khi điền):

- Một người ngoài đọc khung này có biết CHÍNH XÁC ai đau, đau cái gì không?
- Nếu KHÔNG có baseline thì nhóm đo "tốt hơn" bằng cách nào?
- Mục Open Questions trống = nguy hiểm (chưa nghĩ đủ). Nhóm còn chưa biết gì?

### Trả lời

1. **Original Ask** (stakeholder nói gì, nguyên văn): "Xây hệ thống AI cá nhân hóa lộ trình học cho từng học viên dựa trên mục tiêu, level, tiến độ, điểm yếu và hành vi học tập"

2. **Reframed problem** (vấn đề thật sau khi tách): Học viên track Product (~80 người) vừa hoàn thành D28 không biết họ còn yếu concept nào trong Problem Framing, Build/Buy/Boost, AI Pilot Plan — và không có cơ chế nào sinh gợi ý cá nhân hóa những gì cần xem lại trước khi bước vào 6 tuần thực chiến. Kết quả: học viên vào sprint với lỗ hổng kiến thức chưa được vá.

3. **Current workflow** (hiện tại đang xử lý thế nào, kể cả "không ai làm gì"): Học viên nộp bài D28 → nhận feedback nhóm chung sau buổi pitch → không nhận gợi ý cá nhân → tự đọc lại toàn bộ slide/handbook (hầu như không ai làm do thiếu định hướng) hoặc hỏi Discord ngẫu nhiên. Coach đưa feedback nhóm, không thể đưa gợi ý cá nhân cho từng người trong 80 học viên.

4. **Pain evidence — bằng SỐ** (ai đau · đau ở khoảnh khắc nào trong việc · tần suất · quy mô; số giả định ghi rõ nguồn giả định):

```text
• 🧮 Giả định: ~60% học viên track Product D28 có ≥1 Gate trượt trong 5 Gate rubric
  (Problem Framing hoặc Pilot Plan yếu) nhưng không nhận gợi ý cá nhân về concept cần bù.
  Nguồn giả định: ước tính từ pattern lỗi phổ biến trong README D28 (mục "Lỗi hay mắc").

• 🧮 Giả định: Nếu coach làm thủ công, cần ~5 phút/học viên để đọc bài và đưa gợi ý cá nhân
  → 80 học viên × 5 phút = 400 phút (~6.7 giờ/cohort) — không khả thi với lịch coach.
  Nguồn giả định: ước tính dựa trên độ phức tạp của bài nộp D28 (3 file FINAL).

• Số thật có thể verify ngay: D28 rubric 5 Gate (có trong templates/rubric-gate-sheet.md)
  + bài nộp D28 của 80 học viên track Product (có sau buổi hôm nay).
```

5. **Affected people** (ai dùng · ai quyết · ai là người review/expert):
   - **Người dùng**: ~80 học viên track Product D28
   - **Người quyết approve pilot**: Instructor D28 / Program Lead
   - **Người review output**: 1–2 coach track Product (review gợi ý AI trước khi gửi học viên)

6. **Constraints** (từ `00-context.md`):
   - **Privacy**: bài nộp D28 là data cá nhân → cần consent rõ trước khi AI đọc; trong lab dùng 5 bài mẫu giả định
   - **Human review**: gợi ý cá nhân hóa là output ảnh hưởng lộ trình học → coach phải xem qua trước khi gửi học viên
   - **Citation**: tài liệu gợi ý phải trỏ đúng tên slide/handbook trong khóa, không được bịa
   - **Budget nhỏ**: ưu tiên API sẵn có, ước tính <$10 tổng cho 80 học viên
   - **Formative**: gợi ý là hỗ trợ học, không phải điểm chính thức
   - **Adoption**: nếu không ai click vào tài liệu gợi ý → pilot thất bại dù accuracy cao

7. **Quick Win đã chọn** (1 dòng, lấy từ file `2`): AI phân tích bài nộp D28 theo rubric 5 Gate → sinh danh sách cá nhân 3 concept/tài liệu cần xem lại trước 6 tuần thực chiến

8. **Open questions** (còn chưa biết gì — không được để trống):
   - Học viên có consent cho AI đọc bài nộp không? Quy trình consent là gì (opt-in hay mặc định)?
   - Kênh gửi gợi ý nào học viên thật sự đọc — Discord DM, LMS notification, hay email?
   - Rubric 5 Gate D28 có đủ granular để map "lỗi X → tài liệu Y cụ thể" không, hay cần xây thêm mapping table riêng?

9. **Validation** (đóng vai owner: *"đúng, đây là vấn đề đáng giải"* — Có / Chưa, vì sao):

```text
Đóng vai Instructor D28 / Program Lead:

"Đúng — đây là vấn đề đáng giải. Sau D28, học viên bước vào 6 tuần thực chiến mà không
có gì bridge cá nhân hóa giữa bài nộp và kế hoạch bù kiến thức. Nếu nhóm có thể chứng
minh trong 2 tuần rằng ≥70% gợi ý AI được coach đánh giá phù hợp (không phải gợi ý
chung chung) và ≥50% học viên thực sự click vào tài liệu được gợi ý, xứng đáng mở rộng
cho các track khác trong khóa."

→ CÓ xác nhận. Vấn đề rõ, scope pilot nhỏ, metric đo được.
```

---

## Tự phản biện

- Khung này còn câu chung chung kiểu "cần học tốt hơn" không? → Không. Đã chỉ rõ: 80 học viên track Product, sau D28, tại khoảnh khắc chuyển sang 6 tuần thực chiến, lỗ hổng cụ thể là concept trong Problem Framing/Pilot Plan.
- 3 câu sẽ bị hỏi — trả lời câu 1: *"Số liệu lấy ở đâu?"* → ~60% học viên trượt Gate và 5 phút/học viên của coach là 🧮 giả định, đánh dấu rõ. Số thật (bài nộp D28 thật + rubric) có thể verify ngay sau buổi hôm nay.

---

## Tổng kiểm tra trước khi sang `02-solution/`

| Hạng mục | Xong? |
|---|---|
| Chỉ rõ 1 nhóm người + 1 khoảnh khắc cụ thể (không "user nói chung") | ✓ (80 học viên track Product, sau D28, trước 6 tuần thực chiến) |
| Pain có số (hoặc kế hoạch lấy số), nói rõ số từ đâu | ✓ (🧮 đánh dấu rõ; kế hoạch verify từ bài nộp D28 thật) |
| Có baseline (hoặc cách đo baseline) + ≥1 chỉ số có ngưỡng | ✓ (baseline: 0% nhận gợi ý cá nhân; ngưỡng: ≥70% coach chấp nhận) |
| Mục 9: owner (giả định) xác nhận đúng vấn đề = qua cổng phase Frame | ✓ |

⚑ Coach kiểm tra ở Mốc 2: *"Ai đau? Baseline là gì? Không có baseline thì đo thế nào?"*

Owner chưa xác nhận → quay lại file `1`/`2`, đừng sang Solution. Owner xác nhận → mở `../02-solution/1-find-existing-solutions.md`.

*Liên quan: handbook §A4 · `prompts/03-problem-framing-challenge.md`*
