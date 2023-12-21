- Giới thiệu
- Cài đặt
    - Cài đặt thủ công
    - Sử dụng thư viện chuẩn
    - Phân tích
        - Độ phức tạp thời gian
        - Độ phức tạp bộ nhớ
- Ứng dụng
    - Sử dụng Stack để xử lý xâu
        - Bài toán 1
            - Cách giải
        - Bài toán 2
            - Nhận xét
            - Bổ đề 1
            - Chứng minh
            - Bổ đề 2
            - Chứng minh
            - Hệ quả 1
            - Cách giải
            - Cài đặt
        - Mở rộng
    - Sử dụng Stack để khử đệ quy
    - Stack đơn điệu
        - Bài toán
            - Nhận xét
            - Mô hình lại bài toán
            - Cài đặt
            - Đánh giá độ phức tạp
        - Mở rộng
            - Hình chữ nhật lớn nhất
                - Cách giải
            - Hình chữ nhật lớn nhất trong lưới ô vuông
                - Cách giải
- Bài tập áp dụng

# Giới thiệu

Stack là một danh sách được bổ sung 2 thao tác: **thêm một phần tử vào cuối danh sách,** và **loại bỏ một phần tử ở cuối danh sách.** Ví trí cuối của Stack được gọi là đỉnh **(top).**

Có thể hình dung Stack như một chồng sách. Việc đặt một quyển sách lên trên cùng chính là thao tác thêm phần tử, và lấy ra quyển sách ở trên đầu là thao tác loại bỏ phần tử. Như vậy, quyển sách được đặt vào sau cùng sẽ luôn được lấy ra trước tiên. Vì tính chất này, Stack còn được gọi là danh sách **LIFO** (Last In - First Out, hay vào sau - ra trước).

Hình ảnh minh họa cho Stack chứa các phần tử kiểu `char`:
<img src="https://scontent.fhan17-1.fna.fbcdn.net/v/t39.30808-6/412610850_1597099371039033_1622876650002020237_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=524774&_nc_eui2=AeHh2awnMIzcTEC1NIamHYzCObINICITld85sg0gIhOV31ms-9jeYMm5ZndFeSB9-CkZCtq1MQc-jliriQBWfUPa&_nc_ohc=m9U91tvn3RUAX8nTlDx&_nc_ht=scontent.fhan17-1.fna&oh=00_AfBndlcFdSEdaiIh20S0eYZ61i3b_fIaDoLCSqn9bBLWJg&oe=658911DD">

Stack có khá nhiều ứng dụng trong lập trình thi đấu. Bài viết này sẽ xem xét các ứng dụng điển hình của Stack.


# Cài đặt
## Cài đặt thủ công

Ta có thể biểu diễn Stack bằng một mảng, cùng với biến `top` biểu diễn vị trí của phần tử nằm ở đỉnh Stack. Dưới đây là một cách cài đặt Stack chứa các phần tử thuộc kiểu `int`:

