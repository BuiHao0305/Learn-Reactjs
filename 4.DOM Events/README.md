# DOM Events trong React

React cung cấp cách hiệu quả để xử lý và quản lý các sự kiện DOM thông qua hệ thống sự kiện tổng hợp (Synthetic Events). Điều này giúp đảm bảo tính tương thích giữa các trình duyệt và cung cấp API tương tự như các sự kiện DOM gốc.

---

## 🌟 **Tính Năng Chính**

1. Hỗ trợ đầy đủ các loại sự kiện DOM (click, keypress, mouseover, v.v.).
2. Đảm bảo tính nhất quán giữa các trình duyệt thông qua hệ thống Synthetic Events.
3. Sử dụng cú pháp đơn giản và dễ đọc.
4. Hỗ trợ xử lý các sự kiện tùy chỉnh.

---

## 🛠️ **Các Bước Sử Dụng DOM Events Trong React**

### **1. Gắn Sự Kiện Trực Tiếp Vào JSX**

Sử dụng các thuộc tính giống sự kiện DOM, nhưng với cách viết kiểu camelCase trong React.

#### Ví dụ:

```jsx
function App() {
  const handleClick = () => {
    alert("Button clicked!");
  };

  return <button onClick={handleClick}>Click Me</button>;
}
```

🖱️ **Các Loại DOM Events Phổ Biến Trong React**

### 1. **Mouse Events**

- **onClick**: Khi người dùng nhấp chuột vào phần tử.

  ```jsx
  <button onClick={() => alert("Button clicked!")}>Click Me</button>
  ```

- **onDoubleClick**: Khi người dùng nhấp đúp chuột vào phần tử.

  ```jsx
  <button onDoubleClick={() => alert("Button double-clicked!")}>
    Double Click Me
  </button>
  ```

- **onMouseOver**: Khi chuột di chuyển qua phần tử.

  ```jsx
  <div onMouseOver={() => console.log("Mouse is over the div!")}>
    Hover over me!
  </div>
  ```

- **onMouseOut**: Khi chuột rời khỏi phần tử.
  ```jsx
  <div onMouseOut={() => console.log("Mouse has left the div!")}>
    Move mouse out!
  </div>
  ```

### 2. **Keyboard Events**

- **onKeyPress**: Khi một phím được nhấn.

  ```jsx
  <input type="text" onKeyPress={(e) => console.log("Key pressed:", e.key)} />
  ```

- **onKeyDown**: Khi một phím được nhấn xuống.

  ```jsx
  <input type="text" onKeyDown={(e) => console.log("Key down:", e.key)} />
  ```

- **onKeyUp**: Khi một phím được nhả ra.
  ```jsx
  <input type="text" onKeyUp={(e) => console.log("Key up:", e.key)} />
  ```

### 3. **Form Events**

- **onChange**: Khi giá trị của input, textarea, hoặc select thay đổi.

  ```jsx
  <input
    type="text"
    onChange={(e) => console.log("Input value:", e.target.value)}
  />
  ```

- **onSubmit**: Khi một form được gửi đi.
  ```jsx
  <form
    onSubmit={(e) => {
      e.preventDefault();
      alert("Form submitted!");
    }}
  >
    <button type="submit">Submit</button>
  </form>
  ```

### 4. **Focus Events**

- **onFocus**: Khi phần tử nhận focus.

  ```jsx
  <input type="text" onFocus={() => console.log("Input focused")} />
  ```

- **onBlur**: Khi phần tử mất focus.
  ```jsx
  <input type="text" onBlur={() => console.log("Input lost focus")} />
  ```

### 5. **Other Events**

- **onScroll**: Khi cuộn trong một container.

  ```jsx
  <div onScroll={() => console.log("Scrolled!")}>Scroll me!</div>
  ```

- **onLoad**: Khi một hình ảnh hoặc tài liệu hoàn tất tải.
  ```jsx
  <img src="path/to/image.jpg" onLoad={() => console.log("Image loaded")} />
  ```
