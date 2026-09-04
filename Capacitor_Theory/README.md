### 1. Bản chất vật lý: "Hồ chứa nước" của dòng điện

* Tưởng tượng mạch điện của bạn là một hệ thống ống nước. Nguồn điện (Pin LiPo) là trạm bơm chính, còn các IC (như module Wi-Fi hay vi xử lý) là những hộ gia đình tiêu thụ nước.
* Tụ điện chính là những **tháp chứa nước** được đặt rải rác trên đường ống.
* Khi điện áp ổn định, tụ sẽ nạp đầy "nước" (tích trữ năng lượng). Khi nguồn điện bị sụt áp đột ngột, tụ sẽ lập tức xả năng lượng ra để bù đắp, giữ cho áp suất (điện áp) luôn phẳng lặng. Ngược lại, nếu có một xung điện áp tăng vọt, tụ sẽ hút lấy phần dư thừa đó.
* Chân lý cơ bản: Tụ điện **cho phép dòng điện xoay chiều (nhiễu, xung) đi qua** nhưng lại **chặn đứng dòng điện một chiều (DC)**.

### 2. Ứng dụng cốt lõi trên PCB thực chiến

* **Tụ Bypass / Decoupling (Thoát nhiễu):** Đây là ứng dụng sống còn nhất. Khi các cơ cấu chấp hành như động cơ không người lái khởi động hoặc module Wi-Fi phát sóng, chúng sẽ rút dòng cực mạnh theo từng xung ngắn. Tụ Bypass (thường là tụ gốm 0.1uF) đặt sát rạt chân IC sẽ xả điện tức thì để "cứu đói", ngăn IC bị reset do sụt áp nguồn, đồng thời xả nhiễu cao tần thẳng xuống đất (GND).
* **Tụ Bulk (Lọc nguồn chính):** Là các tụ có dung lượng lớn (10uF, 22uF) đặt ở đầu ra của IC hạ áp (Buck). Chúng đóng vai trò như một hồ chứa lớn, làm phẳng các gợn sóng (ripple) từ quá trình băm xung của nguồn.
* **Tụ Boot (Bơm điện tích):** Hoạt động như một nấc thang năng lượng, tích điện áp phụ để kích mở các van bán dẫn (MOSFET) bên trong các IC nguồn.

### 3. Thông số "ẩn" quyết định chất lượng: ESR & ESL

* **ESR (Điện trở nối tiếp tương đương):** Bên trong tụ luôn có một phần tử điện trở ký sinh. Tụ có ESR càng thấp (như tụ gốm SMD) thì xả điện càng nhanh và ít bị nóng khi hoạt động cường độ cao.
* **ESL (Độ tự cảm tương đương):** Ở tần số cực cao, phần thân tụ sẽ sinh ra từ trường cản trở dòng điện. Đó là lý do không thể dùng một tụ hóa to đùng để lọc nhiễu tần số cao, mà phải dùng các tụ gốm MLCC siêu nhỏ (0603, 0402).

### 4. Nguyên tắc "Bất di bất dịch" khi Layout

* **Khoảng cách là vàng:** Tụ Bypass bắt buộc phải được đặt **càng gần chân cấp nguồn của linh kiện càng tốt**. Khoảng cách xa sẽ làm tăng ESL của chính đường đồng dẫn điện.
* **Đường mạch ngắn & to:** Đường mạch từ Tụ đến chân IC và từ Tụ đâm xuống Via Mass (GND) phải ngắn và to để dòng điện xả ra phản ứng nhanh nhất có thể.
