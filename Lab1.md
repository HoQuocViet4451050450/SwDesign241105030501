# Hồ Quốc Việt  
## Lab1: PHÂN TÍCH KIẾN TRÚC, CƠ CHẾ, CA SỬ DỤNG

---

### #1. Phân tích Kiến trúc  
- **Hệ thống Payroll System** là một hệ thống phân tán.
- Tương tác với **Cơ sở dữ liệu (CSDL) cũ** để quản lý dự án.
- Hệ thống được chia thành **2 phía chính**:
  - **Phía người dùng**: Cung cấp giao diện cho nhân viên.
  - **Phía máy chủ**: Xử lý backend cho các nghiệp vụ hệ thống.
- Bao gồm **3 mô-đun chính**:
  - **Quản lý Thẻ Chấm Công**: Nhập giờ làm việc.
  - **Xử lý Bảng Lương**: Tính toán và quản lý bảng lương.
  - **Quản lý Nhân Viên**: Quản lý thông tin và hồ sơ nhân viên.

### #2. Cơ chế Phân tích  
#### Xác thực và Phân quyền  
- Nhân viên chỉ có quyền **xem và chỉnh sửa** thẻ chấm công, đơn hàng và tùy chọn thanh toán của mình.
- **Quản trị viên Bảng lương** có quyền mở rộng để quản lý dữ liệu nhân viên.
- **Đề xuất cơ chế**: Áp dụng kiểm soát truy cập dựa trên vai trò (*Role-Based Access Control - RBAC*) để bảo mật quyền truy cập.

#### Xác thực Thẻ Chấm Công  
- Thẻ chấm công cần xác thực cho **nhân viên tính theo giờ**, đảm bảo **tính toán giờ làm thêm** cho các giờ vượt quá 8 giờ mỗi ngày.
- **Đề xuất cơ chế**: Định nghĩa quy tắc tự động tính giờ làm thêm trong mô-đun quản lý thẻ chấm công.

#### Tích hợp Cơ sở Dữ liệu Quản lý Dự án  
- Dữ liệu từ **CSDL quản lý dự án DB2 cũ** chỉ được phép **đọc** mà không được chỉnh sửa.
- **Đề xuất cơ chế**: Sử dụng **API chỉ đọc** hoặc tạo *chế độ xem (view)* trong cơ sở dữ liệu để truy cập dữ liệu dự án một cách bảo mật.

#### Lịch trình Bảng Lương Tự động  
- Quy trình xử lý bảng lương phải tự động chạy vào các ngày cố định (thứ Sáu hàng tuần và ngày làm việc cuối cùng của tháng).
- **Đề xuất cơ chế**: Thiết lập *tác vụ tự động (scheduled task)* hoặc *cron job* để kích hoạt quy trình bảng lương.

### #3. Phân tích Ca Sử dụng: Payment  
**Tác nhân**:
- **Nhân viên**: Có thể chọn phương thức thanh toán, xem lịch sử thanh toán, và tra cứu tổng lương.
- **Quản trị viên Bảng lương**: Quản lý dữ liệu nhân viên, bao gồm phân loại thanh toán.

**Các bước**:
1. **Nhân viên** chọn phương thức thanh toán (thư tín, chuyển khoản, hoặc nhận tại văn phòng).
2. **Hệ thống** lưu trữ thông tin thanh toán một cách an toàn và đảm bảo tiền lương được phát đúng phương thức.
3. **Tính toán bảng lương**:
   - **Nhân viên theo giờ**: Tính tiền lương và giờ làm thêm dựa trên thẻ chấm công.
   - **Nhân viên hưởng lương cố định**: Thanh toán mức lương cố định hàng tháng.
   - **Nhân viên hưởng hoa hồng**: Thêm hoa hồng bán hàng vào lương cơ bản (10%, 15%, 25%, hoặc 35%).

### #4. Phân tích Ca Sử dụng: Maintain Timecard  
**Tác nhân**:
- **Nhân viên**: Gửi thẻ chấm công với số giờ làm và mã chi phí.
- **Quản trị viên Bảng lương**: Xem các mục thẻ chấm công khi cần.

**Các bước**:
1. **Gửi thẻ chấm công**:
   - Nhân viên nhập ngày, số giờ làm và mã số chi phí.
   - Hệ thống xác minh mã chi phí qua cơ sở dữ liệu quản lý dự án.
2. **Xác thực thẻ chấm công**:
   - Hệ thống kiểm tra giờ làm thêm và tính toán lương tương ứng.
   - Lưu trữ thẻ chấm công an toàn trong hệ thống.
3. **Truy cập và chỉnh sửa**:
   - Nhân viên có thể xem và chỉnh sửa thẻ chấm công trước ngày xử lý.
   - Sau khi xử lý, việc chỉnh sửa bị khóa để kiểm tra.

### #5. Hợp nhất Kết quả Phân tích  
- **Vai trò người dùng và bảo mật**: Sử dụng RBAC để đảm bảo quyền truy cập.
- **Lập lịch tự động**: Chạy bảng lương định kỳ không cần can thiệp.
- **Tích hợp dữ liệu**: Đọc dữ liệu từ CSDL DB2 của hệ thống quản lý dự án.
- **Giao diện người dùng**: Tương tác dễ dàng qua giao diện Windows.
- **Thiết kế module**: Phân chia ứng dụng thành các module độc lập cho dễ bảo trì.

---
