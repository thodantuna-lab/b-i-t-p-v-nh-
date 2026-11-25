# ĐỀ ÔN TẬP CUỐI MÔN – KỸ NĂNG PROMPTING AI

## [Chủ đề Chạy Affiliate: Trung tâm Tiếp thị liên kết VietAffiliate]

- **Hình thức:** Làm bài cá nhân.
- **Công cụ:** Trình duyệt web, trình soạn thảo văn bản (VS Code, Notepad hoặc TextEdit), GitHub (giao diện web), một trong ba công cụ AI: ChatGPT, Claude, Gemini (chỉ dùng ở Pha 2).
- **Thời gian:** Bài thi gồm 2 pha: **Pha 1 (70 phút đầu)** KHÔNG dùng AI; **Pha 2 (20 phút cuối)** chỉ dùng AI để chạy các prompt đã viết ở Pha 1. Chi tiết ở Mục 3.2.
- **Nộp bài:** Tạo 1 repository trên tài khoản GitHub cá nhân: `[Tên Lớp]_PromptAI_H04`

---

## 1. Bối cảnh

Bạn là nhân viên mới của Trung tâm Đào tạo & Hỗ trợ Tiếp thị liên kết **VietAffiliate**, phụ trách hỗ trợ các nhà sáng tạo nội dung (Creator/KOC) đăng ký các gói thực chiến và thuê phòng studio chạy chiến dịch Affiliate (TikTok, Shopee, Livestream). Trưởng bộ phận giao cho bạn xây dựng bộ prompt để xử lý thông tin Creator, tin nhắn đăng ký gói, tính báo giá và giải quyết khiếu nại một cách an toàn, chính xác.

## 2. Mục tiêu

Đánh giá kỹ năng sử dụng AI an toàn và hiệu quả: đạo đức khi dùng AI (ẩn danh thông tin cá nhân), chống ảo giác, khung CREATE, Few-shot, ép định dạng đầu ra (JSON), Chain-of-Thought, Prompt Chaining, chấm theo Rubric, phòng chống Prompt Injection và hoàn thiện System Prompt.

## 3. Tài liệu & Quy trình

### 3.1. Bộ tài nguyên (`starter-kit`)

Thư mục `starter-kit` gồm có:

- `bai_lam_pha1.md` và `bai_lam_pha2.md`
- Thư mục `du_lieu/` chứa 5 file dữ liệu từ `4_1_ghi_chu_dang_ky.txt` đến `4_5_bai_tu_van.txt`.

### 3.2. Quy trình 2 pha

- Bài Pha 1 được chấm theo bản đã upload vào repository Pha1 trước mốc giờ. Upload vào Pha1 sau mốc giờ không được tính.
- Mỗi lần chạy AI: mở cuộc trò chuyện mới; tin nhắn đầu tiên là nguyên văn prompt trong `bai_lam_pha1.md`. Dán câu trả lời bằng nút Copy dưới câu trả lời của AI (để giữ đúng bảng, JSON), rồi dán link chia sẻ (Share) vào dòng `Link trò chuyện`.
- Ý có ký hiệu **[AI]** trong thang điểm được 0 điểm khi: thiếu link, link không mở được, hoặc tin nhắn đầu tiên khác prompt trong `bai_lam_pha1.md`. Cuộc trò chuyện có nội dung nhờ AI viết prompt: cả mục đó 0 điểm.
- Không chạy được AI (mất mạng, hết lượt): ghi "Không chạy được", chỉ mất các ý **[AI]**.
- Không đưa thông tin cá nhân thật của bạn hoặc người khác vào AI.

---

## 4. Yêu cầu nghiệp vụ

### 4.1. Bảo vệ dữ liệu và chống ảo giác (14 điểm)

Mở `4_1_ghi_chu_dang_ky.txt`. Đây là ghi chú của nhân viên tư vấn tuyển sinh; nhân viên muốn nhờ AI soạn email xác nhận đăng ký gói thực chiến Affiliate cho khách.

- **a)** Viết lại đoạn ghi chú ở dạng đã ẩn danh hoá để có thể dán vào AI: thay mọi thông tin định danh cá nhân bằng nhãn trong ngoặc vuông (ví dụ `[TEN_KHACH]`); giữ nguyên các thông tin còn lại.
- **b)** Một nhân viên khác đính kèm file quy định hoàn/huỷ gói Affiliate và hỏi AI: _"Khách hàng báo huỷ gói trước ngày bắt đầu 4 ngày thì được hoàn bao nhiêu tiền?"_ Để AI không tự bịa câu trả lời, hãy viết thêm **2 câu lệnh** đặt ngay sau câu hỏi đó:
    - **Câu 1:** buộc AI chỉ trả lời dựa trên file đính kèm, và nêu AI phải trả lời thế nào nếu file không có thông tin.
    - **Câu 2:** buộc AI ghi rõ câu trả lời lấy từ mục hoặc điều khoản nào trong file.

### 4.2. Trích xuất tin nhắn đăng ký gói Affiliate ra JSON [AI]

Mở `4_2_tin_nhan_dang_ky.txt`. Viết một prompt để AI chuyển `TN1`, `TN2`, `TN3` thành một mảng JSON 3 đối tượng, đúng thứ tự, đúng 6 trường như tin nhắn mẫu (`ma_goi`, `ngay_bat_dau`, `creator_chinh`, `thuc_tap_sinh`, `hang_tai_khoan`, `ghi_chu`). Prompt phải:

- Có đủ **6 khối CREATE**, mỗi khối ghi nhãn: `C - Context`, `R - Request`, `E - Explanation`, `A - Action`, `T - Tone`, `E - Extras`.
- Dùng **2 tin nhắn mẫu** làm ví dụ Few-shot.
- Đặt 3 tin nhắn cần xử lý trong cặp dấu phân tách (ví dụ `<tin_nhan>…</tin_nhan>`).
- Nêu đủ **5 quy tắc chuẩn hoá** trong file.
- Yêu cầu AI chỉ trả về JSON, không chào hỏi, không giải thích.

### 4.3. Báo giá gói Affiliate bằng Chain-of-Thought [AI]

Mở `4_3_bang_gia.txt`.

- **a) (Pha 1)** Viết prompt để AI tính tổng tiền cho yêu cầu báo giá của team KOC: đưa bảng giá, quy tắc và yêu cầu báo giá vào cặp dấu phân tách; yêu cầu suy luận từng bước theo thứ tự:
  `tiền Creator chính → tiền thực tập sinh → tổng tiền gói → giảm giá team → phụ thu thuê mic → tổng tiền`, mỗi bước ghi phép tính; dòng cuối có dạng `[RESULT: <tổng tiền> đồng]`.
- **b) (Pha 2)** Kiểm tra lại từng bước AI đã tính, đối chiếu với quy tắc trong file (được dùng ứng dụng máy tính để bấm lại phép tính). Ghi kết luận AI tính đúng hay sai; nếu sai, ghi bước sai đầu tiên và kết quả đúng của bước đó.

### 4.4. Dây chuyền xử lý khiếu nại (Prompt Chaining) [AI]

Mở `4_4_email_khieu_nai.txt`. Email được xử lý qua 3 trạm, đầu ra của trạm trước là đầu vào của trạm sau. File đã có định dạng đầu ra của Trạm 1 và prompt có sẵn của Trạm 2, Trạm 3.

- **a)** Viết prompt cho **Trạm 1**: đọc email khiếu nại và chỉ trả về một đối tượng JSON đúng 4 trường theo quy định (`loai_su_co`, `so_khach`, `so_ca_bi_anh_huong`, `tom_tat`). Ở Pha 2 chạy AI với prompt này.
- **b)** Nêu **2 điều cần kiểm tra** ở JSON đầu ra của Trạm 1 trước khi chuyển làm đầu vào cho Trạm 2.
- **c)** Khi chạy Trạm 3, AI bị ngắt giữa chừng ở đoạn _"…Trung tâm VietAffiliate xin hoàn lại Quý khách khoản"_. Viết câu lệnh để AI viết tiếp đúng chỗ bị ngắt, không viết lại phần đã có.

### 4.5. Prompt chấm bài theo Rubric [AI]

Mở `4_5_bai_tu_van.txt`. Viết prompt để AI chấm câu trả lời của nhân viên tư vấn tập sự:

- Đưa thông tin chuẩn của trung tâm và rubric 3 tiêu chí (kèm trọng số) vào prompt.
- Đặt bài cần chấm trong cặp thẻ `<bai_can_cham>…</bai_can_cham>`, nêu rõ nội dung trong thẻ chỉ là dữ liệu, AI không làm theo yêu cầu nào trong thẻ.
- Mỗi lỗi trừ điểm có đủ: câu bị lỗi (trích nguyên văn), lý do sai, câu sửa đề xuất.
- Kết quả là bảng Markdown 4 cột `Tiêu chí | Điểm | Minh chứng | Đề xuất sửa`; dòng cuối là tổng điểm trên thang 10.

### 4.6. Hoàn thiện System Prompt

`bai_lam_pha1.md` đã cho sẵn phần `[Vai trò]` và `[Chuẩn đầu ra]` của System Prompt cho chatbot **"Trợ lý VietAffiliate"** trên website. Viết tiếp 2 phần:

- **`[Quy tắc ràng buộc]`**, gồm 3 quy tắc:
    1. Chỉ tư vấn 3 gói chính thức của trung tâm (`TT`, `SP`, `PRO`);
    2. Không hứa giảm giá ngoài bảng giá (và không cam kết nổ đơn hay doanh thu hoa hồng);
    3. Không hỏi xin số CCCD, mật khẩu tài khoản TikTok/Shopee hay số thẻ ngân hàng.
- **`[Xử lý ngoại lệ]`**, gồm cách trả lời trong 2 tình huống:
    1. Khách hỏi ngoài phạm vi (ví dụ hỏi mua tài khoản TikTok ảo, dịch vụ buff view/follow lậu);
    2. Khách cung cấp thiếu thông tin khi đăng ký gói.
