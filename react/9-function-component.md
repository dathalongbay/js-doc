# React function component  
| Định nghĩa      | 
| ----------- | 
| React Function Components - còn được gọi là React Functional Components - là tiêu chuẩn trong việc viết ứng dụng React hiện đại. Trước đây, đã có nhiều loại React Component khác nhau, nhưng với sự ra đời của React Hooks, bạn có thể viết toàn bộ ứng dụng của mình chỉ bằng các hàm như các thành phần React.      | 

### REACT FUNCTION COMPONENT EXAMPLE
Hãy bắt đầu với 1 ví dụ đơn giản của Functional Component trong React bằng cách định nghĩa 1 component Hello1 trả về 1 JSX
```js
import React from 'react';

function App() {
  const greeting = 'Hello Function Component!';

  return <h1>{greeting}</h1>;
}

export default App;
```




