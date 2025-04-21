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
a) Tên đồ án: Phân tích thiết kế hệ thống đặt đồ ăn online cho quán cơm "Sinh viên TNUT"
b) Yêu cầu: Thiết kế hệ thống đặt đồ ăn online cho quán cơm "Sinh viên TNUT" nhằm hiện đại và đơn giản hóa quá trình mua- bán cho khách hàng, làm việc kiểm soát dịch vụ tại quán dễ dàng và tiện lợi hơn thay vì phương pháp pháp truyền thống.
2. CSDL của Đồ án:
a) Các bảng trong Database: ![Database and Tables](https://github.com/user-attachments/assets/59efd06b-e811-408e-9a78-23c02b7e5e12)
b) Liên kết giữa các bảng (Đã chứa các khóa cần thiết): ![image](https://github.com/user-attachments/assets/fd781342-f221-42a3-9d89-0eb208e6b473)
## B. Nội dung Bài Tập 05:
1. CSDL của đồ án đã nêu ở phần A
2. Thêm các trường phi chuẩn (Code đã chạy Successfully) :
a) Thêm cột So_Mon vào bảng Don_Hang nếu chưa tồn tại: ![image](https://github.com/user-attachments/assets/71efe1cf-d282-4cc7-a9ea-e6fd59c423b6)
b) Thêm cột Tong_Tien vào bảng Don_Hang nếu chưa tồn tại: ![image](https://github.com/user-attachments/assets/eabfeeb4-17cd-4ac1-a19f-90dd2231a452)
c) Thêm cột Gia_Mon vào bảng Mon_An nếu chưa tồn tại: ![image](https://github.com/user-attachments/assets/61f992c5-ad7f-40aa-8fad-d97123f01c8f)
ết luận: Việc thêm các trường phi chuẩn như So_Mon, Tong_Tien trong bảng Don_Hang và Gia_Mon trong bảng Mon_An giúp tăng tốc độ truy vấn, giảm tải tính toán tại thời điểm chạy và cải thiện trải nghiệm người dùng—điều đặc biệt quan trọng với các hệ thống có lượng giao dịch lớn. Thay vì truy vấn thông qua bảng khác thì CSDL sẽ truy vấn trực tiếp vào bảng hiện tại!
### 3. Viết Trigger cho bảng Chi_Tiet_Don nhằm tự động cập nhật các trường phi chuẩn trong bảng Don_Hang. Mỗi khi có thêm, sửa hoặc xóa dữ liệu trong Chi_Tiet_Don, trigger này sẽ cập nhật lại So_Mon và Tong_Tien
a) Mục tiêu:
- Giảm thiểu việc tính toán động qua các phép JOIN tại thời điểm truy vấn,
- Tăng tốc độ truy xuất dữ liệu từ Don_Hang,
- Đảm bảo rằng các giá trị phi chuẩn luôn được cập nhật khi dữ liệu chi tiết thay đổi.
b) Code Trigger: ![image](https://github.com/user-attachments/assets/b2a2939e-044c-4fba-8965-05345f6686ff)
4. Nhập dữ liệu: 



 






 
