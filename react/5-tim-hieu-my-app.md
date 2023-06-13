# Tìm hiểu ứng dụng đầu tiên 

![image](https://github.com/dathalongbay/js-doc/assets/6966136/6fe915ae-8a7a-458e-b870-e5a25dbfaa9f)

Chúng ta cùng xem qua cấu trúc ứng dụng :

- folder node_modules : đây là folder chứa code của các thư viện mà chúng ta sẽ sử dụng trong ứng dụng .
- folder public : chứa file index.html có thẻ div với id là root để ứng dụng react sẽ render nội dung vào thẻ này. 
```html
<body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
    <!--
      This HTML file is a template.
      If you open it directly in the browser, you will see an empty page.

      You can add webfonts, meta tags, or analytics to this file.
      The build step will place the bundled scripts into the <body> tag.

      To begin the development, run `npm start` or `yarn start`.
      To create a production bundle, use `npm run build` or `yarn build`.
    -->
  </body>
```
- folder src : chứa source code mà chúng ta sẽ viết trong ứng dụng react này 
- .gitignore <nếu có> : file này khai báo các folder và file mà chúng ta không muốn git theo dõi
- package.json : khai báo tên các thư viên sẽ được cài đặt và npm script có thể được chạy khi gõ câu lệnh. hãy tự mở file này lên và quan sát
- package-lock.json 
Package-lock.json có các tác dụng sau:

1. Đảm bảo sự nhất quán về phiên bản: Khi tạo ra tệp package-lock.json, npm ghi lại các phiên bản cụ thể của các gói phụ thuộc mà dự án của bạn đang sử dụng. Điều này đảm bảo rằng tất cả thành viên trong nhóm phát triển sẽ cài đặt cùng các phiên bản này và đảm bảo sự nhất quán giữa các môi trường phát triển khác nhau.

2. Tăng tốc quá trình cài đặt: Khi bạn hoặc ai đó khác tải dự án của bạn về và chạy lệnh npm install, npm sẽ sử dụng tệp package-lock.json để cài đặt các phiên bản cụ thể của các gói phụ thuộc mà không cần phải kiểm tra phiên bản mới nhất. Điều này giúp tăng tốc quá trình cài đặt và đảm bảo rằng các phiên bản cụ thể được cài đặt một cách nhất quán trên các máy tính khác nhau.
- Readme.md : file viết thông tin hướng dẫn sử dụng của 1 project 
