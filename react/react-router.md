# React router
Create React App không bao gồm định tuyến trang router.
Do đó chúng ta phải tự cài thêm :
### cài đặt react router
`npm i -D react-router-dom`    
i là option viết tắt của install   
-D là một cờ ngắn gọn cho --save-dev. Điều này cho biết cho npm biết rằng bạn muốn cài đặt gói react-router-dom là một phần của devDependencies (development dependencies) trong dự án của bạn. 
Đây là nội dung sau khi cài trong file package.json  
```
"devDependencies": {
    "react-router-dom": "^6.11.2"
  }
```
### Cấu trúc thư mục
Để tạo một ứng dụng có nhiều định tuyến trang, trước tiên hãy bắt đầu với cấu trúc tệp.

Trong thư mục src, chúng ta sẽ tạo một thư mục có tên pages với một số tệp:

src\pages\:

- Layout.js
- Home.js
- Blogs.js
- Contact.js
- NoPage.js
Mỗi tệp sẽ chứa một thành phần React rất cơ bản.

  
