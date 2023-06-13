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







