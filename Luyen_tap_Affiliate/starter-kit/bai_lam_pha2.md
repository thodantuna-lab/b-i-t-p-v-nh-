# BÀI LÀM PHA 2 (ĐỀ LUYỆN TẬP CHỦ ĐỀ CHẠY AFFILIATE)

- **Họ tên:**
- **Lớp:**
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đăng ký gói Affiliate ra JSON

**KET QUA AI**

```text
[
  {
    "ma_goi": "TT",
    "ngay_bat_dau": "2026-12-20",
    "creator_chinh": 2,
    "thuc_tap_sinh": 1,
    "hang_tai_khoan": "thuong",
    "ghi_chu": null
  },
  {
    "ma_goi": "SP",
    "ngay_bat_dau": "2027-01-08",
    "creator_chinh": 3,
    "thuc_tap_sinh": 0,
    "hang_tai_khoan": null,
    "ghi_chu": "Có một bạn đang bó bột chân cần ngồi bàn gần cửa ra vào"
  },
  {
    "ma_goi": "PRO",
    "ngay_bat_dau": null,
    "creator_chinh": 4,
    "thuc_tap_sinh": 0,
    "hang_tai_khoan": "vip",
    "ghi_chu": "cần mượn thêm đèn trợ sáng và phông xanh để quay mẫu"
  }
]
```

**Link trò chuyện:** https://share.gemini.google/J8FRkrutrZ5h

## 4.3. Báo giá gói Affiliate bằng Chain-of-Thought

**KET QUA AI**

```text
**Bước 1: Tiền Creator chính**

* Gói được chọn: TT (Gói TikTok Affiliate) = $1.500.000$ đồng/Creator chính.
* Số lượng Creator chính: $4$ người.
* Tiền Creator chính = $4 \times 1.500.000 = 6.000.000$ đồng.

**Bước 2: Tiền thực tập sinh**

* Thực tập sinh (từ 15 đến dưới 18 tuổi) tính $60\%$ giá Creator chính: $1.500.000 \times 60\% = 900.000$ đồng/người.
* Số lượng thực tập sinh hợp lệ: $2$ người (16 tuổi và 17 tuổi).
* Bé 7 tuổi (dưới 15 tuổi, ngồi khu chờ) được miễn phí: $0$ đồng.
* Tiền thực tập sinh = $(2 \times 900.000) + 0 = 1.800.000$ đồng.

**Bước 3: Tổng tiền gói**

* Tổng tiền gói = Tiền Creator chính + Tiền thực tập sinh
* Tổng tiền gói = $6.000.000 + 1.800.000 = 7.800.000$ đồng.

**Bước 4: Giảm giá team**

* Điều kiện: Team có $4$ Creator chính (thỏa điều kiện từ 4 Creator chính trở lên) nên được giảm $10\%$ trên tổng tiền gói.
* Số tiền được giảm = $7.800.000 \times 10\% = 780.000$ đồng.
* Tiền gói sau giảm = $7.800.000 - 780.000 = 7.020.000$ đồng.

**Bước 5: Phụ thu thuê mic**

* Đơn giá thuê bộ mic thu âm không dây: $250.000$ đồng/bộ (không áp dụng giảm giá).
* Số lượng thuê: $2$ bộ.
* Phụ thu thuê mic = $2 \times 250.000 = 500.000$ đồng.

**Bước 6: Tổng tiền**

* Tổng tiền = Tiền gói sau giảm + Phụ thu thuê mic
* Tổng tiền = $7.020.000 + 500.000 = 7.520.000$ đồng.

[RESULT: 7.520.000 đồng]

```

**Link trò chuyện:** https://share.gemini.google/UbiT1F9Rc4Gl

### b) Kiểm tra kết quả AI

AI đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "sai_phong",
  "so_khach": 3,
  "so_ca_bi_anh_huong": 2,
  "tom_tat": "Khách gói TT bị xếp sai phòng thiếu đèn livestream và cách âm trong 2 ca thực hành đầu."
}
```

**Link trò chuyện:** https://share.gemini.google/73UClYcc2VHX

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin (50%)** | 0/5.0 | • **Câu bị lỗi:** *"Gói TikTok Affiliate bên mình giá chỉ 1.200.000đ/người thôi"*<br>

<br>• **Lý do sai:** Sai mức giá niêm yết chuẩn của trung tâm (giá chuẩn là 1.500.000đ/người).<br>

<br>

<br>• **Câu bị lỗi:** *"Bạn báo huỷ trước 5 ngày thì được hoàn lại đủ 100% tiền nha"*<br>

<br>• **Lý do sai:** Sai chính sách hoàn tiền khi huỷ (thông báo trước 5 ngày không thuộc diện hoàn 100% theo quy định chuẩn). | • **Câu sửa 1:** *"Hiện tại, khóa đào tạo TikTok Affiliate bên mình có mức học phí niêm yết là 1.500.000đ/người."*<br>

<br>

<br>• **Câu sửa 2:** *"Về chính sách hoàn phí, bạn vui lòng tham khảo quy định hoàn tiền theo đúng mốc thời gian trước ngày khai giảng của trung tâm nhé."* |
| **Đầy đủ (30%)** | 1.0/3.0 | • **Câu bị lỗi:** *(Thiếu nội dung kêu gọi hành động ở cuối câu trả lời)*<br>

<br>• **Lý do sai:** Đã đề cập đủ 2 nội dung về giá và chính sách huỷ nhưng hoàn toàn bỏ sót bước mời khách hàng cung cấp ngày đợt thực chiến và số lượng suất muốn đăng ký. | • **Câu sửa:** *"Để mình hỗ trợ giữ suất sớm nhất, bạn cho mình xin thông tin về ngày đợt thực chiến dự kiến và số lượng suất bạn muốn đăng ký nhé!"* |
| **Giọng điệu (20%)** | 0.5/2.0 | • **Câu bị lỗi:** *"Dạ hello bạn nha!"*, *"cứ chốt lẹ kẻo hết slot nè!"*<br>

<br>• **Lý do sai:** Sử dụng văn phong quá suồng sã, thiếu tính chuyên nghiệp trong tư vấn.<br>

<br>

<br>• **Câu bị lỗi:** *"đăng ký xong gắn link là nổ đơn hoa hồng trăm triệu luôn ạ."*<br>

<br>• **Lý do sai:** Vi phạm quy định khi đưa ra cam kết doanh thu/hoa hồng ảo, thổi phồng kết quả. | • **Câu sửa 1:** *"Chào bạn, cảm ơn bạn đã quan tâm đến khóa học bên mình."* / *"Bạn hãy sớm hoàn tất đăng ký để giữ suất tham gia nhé!"*<br>

<br>

<br>• **Câu sửa 2:** *"Sau khi hoàn thành khóa học và áp dụng đúng quy trình gắn link, bạn sẽ nắm vững phương pháp xây dựng kênh và tối ưu tỷ lệ chuyển đổi hoa hồng hiệu quả."* |
| **Tổng điểm** | **1.5/10** |  |  |
```

**Link trò chuyện:** https://share.gemini.google/p07byHSPQIrF
