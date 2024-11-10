# Hồ Quốc Việt  
## Lab2: Tiến Hành Phân Tích Các Ca Sử Dụng Còn Lại

---

### #1. Phân tích Ca Sử Dụng Create Employee
**Tác nhân**:
- **Quản trị viên Bảng lương**: Quản trị viên bảng lương có thể thêm nhân viên mới, thiết lập phân loại thanh toán của họ và ghi lại các chi tiết khác. Trường hợp sử dụng này cho phép thêm nhân viên mới vào hệ thống, đảm bảo họ có thể nhận được thanh toán theo phương thức và loại thanh toán đã chỉ định (theo giờ, theo lương hoặc theo hoa hồng).
  
**Các bước**:
1. Quản trị viên bảng lương chọn tùy chọn thêm nhân viên mới.
2. Hệ thống hiển thị biểu mẫu để nhập thông tin chi tiết về nhân viên như tên, địa chỉ, loại thanh toán, tỷ lệ hoa hồng (nếu có) và phương thức thanh toán.
3. Quản trị viên bảng lương nhập thông tin nhân viên và gửi biểu mẫu.
4. Hệ thống xác thực thông tin đầu vào và lưu dữ liệu nhân viên mới một cách an toàn.
5. Nhân viên hiện đang hoạt động trong hệ thống và quá trình xử lý bảng lương có thể tiến hành dựa trên phân loại của họ.

### #2. Phân tích Ca Sử Dụng Maintain Purchase Order
**Tác nhân**:
- **Nhân viên được hưởng hoa hồng**:Trường hợp sử dụng này cho phép nhân viên được hưởng hoa hồng ghi lại các giao dịch bán hàng, cần thiết để tính hoa hồng của họ. Mỗi lần bán hàng được ghi lại sẽ góp phần vào việc tính hoa hồng của nhân viên theo tỷ lệ đã chỉ định.

**Các bước**:
Các bước:
1. Nhân viên chọn tùy chọn ghi lại một đơn đặt hàng mua mới.
2. Hệ thống hiển thị biểu mẫu cho phép nhập thông tin đơn hàng, bao gồm ngày và số tiền bán hàng.
3. Nhân viên điền chi tiết và gửi biểu mẫu.
4. Hệ thống xác thực dữ liệu đầu vào, đảm bảo rằng các trường bắt buộc đã được điền đầy đủ và hợp lệ.
5. Đơn đặt hàng mua được lưu vào hệ thống, sẵn sàng cho quá trình tính hoa hồng của nhân viên.

### #3. Phân tích Ca Sử Dụng Generate Paycheck
**Tác nhân**:
- **Hệ thống**:Hệ thống sẽ tự động tạo phiếu lương dựa trên các thông tin liên quan về thời gian làm việc, số tiền bán hàng (đối với nhân viên được hưởng hoa hồng) và phương thức thanh toán đã chỉ định của nhân viên.

**Các bước**:
Các bước:
1. Vào ngày chi trả lương, hệ thống tự động kích hoạt quy trình tạo phiếu lương cho các nhân viên dựa trên phân loại thanh toán của họ (hàng giờ, lương cố định, hoặc lương cố định có hoa hồng).
2. Hệ thống tổng hợp thông tin từ thẻ chấm công, đơn đặt hàng, và các dữ liệu liên quan để tính toán số tiền chính xác mà mỗi nhân viên được trả.
Đối với nhân viên theo giờ: Tính toán dựa trên giờ làm việc và tỷ lệ lương theo giờ, bao gồm tính toán giờ làm thêm.
Đối với nhân viên lương cố định: Số tiền cố định được xác định trước.
Đối với nhân viên có hoa hồng: Tính tổng hoa hồng dựa trên số tiền bán hàng ghi trong các đơn hàng.
3. Hệ thống tạo ra phiếu lương và xác định phương thức thanh toán theo lựa chọn của nhân viên (chuyển khoản trực tiếp, gửi qua bưu điện, hoặc nhận tại văn phòng).
4. Phiếu lương và các bản ghi cần thiết được lưu vào hệ thống để phục vụ các mục đích kiểm toán và báo cáo.
  
### #4. Phân tích Ca Sử Dụng Generate Report
**Tác nhân**:
- **Nhân viên và Quản trị viên Bảng lương**:Nhân viên có thể xem các báo cáo về số giờ đã làm, tổng thu nhập đến thời điểm hiện tại, số giờ đã báo cáo theo mã số dự án, và thông tin về kỳ nghỉ còn lại. Quản trị viên có thể chạy các báo cáo hành chính để giám sát toàn bộ hoạt động bảng lương.
**Các bước**:
Các bước:
1. Nhân viên hoặc Quản trị viên chọn tùy chọn tạo báo cáo.
2. Hệ thống hiển thị danh sách các loại báo cáo có sẵn như báo cáo thời gian làm việc, báo cáo lương, báo cáo hoa hồng, hoặc báo cáo giờ làm theo mã số dự án.
3. Người dùng chọn loại báo cáo mong muốn và nhập các thông số như khoảng thời gian hoặc mã số dự án (nếu cần thiết).
4. Hệ thống truy xuất và tổng hợp dữ liệu liên quan để tạo báo cáo, sau đó hiển thị hoặc xuất ra dưới dạng PDF, CSV, hoặc định dạng phù hợp khác.
5. Báo cáo có thể được lưu trữ hoặc gửi đi theo yêu cầu của người dùng.

### #5. Phân tích Ca Sử Dụng Change Payment Method
**Tác nhân**:
- **Nhân viên**:Nhân viên có thể chọn thay đổi phương thức nhận lương của họ cho phù hợp với sở thích hoặc tình hình cá nhân hiện tại.
**Các bước**:
Các bước:
1. Nhân viên truy cập vào tùy chọn thay đổi phương thức thanh toán trong hệ thống.
2. Hệ thống hiển thị các phương thức thanh toán có sẵn: chuyển khoản trực tiếp, gửi qua bưu điện, hoặc nhận tại văn phòng.
3. Nhân viên chọn phương thức mong muốn và cung cấp các chi tiết liên quan (ví dụ: thông tin tài khoản ngân hàng nếu chọn chuyển khoản).
4. Hệ thống xác thực thông tin đầu vào và cập nhật hồ sơ thanh toán của nhân viên.
5. Hệ thống xác nhận rằng phương thức thanh toán đã được cập nhật thành công.

### #6. Phân tích Ca Sử Dụng Modify Employee Information
**Tác nhân**:
- **Quản trị viên Bảng lương**:Quản trị viên có thể cập nhật thông tin cá nhân của nhân viên, bao gồm tên, địa chỉ, và phân loại thanh toán.
**Các bước**:
Các bước:
1. Quản trị viên chọn tùy chọn chỉnh sửa thông tin nhân viên.
2. Hệ thống hiển thị danh sách nhân viên hoặc cung cấp tùy chọn tìm kiếm nhân viên cần chỉnh sửa.
3. Quản trị viên chọn nhân viên và cập nhật thông tin cần thiết như địa chỉ, tên, hoặc phân loại thanh toán (hàng giờ, lương cố định, hoặc lương cố định có hoa hồng).
4. Hệ thống xác thực và lưu các thay đổi.
5. Quản trị viên nhận thông báo về việc cập nhật thành công hồ sơ nhân viên.
