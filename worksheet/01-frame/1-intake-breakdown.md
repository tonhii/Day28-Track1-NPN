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

- **Big Ask, viết lại bằng lời nhóm (2–3 câu)**: LMS hiện tại chỉ là kho tài liệu — học viên đọc thụ động, không hiểu thì hỏi Discord hoặc bỏ qua. Stakeholder muốn biến LMS thành gia sư tương tác: học viên có thể hỏi lại ngay trong khi đọc, nhận giải thích theo level của mình, làm bài tập nhỏ để kiểm tra hiểu biết — và mọi câu trả lời đều có dẫn nguồn từ tài liệu khóa học, không phải AI tự bịa.
- **Tại sao bây giờ**: Sau D28, học viên bước vào 6 tuần thực chiến cần áp dụng đúng framework (Problem Framing, Build/Buy/Boost, AI Pilot Plan). Nếu học viên không nắm concept trong D28, họ vào sprint với lỗ hổng kiến thức chưa biết. LMS đã có đủ tài liệu (handbook, slide, template) nhưng không có cơ chế tương tác — học viên không biết mình đọc sai hay đúng.
- **Người dùng đầu tiên cụ thể**: Học viên track Product (~80 người) đang đọc handbook/slide D28 và gặp khó khăn với concept mới như Double Diamond, Build/Buy/Boost, Exit Criteria — những concept cần hiểu đúng trước khi làm lab.

## Phần B — Tách công cụ lớn thành 5–8 use case

Nhìn mục **Big Vision Modules** trong track card. Mỗi dòng = 1 use case làm được riêng, viết dạng *"AI làm X cho ai để họ Y"* — không phải tính năng mơ hồ. Cần 5–8 dòng (ít hơn 5 = chưa tách đủ; nhiều hơn 8 = đang liệt kê vụn).

| # | Use case (AI làm gì · cho ai · để họ làm được gì) | Người dùng | Làm được độc lập? |
|---|---|---|---|
| 1 | AI trả lời câu hỏi học viên về nội dung D28 (Frame/Solution/Pilot Plan) kèm dẫn nguồn từ handbook/slide → học viên hiểu concept đang đọc mà không cần rời khỏi LMS | Học viên | Có |
| 2 | AI gia sư Socratic: khi học viên hỏi đáp án trực tiếp → đặt câu hỏi ngược để học viên suy luận thay vì cho đáp án thẳng | Học viên | Có |
| 3 | AI tạo mini practice 5 câu sau mỗi phần D28 (Frame / Solution / Pilot Plan) → học viên tự kiểm tra hiểu biết trước khi sang phần tiếp | Học viên | Có |
| 4 | AI giải thích concept theo 3 level (cơ bản / áp dụng / nâng cao) theo yêu cầu → phù hợp với background khác nhau (PM/founder/engineer) | Học viên | Có |
| 5 | AI gợi ý "bài tiếp theo" dựa trên câu hỏi vừa đặt → học viên biết nên đọc gì tiếp, không bị lạc trong LMS | Học viên | Không — phụ thuộc UC1 (cần biết học viên hỏi gì) |
| 6 | AI tổng hợp câu hỏi học viên theo concept → dashboard cho instructor thấy chỗ nào bị hỏi nhiều → phát hiện confusion để can thiệp live | Instructor, Coach | Không — phụ thuộc UC1 (cần dữ liệu câu hỏi thật) |
| 7 | AI tổng hợp FAQ sau mỗi buổi D28 từ câu hỏi Discord → tài liệu tham khảo cho lần sau + giảm câu hỏi lặp lại | Instructor, Coach | Có (độc lập, chỉ cần log Discord) |

Cần ít nhất **4 use case thật sự độc lập** (làm được mà không cần cái khác xong trước). Nếu nhiều cái phụ thuộc nhau → gộp hoặc viết lại cho tách bạch.

---

## Phát hiện ban đầu

- UC1, UC2, UC3, UC4, UC7 là độc lập hoàn toàn — làm được mà không cần cái khác xong trước. Vượt yêu cầu ≥4.
- UC5 và UC6 đều phụ thuộc UC1 — chúng là Phase 2 tự nhiên sau UC1 pilot xong.
- UC1 là nền tảng của cả track: không có chatbot Q&A → không có dashboard (UC6), không có gợi ý tiếp theo (UC5).
- UC3 (mini practice) rất gần UC1 về kỹ thuật (cùng dùng LLM + tài liệu) → có thể build song song hoặc gộp vào Quick Win.

## Câu hỏi mở (mang sang bước chọn Quick Win)

- UC1 và UC3 đều mạnh — cái nào nên là Quick Win duy nhất, hay gộp thành 1?
- Kênh deploy chatbot nào học viên thật sự dùng — trong LMS, Discord bot, hay standalone link?

---

## Tổng kiểm tra trước khi sang `2-quick-win.md`

| Hạng mục | Xong? |
|---|---|
| Cả nhóm phát biểu lại Big Ask giống nhau, không cần nhìn card | ✓ |
| Có 5–8 use case dạng "AI làm X cho ai để Y" | ✓ (7 use case) |
| Có ≥4 use case thật sự độc lập | ✓ (UC1, UC2, UC3, UC4, UC7 độc lập) |
| Nhóm KHÔNG còn ý định pitch "build cả platform" | ✓ |

Sau bước này, mở `2-quick-win.md` — chấm điểm chọn 1 lát cắt làm trước.

*Liên quan: handbook §A1+§A2 · `prompts/01-breakdown.md` · `00-context.md`*
