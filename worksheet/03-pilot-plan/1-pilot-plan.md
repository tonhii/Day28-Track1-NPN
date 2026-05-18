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

1. **Tóm vấn đề** (1 câu, từ Problem Framing): Học viên track Product đọc handbook D28 gặp concept không hiểu — không có cơ chế hỏi-đáp tức thì trong phạm vi tài liệu khóa, phải đợi Discord 30-60 phút hoặc bỏ qua.

2. **Cách làm + lý do** (từ 02-solution, 1 câu): Boost — Claude Haiku API phân tích câu hỏi học viên dựa trên handbook D28 nhét toàn bộ vào context, sinh câu trả lời kèm nguồn §X, nói "không biết" nếu câu hỏi ngoài phạm vi, coach review 10 câu test trước khi deploy.

3. **Scope pilot**: 80 học viên track Product · buổi D28 và 1 tuần sau D28 · 2 phase (Phase 1: build + test; Phase 2: deploy + collect feedback)

4. **Người**:
   - **Build + viết system prompt + test**: Hồ Thị Tố Nhi (nhóm trưởng kỹ thuật)
   - **Hỗ trợ format handbook + thiết kế câu hỏi test**: Lê Thị Phương, Trần Thị Kim Ngân
   - **Review output rủi ro cao (10 câu test)**: 1 coach track Product (confirm trước khi deploy)
   - **Quyết approve/dừng**: Instructor D28 / Program Lead

5. **Data**:
   - Handbook D28 (handbook/d28-student-handbook.md) — có sẵn trong repo, public, dùng nguyên
   - Slide skeleton D28 (nếu cần bổ sung context) — có sẵn trong LMS, public
   - Câu hỏi học viên trong pilot — cần thông báo rõ "chatbot log câu hỏi để cải thiện"; trong Phase 1 test chỉ dùng 10 câu hỏi mẫu giả định
   - Privacy: không lưu câu hỏi học viên lâu dài nếu không có consent; trong Phase 1 chỉ dùng câu hỏi mẫu

6. **Budget** (tách hạng mục):
   - Claude Haiku API: ~$1–3 cho ước tính 500 câu hỏi/tuần × ~500 tokens/câu (**🧮 ước tính**)
   - Overhead + retry + test 10 câu: ~$1
   - Thời gian người build (3 người × 2 giờ): ~6 giờ × $0 (học viên tự làm)
   - Thời gian coach review (1 coach × 30 phút): ~0.5 giờ coach time
   - Maintenance sau pilot: $0 (context stuffing không cần infra riêng)
   - **Tổng cash: <$5**

7. **Timeline + cổng giữa phase**:
   - **Phase 1** (ngày 1–2 sau D28): Format handbook D28 → viết system prompt → test với 10 câu hỏi mẫu → coach review
     → **Cổng Phase 1**: ≥8/10 câu test coach xác nhận đúng nguồn + phù hợp → tiếp tục Phase 2. Dưới → chỉnh system prompt, test lại, không deploy.
   - **Phase 2** (ngày 3–7): Deploy link/bot cho 80 học viên track Product → thu feedback sau 5 ngày (số lượng câu hỏi, % nói "không biết", feedback học viên)

8. **Metrics** (SMART + baseline + ngưỡng + ai đo):

| Metric | Đo bằng gì · ai đo | Baseline | Ngưỡng đạt |
|---|---|---|---|
| % câu trả lời kèm nguồn đúng (section tồn tại trong handbook + nội dung phù hợp câu hỏi) | Coach đánh giá Y/N trên 10 câu test Phase 1 · người build log lại | 0% (không có chatbot hiện tại) | ≥80% |
| % học viên track Product dùng chatbot ≥1 lần trong tuần | Log số unique user (không log nội dung nếu không có consent) · người build theo dõi | 0% | ≥40% |
| % câu hỏi chatbot trả lời "ngoài phạm vi" (fallback rate) — dùng để calibrate scope | Log tự động | 0% (chưa có data) | ≤30% (nếu cao hơn → handbook chưa cover đủ) |

   **Leading indicator** (biết kết quả sớm trong 1–2 ngày): Kết quả cổng Phase 1 — nếu ≥8/10 câu test coach chấp nhận → confidence cao cho Phase 2.

9. **Exit criteria** (định trước, ≥2 mức):

| Mức | Điều kiện | Hành động | Ai có quyền dừng |
|---|---|---|---|
| Cảnh báo | <8/10 câu test coach chấp nhận sau Phase 1 | Không sang Phase 2; chỉnh system prompt; test lại bộ 10 câu mới | Người build (Hồ Thị Tố Nhi) |
| Nghiêm trọng | Chatbot trỏ section không tồn tại trong handbook (citation hallucination) HOẶC trả lời câu hỏi ngoài phạm vi D28 mà không nói "không biết" | Dừng pilot ngay, không deploy thêm, thông báo học viên đang dùng, báo coach + Program Lead | Program Lead / Instructor D28 |

   *Liên hệ 2 Red Flag:*
   - **Red Flag #1 (bịa nội dung)**: Được chặn bởi instruction guard trong system prompt + cổng Phase 1 — coach kiểm tra từng câu trả lời có section thật không.
   - **Red Flag #2 (học viên hỏi bot thay vì đọc)**: Được chặn bởi prompt design — chatbot luôn trỏ về section cụ thể để học viên tự đọc; không đưa tóm tắt thay thế việc đọc. Đo bằng metric fallback rate và feedback học viên.

10. **Adoption** (tool không ai dùng = $0):
    - **Ai dùng đầu tiên**: 80 học viên track Product đang đọc handbook D28 trong buổi lab — nhóm có pain ngay lập tức (gặp concept không hiểu trong buổi)
    - **Workflow đổi ở đâu**: Thay vì post Discord khi không hiểu → hỏi chatbot trước; nếu chatbot nói "không biết" → mới post Discord
    - **Ai thông báo + support**: Coach giới thiệu chatbot đầu buổi D28 ("hôm nay chúng ta có chatbot riêng cho handbook D28, hỏi nó trước khi post Discord"). Nhóm build để link/hướng dẫn trong kênh Discord buổi.
    - **Nếu usage <20% sau 3 ngày**: Phỏng vấn nhanh 3-5 học viên (không biết link? link không mở được? không tin chatbot?). Điều chỉnh kênh announce hoặc format trả lời theo feedback; ghi vào lesson learned.

---

## Tự phản biện

- **Budget thiếu hạng mục ẩn nào không?** Đã tách API cost + retry + thời gian người + coach time. Nếu cần upgrade sang Sonnet (đắt hơn ~5×) → tổng API ~$5–15. Vẫn trong budget nhỏ.
- **Exit criteria đủ mạnh để THẬT SỰ dừng, hay chỉ trên giấy?** Mức Nghiêm trọng giao quyền dừng cho Program Lead (người ngoài nhóm build) — không thể bị nhóm override. Điều kiện dừng là kỹ thuật (citation hallucination), không cần judgement — dễ thực thi.
- **Giả định quan trọng nhất sai → plan gì?** Giả định: handbook D28 đủ phủ các câu hỏi phổ biến của học viên. Nếu sai (fallback rate >50%) → bổ sung slide skeleton vào context; nếu vẫn cao → thu thập top 20 câu hỏi thật từ Discord để thêm vào FAQ guard trong system prompt.

---

## Tổng kiểm tra trước khi sang `2-FINAL-pitch.md`

| Hạng mục | Xong? |
|---|---|
| Tóm vấn đề trong 1 câu | ✓ |
| Budget tách hạng mục, không "miscellaneous" | ✓ (API + retry + thời gian người + coach time) |
| Metric có baseline + ngưỡng + ai đo | ✓ (3 metric, có baseline rõ, có ngưỡng định trước) |
| Exit criteria có người có quyền thực thi (≥2 mức) | ✓ (Cảnh báo: người build; Nghiêm trọng: Program Lead) |
| Adoption: chỉ rõ ai dùng đầu tiên (không "cả khóa") | ✓ (80 học viên track Product D28, kênh Discord + link đầu buổi) |

⚑ Coach kiểm tra ở Mốc 4: *"Xin gì? Hứa gì? Đo gì? Dừng khi nào?"*

Sau bước này, mở `2-FINAL-pitch.md` — dồn tất cả thành 5-slide pitch + AI Support Log.

*Liên quan: handbook §A7+§A8 · `templates/ai-pilot-plan-core.md` · `prompts/06-pilot-plan-challenge.md`*
