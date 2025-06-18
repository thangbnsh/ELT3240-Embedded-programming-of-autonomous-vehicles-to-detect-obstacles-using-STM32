Hệ thống phát hiện và đo khoảng cách tới vật cản
Giới thiệu
Mục tiêu của dự án này là phát triển một hệ thống nhúng có khả năng phát hiện vật cản và đo khoảng cách đến vật thể, ứng dụng trong các xe tự hành. Hệ thống được thiết kế với vi điều khiển STM32 Nucleo-F401RE, sử dụng các cảm biến siêu âm, hồng ngoại, hoặc radar để đo khoảng cách và phát hiện vật cản. Dự án giúp sinh viên vận dụng các kiến thức về lập trình nhúng, vi xử lý ARM-Cortex-M và các thiết bị ngoại vi.

Yêu cầu hệ thống
Chức năng:

Phát hiện vật cản và đo khoảng cách.

Hiển thị kết quả trên màn hình LCD.

Cung cấp các tín hiệu LED để thông báo trạng thái hệ thống và vật cản.

CPU:

Vi điều khiển ARM-Cortex-M (STM32 Nucleo-F401RE hoặc bo mạch tương đương).

Đầu vào:

Cảm biến siêu âm, hồng ngoại hoặc radar để phát hiện và đo khoảng cách đến vật cản.

SW1 để chuyển đổi hệ thống giữa trạng thái hoạt động và trạng thái dừng.

SW2 để xóa (reset) trạng thái hệ thống về trạng thái ban đầu.

Đầu ra:

LED xanh: Nhấp nháy 1Hz khi hệ thống hoạt động, tắt khi dừng hoạt động.

LED đỏ: Nhấp nháy từ 2Hz đến 10Hz tùy vào khoảng cách vật cản. Tắt khi không có vật cản.

LCD:

Hiển thị trạng thái hệ thống (0: bình thường, 1: hoạt động).

Hiển thị trạng thái vật cản (0: không có, 1: có vật cản).

Hiển thị khoảng cách đến vật cản khi phát hiện vật cản.

Tính năng bổ sung:

Khuyến khích lắp ráp một xe tự hành tích hợp hệ thống này.

Cài đặt
Cài đặt phần mềm:

Cài đặt STM32CubeIDE (hoặc môi trường phát triển tương đương) để lập trình cho STM32.

Cài đặt các thư viện cần thiết cho LCD, cảm biến siêu âm, cảm biến hồng ngoại hoặc radar.

Kết nối phần cứng:

Kết nối cảm biến siêu âm, hồng ngoại, hoặc radar với các chân GPIO của STM32.

Kết nối LED xanh, LED đỏ và màn hình LCD với các chân đầu ra.

Kết nối công tắc SW1 và SW2 với các chân đầu vào.

Biên dịch và nạp chương trình:

Mở dự án trong STM32CubeIDE.

Biên dịch chương trình và nạp vào vi điều khiển.

Mô tả chức năng
Phát hiện vật cản:

Hệ thống sử dụng cảm biến siêu âm, hồng ngoại, hoặc radar để đo khoảng cách đến vật cản.

Tùy vào khoảng cách đo được, hệ thống sẽ điều chỉnh tần số nhấp nháy của LED đỏ.

Chuyển trạng thái hệ thống:

SW1 cho phép người dùng chuyển đổi giữa trạng thái hoạt động và dừng.

Khi hệ thống dừng hoạt động, các cảm biến không được kích hoạt và màn hình LCD sẽ hiển thị trạng thái dừng.

Khi chuyển sang trạng thái hoạt động, hệ thống tiếp tục giám sát cảm biến và hiển thị kết quả.

Xóa (reset) hệ thống:

SW2 giúp người dùng reset hệ thống về trạng thái ban đầu.

Hiển thị trên LCD:

Màn hình LCD hiển thị trạng thái của hệ thống (bình thường hoặc hoạt động).

LCD cũng sẽ hiển thị thông tin về vật cản (có hay không có) và khoảng cách đến vật cản.

Các tệp dự án
main.c: Tệp mã nguồn chính của hệ thống.

lcd.c, lcd.h: Thư viện điều khiển màn hình LCD.

sensor.c, sensor.h: Thư viện cho cảm biến siêu âm, hồng ngoại hoặc radar.

led.c, led.h: Thư viện điều khiển các LED hiển thị trạng thái.

button.c, button.h: Thư viện điều khiển các nút nhấn (SW1, SW2).

config.h: Cấu hình chung của dự án.

Hướng dẫn sử dụng
Khởi động hệ thống:

Kết nối nguồn điện cho STM32 Nucleo-F401RE và các cảm biến.

Khi hệ thống hoạt động, LED xanh sẽ nhấp nháy 1Hz và LCD sẽ hiển thị trạng thái hệ thống là "Hoạt động".

Chuyển trạng thái hoạt động:

Nhấn SW1 để chuyển sang trạng thái hoạt động. Khi đó, hệ thống sẽ bắt đầu đo khoảng cách và phát hiện vật cản.

LED đỏ sẽ nhấp nháy với tần số tương ứng với khoảng cách đến vật cản.

Reset hệ thống:

Nhấn SW2 để reset hệ thống về trạng thái ban đầu.

Lưu ý
Khi hệ thống phát hiện vật cản, LED đỏ sẽ nhấp nháy với tần số thay đổi tùy thuộc vào khoảng cách đo được.

Cảm biến có thể cần được hiệu chỉnh hoặc cấu hình để đạt được độ chính xác tối ưu trong các môi trường khác nhau.

Tích hợp với xe tự hành (Tùy chọn)
Nếu bạn muốn tích hợp hệ thống vào một xe tự hành, hãy đảm bảo rằng các cảm biến được gắn cố định và được cấp nguồn đúng cách. Hệ thống có thể được sử dụng để hỗ trợ xe tự hành trong việc tránh vật cản và điều hướng.
