---
artifact: 7 — AI Pilot Plan core
bai-tap: Pilot Plan — cam kết hai chiều: xin – hứa – đo – dừng
phase: Double Diamond vòng 2 · ◇ giãn → ◆ siết (liệt kê hết rồi chốt gọn)
time: ~10 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 02-solution/2-FINAL-solution.md · 00-context.md · prompts/06-pilot-plan-challenge.md
nop-cuoi: Không — file trung gian (bản nộp ở 2-FINAL-pitch.md)
---

# 1 — AI Pilot Plan core

Mục tiêu: viết phần kế hoạch xin pilot — scope, người, data, budget, timeline, metric, exit criteria, adoption, lời hứa, lời xin. Bước này giãn ra (liệt kê hết những thứ cần) rồi siết lại (chốt bản gọn đủ để stakeholder quyết).

Lý do làm bước này: đây là thứ stakeholder dùng để **quyết approve hay dừng**. AI Pilot Plan **không phải proposal xin tiền** — là *cam kết hai chiều*: nhóm xin nguồn lực, đổi lại hứa giao evidence + chấp nhận dừng nếu metric fail. Demo đẹp mà không nói được "xin gì, hứa gì, đo gì, dừng khi nào" → trượt Gate 5.

Quy tắc: **budget tách từng hạng mục, không gộp 1 cục; không có mục "miscellaneous".** Exit criteria phải có người có quyền thực thi, không chỉ trên giấy.

## Quy trình 10 phút

```text
6 phút  — Điền 10 mục core (kéo nguyên liệu từ 00 + 01-frame + 02-solution)
3 phút  — Phần exit criteria + adoption (chỗ nhóm hay bỏ quên)
1 phút  — Tự phản biện
```

---

## 10 mục core

Câu hỏi phụ (tự trả lời):

- Nếu tóm vấn đề không gọn trong 1 câu → nhóm chưa hiểu vấn đề.
- Exit criteria của nhóm có ai DÁM thực thi khi sếp vẫn thích pilot không?
- Adoption: ai dùng đầu tiên — không phải "cả khóa ~500 người"?

### Trả lời

1. **Tóm vấn đề** (1 câu, từ Problem Framing): Học viên track Product sau D28 không biết mình còn yếu concept nào và không nhận được gợi ý cá nhân để chuẩn bị vào 6 tuần thực chiến.

2. **Cách làm + lý do** (từ 02-solution, 1 câu): Boost — Claude API phân tích bài nộp D28 theo rubric 5 Gate + mapping table lỗi→tài liệu khóa, sinh gợi ý 3 tài liệu cần xem lại cá nhân hóa, coach review trước khi gửi.

3. **Scope pilot**: 80 học viên track Product · cohort D28 (buổi hôm nay) · 2 tuần sau D28 · 2 phase (Phase 1: build + test 5 mẫu; Phase 2: chạy đủ 80 + deliver)

4. **Người**:
   - **Build + chạy pipeline**: Hồ Thị Tố Nhi (nhóm trưởng kỹ thuật)
   - **Hỗ trợ prompt + mapping table**: Lê Thị Phương, Trần Thị Kim Ngân
   - **Review output rủi ro cao**: 1–2 coach track Product (review trước khi gửi học viên)
   - **Quyết approve/dừng**: Instructor D28 / Program Lead

5. **Data**:
   - Bài nộp D28 FINAL của 80 học viên (3 file/học viên) — cần opt-in consent; trong Phase 1 test dùng 5 bài mẫu giả định
   - Rubric 5 Gate D28 (có sẵn: `templates/rubric-gate-sheet.md`) — public, không vấn đề
   - Mapping table lỗi→tài liệu (tự build, ~15 entries) — public
   - Privacy: bài nộp chỉ đọc trong session xử lý, không lưu trữ lâu dài; consent rõ trong email thông báo

6. **Budget** (tách hạng mục):
   - Claude API (Haiku/Sonnet): ~$5–8 cho 80 bài × ~2,500 tokens (**🧮 ước tính**)
   - Overhead + retry + test: ~$2
   - Thời gian người build (3 người × 4 giờ): ~12 giờ × $0 (học viên tự làm)
   - Thời gian coach review (1–2 coach × 1 giờ): ~2 giờ coach time
   - Maintenance sau pilot: $0 (one-shot cho cohort D28)
   - **Tổng cash: <$10**

7. **Timeline + cổng giữa phase**:
   - **Phase 1** (1 tuần sau D28): Xây mapping table + viết system prompt + test với 5 bài mẫu giả định
     → **Cổng Phase 1**: ≥4/5 coach đánh giá gợi ý phù hợp trên 5 mẫu → tiếp tục Phase 2. Dưới → chỉnh prompt, không sang Phase 2.
   - **Phase 2** (tuần 2): Thu consent + chạy cho 80 học viên → coach review → gửi → thu feedback trong 3 ngày

8. **Metrics** (SMART + baseline + ngưỡng + ai đo):

| Metric | Đo bằng gì · ai đo | Baseline | Ngưỡng đạt |
|---|---|---|---|
| % gợi ý được coach đánh giá phù hợp (tài liệu đúng + lý do khớp lỗi) | Coach đánh giá Y/N mỗi gợi ý trước khi gửi · người build log lại | 0% (không có hệ thống hiện tại) | ≥70% |
| % học viên click ≥1 tài liệu được gợi ý trong 1 tuần | Link tracking (bit.ly hoặc LMS analytics) · người build theo dõi | 0% | ≥50% |
| Thời gian coach tiết kiệm/học viên so với làm thủ công | Coach log thời gian review AI output (🧮 baseline ~5 phút/học viên nếu thủ công) | 🧮 ~5 phút/học viên | ≤1.5 phút/học viên |

   **Leading indicator** (biết kết quả sớm trong 1–2 tuần): Kết quả cổng Phase 1 — nếu ≥4/5 mẫu coach chấp nhận → confidence cao cho Phase 2.

9. **Exit criteria** (định trước, ≥2 mức):

| Mức | Điều kiện | Hành động | Ai có quyền dừng |
|---|---|---|---|
| Cảnh báo | <50% gợi ý coach chấp nhận sau test 5 mẫu (Phase 1) | Không sang Phase 2; chỉnh lại prompt + mapping table; test lại | Người build (Hồ Thị Tố Nhi) |
| Nghiêm trọng | AI trỏ tài liệu không tồn tại trong khóa (citation sai) HOẶC học viên phản hồi gợi ý gây hiểu nhầm nghiêm trọng về lộ trình học | Dừng pilot ngay, không gửi thêm output, thông báo tất cả học viên đã nhận, báo coach + Program Lead | Program Lead / Instructor D28 |

   *Liên hệ 2 Red Flag:*
   - **Red Flag #1 (cá nhân hóa giả)**: Được chặn bởi cổng Phase 1 — coach kiểm tra từng gợi ý có khác nhau và có bám lỗi cụ thể không.
   - **Red Flag #2 (không đo được)**: Được chặn bởi 3 metric rõ ràng với baseline và ngưỡng định trước.

10. **Adoption** (tool không ai dùng = $0):
    - **Ai dùng đầu tiên**: 80 học viên track Product D28 — nhóm sẵn sàng nhất (vừa nộp bài, đang cần biết phải bù gì)
    - **Workflow đổi ở đâu**: Sau khi nộp bài D28 → thay vì không nhận gì → học viên nhận thêm 1 message cá nhân (Discord DM hoặc LMS) với danh sách 3 gợi ý trong vòng 48 giờ
    - **Ai thông báo + support**: Coach announce trong recap buổi D28 ("trong 2 ngày tới các bạn sẽ nhận gợi ý cá nhân..."); nhóm build trả lời câu hỏi kỹ thuật nếu link không mở được
    - **Nếu click rate <30% sau 1 tuần**: Khảo sát nhanh 5 học viên ngẫu nhiên (gợi ý không relate? sai kênh gửi? sai thời điểm?) → điều chỉnh kênh hoặc format, ghi vào lesson learned

---

## Tự phản biện

- **Budget thiếu hạng mục ẩn nào không?** Đã tách API cost + retry + thời gian người. Hạng mục ẩn còn lại: nếu cần thay model sang Sonnet (đắt hơn ~5×) → tổng API ~$25–40. Vẫn trong budget nhỏ.
- **Exit criteria đủ mạnh để THẬT SỰ dừng, hay chỉ trên giấy?** Mức Nghiêm trọng giao quyền dừng cho Program Lead (người ngoài nhóm build) — không thể bị nhóm override vì "muốn tiếp tục".
- **Giả định quan trọng nhất sai → plan gì?** Giả định: coach có ~1 giờ để review 80 output. Nếu sai (coach bận >3 giờ) → thu hẹp scope Phase 2 xuống 20 học viên tình nguyện trước, rồi mở rộng sau.

---

## Tổng kiểm tra trước khi sang `2-FINAL-pitch.md`

| Hạng mục | Xong? |
|---|---|
| Tóm vấn đề trong 1 câu | ✓ |
| Budget tách hạng mục, không "miscellaneous" | ✓ (API + retry + thời gian người + coach time) |
| Metric có baseline + ngưỡng + ai đo | ✓ (3 metric, 2 có baseline thật, 1 có 🧮 rõ) |
| Exit criteria có người có quyền thực thi (≥2 mức) | ✓ (Cảnh báo: người build; Nghiêm trọng: Program Lead) |
| Adoption: chỉ rõ ai dùng đầu tiên (không "cả khóa") | ✓ (80 học viên track Product D28, kênh Discord DM/LMS) |

⚑ Coach kiểm tra ở Mốc 4: *"Xin gì? Hứa gì? Đo gì? Dừng khi nào?"*

Sau bước này, mở `2-FINAL-pitch.md` — dồn tất cả thành 5-slide pitch + AI Support Log.

*Liên quan: handbook §A7+§A8 · `templates/ai-pilot-plan-core.md` · `prompts/06-pilot-plan-challenge.md`*
