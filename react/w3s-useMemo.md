# React useMemo Hook
The React useMemo Hook trả về 1 giá trị "đã được ghi nhớ"

Hãy hiểu memoization như việc lưu trữ một giá trị để không cần tính toán lại.

Hook useMemo chỉ chạy khi một trong số các phụ thuộc của nó được cập nhật.

Điều này có thể cải thiện hiệu suất.

Cả hai Hook useMemo và useCallback tương tự nhau. Sự khác biệt chính là useMemo trả về một giá trị đã được ghi nhớ (memoized value), trong khi useCallback trả về một hàm đã được ghi nhớ (memoized function). 

## Performance Hiệu suất 
Hook useMemo có thể được sử dụng để ngăn chặn việc chạy không cần thiết các hàm tốn kém và tài nguyên.

Trong ví dụ này, chúng ta có một hàm tốn kém được chạy trong mỗi lần render.

Khi thay đổi giá trị của count hoặc thêm một todo, bạn sẽ nhận thấy sự trễ trong thực thi.

### Ví dụ : 
Một hàm có hiệu suất kém. Hàm expensiveCalculation được chạy trong mỗi lần render:
```js
import { useState } from "react";
import ReactDOM from "react-dom/client";

const App = () => {
  const [count, setCount] = useState(0);
  const [todos, setTodos] = useState([]);
  const calculation = expensiveCalculation(count);

  const increment = () => {
    setCount((c) => c + 1);
  };
  const addTodo = () => {
    setTodos((t) => [...t, "New Todo"]);
  };

  return (
    <div>
      <div>
        <h2>My Todos</h2>
        {todos.map((todo, index) => {
          return <p key={index}>{todo}</p>;
        })}
        <button onClick={addTodo}>Add Todo</button>
      </div>
      <hr />
      <div>
        Count: {count}
        <button onClick={increment}>+</button>
        <h2>Expensive Calculation</h2>
        {calculation}
      </div>
    </div>
  );
};

const expensiveCalculation = (num) => {
  console.log("Calculating...");
  for (let i = 0; i < 1000000000; i++) {
    num += 1;
  }
  return num;
};

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```
## Sử dụng useMemo
