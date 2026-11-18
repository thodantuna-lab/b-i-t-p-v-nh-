## 4.2. Trích xuất tin nhắn đặt vé ra JSON

**KET QUA AI**

```text
[
  {
    "ma_goi": "SVT",
    "ngay_su_kien": "2026-12-20",
    "nguoi_lon": 2,
    "tre_em": 1,
    "loai_ve": "thuong",
    "ghi_chu": null
  },
  {
    "ma_goi": "FZ",
    "ngay_su_kien": "2027-01-05",
    "nguoi_lon": 3,
    "tre_em": 0,
    "loai_ve": null,
    "ghi_chu": "cần hỗ trợ xe lăn"
  },
  {
    "ma_goi": "VIP",
    "ngay_su_kien": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "loai_ve": "vip",
    "ghi_chu": "một người khiếm thị cần hỗ trợ tìm chỗ"
  }
]
```

**Link trò chuyện:**https://share.gemini.google/YwS5rMW2hEx1

## 4.3. Báo giá vé bằng Chain-of-Thought

**KET QUA AI**

```text
```python
adult_price = 1200000
num_adults = 5
adult_total = num_adults * adult_price

child_rate = 0.7
num_children = 2 # 8 and 10 years old; 3 years old is free
child_total = num_children * adult_price * child_rate

ticket_total = adult_total + child_total
discount = ticket_total * 0.05 # 5 adults >= 5
ticket_after_discount = ticket_total - discount

surcharge = 1 * 300000
grand_total = ticket_after_discount + surcharge

print(f"{adult_total=}, {child_total=}, {ticket_total=}, {discount=}, {ticket_after_discount=}, {surcharge=}, {grand_total=}")


```

```text
adult_total=6000000, child_total=1680000.0, ticket_total=7680000.0, discount=384000.0, ticket_after_discount=7296000.0, surcharge=300000, grand_total=7596000.0


```

Dưới đây là bảng tính chi tiết từng bước cho yêu cầu báo giá gói **SVT – Sân Vận Động** (đơn giá gốc: **1.200.000 đồng/người lớn**):

1. **Tiền người lớn:**
* Nhóm có 5 người lớn, áp dụng 100% đơn giá gói SVT.
* Phép tính: `5 × 1.200.000 = 6.000.000` đồng.


2. **Tiền trẻ em:**
* Nhóm có 2 trẻ em trong độ tuổi từ 5 đến 11 tuổi (8 tuổi và 10 tuổi) được tính 70% giá người lớn; 1 bé 3 tuổi (dưới 5 tuổi) được miễn phí (`0` đồng).
* Phép tính: `(2 × 1.200.000 × 70%) + (1 × 0) = 2 × 840.000 + 0 = 1.680.000` đồng.


3. **Tiền vé (trước giảm giá):**
* Tổng tiền vé của người lớn và trẻ em.
* Phép tính: `6.000.000 + 1.680.000 = 7.680.000` đồng.


4. **Giảm giá nhóm:**
* Nhóm có đủ 5 người lớn (thỏa điều kiện từ 5 người lớn trở lên) nên được giảm 5% trên tổng tiền vé.
* Phép tính mức giảm: `7.680.000 × 5% = 384.000` đồng.
* Tiền vé sau giảm: `7.680.000 - 384.000 = 7.296.000` đồng.


5. **Phụ thu:**
* Có 1 người lớn chọn khu ghế ưu tiên với mức phụ thu 300.000 đồng/người (không áp dụng giảm giá).
* Phép tính: `1 × 300.000 = 300.000` đồng.


6. **Tổng tiền:**
* Cộng tiền vé sau giảm và khoản phụ thu.
* Phép tính: `7.296.000 + 300.000 = 7.596.000` đồng.



[RESULT: 7.596.000 đồng]
```

**Link trò chuyện:**https://share.gemini.google/reZ6R13AxmoD

### b) Kiểm tra kết quả AI


## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "sai_khu_vuc",
  "so_khach": 2,
  "so_hiep_bi_anh_huong": 2,
  "tom_tat": "Khách mua gói có mái che nhưng bị xếp sang khu không mái trong 2 hiệp đầu gặp trời mưa."
}
```

**Link trò chuyện:**https://share.gemini.google/dkTF0r1MaFe0
