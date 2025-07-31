# KT Shopping Shipping Calculator

Ứng dụng tính toán chi phí vận chuyển cho hệ thống mua sắm KT Shopping.

## Đối tượng sử dụng

### Người bán (Tất cả đều bán hàng từ Hàn Quốc)
- **Admin**: Quản trị viên của website
- **Seller**: Các người bán đã đăng ký bán tại website

### Người mua
- **Người Việt tại Hàn Quốc**: Khách hàng Việt Nam đang ở Hàn Quốc
- **Người Việt tại Việt Nam**: Khách hàng Việt Nam đang ở Việt Nam  
- **Người Hàn Quốc**: Khách hàng Hàn Quốc
- **Người ở các quốc gia khác**: Khách hàng từ các nước khác

## Quy tắc tính phí vận chuyển

### 1. Vận chuyển nội địa Hàn Quốc
- **Phí vận chuyển**: Do seller quyết định và đăng giá khi đăng sản phẩm

### 2. Vận chuyển quốc tế về Việt Nam
**Tổng phí vận chuyển = Phí vận chuyển nội địa Hàn + Phí vận chuyển quốc tế**

Trong đó:
- **Phí vận chuyển quốc tế**: 10.000 won/1kg
- **Quy tắc làm tròn**: Làm tròn lên 0.5kg
  - Ví dụ: 2.4kg → tính 2.5kg
  - Ví dụ: 2.7kg → tính 3.0kg

### 3. Phân loại theo người bán

#### Sản phẩm do SELLER đăng:
- **Vận chuyển nội địa Hàn**: Seller quyết định và đăng giá khi đăng sản phẩm
- **Vận chuyển về VN**: Tổng phí = Phí vận chuyển nội địa Hàn + Phí vận chuyển quốc tế

#### Sản phẩm do ADMIN đăng:
- **Vận chuyển nội địa Hàn**: 2.500 won
- **Vận chuyển về VN**: 
  - Phí vận chuyển nội địa Hàn = 0 (FREE)
  - Tổng phí = Phí vận chuyển quốc tế (FREE vận chuyển nội địa Hàn và VN)
- **Vận chuyển đến các quốc gia khác**: Tính phí vận chuyển nội địa Hàn bình thường (2.500 won)

## Cấu trúc dự án

```
kt-shopping-shipping/
├── README.md                    # Tài liệu dự án
├── combined_shipping_rates.json # Bảng giá vận chuyển quốc tế
└── index.html                   # Trang web tính toán (sẽ tạo)
```

## Bảng giá vận chuyển quốc tế

File `combined_shipping_rates.json` chứa bảng giá vận chuyển quốc tế theo trọng lượng cho các quốc gia:
- Hong Kong
- Taiwan  
- Singapore
- United States
- Japan

## Tính năng dự kiến

- [ ] Giao diện web tính toán phí vận chuyển
- [ ] Tính toán tự động theo quy tắc đã định
- [ ] Hỗ trợ tính phí cho cả seller và admin
- [ ] Hiển thị chi tiết từng khoản phí
- [ ] Responsive design cho mobile