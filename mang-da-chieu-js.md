
Trong JavaScript, mảng đa chiều có thể được tạo bằng cách sử dụng mảng lồng nhau.   
Một mảng đa chiều trong JavaScript thực chất là một mảng chứa các mảng khác, tạo thành một cấu trúc lưới.  
Dưới đây là một ví dụ về cách tạo và truy cập vào một mảng đa chiều trong JavaScript:  
```js
// Tạo một mảng đa chiều 2x3
let multiArray = [
  [1, 2, 3],
  [4, 5, 6]
];

// Truy cập vào các phần tử của mảng đa chiều
console.log(multiArray[0][0]); // Output: 1
console.log(multiArray[1][2]); // Output: 6

// Thay đổi giá trị của một phần tử trong mảng đa chiều
multiArray[0][1] = 9;
console.log(multiArray[0][1]); // Output: 9
```
