Nullish operator trong JavaScript là một toán tử mới được giới thiệu trong phiên bản ECMAScript 2020 (còn được gọi là ES11) để kiểm tra giá trị nullish (null hoặc undefined). Nullish operator được biểu thị bằng hai dấu chấm kép (??).

Nullish operator trả về giá trị bên phải nếu giá trị bên trái là null hoặc undefined, ngược lại nó trả về giá trị bên trái. Điều này khác với toán tử OR (||), trong đó giá trị bên phải sẽ được trả về nếu giá trị bên trái là falsy (bằng false, 0, '', null, undefined hoặc NaN).

Dưới đây là một ví dụ minh họa về sử dụng nullish operator:
```js
const foo = null ?? 'default value';
console.log(foo); // Output: 'default value'

const bar = 0 ?? 42;
console.log(bar); // Output: 0

const baz = undefined ?? 'some value';
console.log(baz); // Output: 'some value'

const qux = false ?? true;
console.log(qux); // Output: false
```
Trong ví dụ trên, giá trị của biến foo được gán là 'default value' vì giá trị ban đầu của foo là null. Biến bar giữ giá trị 0 vì 0 không được coi là nullish. Biến baz chứa 'some value' vì giá trị ban đầu của baz là undefined. Cuối cùng, biến qux giữ giá trị false vì false không được xem là nullish.

Nullish operator là một cách tiện lợi để kiểm tra giá trị null hoặc undefined trong JavaScript và xử lý các giá trị mặc định.
