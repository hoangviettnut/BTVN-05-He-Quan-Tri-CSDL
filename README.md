# BTVN 05 Hệ Quản Trị CSDL
# Sinh viên: Lương Hoàng Việt - K225480106073

# SUBJECT: Trigger on mssql

A. Trình bày lại đầu bài của đồ án PT&TKHT:
1. Mô tả bài toán của đồ án PT&TKHT, 
   đưa ra yêu cầu của bài toán đó
2. Cơ sở dữ liệu của Đồ án PT&TKHT :
   Có database với các bảng dữ liệu cần thiết (3nf),
   Các bảng này đã có PK, FK, CK cần thiết
 
B. Nội dung Bài tập 05:
1. Dựa trên cơ sở là csdl của Đồ án
2. Tìm cách bổ xung thêm 1 (hoặc vài) trường phi chuẩn
   (là trường tính toán đc, nhưng thêm vào thì ok hơn,
    ok hơn theo 1 logic nào đó, vd ok hơn về speed)
   => Nêu rõ logic này!
3. Viết trigger cho 1 bảng nào đó, 
   mà có sử dụng trường phi chuẩn này,
   nhằm đạt được 1 vài mục tiêu nào đó.
   => Nêu rõ các mục tiêu 
4. Nhập dữ liệu có kiểm soát, 
   nhằm để test sự hiệu quả của việc trigger auto run.
5. Kết luận về Trigger đã giúp gì cho đồ án của em.
## DeadLine 23H59:59 NGÀY 23/04/2025
# Bài Làm
## A. Trình bày lại đầu bài của đồ án PT&TKHT
1. Khái quát Đồ án:

a) Tên đồ án: Phân tích thiết kế hệ thống đặt đồ ăn online cho cửa hàng đồ ăn

b) Yêu cầu: Thiết kế hệ thống đặt đồ ăn online cho cửa hàng đồ ăn nhằm hiện đại và đơn giản hóa quá trình mua- bán cho khách hàng, làm việc kiểm soát dịch vụ tại quán dễ dàng và tiện lợi hơn thay vì phương pháp pháp truyền thống.

2. CSDL của Đồ án:

a) Các bảng trong Database: ![Ảnh1](https://github.com/user-attachments/assets/f3f84330-cfd9-41d7-88e5-ff216e6d309b)
b) Liên kết giữa các bảng (Đã chứa các khóa cần thiết):![image](https://github.com/user-attachments/assets/0349ea10-f7ac-48fe-a34c-f4e0c2625b4e)
## B. Nội dung Bài Tập 05:
1. CSDL của đồ án đã nêu ở phần A
2. Thêm trường phi chuẩn TongTien cho bảng DonHang (Code đã chạy Successfully) :![image](https://github.com/user-attachments/assets/749a1408-e46a-4626-8d8f-a1d50d7b9eca)
* Sau khi thêm trường phi chuẩn: ![image](https://github.com/user-attachments/assets/66e52904-9342-44b1-90ed-3108b1a16784)
Kết luận:
a) Lưu tổng giá trị đơn hàng, bao gồm tất cả món ăn được đặt.
a) Dữ liệu này giúp hệ thống dễ dàng tính toán tổng số tiền cần thanh toán.
c) Khi xử lý thanh toán hoặc hóa đơn, có thể truy vấn trực tiếp từ bảng DonHang.

3.  Tạo Trigger trên bảng DonHang
a) Mục tiêu: Tự động kiểm tra nếu tổng tiền của đơn hàng quá thấp hoặc quá cao, giá từ 10.000 VNĐ - 500.000 VNĐ
b) Code Trigger: ![image](https://github.com/user-attachments/assets/176ba716-9935-4322-97b9-f9ccffee524a)

4. Nhập dữ liệu Demo để test:

a) Nhập dữ liệu lần 1:  ![image](https://github.com/user-attachments/assets/835e295a-3406-42b1-98d9-b6d589db1972)
Lỗi này xảy ra vì Trigger KiemTraTongTien đã kích hoạt và phát hiện rằng Tổng tiền đơn hàng không nằm trong khoảng hợp lệ (10,000 - 500,000 VND), dẫn đến RAISERROR và ROLLBACK TRANSACTION, khiến lệnh INSERT bị hủy bỏ.

b) Nhập dữ liệu lần 2: ![image](https://github.com/user-attachments/assets/fb9d5e79-8cc8-4bfe-972b-57d2e0829360)
* Tại MaDH 1 nhập được do TongTien thỏa mãn Trigger

* Tại MaDH 2 không nhập được do TongTien không thỏa mãn Trigger

5. Công dụng của Trigger với đồ án:
a)Tự động cập nhật tổng tiền đơn hàng
b) Hỗ trợ quá trình thanh toán
c) Giảm tải tính toán cho hệ thống
d) Đảm bảo dữ liệu nhất quán






 






 
