Trong JavaScript, thuật ngữ "truthsy" và "falsy" được sử dụng để mô tả cách mà giá trị của một biểu thức được đánh giá như là true hoặc false trong ngữ cảnh của một phép so sánh hoặc điều kiện.

Các giá trị "truthsy" trong JavaScript là những giá trị mà JavaScript coi là true khi được đánh giá trong một phép so sánh hoặc điều kiện. Các giá trị "truthsy" bao gồm:
- Boolean true: true là một giá trị boolean thể hiện sự đúng đắn.
- Số khác 0: Tất cả các số không phải 0 (ví dụ: 1, -1, 2.5) được coi là "truthsy".
- Chuỗi không rỗng: Một chuỗi có ít nhất một ký tự được coi là "truthsy".
- Một đối tượng không rỗng: Đối tượng JavaScript (bao gồm cả mảng và hàm) không rỗng được coi là "truthsy".
- Giá trị null: null là giá trị đặc biệt không có giá trị hoặc tham chiếu đến đối tượng. Null được coi là "falsy" và không phải "truthsy".
Các giá trị "falsy" trong JavaScript là những giá trị mà JavaScript coi là false khi được đánh giá trong một phép so sánh hoặc điều kiện. Các giá trị "falsy" bao gồm:
- Boolean false: false là giá trị boolean thể hiện sự sai.
- Số 0: Số 0 được coi là "falsy".
- Chuỗi rỗng: Một chuỗi không có ký tự nào được coi là "falsy".
- NaN: NaN là một giá trị đặc biệt thể hiện Not-a-Number. NaN được coi là "falsy".
- Giá trị null: null là giá trị đặc biệt không có giá trị hoặc tham chiếu đến đối tượng. Null được coi là "falsy".
- Giá trị undefined: undefined là một giá trị đặc biệt khi một biến không được gán giá trị. Undefined được coi là "falsy".
