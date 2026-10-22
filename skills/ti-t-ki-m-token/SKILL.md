---
name: Tiết kiệm token
description: >-
  Dùng TRƯỚC MỌI việc (báo cáo, chạy ads, phân tích, học, sheet, browser): lên
  kế hoạch để tốn ít token nhất mà vẫn đúng kết quả.
---
# Nguyên tắc: tính trước, làm ít bước nhất

Trước khi làm, ước lượng số bước/tool call và chọn đường rẻ nhất cho cùng kết quả.

## Thứ tự ưu tiên nguồn (rẻ → đắt)
1. Trí nhớ, file đã có (sheet, CSV, log, ghi chú) — dùng lại, không lấy lại dữ liệu đã có hôm nay.
2. Connector/API (Google Sheets…) — đọc đúng range cần, không đọc cả sheet.
3. Shell/script — xử lý số liệu bằng code thay vì đọc tay.
4. Browser — đắt nhất: gộp tất cả yêu cầu vào MỘT lần chạy, chỉ định rõ URL, cột, khoảng ngày, điểm dừng; dùng export CSV thay vì đọc màn hình.

## Quy tắc
- Không chạy lại việc trùng; không mở cùng trang nhiều lần.
- Gộp nhiều câu hỏi/tài khoản vào một lượt.
- Đọc file theo đoạn cần (offset/limit, rg) thay vì đọc hết.
- Prompt giao việc ngắn, cụ thể; yêu cầu báo cáo gọn, chỉ số cần.
- Tin nhắn cho người dùng ngắn gọn, không lặp lại, không giải thích thừa.
- Không đọc lại skill/tài liệu đã đọc trong cùng cuộc trò chuyện.
- Việc lặp lại → viết script/routine một lần, dùng mãi.
- Nếu một cách rẻ hơn cho kết quả tương đương, chọn cách rẻ hơn.
