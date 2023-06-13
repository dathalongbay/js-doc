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

### Sử dụng cơ bản
Bây giờ chúng ta sẽ sử dụng Bộ định tuyến trong tệp của mình index.js.
```js
import ReactDOM from "react-dom/client";
import { BrowserRouter, Routes, Route } from "react-router-dom";
import Layout from "./pages/Layout";
import Home from "./pages/Home";
import Blogs from "./pages/Blogs";
import Contact from "./pages/Contact";
import NoPage from "./pages/NoPage";

export default function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Layout />}>
          <Route index element={<Home />} />
          <Route path="blogs" element={<Blogs />} />
          <Route path="contact" element={<Contact />} />
          <Route path="*" element={<NoPage />} />
        </Route>
      </Routes>
    </BrowserRouter>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```

Đầu tiên chúng ta cần import các thành phần cơ bản của react router bằng lệnh 
```js
import { BrowserRouter, Routes, Route } from "react-router-dom";
```
Tiếp theo chúng ta import layout và các page chúng ta đã tạo nhé . 
```js
import Layout from "./pages/Layout";
import Home from "./pages/Home";
import Blogs from "./pages/Blogs";
import Contact from "./pages/Contact";
import NoPage from "./pages/NoPage";
```

Chúng ta sẽ bao bọc nội dung của mình trước với thẻ **`<BrowserRouter> ... </BrowserRouter>`**

Sau đó chúng ta đưa tiếp thẻ **`<Routes>...</Routes>`** vào bên trong thẻ **`<BrowserRouter><Routes>...</Routes></BrowserRouter>`**

Dưới đây là ý nghĩa của các đoạn mã trong tập hợp trên:

**`<Route path="/" element={<Layout />} />>`**: Đây là đường dẫn gốc của ứng dụng, được định nghĩa là **`<Layout />`**. Nghĩa là khi bạn truy cập vào đường dẫn gốc **`(/), <Layout />`** sẽ được hiển thị.

**`<Route index element={<Home />} />>`**: Đây là một con đường dẫn con của "/", được định nghĩa là <Home />. Nghĩa là khi bạn truy cập vào đường dẫn gốc (/), <Home /> sẽ được hiển thị.

**`<Route path="blogs" element={<Blogs />} />>`**: Đây là một con đường dẫn tương đối, nghĩa là khi bạn truy cập vào đường dẫn /blogs, <Blogs /> sẽ được hiển thị.

**`<Route path="contact" element={<Contact />} />>`**: Đây là một con đường dẫn tương đối, nghĩa là khi bạn truy cập vào đường dẫn /contact, <Contact /> sẽ được hiển thị.

**`<Route path="*" element={<NoPage />} />`**: Đây là một con đường dẫn tương đối với **`"*">`** đại diện cho bất kỳ đường dẫn nào không khớp với các đường dẫn trước đó. Nghĩa là khi bạn truy cập vào một đường dẫn không khớp với các đường dẫn trên, **`<NoPage />`** sẽ được hiển thị.

Với cấu trúc định tuyến trên, khi bạn truy cập vào các đường dẫn khác nhau, các thành phần tương ứng **`(<Home />, <Blogs />, <Contact />, <NoPage />)`** sẽ được hiển thị trong thành phần **`<Layout />`**




  
