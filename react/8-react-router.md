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

**`<Route index element={<Home />} />>`**: Đây là một con đường dẫn con của "/", được định nghĩa là **`<Home />`**. Nghĩa là khi bạn truy cập vào đường dẫn gốc **`(/), <Home />`** sẽ được hiển thị.

**`<Route path="blogs" element={<Blogs />} />>`**: Đây là một con đường dẫn tương đối, nghĩa là khi bạn truy cập vào đường dẫn /blogs, **`<Blogs />`** sẽ được hiển thị.

**`<Route path="contact" element={<Contact />} />>`**: Đây là một con đường dẫn tương đối, nghĩa là khi bạn truy cập vào đường dẫn /contact, **`<Contact />`** sẽ được hiển thị.

**`<Route path="*" element={<NoPage />} />`**: Đây là một con đường dẫn tương đối với **`"*">`** đại diện cho bất kỳ đường dẫn nào không khớp với các đường dẫn trước đó. Nghĩa là khi bạn truy cập vào một đường dẫn không khớp với các đường dẫn trên, **`<NoPage />`** sẽ được hiển thị.

Với cấu trúc định tuyến trên, khi bạn truy cập vào các đường dẫn khác nhau, các thành phần tương ứng **`(<Home />, <Blogs />, <Contact />, <NoPage />)`** sẽ được hiển thị trong thành phần **`<Layout />`**

Đây là nội dung của file **`pages/Layout.js`**
```js
import { Outlet, Link } from "react-router-dom";

const Layout = () => {
  return (
    <>
      <nav>
        <ul>
          <li>
            <Link to="/">Home</Link>
          </li>
          <li>
            <Link to="/blogs">Blogs</Link>
          </li>
          <li>
            <Link to="/contact">Contact</Link>
          </li>
        </ul>
      </nav>

      <Outlet />
    </>
  )
};

export default Layout;
```
Đoạn mã **`import { Outlet, Link } from "react-router-dom";`** là cách để nhập các thành phần Outlet và Link từ thư viện **react-router-dom** vào trong tệp tin của bạn.

**Outlet** là một thành phần trong react-router-dom được sử dụng trong cấu trúc định tuyến. Nó được đặt trong một thành phần cha và chịu trách nhiệm hiển thị thành phần con tương ứng với địa chỉ URL. Khi bạn định nghĩa các tuyến con như trong ví dụ trước đó, Outlet sẽ hiển thị các thành phần tương ứng với địa chỉ URL trong thành phần cha.

**Link** là một thành phần trong react-router-dom được sử dụng để tạo liên kết trong ứng dụng đơn trang (single-page application). Thay vì tải lại trang, Link cho phép bạn chuyển đổi giữa các địa chỉ URL mà không làm tải lại trang hoặc làm mất trạng thái của ứng dụng. Bằng cách sử dụng Link, bạn có thể tạo các liên kết trong ứng dụng của bạn để điều hướng giữa các trang hoặc các địa chỉ URL khác nhau.

file **`pages/Home.js`**
```js
const Home = () => {
  return <h1>Home</h1>;
};

export default Home;
```

file **`pages/Blogs.js`**
```js
const Blogs = () => {
  return <h1>Blog Articles</h1>;
};

export default Blogs;
```

file **`pages/Contact.js`**
```js
const Contact = () => {
  return <h1>Contact Me</h1>;
};

export default Contact;
```

file **`pages/NoPage.js`**
```js
const NoPage = () => {
  return <h1>404</h1>;
};

export default NoPage;
```



  
