# JSX
JSX (JavaScript XML): JSX là một phần cú pháp của React cho phép bạn viết các đoạn mã JavaScript trong HTML. JSX giúp tạo ra các thành phần UI trong React một cách rõ ràng và dễ đọc hơn.   
Sau đây là các ví dụ về JSX 
## Ví dụ cơ bản:
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
## Sử dụng biểu thức JavaScript trong JSX:
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
