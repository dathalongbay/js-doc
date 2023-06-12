# Các khái niệm cơ bản trong react
React là một thư viện JavaScript phổ biến được sử dụng để xây dựng giao diện người dùng (UI) tương tác trong các ứng dụng web. Dưới đây là một số khái niệm cơ bản trong React:

1. Components (Các thành phần): React được xây dựng dựa trên khái niệm components. Components là các phần tử độc lập và có thể tái sử dụng trong ứng dụng React. Có hai loại component chính là functional components và class components.   

 ![image](https://github.com/dathalongbay/js-doc/assets/6966136/445c8d75-6b0c-4e74-bdbb-12985b65e1ff)

```js
// Header.js
const Header = () => {
  return (
    <header>
      <h1>Ứng dụng React</h1>
    </header>
  );
};

// MainContent.js
const MainContent = () => {
  return (
    <main>
      <p>Đây là nội dung chính của ứng dụng.</p>
    </main>
  );
};

// App.js
const App = () => {
  return (
    <div>
      <Header />
      <MainContent />
    </div>
  );
};
```
2. JSX (JavaScript XML): JSX là một phần cú pháp của React cho phép bạn viết các đoạn mã JavaScript trong HTML. JSX giúp tạo ra các thành phần UI trong React một cách rõ ràng và dễ đọc hơn.

3. Props (Thuộc tính): Props là một cách để truyền dữ liệu từ một thành phần cha đến một thành phần con trong React. Props là chỉ đọc và không thể thay đổi giá trị của chúng.

4. State (Trạng thái): State là một đối tượng trong React để lưu trữ và quản lý trạng thái của một thành phần. Khi state thay đổi, React sẽ tự động cập nhật lại giao diện người dùng.

5. Lifecycle methods (Các phương thức vòng đời): React cung cấp một số phương thức vòng đời cho các thành phần để thực hiện các hành động trong quá trình chúng được tạo ra, cập nhật hoặc bị hủy bỏ. Các phương thức như componentDidMount, componentDidUpdate, và componentWillUnmount là các ví dụ về các phương thức vòng đời trong React.

6. Hooks: Hooks là một tính năng mới trong React từ phiên bản 16.8. Hooks cho phép bạn sử dụng trạng thái và các tính năng của React trong các hàm không phải là thành phần lớp. Các hooks như useState và useEffect giúp quản lý trạng thái và thực hiện các tác vụ phụ trong hàm.

7. Virtual DOM (DOM ảo): Virtual DOM là một bản sao của DOM thực tế trong trình duyệt. React sử dụng Virtual DOM để cải thiện hiệu suất bằng cách cập nhật chỉ các phần tử thực sự thay đổi thay vì cập nhật toàn bộ DOM.

Đây chỉ là một số khái niệm cơ bản trong React. Có rất nhiều khái niệm và khái niệm nâng cao khác trong React mà bạn có thể khám phá thêm khi làm việc với nó.
