Short-circuit evaluation là một kỹ thuật được sử dụng trong JavaScript (JS) để đánh giá các biểu thức logic có chứa các toán tử logic "&&" và "||". Kỹ thuật này cho phép JS dừng việc đánh giá các biểu thức nếu kết quả cuối cùng có thể được xác định từ các giá trị trước đó, mà không cần phải đánh giá toàn bộ các biểu thức.

Trong JS, toán tử "&&" sẽ trả về giá trị đầu tiên trong biểu thức nếu nó là một giá trị sai (false), ngược lại nó sẽ trả về giá trị cuối cùng trong biểu thức. Khi biểu thức có nhiều hơn hai toán hạng, JS sẽ đánh giá từ trái sang phải. Nếu một giá trị sai được tìm thấy, JS sẽ dừng việc đánh giá và trả về giá trị sai đó mà không cần kiểm tra các toán hạng còn lại.

Ví dụ:
```js
var result = (false && true && true); 
console.log(result); // false

var result2 = (true && true && true); 
console.log(result2); // true
```
