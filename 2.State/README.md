# State - Kiểm Soát Trạng Thái Ứng Dụng trong React.js

**State** trong React là một trong những khái niệm cốt lõi dùng để quản lý **trạng thái của ứng dụng**. Nó đại diện cho dữ liệu động của component và quyết định cách component sẽ được hiển thị. Việc sử dụng state giúp ứng dụng trở nên tương tác và phản hồi với các hành động của người dùng.

---

## 1. Định nghĩa State

- **State** là một đối tượng JavaScript lưu trữ dữ liệu động của component.
- Khi state thay đổi, React sẽ tự động **re-render** component để hiển thị giao diện mới.
- State thường được sử dụng trong các component có logic phức tạp hoặc cần quản lý dữ liệu thay đổi theo thời gian.

---

## 2. Khai báo State

### Class Component

Trong các **class component**, state được khai báo và quản lý bằng cách sử dụng `this.state` và thay đổi với `this.setState`.

```jsx
import React, { Component } from "react";

class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0,
    };
  }

  increment = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.increment}>Increase</button>
      </div>
    );
  }
}
export default Counter;
```

---

### Functional Component (với React Hooks)

React khuyến khích sử dụng **functional components** kết hợp với **React Hooks** để quản lý state thông qua `useState`.

```jsx
import React, { useState } from "react";

const Counter = () => {
  const [count, setCount] = useState(0); // Khởi tạo state

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increase</button>
    </div>
  );
};

export default Counter;
```

---

## 3. Quản lý State

### a. Local State

- State được quản lý cục bộ bên trong một component.
- Dùng để lưu trữ dữ liệu chỉ liên quan đến component đó.

```jsx
const Toggle = () => {
  const [isOn, setIsOn] = useState(false);

  return <button onClick={() => setIsOn(!isOn)}>{isOn ? "ON" : "OFF"}</button>;
};
```

---

### b. Lift State Up

- Khi cần chia sẻ state giữa các component con, ta "nâng state lên" một component cha và truyền xuống thông qua props.

```jsx
const Parent = () => {
  const [value, setValue] = useState(0);

  return (
    <div>
      <Child value={value} setValue={setValue} />
    </div>
  );
};

const Child = ({ value, setValue }) => {
  return <button onClick={() => setValue(value + 1)}>Value: {value}</button>;
};
```

---

### c. State Management với Redux

Khi ứng dụng trở nên lớn và phức tạp, có thể sử dụng thư viện như **Redux** để quản lý state toàn cục.

---

## 4. Các lưu ý khi làm việc với State

1. **Không thay đổi State trực tiếp:**

   - Sử dụng `setState` (class component) hoặc `useState` (functional component) để thay đổi state.
   - Tránh việc thay đổi state trực tiếp, vì điều này sẽ không kích hoạt re-render.

   ```jsx
   // Sai
   this.state.count = 1;

   // Đúng
   this.setState({ count: 1 });
   ```

2. **State có thể bất đồng bộ:**

   - Khi cập nhật state phụ thuộc vào state trước đó, dùng hàm callback:

   ```jsx
   this.setState((prevState) => ({ count: prevState.count + 1 }));
   ```

3. **Tối ưu hóa việc quản lý state:**

   - Sử dụng state cục bộ cho dữ liệu ít thay đổi hoặc không liên quan đến toàn bộ ứng dụng.
   - Sử dụng state toàn cục hoặc Redux cho dữ liệu được chia sẻ giữa nhiều component.

4. **State vs Props:**
   - **State:** Thay đổi được, quản lý nội bộ component.
   - **Props:** Không thay đổi, được truyền từ component cha xuống component con.

---

State là yếu tố rất quan trọng trong việc phát triển ứng dụng React. Việc hiểu rõ và sử dụng hợp lý sẽ giúp bạn tạo ra các ứng dụng React hiệu quả và dễ bảo trì hơn.
