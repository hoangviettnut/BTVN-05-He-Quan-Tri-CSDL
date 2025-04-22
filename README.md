# BTVN 05 Hệ Quản Trị CSDL
# Sinh viên: Lương Hoàng Việt - K225480106073

# SUBJECT: Trigger on mssql

## A. Trình bày lại đầu bài của đồ án PT&TKHT:
1. Mô tả bài toán của đồ án PT&TKHT, 
   đưa ra yêu cầu của bài toán đó
2. Cơ sở dữ liệu của Đồ án PT&TKHT :
   Có database với các bảng dữ liệu cần thiết (3nf),
   Các bảng này đã có PK, FK, CK cần thiết
 
## B. Nội dung Bài tập 05:
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
1. Khái quát Đồ án:<br>
a) Tên đồ án: Phân tích thiết kế hệ thống đặt đồ ăn online cho cửa hàng đồ ăn TNUT<br>
b) Yêu cầu: Thiết kế hệ thống đặt đồ ăn online cho cửa hàng đồ ăn nhằm hiện đại và đơn giản hóa quá trình mua- bán cho khách hàng, làm việc kiểm soát dịch vụ tại quán dễ dàng và tiện lợi hơn thay vì phương pháp pháp truyền thống.

2. CSDL của Đồ án:<br>
a) Các bảng trong Database: ![image](https://github.com/user-attachments/assets/5a494ddc-a0d4-4181-9323-6f408b385057)
b) Liên kết giữa các bảng (Đã chứa các khóa cần thiết):![image](https://github.com/user-attachments/assets/e8e71668-ec13-4f11-9818-8a919bec0923)

## B. Nội dung Bài Tập 05:
1. CSDL của đồ án đã nêu ở phần A

2. Thêm trường phi chuẩn DanhMuc cho bảng MonAn (Code đã chạy Successfully) :![image](https://github.com/user-attachments/assets/5ab91efc-82ad-42f0-87ee-7a281377c863)
Sau khi thêm trường phi chuẩn (Bảng đã xuất hiện thêm DanhMuc): ![image](https://github.com/user-attachments/assets/df9f9ef5-d689-4a98-a240-d4f61468ac60)
Kết luận: Thêm trường DanhMuc vào bảng MonAn để phân loại món ăn theo từng nhóm như "Món chính", "Đồ uống" và "Tráng miệng". Điều này giúp hệ thống linh hoạt hơn khi hiển thị thực đơn và hỗ trợ quản lý dễ dàng.

3.  Tạo Trigger trên bảng MonAn<br>
a) Mục tiêu: Đảm bảo dữ liệu nhập vào bảng MonAn luôn hợp lệ<br>
b) Code Trigger: ![image](https://github.com/user-attachments/assets/f7861695-2d92-41d6-bb1a-4f24f52b1cf1)


4. Nhập dữ liệu Demo để test:<br>
a) Nhập dữ liệu lần 1:  ![image](https://github.com/user-attachments/assets/595d5e85-7f44-4f36-a632-6b6e0bbb1e3b)<br>
Dòng thứ nhất ta nhập thành công do giá trị ở DanhMuc phù hợp với điều kiện trước đó trong Trigger đã đặt ra<br>
b) Nhập dữ liệu lần 2: ![image](https://github.com/user-attachments/assets/dab8062e-612d-41e3-9a27-ed159dd18e7f)<br>
Dòng thứ 2 hệ thống đã báo lỗi do phần DanhMuc ta nhập không khớp với điều kiện mà Trigger đặt ra<br>

5. Công dụng của Trigger với đồ án:<br>
a) Quản lí đơn hàng, món ăn tốt hơn <br>
b) Hỗ trợ quá trình quản lí hệ thống <br>
c) Giảm tải tính toán cho hệ thống <br>
d) Đảm bảo dữ liệu nhất quán <br>
### NOTE: Đây chỉ CSDL ban đầu cho đồ án. Trong quá trình thực hiện có thể sẽ có thêm nhiều sự thay đổi với CSDL trong bài tập trên!






 






 
