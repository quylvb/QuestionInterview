# QuestionInterview
PHP

1. Phân biệt POST và GET trong php?
  + Cả GET và POST đều được dùng để gửi dữ liệu lên server.
    - GET: Gửi dữ liệu lên server thông qua URL, nên thông tin dữ liệu hiển thị lên url vì thế bảo mật kém, dữ liệu gửi lên bị giới hạn 1024 ký tự.
    - POST: Gửi dữ liệu lên server dưới dạng ẩn thông qua HTTP Header vì thế nó có tính bảo mật cao hơn so với GET, dữ liệu gửi lên không bị giới hạn.
    Tuy nhiên tốc độ thực thi xử lý của Post chậm hơn Get.
2. Cookie và session có gì khác nhau ?
  + COOKIE là một tập tin nhỏ được server nhúng vào máy tính của người dùng. Nếu lần đầu tiên trình duyệt truy cập vào website nó sẽ gửi một COOKIE đến trình duyệt của người dùng, và mỗi khi người dùng tiếp tục yêu cầu một trang web từ website này thì COOKIE với các thông tin thu nhập từ phía người dùng trên website này sẽ được sẽ gửi trả về server của website.
  + SESSION cũng giống như COOKIE nhưng SESSION được lưu trữ hoàn toàn trên server, do vậy tính bảo mật cao hơn cookie, các website hiện này thường dùng session để lưu thông tin của người dùng khi họ đăng nhập. Chu kỳ sống của SESSION do webserver qui định, ta có thể điều chỉnh chu kỳ này khi cấu hình webserver, tại server sẽ có 1 PHP SESSID tương ứng được tạo ra, các PHP SESSID sẽ được lưu trong một tập tin văn bản ở tại vị trí được qui định trong file php.ini ở dòng session.save_path.
3. Sự khác nhau giữ biến và hằng, Nêu 1 hằng được định nghĩa 2 lần thì sẽ như thế nào ?
+ Điểm khác biệt lớn nhất là hằng là không thể thay đổi trong suốt quá trình chạy chương trình, biến thì có.
+ Nếu 1 hằng được định nghĩa 2 lần thì chương trình sẽ bị lỗi "Constant NAME already defined".
4. sự khác nhau của toán tử & và && trong PHP là gì?
+ Toán từ & và && trong PHP đều là phép toán AND, tuy nhiên toán tử một dấu & áp dụng theo kiểu bit, nói dễ hiểu hơn một dấu & là phép AND thao tác trên các bit ví dụ a = 10 = 1010, b = 14 = 1110 nên ta có  a&b = 1010 = 10 . Còn phép toán  && thì chỉ trả về kiểu boolean True và False, 0 và 1.
5. Sự khác nhau giữa == và ===
+ == không so sánh kiểu dữ liệu còn === thì có
6. sự khác nhau giữ emty() và isset()
+ Empty() check biến có giá trị là rỗng hoặc mảng rỗng,null,0. 
+ Còn isset() thì chỉ check sự tồn tại của biến, và biến có giá trị null không .
+ Empty bao quát hơn isset
7. Sẽ hỏi những câu hỏi về các hàm có sẵn trong php ví dụ như:
+ Tìm một phần tử tồn tại trong mảng ta dùng hàm gì ? (in_array)
+ Hàm array_merge() và array_combine() có gì khác nhau ?
+ Đếm số phần tử trong mảng dùng hàm nào count();
+ Thêm một hoặc nhiều phần tử vào cuối mảng và trả về số lượng phần tử của mảng ta dùng hàm gì? array_push()
+ Hàm nào  sẽ chuyển một chuỗi $string thành một mảng các phần tử explode ();
+ hàm xử lí của php thì rất nhiều, bạn nên tham khảo những hàm của php trên trang chủ của php để tham khảo.

8: $$ có nghĩa là gì
+ gắn tên cho biến:
+ ví dụ: $a = "hello"
+ thì ta có:  $$a = $hello.

9: Khi tắt cookie trên trình duyệt thì có ảnh hưởng tới session không:
+ không thể sử dụng được cả cookie và session khi tắt cookie, vì bản chất là session khi hoạt động cũng sẽ tạo một cookie trên trình duyệt để lưu dữ liệu, nên khi tắt cookie trên trình duyệt thì session cũng không sử dụng được


# Những câu hỏi về hướng đối tượng
1. Nêu các tính chất của OOP, và giải thích chúng
2. Lớp và đối tượng có gì khác nhau
3: phân biệt abtrast class và interface, khi nào sử dụng chúng
4. Tính đóng gói trong php là gì, mục đích của chúng để làm gì
+ Tính đóng gói (encapsulation) là "đóng gói" thuộc tính và phương thức của đối tượng (hoặc lớp) thông qua việc giới hạn quyền truy cập (hoặc thay đổi) giá trị của thuộc tính hoặc quyền gọi phương thức. được thể hiện qua các từ khóa
+ public: Cho phép truy cập (và thay đổi giá trị) của thuộc tính và phương thức ở mọi phạm vi
+ private: Chỉ cho phép truy cập (hay thay đổi) giá trị của thuộc tính và phương thức ở phạm vi  của lớp đó
+ protected: Chỉ cho phép truy cập (hay thay đổi) giá trị của thuộc tính và phương thức ở phạm vi của lớp đó và lớp con của nó (lớp kế thừa của chính nó)
+ Mục đích thực tế: Là để phục vụ cho việc đọc mã của người khác được dễ dàng hơn, vì dụ trong 1 lớp, nhìn thấy các phương thức private thì họ sẽ biết ngay là phương thức này dùng để thực thi, tính toán cho các phương thức khác, không được dùng để gọi ra ngoài, nên ko cần quan tâm tới nó, hơn nữa nó ngăn chặn việc truy cập, sửa đổi các hàm private, protect ở ngoài phạm vi lớp theo chủ đích của người lập trình

=> nói tóm lại là các tính chất của hướng đói tượng nói  chung, và đóng gói nói triêng giúp phục vụ cho việc viết mã được dễ dàng hơn
5. Tính Chất kế thừa là gì, em hiểu thế nào về tính chất kế thừa

# Laravel
1. Middleware trong Laravel là gì
+ Middleware như một cánh cửa trung gian giữa Router và controller. Middleware là một loại cơ chế lọc HTTP request. Ví dụ: Nếu người dùng không được xác thực và nó đang cố truy cập vào admin Middleware sẽ chuyển hướng người dùng đó đến trang đăng nhập. Hoăc thực hiện một thực thi lệnh nào đó trước khi người dùng truy cập vào controller...
+Một số  cách dùng middleware, 
- middleware globle, được sử dụng trong mọi request
- middleware  được sử dụng cho router hoặc nhóm router
- middleware  được sử dụng trong controller
2. Có mấy cách query trong laravel, bạn hay sử dụng cách nào, vì sao
+ Có 2 cách truy vấn trong laravel, đó là Eloquent và Query builder
-Eloquent  và Query builder đều là công cụ truy vấn của laravel giúp cho coder dễ dàng thao tác với database
-Eloquent, các thao tác với database đều cần thông qua model, và hỗ trợ rất nhiều hàm làm cho việc truy vấn đơn giản hơn, hỗ trợ những relationship giúp cho code dễ đọc và đẹp hơn, 
- Query buider, thao tác với db thông qua lớp DB, Nó có thể được sử dụng để thực thi hầu hết những thao tác về database trong ứng dụng
+ So sánh:
- Query builder và Eloquent đều sử dụng : 'PDO parameter binding' nên sẽ giúp chúng ta tránh được lỗi sql injection.

- Có thể dùng tất cả hàm của query buider trong eloquent, nhưng không thể làm ngược lại
-Nhưng eloquent không thể thực hiện được những truy vấn quá phức tạp
-Tùy vào câu truy vấn mà ta có thể lựa chọn cách dùng eloquent hay query builder, Tôi thì hay sử dụng eloquent nhưng lai query buider, tức là vẫn dùng model để thao tác với database
-Nhưng câu truy vấn thì vẫn sự dụng hàm của eloquent và query builder, với những câu truy vấn phức tạp cần chèn sql thuần thì cần sài hàm 

DB::raw()

3. Migration là gì
- Migration là công cụ để giúp quản lí các thao tác tạo database và data bằng code
+ ưu điểm của migration là khi chung một team làm project, hầu hết sự thay đổi về database sẽ được thể hiện trong mygration, và member mới join team chỉ cần chạy lệnh thì sẽ có nguyên bộ database của project mà không cần phải kéo về, vì thế  nó rất tiện khi trong team làm việc mỗi khi có thay đổi table, cả team sẽ có thể cập nhật db mới một cách đễ dàng. Lúc mới cái đặt larvel thì trong source code đã có sẵn một số bảng liên quan tới đăng nhập, đăng kí người dùng.
4.Command line trong laravel là gì
+ Đây là hệ thống giao diện command line trong laravel giúp thực hiện nhiều thao tác hỗ trợ cho việc chạy các lệnh laravel cơ bản, cũng như là thực hiện một số thao tác như chạy một controller nào đó mà không cần thông qua router, hoặc viết batch job

+ Đây là một vấn đề tương đối dài, để hiểu chi tiết về command line, xin mời các bạn đọc bài: https://daylaptrinhphp.com/32-cach-tao-command-artisan-trong-laravel.html
5. Service container là gì
+ Service container là một khái niệm nằm trong tần Architecture Concepts (kiến trúc) của laravel, hỗ trợ sử dụng dependecy injection dễ hàng hơn, và có thể sử dụng được ở tất cả các class chỉ cần 1 lần khai báo duy nhất, mà không cần phải thực hiện khai báo nhiều lần, 
+ Đây là một vấn đề tương đối khó, để hiểu chi tiết về Service container, các bạn xin đọc bài: https://daylaptrinhphp.com/44-service-container-laravel.html
6. Service Provider là gì
+ Service provider là trung tâm của laravel, tất cả quá trình khởi động, thực thi code của core laravel, những ứng dụng của bạn hoặc ứng dụng bên thứ ba đều phải thông qua Service Provider
+ i tất cả các service provider được đăng kí trong app/config/app.php, Khi cài bất kì ứng dụng nào thông qua composer, các bạn cũng để phải đăng kí các service provider.
+Đây là một vấn đề tương đối khó, để hiểu chi tiết về Service Provide , các bạn xin đọc bài: https://daylaptrinhphp.com/45-service-provider-trong-laravel.html
7. Queue trong laravel là gì.
+ Queue cho phép đưa những công việc đòi hỏi thời gian nhiều lên hàng đợi, giúp tránh phát sinh lỗi và thiếu sót các tác vụ cần thực hiện, ví dụ: khi export 1 file exel có dung dượng lớn, vấn đề xảy ra là khi client sent request tới sever,và đợi sever phản hồi, nếu như file exel đó quá nặng đòi hỏi thời gian chờ quá lâu, thì lúc đó sẽ xảy ra lỗi connection time out, hay giả sử client request emeil quá nhiều, sẽ dẫn đến tình trạng nghẽn sever email... Queue ra đời để giải quyết các vấn đề đó
+ Chi tiết về Queue, các bạn xin đọc bài: https://daylaptrinhphp.com/39-queue-trong-laravel.html
8. Facade là gì
+ Facade là kiểu design của laravel cho phép truy cập đến các hàm bên trong các service được khai báo trong Service Container bằng cách gọi các hàm static. ví dụ Auth::user(), Auth::check();
+ Ta có thể tạo facade mới bằng cách tạo một sevirce provider mới và bỏ vào config, tham khảo service provider
 9. Vòng đời Request của laravel 
 10. khi nào thì sử dụng trait
 11. php là thông dịch hay biên dịch
 12. php là đơn kế thừa hay đa kế thừa
 
