### 1. USB 1.0 & 2.0 (Chuẩn Cổ điển)

Thời kỳ đầu, USB chủ yếu phục vụ giao tiếp dữ liệu cơ bản và cấp nguồn nhẹ (5V/500mA). Các cổng giao tiếp to (Type-A, Type-B) thường có **4 chân**, trong khi các thiết bị di động (Mini, Micro) được bổ sung thêm chân ID thành **5 chân** để hỗ trợ tính năng OTG (On-The-Go).

| Chân (Pin) | Ký hiệu | Chức năng (Dòng 4 Pin) | Chức năng bổ sung (Dòng 5 Pin - Micro/Mini) |
| --- | --- | --- | --- |
| 1 | VBUS | Nguồn +5V | Nguồn +5V |
| 2 | D- | Tín hiệu Data âm | Tín hiệu Data âm |
| 3 | D+ | Tín hiệu Data dương | Tín hiệu Data dương |
| 4 | ID | (Không có) | Nhận diện thiết bị Host/Slave (Dùng cho OTG) |
| 5 | GND | Cực âm (Mass) | Cực âm (Mass) |

---

### 2. USB 3.x (Chuẩn Siêu Tốc - SuperSpeed)

Để tăng tốc độ từ 480Mbps lên 5Gbps/10Gbps, tổ chức USB-IF đã phải nhồi thêm 5 chân tín hiệu mới vào chuẩn cũ, tạo ra các ngàm cắm **9 chân** (Type-A SuperSpeed) và **10 chân** (Micro-B SuperSpeed - loại cổng dẹp dài hay thấy trên ổ cứng di động).

| Chân (Pin) | Ký hiệu | Chức năng chính |
| --- | --- | --- |
| 1 đến 4 | VBUS, D-, D+, GND | Tương thích ngược với USB 2.0 |
| 5, 6 | SSRX-, SSRX+ | Cặp vi sai nhận dữ liệu siêu tốc (SuperSpeed Receive) |
| 7 | GND_DRAIN | Dây chống nhiễu (Mass riêng cho tín hiệu siêu tốc) |
| 8, 9 | SSTX-, SSTX+ | Cặp vi sai truyền dữ liệu siêu tốc (SuperSpeed Transmit) |

---

### 3. USB Type-C (Chuẩn Đa Năng)

Đây là cổng kết nối đối xứng, cắm chiều nào cũng được. Để làm được điều này, bản đầy đủ (Full-featured) của nó có tới **24 chân** (gắn đối xứng trên dưới). Tuy nhiên, trên thị trường sẽ có các biến thể rút gọn (như loại **16 chân** bạn vừa dùng trên bản vẽ sơ đồ) khi không cần tốc độ truyền quá cao.

| Ký hiệu | Chức năng (Bản Full 24-Pin) | Sự khác biệt ở bản 16-Pin (Dùng cho USB 2.0) |
| --- | --- | --- |
| **VBUS & GND** | 4 chân VBUS, 4 chân GND chịu dòng sạc cao (PD). | Vẫn giữ lại để cấp nguồn. |
| **D+ / D-** | 2 cặp chân D+/D- cho USB 2.0. | Vẫn giữ lại 1 cặp D+/D- để truyền dữ liệu. |
| **CC1 / CC2** | Cấu hình kênh, đàm phán điện áp sạc, xác định chiều cắm. | Giữ nguyên (Bắt buộc phải có để hoạt động). |
| **TX1/2, RX1/2** | 4 cặp vi sai truyền/nhận dữ liệu siêu tốc (USB 3.1/3.2, Thunderbolt). | **Bị lược bỏ hoàn toàn** để giảm giá thành linh kiện. |
| **SBU1 / SBU2** | Chân phụ trợ (xuất hình ảnh DisplayPort, âm thanh). | Thường bị lược bỏ hoặc nối đất. |

