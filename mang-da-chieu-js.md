
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
Trong ví dụ trên, multiArray là một mảng đa chiều có 2 hàng và 3 cột.   
Bạn có thể truy cập vào các phần tử bằng cách sử dụng cú pháp array[row][column].  
Ví dụ multiArray[0][0] trả về phần tử đầu tiên của mảng đa chiều là 1.  

Bạn có thể tạo mảng đa chiều với nhiều chiều hơn bằng cách lồng thêm các mảng trong mảng. Ví dụ:
```js
let multiArray = [
  [[1, 2], [3, 4]],
  [[5, 6], [7, 8]]
];

console.log(multiArray[0][1][0]); // Output: 3
```
Trên đây là cách sử dụng mảng đa chiều trong JavaScript.   
Bạn có thể tạo và làm việc với mảng đa chiều có số chiều tùy ý bằng cách lồng nhau các mảng như ví dụ bên trên.
