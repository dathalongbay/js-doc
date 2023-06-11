Từ phiên bản JavaScript ES2020 trở đi, dấu chấm hỏi ?. cung cấp cú pháp cho toán tử optional chaining. Đây là một cách để kiểm tra và truy cập các thuộc tính và phương thức của một đối tượng mà không gây ra lỗi nếu giá trị là null hoặc undefined. Ví dụ:
```js
var person = {
  name: "John",
  age: 25,
  address: {
    city: "New York",
    street: "123 ABC"
  }
};

var street = person.address?.street;
console.log(street); // Kết quả: "123 ABC"

var zipCode = person.address?.zipCode;
console.log(zipCode); // Kết quả: undefined
```
Trong ví dụ trên, person.address?.street được sử dụng để truy cập thuộc tính "street" của đối tượng person.address. Nếu person.address không tồn tại hoặc bằng null hoặc undefined, kết quả sẽ là undefined mà không gây ra lỗi.
