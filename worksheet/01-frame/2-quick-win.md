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
| UC2/UC3: AI phân tích bài nộp D28 → gợi ý 3 tài liệu cần xem lại | 4 | 5 | 5 | 5 | **19** |
| UC1: AI chẩn đoán từ quiz → lộ trình cá nhân đầu khóa | 5 | 3 | 2 | 3 | **13** |
| UC5: AI gợi ý peer learning theo điểm mạnh/yếu | 3 | 3 | 2 | 4 | **12** |
| UC7: View cho coach — ai cần can thiệp ngay | 4 | 2 | 2 | 3 | **11** |
| UC4: Dashboard tiến độ theo concept | 3 | 2 | 1 | 3 | **9** |

(Thang điểm chi tiết: `templates/quick-win-scoring.md`.)

## Phần B — 1 lý do nên / 1 lý do không, cho top 2

**Ứng viên A — UC2/UC3: AI phân tích bài nộp D28 → gợi ý 3 tài liệu cần xem lại**

```text
Nên chọn vì: Data có sẵn ngay (bài nộp D28 + rubric 5 Gate), test được trong 1 tuần,
             impact rõ cho 80 học viên track Product trước 6 tuần thực chiến.
Không nên vì: Cần mapping table lỗi→tài liệu chưa có, phải build thêm 2-3 giờ đầu.
```

**Ứng viên B — UC1: AI chẩn đoán từ quiz → lộ trình cá nhân**

```text
Nên chọn vì: Impact cao nhất về lâu dài — học viên có lộ trình riêng từ đầu.
Không nên vì: Data quiz đầu khóa đã cũ (thời điểm đã qua), cần infrastructure
             phức tạp hơn để lưu trữ và track tiến độ, evidence nhanh rất khó.
```

## Phần C — Chốt Quick Win

- **Quick Win nhóm chọn**: AI phân tích bài nộp D28 của từng học viên theo rubric 5 Gate → sinh danh sách cá nhân 3 concept/tài liệu cần xem lại trước 6 tuần thực chiến
- **Vì sao chọn cái này trước** (2–4 câu, bám điểm + impact + evidence nhanh): Tổng điểm 19/20 — cao nhất trong 5 ứng viên. Data có sẵn ngay sau D28 (bài nộp + rubric), không cần xây hệ thống tracking mới. Evidence nhanh: test được trong 1 tuần với 5 bài mẫu trước khi scale. Risk thấp vì chỉ gợi ý học liệu, không chấm điểm, coach vẫn là người quyết.
- **Ai trong AI20k sẽ ủng hộ pilot này** (và vì sao họ care): Instructor D28 — cần bridge cá nhân hóa sau D28 trước khi học viên vào 6 tuần thực chiến, không có gì hiện tại. Coach track Product — muốn tiết kiệm thời gian đưa feedback cá nhân (hiện mất ~5 phút/người nếu làm thủ công).
- **Nhóm KHÔNG chọn gì + vì sao**: 1. UC1 (chẩn đoán từ quiz đầu khóa) — thời điểm đã qua, data quiz cũ, cần infrastructure phức tạp, evidence không thể có trong 1-2 tuần.  2. UC7 (view cho coach) — phụ thuộc hoàn toàn vào UC4 (dashboard tiến độ) chưa có, không thể pilot độc lập.

---

## Phát hiện ban đầu

- UC2/UC3 vượt trội so với các ứng viên còn lại vì có data sẵn + evidence nhanh + risk thấp — 3 yếu tố quan trọng nhất cho Quick Win.

## Câu hỏi mở (mang sang Problem Framing)

- Số học viên thật sự có Gate trượt trong D28 là bao nhiêu? (Hiện tại chỉ là giả định ~60%)
- Kênh gửi gợi ý về cho học viên là Discord, LMS hay email — cái nào học viên thật sự đọc?

---

## Tổng kiểm tra trước khi sang `3-FINAL-problem-framing.md`

| Hạng mục | Xong? |
|---|---|
| Có bảng chấm 4 trục cho ≥4 use case | ✓ (5 use case) |
| Chốt 1 Quick Win, lý do bám số/impact (không "nghe hay") | ✓ |
| Nêu rõ ai ủng hộ pilot này | ✓ (Instructor D28 + Coach track Product) |
| Ghi rõ ≥2 phần KHÔNG chọn + lý do | ✓ (UC1 và UC7) |

⚑ Đây là phần coach kiểm tra ở Mốc 1: *"Vì sao không làm full tool? Vì sao chọn lát cắt này trước?"*

Sau bước này, mở `3-FINAL-problem-framing.md` — đóng khung vấn đề thật (bản nộp của phase Frame).

*Liên quan: handbook §A3 · `templates/quick-win-scoring.md` · `prompts/02-quick-win-challenge.md`*
