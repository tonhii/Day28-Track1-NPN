---
artifact: 1 — Track & Big Ask + 2 — Tool Breakdown
bai-tap: Frame — nghe đúng đề rồi tách nhỏ
phase: Double Diamond vòng 1 · ◇ giãn (nghe rộng, chưa chốt)
time: ~12 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 00-context.md · track card · prompts/01-breakdown.md
nop-cuoi: Không — file trung gian (bản chốt phase này ở 3-FINAL-problem-framing.md)
---

# 1 — Intake & Breakdown: nghe đúng đề, tách nhỏ

Mục tiêu: cả nhóm hiểu giống nhau "công cụ lớn stakeholder muốn", rồi tách nó thành 5–8 use case nhỏ làm được riêng. Đây là nửa "giãn ra" của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 1 — nghe rộng, tách rộng, chưa chọn.

Lý do làm bước này: hai cái bẫy chết người ở đây. Một, nhận đề literal ("làm con chatbot") rồi nhảy vào build — trong khi yêu cầu mơ hồ thường chỉ là triệu chứng. Hai, ôm cả công cụ lớn đi pitch "build cả platform" → trượt Gate 1 ngay. Tách nhỏ là động tác bắt buộc để từ "một ý tưởng to" sang "danh sách phần làm được".

Quy tắc: **nghe trước, tách trước, chưa chọn.** Bước này không được chốt Quick Win (việc đó ở file `2`).

## Bước 0 — Đọc track card + 00-context (2 phút)

Đọc track card được giao và `00-context.md` (mục 2 đã điền). Đừng lướt.

## Quy trình 12 phút

```text
2 phút  — Bước 0: đọc track card + context
4 phút  — Phần A: phát biểu lại Big Ask bằng lời nhóm
6 phút  — Phần B: tách 5–8 use case + check độc lập
```

---

## Phần A — Phát biểu lại Big Ask bằng lời nhóm

Đừng chép lại đề. Cả nhóm nói lại "công cụ lớn stakeholder muốn" bằng lời mình. Nếu 3 người nói 3 kiểu khác nhau → chưa hiểu giống nhau, bàn thêm.

Câu hỏi phụ (tự trả lời):

- Stakeholder nói họ muốn gì, và họ thực sự *cần* gì — có khác nhau không?
- "Tại sao bây giờ?" — ở quy mô ~500 người, cái gì đang đau khiến phải làm công cụ này lúc này?
- Ai là người dùng đầu tiên thật sự, không phải "cả khóa"?

### Trả lời

- **Big Ask, viết lại bằng lời nhóm (2–3 câu)**: Khóa AI Thực Chiến có ~500 học viên với background rất khác nhau (PM, founder, engineer, operator) nhưng lộ trình học gần như giống hệt nhau cho tất cả. Stakeholder muốn xây một hệ thống AI hiểu từng học viên — biết họ đang ở level nào, đã nắm được gì, còn yếu chỗ nào — để sinh ra lộ trình học riêng thay vì ai cũng đi cùng một con đường.
- **Tại sao bây giờ**: Sau D28, khóa bước vào 6 tuần thực chiến — giai đoạn đòi hỏi học viên áp dụng đúng concept đã học. Học viên với background khác nhau cần biết họ phải bổ sung gì trước khi vào sprint, nhưng hiện tại không có gì giúp họ biết điều đó một cách cá nhân hóa. Coach không thể đưa gợi ý riêng cho 500 người trong thời gian có hạn.
- **Người dùng đầu tiên cụ thể**: Học viên track Product (~80 người) vừa nộp bài D28, đang chuẩn bị bước vào 6 tuần thực chiến và chưa biết mình còn yếu concept nào.

## Phần B — Tách công cụ lớn thành 5–8 use case

Nhìn mục **Big Vision Modules** trong track card. Mỗi dòng = 1 use case làm được riêng, viết dạng *"AI làm X cho ai để họ Y"* — không phải tính năng mơ hồ. Cần 5–8 dòng (ít hơn 5 = chưa tách đủ; nhiều hơn 8 = đang liệt kê vụn).

| # | Use case (AI làm gì · cho ai · để họ làm được gì) | Người dùng | Làm được độc lập? |
|---|---|---|---|
| 1 | AI chẩn đoán kỹ năng từ quiz đầu/giữa khóa → tạo lộ trình học cá nhân cho từng học viên để họ biết bắt đầu từ đâu | Học viên | Có |
| 2 | AI phân tích bài nộp lab → gợi ý 3 tài liệu/concept cần xem lại theo lỗi cụ thể trong bài | Học viên | Có |
| 3 | AI sinh lộ trình bù sau D28 cho học viên sai nhiều ở Build/Buy/Boost & Pilot Plan → chuẩn bị 6 tuần thực chiến | Học viên | Có (cần bài nộp D28) |
| 4 | AI theo dõi tiến độ học tập theo concept xuyên khóa → hiển thị trên dashboard cho học viên biết họ đang ở đâu | Học viên, Coach | Không — phụ thuộc #1 và hệ thống tracking |
| 5 | AI gợi ý peer learning: ghép đôi học viên có điểm mạnh/yếu bổ sung nhau → tăng hỗ trợ peer-to-peer | Học viên, Coach | Không — phụ thuộc #1 (cần profile kỹ năng) |
| 6 | AI sinh quiz kiểm tra điểm yếu định kỳ theo concept → học viên biết tiến độ tự học theo tuần | Học viên | Không — phụ thuộc #1 |
| 7 | AI tạo view cho coach: danh sách học viên cần can thiệp ngay theo mức độ → coach ưu tiên đúng người | Coach | Không — phụ thuộc #4 |

Cần ít nhất **4 use case thật sự độc lập** (làm được mà không cần cái khác xong trước). Nếu nhiều cái phụ thuộc nhau → gộp hoặc viết lại cho tách bạch.

---

## Phát hiện ban đầu

- Chỉ có UC1, UC2, UC3 là độc lập hoàn toàn — làm được mà không cần cái khác xong trước. Các UC còn lại (4, 5, 6, 7) đều phụ thuộc.
- UC2 và UC3 rất gần nhau về bản chất (đều dùng bài nộp lab → gợi ý cá nhân); có thể gộp thành 1 Quick Win.
- Data sẵn có ngay cho UC2/UC3 (bài nộp D28 + rubric) — không cần xây infrastructure mới.

## Câu hỏi mở (mang sang bước chọn Quick Win)

- UC1 và UC2/UC3 đều mạnh — cái nào có evidence nhanh hơn, ít rủi ro hơn trong 2 tuần?
- Coach có sẵn sàng review output AI trước khi gửi cho học viên không? Bao nhiêu thời gian họ có?

---

## Tổng kiểm tra trước khi sang `2-quick-win.md`

| Hạng mục | Xong? |
|---|---|
| Cả nhóm phát biểu lại Big Ask giống nhau, không cần nhìn card | ✓ |
| Có 5–8 use case dạng "AI làm X cho ai để Y" | ✓ (7 use case) |
| Có ≥4 use case thật sự độc lập | ✓ (UC1, UC2, UC3 độc lập hoàn toàn) |
| Nhóm KHÔNG còn ý định pitch "build cả platform" | ✓ |

Sau bước này, mở `2-quick-win.md` — chấm điểm chọn 1 lát cắt làm trước.

*Liên quan: handbook §A1+§A2 · `prompts/01-breakdown.md` · `00-context.md`*
