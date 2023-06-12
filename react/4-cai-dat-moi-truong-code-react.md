# Cài đặt môi trường code react
### Bước 1 : cài đặt nodejs 
https://nodejs.org/en   
![image](https://github.com/dathalongbay/js-doc/assets/6966136/63fc500b-61f6-4c72-ad36-e254bcc424f3)
Cài đặt xong nodejs :  
### Bước 2 : mở terminal để gõ lệnh :
Hãy gõ lệnh `node -v` để kiểm tra phiên bản nodejs đang chạy  
![image](https://github.com/dathalongbay/js-doc/assets/6966136/84890c9a-bc89-42e5-a2aa-960d476bb1a6)

Kiểm tra phiên bản npm bằng lệnh `npm -v`   
![image](https://github.com/dathalongbay/js-doc/assets/6966136/96316f75-db36-41b0-8821-9bcc54178f3b)
### Bước 3 : tìm hiểu npm là gì ?
npm (Node Package Manager) là một công cụ quản lý gói phần mềm cho Node.js. Nó được cài đặt cùng với Node.js và cho phép bạn quản lý và cài đặt các thư viện và module JavaScript từ kho lưu trữ công cộng của npm hoặc từ các kho lưu trữ riêng tư.

Với npm, bạn có thể dễ dàng tìm kiếm, cài đặt, cập nhật và gỡ bỏ các gói phần mềm JavaScript đã được đóng gói sẵn. Các gói phần mềm này thường chứa mã nguồn, tài liệu, tệp cấu hình và các tài nguyên khác liên quan đến một chức năng cụ thể. Bằng cách sử dụng npm, bạn có thể tận dụng được công sức và kinh nghiệm của cộng đồng phát triển để nhanh chóng tích hợp các chức năng mở rộng vào ứng dụng của mình.

npm cũng cho phép bạn quản lý các phụ thuộc (dependencies) của ứng dụng của mình. Bạn có thể khai báo các phụ thuộc trong tệp package.json của dự án và npm sẽ tự động tải và cài đặt các gói phần mềm tương ứng khi bạn cần.

Bên cạnh việc quản lý gói phần mềm, npm còn cung cấp các công cụ khác như xây dựng (build), kiểm tra (test) và triển khai (deploy) ứng dụng. Nó cung cấp một hệ sinh thái phong phú của các lệnh và tài liệu để hỗ trợ việc phát triển ứng dụng Node.js một cách hiệu quả.

Tóm lại, npm là một công cụ quản lý gói phần mềm cho Node.js, cho phép bạn tìm kiếm, cài đặt và quản lý các thư viện và module JavaScript, cùng với các tính năng khác như quản lý phụ thuộc và công cụ phát triển ứng dụng.
### Bước 4 : bắt đầu với https://create-react-app.dev/
Truy cập vào trang web : https://create-react-app.dev/ đây là tool sẽ giúp chúng ta bắt đầu với react js
### Bước 5 : tạo ứng dụng đầu tiên 
Mở terminal trên máy và gõ lệnh 
```
npx create-react-app my-app
```
trong đó `my-app` là tên ứng dụng react và cũng là tên folder chứa ứng dụng react được tạo ra  
bạn có thể đổi `my-app` thành tên ứng dụng khác mà bạn mong muốn ví dụ như : code-app,demo-app ...   
![image](https://github.com/dathalongbay/js-doc/assets/6966136/d7fac62c-6c50-4ca9-ad28-03c6c8815cfd)
Lần đầu tiên bạn sẽ phải cài đặt create-react-app bạn gõ y để xác nhận cài đặt tool này   

![image](https://github.com/dathalongbay/js-doc/assets/6966136/cd08dbde-0c48-4a93-8bac-27a47cb7527b)

Sau khi cài đặt `create-react-app` thành công bạn tiếp tục chạy lại lệnh để tạo ứng dụng `my-app` của bạn
```
npx create-react-app my-app
```
Điều này chỉ xảy ra khi bạn chưa cài `create-react-app` . Từ lần sau bạn có thể tạo ứng dụng luôn mà không phải cài lại .

Đây là ảnh sau khi cài thành công .

![image](https://github.com/dathalongbay/js-doc/assets/6966136/33e4f490-7c39-4f03-9dcb-16d436e5fc29)






