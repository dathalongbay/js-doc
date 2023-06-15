Tutorial: Đồng bộ và Bất đồng bộ trong JavaScript

Trong JavaScript, đồng bộ (synchronous) và bất đồng bộ (asynchronous) là hai cách tiếp cận để xử lý các tác vụ. Đồng bộ có nghĩa là các tác vụ được thực hiện theo thứ tự từ trên xuống dưới, trong khi bất đồng bộ cho phép các tác vụ chạy đồng thời và không chờ đợi nhau hoàn thành. Trong bài viết này, chúng ta sẽ tìm hiểu về cả hai cách tiếp cận này và cách áp dụng chúng trong JavaScript.

1. Đồng bộ (Synchronous):

Trong JavaScript, mặc định là đồng bộ. Điều này có nghĩa là các tác vụ sẽ thực hiện theo thứ tự từ trên xuống dưới và phải chờ đợi tác vụ trước hoàn thành mới tiếp tục tác vụ sau. Đây là một ví dụ đơn giản về cách thực hiện đồng bộ trong JavaScript:

```javascript
console.log("Bắt đầu");

function doSomething() {
  console.log("Tác vụ 1");
  console.log("Tác vụ 2");
}

doSomething();

console.log("Kết thúc");
```

Kết quả đầu ra sẽ là:

```
Bắt đầu
Tác vụ 1
Tác vụ 2
Kết thúc
```

2. Bất đồng bộ (Asynchronous):

Trong JavaScript, bất đồng bộ được sử dụng khi có các tác vụ mà chúng ta không muốn chờ đợi hoàn thành trước khi tiếp tục các tác vụ khác. Thông thường, các tác vụ bất đồng bộ được thực hiện thông qua sử dụng callbacks, promises hoặc async/await. Dưới đây là ví dụ về việc sử dụng callbacks để thực hiện tác vụ bất đồng bộ:

```javascript
console.log("Bắt đầu");

function doSomething(callback) {
  setTimeout(function() {
    console.log("Tác vụ bất đồng bộ");
    callback();
  }, 2000);
}

function done() {
  console.log("Kết thúc");
}

doSomething(done);
```

Trong ví dụ trên, hàm `doSomething` là một tác vụ bất đồng bộ và sử dụng `setTimeout` để giả lập thời gian chờ. Khi tác vụ hoàn thành, nó sẽ gọi lại hàm `callback` được truyền vào và tiếp tục thực hiện các tác vụ tiếp theo.

Kết quả đầu ra sẽ là:

```
Bắt đầu
Tác vụ bất đồng bộ
Kết
