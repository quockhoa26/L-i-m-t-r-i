# Layout Refactoring Report - CreativeChronicle

1. **Hạn chế của `position: absolute`:**
   Sử dụng `position: absolute` rút phần tử ra khỏi luồng hiển thị tự nhiên (Document Flow) của DOM. Điều này khiến phần tử cha mất chiều cao thực tế (height: 0), dẫn đến các đoạn văn bản bên dưới chèn đè lên hình ảnh khi thay đổi kích thước màn hình responsive.

2. **Giải pháp cứu cánh từ CSS Grid:**
   CSS Grid quản lý không gian 2 chiều (hàng và cột) một cách linh hoạt. Nó tự động tính toán kích thước các ô ảnh (`grid-row: span 2`) và duy trì chiều cao tự nhiên của phần tử cha, đảm bảo nội dung phía dưới luôn được đẩy xuống chính xác mà không cần cố định chiều cao bằng pixel.