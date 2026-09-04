### 1. Phân loại Diode trong Thiết kế Phần cứng

| Tên gọi (Loại) | Công dụng chính | Phạm vi sử dụng | Thông số cốt lõi khi chọn |
| --- | --- | --- | --- |
| **Diode Thường (Rectifier)** | Chỉ cho dòng điện đi qua một chiều, chặn triệt để chiều ngược lại. | Chỉnh lưu điện xoay chiều (AC sang DC), chống cắm ngược cực nguồn cấp thông thường. | Dòng điện thuận tối đa ($I_F$), Điện áp ngược chịu đựng ($V_{RRM}$). |
| **Diode Schottky** | Đóng cắt siêu tốc, độ sụt áp thuận rất thấp (chỉ từ 0.15V - 0.45V). | Mạch nguồn xung (Buck/Boost), mạch tần số cao, mạch chống ngược cực pin cần hiệu suất cao. | Sụt áp thuận ($V_F$) thấp, nhưng cần lưu ý dòng rò ngược ($I_R$) thường cao hơn diode thường. |
| **Diode Zener** | Ghim và duy trì một mức điện áp cố định khi bị phân cực ngược. | Tạo điện áp tham chiếu, bảo vệ linh kiện khỏi tình trạng quá áp (overvoltage) nhẹ. | Điện áp Zener ($V_Z$), Công suất tiêu tán ($P_Z$). |
| **TVS Diode (Transient Voltage Suppressor)** | Triệt tiêu xung điện áp cực cao và đột ngột (ESD) trong thời gian tính bằng pico-giây. | Bảo vệ cổng tín hiệu (USB, HDMI), mạch Anten, đầu vào nguồn khỏi tĩnh điện và nhiễu xung. | Điện áp làm việc ($V_{RWM}$), Điện áp đánh thủng ($V_{BR}$). |
| **PIN Diode** | Hoạt động như một điện trở có thể thay đổi được bằng dòng điện một chiều. | Bộ chuyển mạch tín hiệu RF (Anten Wi-Fi 5G, vi sóng), mạch suy hao tín hiệu cao tần. | Trở kháng RF, Tần số hoạt động. |

### 2. Tiêu chí Đánh giá Diode Chất lượng cao

Để hệ thống phần cứng hoạt động bền bỉ trong môi trường khắc nghiệt, một diode chất lượng cao đến từ các hãng lớn (như Vishay, Nexperia, ON Semi) phải đáp ứng các tiêu chuẩn kỹ thuật sau:

* **Dòng rò ngược (Leakage Current - $I_R$) siêu nhỏ:** Khi phân cực ngược, diode lý tưởng không cho dòng điện đi qua. Diode chất lượng sẽ giữ dòng rò ở mức nano-Ampe (nA), giúp mạch không bị suy hao năng lượng và sai lệch tín hiệu.
* **Điện dung ký sinh (Junction Capacitance - $C_j$) cực thấp:** Đặc biệt quan trọng với tín hiệu tốc độ cao (USB 2.0/3.0, Wi-Fi 5G). Điện dung cao sẽ biến diode thành một tụ điện tích điện, làm biến dạng, méo mó và nghẽn tín hiệu truyền tải.
* **Thời gian phục hồi (Recovery Time - $t_{rr}$) cực nhanh:** Giúp diode chuyển trạng thái từ "dẫn" sang "ngắt" gần như ngay lập tức, giảm thiểu suy hao nhiệt trong các mạch nguồn hoạt động ở tần số hàng trăm kHz.

### 3. Hướng dẫn Lựa chọn Thực Chiến

* **Bảo vệ nguồn cấp đầu vào (Chống cắm ngược pin):** Hãy ưu tiên dùng **Diode Schottky** (các mã phổ biến như SS34, SS54) vì độ sụt áp thấp, giúp thiết bị không bị hao pin và cụm nguồn ít sinh nhiệt.
* **Bảo vệ đường truyền tín hiệu (USB, I2C, SPI):** Bắt buộc sử dụng mảng **TVS Diode Array**. Lựa chọn linh kiện phải có điện dung ký sinh $< 1pF$ để đảm bảo tính toàn vẹn của dữ liệu tốc độ cao.
* **Ổn định nguồn cấp dòng thấp:** Sử dụng **Diode Zener** kết hợp cùng một điện trở hạn dòng để ghim áp bảo vệ các IC logic nhạy cảm.
