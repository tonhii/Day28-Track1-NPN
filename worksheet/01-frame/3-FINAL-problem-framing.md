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

1. **Original Ask** (stakeholder nói gì, nguyên văn): "Biến LMS thành gia sư tương tác cho ~500 học viên — học viên đọc bài, hỏi lại, làm mini practice, nhận giải thích theo level, có dẫn nguồn từ tài liệu khóa học"

2. **Reframed problem** (vấn đề thật sau khi tách): Học viên track Product (~80 người) đang đọc handbook D28 gặp concept không hiểu — không có cơ chế hỏi-đáp tức thì trong phạm vi tài liệu khóa. Phải post Discord và đợi 30-60 phút (hoặc bỏ qua), dẫn đến vào lab với concept hiểu sai. Kết quả: framing sai, pilot plan thiếu chỉ số, bài nộp trượt Gate.

3. **Current workflow** (hiện tại đang xử lý thế nào, kể cả "không ai làm gì"): Học viên đọc handbook D28 → gặp concept khó (Double Diamond, Exit Criteria, Build/Buy/Boost) → hoặc bỏ qua, hoặc post Discord (chờ coach/bạn trả lời ~30-60 phút), hoặc Google (câu trả lời không khớp với định nghĩa của khóa) → vào lab với hiểu biết không chắc.

4. **Pain evidence — bằng SỐ** (ai đau · đau ở khoảnh khắc nào trong việc · tần suất · quy mô; số giả định ghi rõ nguồn giả định):

```text
• 🧮 Giả định: Discord D28 nhận ~50–80 câu hỏi/buổi từ 80 học viên track Product
  về concept (Problem Framing, Build/Buy/Boost, Exit Criteria, Double Diamond).
  Nguồn giả định: ước tính từ pattern câu hỏi điển hình trong buổi lab nhiều module.

• 🧮 Giả định: ~40% câu hỏi Discord đó có thể trả lời bằng cách trỏ thẳng về
  1 đoạn trong handbook D28 — chứng tỏ học viên không tìm thấy nội dung tài liệu
  hoặc không biết tìm ở đâu. Nguồn: ước tính dựa trên loại câu hỏi định nghĩa
  ("Exit criteria là gì?", "Double Diamond vòng 2 khác gì vòng 1?").

• 🧮 Giả định: Coach mất ~15–20 phút/buổi trả lời câu hỏi Discord lặp lại
  (câu đã có trong handbook, chỉ cần trỏ section) thay vì tập trung coaching chiều sâu.
  Nguồn: ước tính; số thật cần log Discord thực tế.

• Số thật có thể verify ngay: handbook D28 (handbook/d28-student-handbook.md) +
  slide skeleton + log câu hỏi Discord buổi D28 hôm nay — có sau buổi.
```

5. **Affected people** (ai dùng · ai quyết · ai là người review/expert):
   - **Người dùng**: ~80 học viên track Product D28 (trong buổi học và sau buổi)
   - **Người quyết approve pilot**: Instructor D28 / Program Lead
   - **Người review output**: 1 coach track Product (review 10 câu test trước khi mở cho học viên)

6. **Constraints** (từ `00-context.md`):
   - **Privacy**: câu hỏi học viên hỏi chatbot không lưu trữ lâu dài hoặc chia sẻ mà không có consent; trong lab test chỉ dùng câu hỏi mẫu giả định
   - **Human review**: trước khi deploy cho 80 học viên, coach review 10 câu test để xác nhận chatbot không bịa nguồn
   - **Citation**: chatbot phải trỏ đúng section trong handbook D28 (ví dụ "handbook §A3"); nếu không tìm thấy nguồn → nói "không biết", không được bịa
   - **Budget nhỏ**: ưu tiên Claude Haiku API hoặc context window đơn giản, ước tính <$5 cho pilot 1 tuần
   - **Adoption**: nếu học viên không hỏi chatbot (vẫn đi Discord) → pilot thất bại dù accuracy 99%; cần onboarding rõ
   - **Ranh giới gia sư/đáp án**: chatbot hỗ trợ hiểu tài liệu, không làm bài thay học viên; cần prompt phân biệt rõ

7. **Quick Win đã chọn** (1 dòng, lấy từ file `2`): Chatbot gia sư D28 — học viên hỏi về handbook D28 → nhận câu trả lời kèm nguồn cụ thể (section + đoạn trích); nói "không biết" nếu câu hỏi ngoài phạm vi

8. **Open questions** (còn chưa biết gì — không được để trống):
   - Kênh deploy nào phù hợp nhất cho 80 học viên — trong LMS, Discord bot, hay link standalone Claude.ai?
   - Học viên thật sự sẽ dùng chatbot hay vẫn dùng Discord? Cần onboarding thế nào?
   - Handbook D28 có đủ bao phủ các câu hỏi phổ biến nhất không, hay cần bổ sung thêm slide skeleton vào context?

9. **Validation** (đóng vai owner: *"đúng, đây là vấn đề đáng giải"* — Có / Chưa, vì sao):

```text
Đóng vai Instructor D28 / Program Lead:

"Đúng — đây là vấn đề đáng giải. Học viên hỏi Discord về khái niệm có sẵn trong handbook
là dấu hiệu rõ: LMS chưa đủ tương tác. Nếu nhóm có thể chứng minh trong 1 tuần rằng
≥80% câu trả lời của chatbot có nguồn đúng từ handbook (không bịa section) và
≥40% học viên track Product thật sự dùng ít nhất 1 lần, xứng đáng mở rộng sang
toàn bộ D28 và các ngày khác trong khóa."

→ CÓ xác nhận. Vấn đề rõ, scope pilot nhỏ, metric đo được.
```

---

## Tự phản biện

- Khung này còn câu chung chung kiểu "học viên cần học tốt hơn" không? → Không. Đã chỉ rõ: 80 học viên track Product, khoảnh khắc đọc handbook D28, pain cụ thể là không có cơ chế hỏi-đáp tức thì kèm nguồn, đo được bằng % câu trả lời đúng nguồn và % học viên dùng.
- 3 câu sẽ bị hỏi — trả lời câu 1: *"Số liệu lấy ở đâu?"* → Ba con số chính (50-80 câu hỏi/buổi, 40% trả lời được bằng handbook, 15-20 phút coach mất) là 🧮 giả định, đánh dấu rõ. Số thật có thể verify từ log Discord buổi D28 hôm nay + thời gian coach đo sau buổi.

---

## Tổng kiểm tra trước khi sang `02-solution/`

| Hạng mục | Xong? |
|---|---|
| Chỉ rõ 1 nhóm người + 1 khoảnh khắc cụ thể (không "user nói chung") | ✓ (80 học viên track Product, khi đọc handbook D28, gặp concept không hiểu) |
| Pain có số (hoặc kế hoạch lấy số), nói rõ số từ đâu | ✓ (🧮 đánh dấu rõ; kế hoạch verify từ log Discord buổi D28) |
| Có baseline (hoặc cách đo baseline) + ≥1 chỉ số có ngưỡng | ✓ (baseline: 0% có chatbot hỗ trợ; ngưỡng: ≥80% câu trả lời đúng nguồn) |
| Mục 9: owner (giả định) xác nhận đúng vấn đề = qua cổng phase Frame | ✓ |

⚑ Coach kiểm tra ở Mốc 2: *"Ai đau? Baseline là gì? Không có baseline thì đo thế nào?"*

Owner chưa xác nhận → quay lại file `1`/`2`, đừng sang Solution. Owner xác nhận → mở `../02-solution/1-find-existing-solutions.md`.

*Liên quan: handbook §A4 · `prompts/03-problem-framing-challenge.md`*
