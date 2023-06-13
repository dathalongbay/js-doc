# React function component  
| Định nghĩa      | 
| ----------- | 
| React Function Components - còn được gọi là React Functional Components - là tiêu chuẩn trong việc viết ứng dụng React hiện đại. Trước đây, đã có nhiều loại React Component khác nhau, nhưng với sự ra đời của React Hooks, bạn có thể viết toàn bộ ứng dụng của mình chỉ bằng các hàm như các thành phần React.      | 

### REACT FUNCTION COMPONENT EXAMPLE
Hãy bắt đầu với 1 ví dụ đơn giản của Functional Component trong React bằng cách định nghĩa 1 component App trả về 1 JSX
```js
import React from 'react';

function App() {
  const greeting = 'Hello Function Component!';

  return <h1>{greeting}</h1>;
}

export default App;
```
Đó đã là Cú pháp Chức năng Cơ bản của React. Định nghĩa của thành phần xảy ra chỉ bằng một Hàm JavaScript phải trả về JSX - cú pháp của React để xác định một sự kết hợp của HTML và JavaScript, trong đó JavaScript được sử dụng với dấu ngoặc nhọn trong HTML. Trong trường hợp của chúng ta, chúng ta hiển thị một biến được gọi là "greeting", được định nghĩa trong thân hàm của thành phần và được trả về dưới dạng tiêu đề HTML trong JSX.

Chú ý: Nếu bạn đã quen với các thành phần lớp React (React Class Components), bạn có thể đã nhận ra rằng một Chức năng Component là một React Component mà không có hàm render. Mọi thứ được định nghĩa trong thân của hàm chính là hàm render, cuối cùng nó trả về JSX.

#### Bây giờ, nếu bạn muốn hiển thị một React Component bên trong một Function Component, bạn định nghĩa một thành phần khác và hiển thị nó như một phần tử HTML bằng JSX trong thân của thành phần khác:
```js
import React from 'react';

function App() {
  return <Headline />;
}

function Headline() {
  const greeting = 'Hello Function Component!';

  return <h1>{greeting}</h1>;
}

export default App;
```

Cơ bản, bạn có một hàm như một Child Component bây giờ. Định nghĩa React Components và hiển thị chúng lồng trong nhau làm cho việc Composition trong React trở nên khả thi. Bạn có thể quyết định nơi hiển thị một thành phần và cách hiển thị nó.

### Composition trong react là gì ?

Composition trong React là một khái niệm quan trọng trong việc xây dựng giao diện người dùng (UI) linh hoạt và tái sử dụng trong React. Nó cho phép bạn xây dựng các thành phần lớn bằng cách kết hợp hoặc nhúng các thành phần nhỏ hơn vào bên trong chúng.

Trong React, Composition có nghĩa là bạn có thể sử dụng các thành phần (component) nhỏ hơn để xây dựng thành phần lớn hơn. Thay vì viết mã lặp đi lặp lại, bạn có thể tái sử dụng các thành phần đã có sẵn và kết hợp chúng lại với nhau để tạo thành các thành phần phức tạp hơn. Điều này giúp tăng tính modular, khả năng mở rộng và quản lý dễ dàng trong việc phát triển ứng dụng React.

Ví dụ, bạn có thể có một thành phần Header, một thành phần Sidebar và một thành phần MainContent. Thay vì định nghĩa tất cả các thành phần này trong một thành phần duy nhất, bạn có thể kết hợp chúng lại trong một thành phần cha gọi là App, bằng cách nhúng Header, Sidebar và MainContent vào bên trong App. Điều này giúp bạn quản lý các thành phần riêng lẻ một cách độc lập và tái sử dụng chúng trong các phần khác nhau của ứng dụng của bạn.

Tổ chức các thành phần theo cách này giúp tạo ra một cây thành phần phức tạp, trong đó mỗi thành phần có trách nhiệm duy nhất và có thể được quản lý một cách riêng biệt.

### REACT FUNCTION COMPONENT: PROPS
Hãy tìm hiểu về một React Function Component với props. Trong React, props được sử dụng để truyền thông tin từ thành phần này sang thành phần khác. Cơ bản, props trong React luôn được truyền xuống cây thành phần:
```js
import React from 'react';

function App() {
  const greeting = 'Hello Function Component!';

  return <Headline value={greeting} />;
}

function Headline(props) {
  return <h1>{props.value}</h1>;
}

export default App;
```

Props là các tham số của React Function Component. Trong khi thành phần có thể giữ nguyên tính chất chung, chúng ta quyết định từ bên ngoài nó sẽ hiển thị như thế nào (hoặc hoạt động như thế nào). Khi hiển thị một thành phần (ví dụ: Headline trong thành phần App), bạn có thể truyền props như các thuộc tính HTML cho thành phần đó. Sau đó, trong Function Component, đối tượng props sẽ có sẵn như một đối số trong chữ ký hàm.

Vì props luôn được truyền dưới dạng đối tượng và hầu hết thời gian bạn cần trích xuất thông tin từ props, việc giải cấu trúc đối tượng trong JavaScript rất hữu ích. Bạn có thể sử dụng trực tiếp nó trong chữ ký hàm cho đối tượng props:
```js
import React from 'react';

function App() {
  const greeting = 'Hello Function Component!';

  return <Headline value={greeting} />;
}

function Headline({ value }) {
  return <h1>{value}</h1>;
}

export default App;
```
Chú ý: Nếu bạn quên việc giải cấu trúc JavaScript và chỉ truy cập props từ chữ ký hàm của thành phần như function Headline(value1, value2) { ... }, bạn có thể nhìn thấy thông báo lỗi "props undefined". Cách này không hoạt động vì props luôn có thể truy cập qua đối số đầu tiên của hàm và có thể được giải cấu trúc từ đó: function Headline({ value1, value2 }) { ... }.

Nếu bạn muốn tìm hiểu thêm các mẹo và thủ thuật về props trong React, hãy kiểm tra lại bài viết liên kết ở đầu phần này. Ở đó, bạn sẽ tìm hiểu về các trường hợp mà bạn không muốn giải cấu trúc props và chỉ đơn giản chuyển chúng đến thành phần con tiếp theo với cú pháp `...` được gọi là toán tử spread.

### REACT ARROW FUNCTION COMPONENT

Với sự ra đời của JavaScript ES6, các khái niệm lập trình mới đã được giới thiệu vào JavaScript và do đó vào React. Ví dụ, một hàm JavaScript có thể được biểu diễn dưới dạng lambda (arrow function). Đó là lý do tại sao một Function Component đôi khi được gọi là Arrow Function Components (hoặc có thể còn gọi là Lambda Function Component). Hãy xem thành phần React đã được tái cấu trúc của chúng ta sử dụng Arrow Function:

```js
import React from 'react';

const App = () => {
  const greeting = 'Hello Function Component!';

  return <Headline value={greeting} />;
};

const Headline = ({ value }) => {
  return <h1>{value}</h1>;
};

export default App;
```

Cả hai React Arrow Function Components trên  đều sử dụng một thân hàm trong khối hiện tại. Tuy nhiên, thành phần thứ hai có thể được viết gọn hơn với một thân hàm ngắn gọn, vì nó chỉ trả về đầu ra của thành phần mà không làm gì khác giữa quá trình. Khi loại bỏ dấu ngoặc nhọn, việc trả về rõ ràng trở thành một trả về ngầm định và cũng có thể được bỏ đi:
```js
import React from 'react';

const App = () => {
  const greeting = 'Hello Function Component!';

  return <Headline value={greeting} />;
};

const Headline = ({ value }) =>
  <h1>{value}</h1>;

export default App;
```
Khi sử dụng hàm mũi tên (arrow functions) cho các thành phần React, không có gì thay đổi đối với props. Chúng vẫn có thể truy cập như các đối số như trước đây. Đây là một React Function Component với ES6 Functions được biểu diễn dưới dạng mũi tên thay vì ES5 Functions, đó là cách mặc định hơn để biểu diễn các hàm trong JavaScript.

Chú ý: Nếu bạn gặp phải lỗi "React Component Arrow Function Unexpected Token", hãy đảm bảo rằng JavaScript ES6 có sẵn cho ứng dụng React của bạn. Thông thường khi sử dụng create-react-app, điều này sẽ được cung cấp. Nếu không, nếu bạn tự thiết lập dự án của mình, Babel sẽ bật các tính năng ES6 và các phiên bản mới hơn cho ứng dụng React của bạn.

### REACT STATELESS FUNCTION COMPONENT

Mọi thành phần mà chúng ta đã thấy cho đến nay có thể được gọi là Stateless Function Component. Chúng chỉ nhận đầu vào dưới dạng props và trả về đầu ra dưới dạng JSX: (props) => JSX. Đầu vào, chỉ khi có sẵn dưới dạng props, xác định đầu ra được hiển thị. Loại thành phần này không quản lý trạng thái và không có bất kỳ hiệu ứng phụ nào (ví dụ: truy cập vào bộ nhớ cục bộ của trình duyệt). Mọi người gọi chúng là Functional Stateless Components, vì chúng không có trạng thái và được biểu diễn bằng một hàm. Tuy nhiên, React Hooks đã làm cho việc có trạng thái trong Function Components trở thành điều có thể.






