# React function component  
| Định nghĩa      | 
| ----------- | 
| React Function Components - còn được gọi là React Functional Components - là tiêu chuẩn trong việc viết ứng dụng React hiện đại. Trước đây, đã có nhiều loại React Component khác nhau, nhưng với sự ra đời của React Hooks, bạn có thể viết toàn bộ ứng dụng của mình chỉ bằng các hàm như các thành phần React.      | 

### REACT FUNCTION COMPONENT EXAMPLE
Hãy bắt đầu với 1 ví dụ đơn giản của Functional Component trong React bằng cách định nghĩa 1 component App trả về 1 JSX
```js
import React from 'react';

function App() {
  const greeting = 'Hello Function Component!';

  return <h1>{greeting}</h1>;
}

export default App;
```
Đó đã là Cú pháp Chức năng Cơ bản của React. Định nghĩa của thành phần xảy ra chỉ bằng một Hàm JavaScript phải trả về JSX - cú pháp của React để xác định một sự kết hợp của HTML và JavaScript, trong đó JavaScript được sử dụng với dấu ngoặc nhọn trong HTML. Trong trường hợp của chúng ta, chúng ta hiển thị một biến được gọi là "greeting", được định nghĩa trong thân hàm của thành phần và được trả về dưới dạng tiêu đề HTML trong JSX.

Chú ý: Nếu bạn đã quen với các thành phần lớp React (React Class Components), bạn có thể đã nhận ra rằng một Chức năng Component là một React Component mà không có hàm render. Mọi thứ được định nghĩa trong thân của hàm chính là hàm render, cuối cùng nó trả về JSX.

#### Bây giờ, nếu bạn muốn hiển thị một React Component bên trong một Function Component, bạn định nghĩa một thành phần khác và hiển thị nó như một phần tử HTML bằng JSX trong thân của thành phần khác:
```js
import React from 'react';

function App() {
  return <Headline />;
}

function Headline() {
  const greeting = 'Hello Function Component!';

  return <h1>{greeting}</h1>;
}

export default App;
```

Cơ bản, bạn có một hàm như một Child Component bây giờ. Định nghĩa React Components và hiển thị chúng lồng trong nhau làm cho việc Composition trong React trở nên khả thi. Bạn có thể quyết định nơi hiển thị một thành phần và cách hiển thị nó.

### Composition trong react là gì ?

Composition trong React là một khái niệm quan trọng trong việc xây dựng giao diện người dùng (UI) linh hoạt và tái sử dụng trong React. Nó cho phép bạn xây dựng các thành phần lớn bằng cách kết hợp hoặc nhúng các thành phần nhỏ hơn vào bên trong chúng.

Trong React, Composition có nghĩa là bạn có thể sử dụng các thành phần (component) nhỏ hơn để xây dựng thành phần lớn hơn. Thay vì viết mã lặp đi lặp lại, bạn có thể tái sử dụng các thành phần đã có sẵn và kết hợp chúng lại với nhau để tạo thành các thành phần phức tạp hơn. Điều này giúp tăng tính modular, khả năng mở rộng và quản lý dễ dàng trong việc phát triển ứng dụng React.

Ví dụ, bạn có thể có một thành phần Header, một thành phần Sidebar và một thành phần MainContent. Thay vì định nghĩa tất cả các thành phần này trong một thành phần duy nhất, bạn có thể kết hợp chúng lại trong một thành phần cha gọi là App, bằng cách nhúng Header, Sidebar và MainContent vào bên trong App. Điều này giúp bạn quản lý các thành phần riêng lẻ một cách độc lập và tái sử dụng chúng trong các phần khác nhau của ứng dụng của bạn.

Tổ chức các thành phần theo cách này giúp tạo ra một cây thành phần phức tạp, trong đó mỗi thành phần có trách nhiệm duy nhất và có thể được quản lý một cách riêng biệt.

### REACT FUNCTION COMPONENT: PROPS
Hãy tìm hiểu về một React Function Component với props. Trong React, props được sử dụng để truyền thông tin từ thành phần này sang thành phần khác. Cơ bản, props trong React luôn được truyền xuống cây thành phần:
```js
import React from 'react';

function App() {
  const greeting = 'Hello Function Component!';

  return <Headline value={greeting} />;
}

function Headline(props) {
  return <h1>{props.value}</h1>;
}

export default App;
```

Props là các tham số của React Function Component. Trong khi thành phần có thể giữ nguyên tính chất chung, chúng ta quyết định từ bên ngoài nó sẽ hiển thị như thế nào (hoặc hoạt động như thế nào). Khi hiển thị một thành phần (ví dụ: Headline trong thành phần App), bạn có thể truyền props như các thuộc tính HTML cho thành phần đó. Sau đó, trong Function Component, đối tượng props sẽ có sẵn như một đối số trong chữ ký hàm.

Vì props luôn được truyền dưới dạng đối tượng và hầu hết thời gian bạn cần trích xuất thông tin từ props, việc giải cấu trúc đối tượng trong JavaScript rất hữu ích. Bạn có thể sử dụng trực tiếp nó trong chữ ký hàm cho đối tượng props:
```js
import React from 'react';

function App() {
  const greeting = 'Hello Function Component!';

  return <Headline value={greeting} />;
}

function Headline({ value }) {
  return <h1>{value}</h1>;
}

export default App;
```
Chú ý: Nếu bạn quên việc giải cấu trúc JavaScript và chỉ truy cập props từ chữ ký hàm của thành phần như function Headline(value1, value2) { ... }, bạn có thể nhìn thấy thông báo lỗi "props undefined". Cách này không hoạt động vì props luôn có thể truy cập qua đối số đầu tiên của hàm và có thể được giải cấu trúc từ đó: function Headline({ value1, value2 }) { ... }.

Nếu bạn muốn tìm hiểu thêm các mẹo và thủ thuật về props trong React, hãy kiểm tra lại bài viết liên kết ở đầu phần này. Ở đó, bạn sẽ tìm hiểu về các trường hợp mà bạn không muốn giải cấu trúc props và chỉ đơn giản chuyển chúng đến thành phần con tiếp theo với cú pháp `...` được gọi là toán tử spread.

### REACT ARROW FUNCTION COMPONENT

Với sự ra đời của JavaScript ES6, các khái niệm lập trình mới đã được giới thiệu vào JavaScript và do đó vào React. Ví dụ, một hàm JavaScript có thể được biểu diễn dưới dạng lambda (arrow function). Đó là lý do tại sao một Function Component đôi khi được gọi là Arrow Function Components (hoặc có thể còn gọi là Lambda Function Component). Hãy xem thành phần React đã được tái cấu trúc của chúng ta sử dụng Arrow Function:

```js
import React from 'react';

const App = () => {
  const greeting = 'Hello Function Component!';

  return <Headline value={greeting} />;
};

const Headline = ({ value }) => {
  return <h1>{value}</h1>;
};

export default App;
```

Cả hai React Arrow Function Components trên  đều sử dụng một thân hàm trong khối hiện tại. Tuy nhiên, thành phần thứ hai có thể được viết gọn hơn với một thân hàm ngắn gọn, vì nó chỉ trả về đầu ra của thành phần mà không làm gì khác giữa quá trình. Khi loại bỏ dấu ngoặc nhọn, việc trả về rõ ràng trở thành một trả về ngầm định và cũng có thể được bỏ đi:
```js
import React from 'react';

const App = () => {
  const greeting = 'Hello Function Component!';

  return <Headline value={greeting} />;
};

const Headline = ({ value }) =>
  <h1>{value}</h1>;

export default App;
```
Khi sử dụng hàm mũi tên (arrow functions) cho các thành phần React, không có gì thay đổi đối với props. Chúng vẫn có thể truy cập như các đối số như trước đây. Đây là một React Function Component với ES6 Functions được biểu diễn dưới dạng mũi tên thay vì ES5 Functions, đó là cách mặc định hơn để biểu diễn các hàm trong JavaScript.

Chú ý: Nếu bạn gặp phải lỗi "React Component Arrow Function Unexpected Token", hãy đảm bảo rằng JavaScript ES6 có sẵn cho ứng dụng React của bạn. Thông thường khi sử dụng create-react-app, điều này sẽ được cung cấp. Nếu không, nếu bạn tự thiết lập dự án của mình, Babel sẽ bật các tính năng ES6 và các phiên bản mới hơn cho ứng dụng React của bạn.

### REACT STATELESS FUNCTION COMPONENT

Mọi thành phần mà chúng ta đã thấy cho đến nay có thể được gọi là Stateless Function Component. Chúng chỉ nhận đầu vào dưới dạng props và trả về đầu ra dưới dạng JSX: (props) => JSX. Đầu vào, chỉ khi có sẵn dưới dạng props, xác định đầu ra được hiển thị. Loại thành phần này không quản lý trạng thái và không có bất kỳ hiệu ứng phụ nào (ví dụ: truy cập vào bộ nhớ cục bộ của trình duyệt). Mọi người gọi chúng là Functional Stateless Components, vì chúng không có trạng thái và được biểu diễn bằng một hàm. Tuy nhiên, React Hooks đã làm cho việc có trạng thái trong Function Components trở thành điều có thể.

### REACT FUNCTION COMPONENT: STATE

React Hooks đã cho phép sử dụng trạng thái (và hiệu ứng phụ) trong Function Components. Cuối cùng chúng ta có thể tạo một React Function Component với trạng thái! Hãy nói rằng chúng ta đã chuyển toàn bộ logic sang Function Component khác của chúng ta và không truyền bất kỳ props nào cho nó:

```js
import React from 'react';

const App = () => {
  return <Headline />;
};

const Headline = () => {
  const greeting = 'Hello Function Component!';

  return <h1>{greeting}</h1>;
};

export default App;
```
Cho đến nay, người dùng của ứng dụng này không có cách nào tương tác với ứng dụng và do đó không có cách nào thay đổi biến greeting. Ứng dụng là tĩnh và không tương tác. Trạng thái là điều làm cho các thành phần React trở nên tương tác và cũng làm cho chúng thú vị. React Hook giúp chúng ta thực hiện điều đó:
```js
import React, { useState } from 'react';

const App = () => {
  return <Headline />;
};

const Headline = () => {
  const [greeting, setGreeting] = useState(
    'Hello Function Component!'
  );

  return <h1>{greeting}</h1>;
};

export default App;
```
Hook useState nhận một trạng thái ban đầu làm tham số và trả về một mảng chứa trạng thái hiện tại như phần tử đầu tiên và một hàm để thay đổi trạng thái như phần tử thứ hai. Chúng tôi sử dụng giải cấu trúc mảng JavaScript để truy cập cả hai phần tử bằng một biểu thức ngắn gọn. Ngoài ra, giải cấu trúc cho phép chúng tôi tự đặt tên biến.

Hãy thêm một trường nhập (input field) để thay đổi trạng thái với hàm setGreeting():

```js
import React, { useState } from 'react';

const App = () => {
  return <Headline />;
};

const Headline = () => {
  const [greeting, setGreeting] = useState(
    'Hello Function Component!'
  );

  return (
    <div>
      <h1>{greeting}</h1>

      <input
        type="text"
        value={greeting}
        onChange={event => setGreeting(event.target.value)}
      />
    </div>
  );
};

export default App;
```

Bằng cách cung cấp một trình xử lý sự kiện cho trường nhập (input field), chúng ta có thể thực hiện một hành động với một hàm gọi lại khi trường nhập thay đổi giá trị của nó. Như đối số của hàm gọi lại, chúng ta nhận được một sự kiện React tổng hợp (synthetic React event) giữ giá trị hiện tại của trường nhập. Giá trị này cuối cùng được sử dụng để thiết lập trạng thái mới cho Function Component bằng một hàm mũi tên trong dòng. Chúng ta sẽ thấy sau này làm cách nào để trích xuất hàm này từ đó.

Chú ý: Trường nhập (input field) cũng nhận giá trị của trạng thái của thành phần, bởi vì bạn muốn kiểm soát trạng thái (giá trị) của trường nhập và không để trạng thái nội bộ của phần tử HTML thay thế. Theo cách này, thành phần đã trở thành một thành phần kiểm soát (controlled component).

Như bạn đã thấy, React Hooks cho phép chúng ta sử dụng trạng thái trong React (Arrow) Function Components. Trong khi bạn đã sử dụng phương thức setState để viết trạng thái trong một Class Component, bạn có thể sử dụng hook useState để viết trạng thái trong một Function Component.

Chú ý: Nếu bạn muốn sử dụng Context của React trong Function Components, hãy xem Context Hook của React được gọi là useContext để đọc từ Context của React trong một thành phần.

### REACT FUNCTION COMPONENT: EVENT HANDLER

Trong ví dụ trước, bạn đã sử dụng trình xử lý sự kiện onChange cho trường nhập. Điều này là phù hợp, vì bạn muốn được thông báo mỗi khi giá trị nội bộ của trường nhập thay đổi. Trong trường hợp của các phần tử biểu mẫu HTML khác, bạn có một số trình xử lý sự kiện React khác nhau mà bạn có thể sử dụng như onClick, onMouseDown và onBlur.

Chú ý: Trình xử lý sự kiện onChange chỉ là một trong số các trình xử lý cho các phần tử biểu mẫu HTML. Ví dụ, một nút bấm sẽ cung cấp một trình xử lý sự kiện onClick để phản ứng với sự kiện nhấp chuột.

Cho đến nay, chúng ta đã sử dụng một hàm mũi tên để nhúng trình xử lý sự kiện cho trường nhập. Vậy làm thế nào để trích xuất nó thành một hàm đứng riêng trong thành phần? Nó sẽ trở thành một hàm có tên trong trường hợp đó:

```js
import React, { useState } from 'react';

const App = () => {
  return <Headline />;
};

const Headline = () => {
  const [greeting, setGreeting] = useState(
    'Hello Function Component!'
  );

  const handleChange = event => setGreeting(event.target.value);

  return (
    <div>
      <h1>{greeting}</h1>

      <input type="text" value={greeting} onChange={handleChange} />
    </div>
  );
};

export default App;
```
Chúng ta đã sử dụng một hàm mũi tên để định nghĩa hàm trong thành phần. Nếu bạn đã sử dụng các phương thức lớp trong React Class Components trước đây, cách định nghĩa hàm trong một React Function Component tương đương. Bạn có thể gọi nó là "React Function Component Methods" - tương đương với class components. Bạn có thể tạo hoặc thêm bao nhiêu hàm muốn trong Functional Component để làm trình xử lý sự kiện rõ ràng hoặc đóng gói logic nghiệp vụ khác.\

### REACT FUNCTION COMPONENT: CALLBACK FUNCTION

Mọi thứ xảy ra trong Child Function Component của chúng ta. Không có props được chuyển cho nó, mặc dù bạn đã thấy trước đó làm thế nào một biến chuỗi cho lời chào có thể được truyền từ Parent Component cho Child Component. Liệu có thể truyền một hàm cho một component dưới dạng prop không? Có cách nào để gọi một hàm của component từ bên ngoài! Hãy xem cách làm việc này:

```js
import React, { useState } from 'react';

const App = () => {
  const [greeting, setGreeting] = useState(
    'Hello Function Component!'
  );

  const handleChange = event => setGreeting(event.target.value);

  return (
    <Headline headline={greeting} onChangeHeadline={handleChange} />
  );
};

const Headline = ({ headline, onChangeHeadline }) => (
  <div>
    <h1>{headline}</h1>

    <input type="text" value={headline} onChange={onChangeHeadline} />
  </div>
);

export default App;
```
Đó là tất cả. Bạn có thể truyền một hàm cho một Child Component và xử lý những gì xảy ra trong Parent Component. Bạn cũng có thể thực hiện một số thứ trong Child Component (Headline component) cho hàm onChangeHeadline - như cắt bỏ khoảng trắng của giá trị - để thêm chức năng bổ sung bên trong Child Component. Đó là cách bạn có thể gọi một hàm của Child Component từ một Parent Component.

Hãy đưa ví dụ này một bước xa hơn bằng cách giới thiệu một Sibling Component cho component Headline. Đó có thể là một component Input trừu tượng:

```js
import React, { useState } from 'react';

const App = () => {
  const [greeting, setGreeting] = useState(
    'Hello Function Component!'
  );

  const handleChange = event => setGreeting(event.target.value);

  return (
    <div>
      <Headline headline={greeting} />

      <Input value={greeting} onChangeInput={handleChange}>
        Set Greeting:
      </Input>
    </div>
  );
};

const Headline = ({ headline }) => <h1>{headline}</h1>;

const Input = ({ value, onChangeInput, children }) => (
  <label>
    {children}
    <input type="text" value={value} onChange={onChangeInput} />
  </label>
);

export default App;
```
Tôi nghĩ đây là một ví dụ hoàn hảo nhưng tối giản để minh họa cách truyền hàm giữa các component dưới dạng props; và quan trọng hơn là cách chia sẻ một hàm giữa các component. Bạn có một Parent Component quản lý logic và hai Child Components - là các sibling - nhận props. Những props này luôn có thể bao gồm một hàm gọi lại để gọi một hàm trong một component khác. Đó là cách cơ bản để gọi một hàm trong các component khác nhau trong React.

### Override Component Function with React

Không nên xảy ra thường xuyên, nhưng tôi đã nghe người ta hỏi câu hỏi này. Làm thế nào để ghi đè một hàm của một component? Bạn cần tiếp cận theo cùng một phương pháp như khi ghi đè bất kỳ prop nào khác được truyền vào một component bằng cách đặt giá trị mặc định cho nó:

```js
import React from 'react';

const App = () => {
  const sayHello = () => console.log('Hello');

  return <Button handleClick={sayHello} />;
};

const Button = ({ handleClick }) => {
  const sayDefault = () => console.log('Default');

  const onClick = handleClick || sayDefault;

  return (
    <button type="button" onClick={onClick}>
      Button
    </button>
  );
};

export default App;
```
You can assign the default value in the function signature for the destructuring as well:
```js
import React from 'react';

const App = () => {
  const sayHello = () => console.log('Hello');

  return <Button handleClick={sayHello} />;
};

const Button = ({ handleClick = () => console.log('Default') }) => (
  <button type="button" onClick={handleClick}>
    Button
  </button>
);

export default App;
```

Bạn cũng có thể đặt giá trị mặc định cho props của một React Function Component - đây là một lựa chọn khác:

```js
import React from 'react';

const App = () => {
  const sayHello = () => console.log('Hello');

  return <Button handleClick={sayHello} />;
};

const Button = ({ handleClick }) => (
  <button type="button" onClick={handleClick}>
    Button
  </button>
);

Button.defaultProps = {
  handleClick: () => console.log('Default'),
};

export default App;
```
Tất cả các phương pháp này có thể được sử dụng để định nghĩa default props (trong trường hợp này là một hàm mặc định), để sau đó có thể ghi đè nó từ bên ngoài bằng cách truyền một prop rõ ràng (ví dụ: một hàm) cho component.

### Async Function in Component with React

Trường hợp đặc biệt khác có thể là một hàm bất đồng bộ (async function) trong một component React. Nhưng không có gì đặc biệt về điều đó, vì không quan trọng hàm được thực thi bất đồng bộ hay không:

```js
import React from 'react';

const App = () => {
  const sayHello = () =>
    setTimeout(() => console.log('Hello'), 1000);

  return <Button handleClick={sayHello} />;
};

const Button = ({ handleClick }) => (
  <button type="button" onClick={handleClick}>
    Button
  </button>
);

export default App;
```

Hàm sẽ được thực thi với độ trễ mà không cần bất kỳ chỉ thị nào khác từ phía bạn bên trong component. Component cũng sẽ được kích hoạt để render lại bất đồng bộ trong trường hợp props hoặc state đã thay đổi. Hãy xem mã sau đây để thấy cách chúng ta thiết lập state với độ trễ nhân tạo bằng cách sử dụng setTimeout:

```js
import React, { useState } from 'react';

const App = () => {
  const [count, setCount] = useState(0);

  const handleIncrement = () =>
    setTimeout(
      () => setCount(currentCount => currentCount + 1),
      1000
    );

  const handleDecrement = () =>
    setTimeout(
      () => setCount(currentCount => currentCount - 1),
      1000
    );

  return (
    <div>
      <h1>{count}</h1>

      <Button handleClick={handleIncrement}>Increment</Button>
      <Button handleClick={handleDecrement}>Decrement</Button>
    </div>
  );
};

const Button = ({ handleClick, children }) => (
  <button type="button" onClick={handleClick}>
    {children}
  </button>
);

export default App;
```

Lưu ý rằng chúng ta sử dụng một hàm callback bên trong hàm setCount để truy cập vào state hiện tại. Vì các hàm setter từ useState được thực thi bất đồng bộ theo bản chất, bạn muốn đảm bảo thực hiện thay đổi state trên state hiện tại và không phải trên bất kỳ state cũ nào.

Thí nghiệm: Nếu bạn không sử dụng hàm callback bên trong State Hook, mà thay vào đó thực hiện trên biến count trực tiếp (ví dụ: setCount(count + 1)), bạn sẽ không thể tăng giá trị từ 0 lên 2 với một lần nhấp đúp nhanh, vì cả hai lần hàm sẽ được thực thi trên một count state là 0.

### REACT FUNCTION COMPONENT: LIFECYCLE

Nếu bạn đã sử dụng React Class Components trước đây, có thể bạn đã quen với các phương thức lifecycle như componentDidMount, componentWillUnmount và shouldComponentUpdate. Bạn không có những phương thức này trong Function Components, vì vậy hãy xem cách bạn có thể thay thế chúng.

Trước hết, bạn không có constructor trong một Function Component. Thông thường, constructor được sử dụng trong một React Class Component để cấp phát state ban đầu. Như bạn đã thấy, bạn không cần nó trong một Function Component, vì bạn cấp phát state ban đầu bằng cách sử dụng useState hook và thiết lập các hàm bên trong Function Component cho logic kinh doanh tiếp theo:

```js
import React, { useState } from 'react';

const App = () => {
  const [count, setCount] = useState(0);

  const handleIncrement = () =>
    setCount(currentCount => currentCount + 1);

  const handleDecrement = () =>
    setCount(currentCount => currentCount - 1);

  return (
    <div>
      <h1>{count}</h1>

      <button type="button" onClick={handleIncrement}>
        Increment
      </button>
      <button type="button" onClick={handleDecrement}>
        Decrement
      </button>
    </div>
  );
};

export default App;
```

### React Functional Component: Mount

Thứ hai, có một vòng đời lắp đặt cho các thành phần React khi chúng được hiển thị lần đầu. Nếu bạn muốn thực hiện một công việc nào đó khi một React Function Component đã được lắp đặt, bạn có thể sử dụng hook useEffect:

```js 
import React, { useState, useEffect } from 'react';

const App = () => {
  const [count, setCount] = useState(0);

  const handleIncrement = () =>
    setCount(currentCount => currentCount + 1);

  const handleDecrement = () =>
    setCount(currentCount => currentCount - 1);

  useEffect(() => setCount(currentCount => currentCount + 1), []);

  return (
    <div>
      <h1>{count}</h1>

      <button type="button" onClick={handleIncrement}>
        Increment
      </button>
      <button type="button" onClick={handleDecrement}>
        Decrement
      </button>
    </div>
  );
};

export default App;
```
Nếu bạn thử ví dụ này, bạn sẽ thấy số đếm 0 và 1 hiển thị ngắn gọn sau nhau. Việc hiển thị đầu tiên của thành phần hiển thị số đếm 0 từ trạng thái ban đầu - sau khi thành phần đã được lắp đặt, hook useEffect sẽ chạy để đặt trạng thái số đếm mới là 1.

Quan trọng lưu ý về mảng rỗng là đối số thứ hai của hook useEffect, nó đảm bảo kích hoạt hiệu ứng chỉ khi thành phần được tải (mount) và giải tải (unmount).

Thử nghiệm: Nếu bạn để đối số thứ hai của hook useEffect trống, bạn sẽ gặp vòng lặp vô tận của việc tăng số đếm lên 1, vì hook useEffect luôn chạy sau khi trạng thái đã thay đổi. Vì hook useEffect kích hoạt một trạng thái thay đổi khác, nó sẽ chạy đi chạy lại để tăng số đếm.

### React Functional Component: Update

Mỗi khi props hoặc state của thành phần thay đổi, thành phần kích hoạt một lần render lại để hiển thị trạng thái mới nhất, thường được xuất phát từ props và state. Một lần render thực thi tất cả những gì trong thân của Function Component.

Lưu ý: Trong trường hợp một Function Component không cập nhật đúng trong ứng dụng của bạn, việc sử dụng console log cho state và props của thành phần là một cách gỡ lỗi đầu tiên hiệu quả. Nếu cả hai không thay đổi, không có lần render mới được thực thi và do đó bạn sẽ không thấy console log đầu ra trong trường hợp đó.

```js
import React, { useState, useEffect } from 'react';

const App = () => {
  console.log('Does it render?');

  const [count, setCount] = useState(0);

  console.log(`My count is ${count}!`);

  const handleIncrement = () =>
    setCount(currentCount => currentCount + 1);

  const handleDecrement = () =>
    setCount(currentCount => currentCount - 1);

  return (
    <div>
      <h1>{count}</h1>

      <button type="button" onClick={handleIncrement}>
        Increment
      </button>
      <button type="button" onClick={handleDecrement}>
        Decrement
      </button>
    </div>
  );
};

export default App;
```
Nếu bạn muốn thực hiện một hành động sau khi một lần render lại, bạn có thể sử dụng Effect Hook một lần nữa để làm điều đó sau khi thành phần đã cập nhật:

```js
import React, { useState, useEffect } from 'react';

const App = () => {
  const initialCount = +localStorage.getItem('storageCount') || 0;
  const [count, setCount] = useState(initialCount);

  const handleIncrement = () =>
    setCount(currentCount => currentCount + 1);

  const handleDecrement = () =>
    setCount(currentCount => currentCount - 1);

  useEffect(() => localStorage.setItem('storageCount', count));

  return (
    <div>
      <h1>{count}</h1>

      <button type="button" onClick={handleIncrement}>
        Increment
      </button>
      <button type="button" onClick={handleDecrement}>
        Decrement
      </button>
    </div>
  );
};

export default App;
```




