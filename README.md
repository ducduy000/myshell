# Tên đề tài: Xây dựng ứng dụng shell (tương tự bash)
Mục tiêu:
Xây dựng một chương trình shell đơn giản bằng ngôn ngữ C

Cho phép người dùng nhập lệnh và shell sẽ:

-Thực thi lệnh nội trú

-Thực thi lệnh ngoại trú

-Hỗ trợ pipe, redirection

-Chạy lệnh nền bằng &

-Xử lý ngoặc ‘..’, “..” , `...` và wildcards (?*)





### Compile:

```bash
make 
```

### Run:

```bash
.\test
```



## I. Các lệnh nội trú
1. pwd: Folder đang ở hiện tại
2. cd: Chuyển sang folder khác
3. echo: dùng để in (hiển thị) một chuỗi ký tự hoặc giá trị ra màn hình
4. export: dùng để đưa biến shell thành biến môi trường
5. unset: dùng để xóa biến (biến shell hoặc biến môi trường) ra khỏi shell hiện tại
6. jobs: dùng để liệt kê các tiến trình đang chạy nền (background jobs) trong shell hiện tại
7. set: để thiết lập, hiển thị hoặc thay đổi trạng thái và biến của shell
8. kill: dùng để gửi tín hiệu (signal) tới process hoặc job để điều khiển hoặc kết thúc nó

## II. Các lệnh ngoại trú
1. ls: Liệt kê folder
2. date: In ra ngày tháng năm hiện tại
3. time: In ra giờ hiện tại
4. whoami: dùng để hiển thị tên người dùng (username) hiện đang đăng nhập và đang chạy shell
5. sleep: dùng để tạm dừng (ngủ) tiến trình trong một khoảng thời gian xác định, sau đó tiếp tục hoặc kết thúc
6. cat: dùng để hiển thị nội dung file ra màn hình, hoặc nối nhiều file lại với nhau
7. wc: dùng để đếm số dòng, số từ và số ký tự (byte) của file hoặc dữ liệu đầu vào

## III. Cách dùng
1. cd "dirpath"
2. echo "content"
3. export variable=valid
4. unset variable
5. run background: sheep time &
6. cat "file name"

## IV. Test
1. echo Hello world > out.txt: ghi "Hello world" vào file out.txt
2. echo World >> out.txt: ghi "World" vào cuối file out.txt
3. ls > file.txt: chuyển (redirect) toàn bộ kết quả của lệnh ls vào file file.txt
4. ls *.txt: Liệt kê tất cả các file có phần mở rộng .txt trong thư mục hiện tại.
5. ls *.txt > list.txt: Liệt kê tất cả các file có đuôi .txt trong thư mục hiện tại và ghi danh sách đó vào file list.txt (ghi đè).
6. ls | wc -l: Đếm số dòng trong output của ls → thường được hiểu là đếm số file/thư mục trong thư mục hiện tại.
7. cat out.txt | wc -l: Đếm số dòng có trong file out.txt.
8. echo $HOME:In ra đường dẫn thư mục home của người dùng hiện tại.
9. echo ' * ? `pwd` ': In ra nguyên văn chuỗi * ? \pwd` **, **KHÔNG có globbing (*, ?) và KHÔNG có command substitution (pwd`).
10. echo "thu muc hien tai la `pwd`": In ra chuỗi kèm theo đường dẫn thư mục hiện tại.
11. echo file hien tai la `ls | wc -l `: In ra câu kèm theo số lượng file/thư mục trong thư mục hiện tại.
12. ls *: Liệt kê tất cả các file và thư mục trong thư mục hiện tại (trừ file ẩn).
13. ls *.txt: Liệt kê tất cả các file có phần mở rộng .txt trong thư mục hiện tại.
14. ls main?.txt: Liệt kê các file có tên dạng mainX.txt, trong đó X là đúng 1 ký tự bất kỳ.
15. ls *.txt > list.txt: Liệt kê tất cả các file có đuôi .txt trong thư mục hiện tại và ghi danh sách đó vào file list.txt (ghi đè nội dung cũ nếu có).
16. ls *.txt | wc -l: Đếm số lượng file có đuôi .txt trong thư mục hiện tại.
17. exit: thoát chương trình.
