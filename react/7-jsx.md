# JSX   

What is JSX?
JSX là viết tắt của JavaScript XML.

JSX cho phép chúng ta viết html trong react.

JSX tạo ra 1 cách dễ dàng hơn để viết và thêm html trong react.

Sau đây là các ví dụ về JSX 
### Ví dụ cơ bản:
```js
import React from 'react';

const App = () => {
  return (
    <div>
      <h1>Hello, World!</h1>
      <p>This is a basic example of JSX in React.</p>
    </div>
  );
}

export default App;
```
### Sử dụng biểu thức JavaScript trong JSX:
```js
import React from 'react';

const App = () => {
  const name = 'John Doe';
  const age = 25;

  return (
    <div>
      <h1>Hello, {name}!</h1>
      <p>You are {age} years old.</p>
    </div>
  );
}
export default App;
```
### Sử dụng các thuộc tính (props) trong JSX:
```js
import React from 'react';

const Button = (props) => {
  return (
    <button onClick={props.onClick}>
      {props.label}
    </button>
  );
}

export default Button;
```
### Sử dụng vòng lặp để tạo danh sách trong JSX:
```js
import React from 'react';

const TodoList = (props) => {
  const todos = props.todos.map((todo, index) => (
    <li key={index}>{todo}</li>
  ));

  return (
    <ul>
      {todos}
    </ul>
  );
}

export default TodoList;
```
### Kết hợp JSX và CSS trong React:
```js
import React from 'react';

const App = () => {
  return (
    <div className="container">
      <h1 style={{ color: 'blue' }}>Styled Heading</h1>
      <p className="text">This paragraph has a custom style applied.</p>
    </div>
  );
}

export default App;
```
CẢNH BÁO:

Vì JSX gần với JavaScript hơn là so với HTML, React DOM sử dụng chuẩn quy tắc đặt tên camelCase cho thuộc tính thay vì dùng tên thuộc tính gốc của HTML.

Ví dụ, class trở thành className trong JSX, và tabindex trở thành tabIndex.


