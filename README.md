# BÀI 10: ĐÁNH GIÁ ĐA GIẢI PHÁP QUY TRÌNH KHẮC PHỤC SỰ CỐ KỸ THUẬT

## PHẦN 1: SO SÁNH TRADE-OFF

### 1. Bảng so sánh hai phương án

| Tiêu chí | Phương án 1: Hỗ trợ cảm tính | Phương án 2: Troubleshooting 4 chặng |
|---|---|---|
| Thời gian xử lý | Lâu vì phải chờ Senior Dev phản hồi, làm tăng thời gian trạm ngừng hoạt động. | Nhanh hơn vì kỹ thuật viên có thể tự tìm và xử lý lỗi trong 5–10 phút đầu. |
| Chi phí cho Senior Dev | Tốn thời gian xử lý các lỗi cơ bản, ảnh hưởng công việc chính. | Giảm áp lực, chỉ tiếp nhận những lỗi phức tạp. |
| Năng lực kỹ thuật viên | Thụ động, gặp lỗi là hỏi người khác, không biết tự tìm nguyên nhân. | Chủ động tra cứu, phân tích và tự xử lý lỗi thường gặp. |
| Lưu trữ kiến thức | Tin nhắn nhóm chat dễ bị trôi, khó tìm lại cách sửa lỗi cũ. | Lưu cách khắc phục vào Wiki nội bộ để mọi người cùng tham khảo. |

### 2. Kết luận lựa chọn

Em chọn **Phương án 2 – Troubleshooting 4 Chặng Chuẩn hóa**.

Khi công ty mở rộng lên 1.000 trạm sạc, không thể để Senior Dev xử lý từng lỗi nhỏ. Quy trình này giúp kỹ thuật viên tự giải quyết các sự cố cơ bản, giảm thời gian trạm ngừng hoạt động và tiết kiệm chi phí.

Ngoài ra, những lỗi đã xử lý được lưu lại để nhân viên khác có thể tham khảo khi gặp tình huống tương tự.

## PHẦN 2: SƠ ĐỒ LUỒNG QUYẾT ĐỊNH GỠ LỖI

### 3. Quy trình 4 chặng khi Kiosk gặp sự cố

```text
              [BẮT ĐẦU]
                   |
          Kiosk xuất hiện lỗi
                   |
                   v
       [CHẶNG 1: GOOGLE OPERATORS]
       - Bóc tách từ khóa lỗi.
       - Dùng site:, "..." và dấu -.
                   |
                   v
      [CHẶNG 2: STACKOVERFLOW/GITHUB]
       - Đọc lướt trong 30 giây.
       - Kiểm tra dấu tích xanh (✓).
       - Xem Upvote và độ phù hợp.
                   |
                   v
          [CHẶNG 3: HỎI TRỢ LÝ AI]
       - Gửi Context.
       - Gửi Raw Error.
       - Gửi Instruction.
       - Nhận giải thích và cách khắc phục.
                   |
                   v
          [THỬ 2 GIẢI PHÁP PHÙ HỢP]
             Trong vòng 15 phút
                   |
             +-----+-----+
             |           |
          Thành công   Thất bại
             |           |
             v           v
       Kiểm tra Kiosk  [CHẶNG 4]
       hoạt động bình  Lập Bug Report
       thường.         gửi IT Helpdesk.
             |           |
             v           v
         [KẾT THÚC]  Chờ hỗ trợ xử lý
```

### 4. Nội dung Bug Report

Khi đã thử 2 giải pháp nhưng vẫn không khắc phục được sau 15 phút, kỹ thuật viên cần gửi báo cáo gồm:

1. **Môi trường:** Tên trạm sạc, hệ điều hành và phiên bản phần mềm
2. **Mô tả lỗi:** Lỗi xuất hiện khi nào và đã thực hiện thao tác gì
3. **Bằng chứng:** Ảnh chụp màn hình, thông báo lỗi và các cách đã thử
4. **Kết quả:** Kết quả thực tế và kết quả mong muốn
