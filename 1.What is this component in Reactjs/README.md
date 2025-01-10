# Cấu Trúc Component trong ReactJS

Tài liệu này giải thích cấu trúc của một component trong ReactJS và hướng dẫn cách tạo, sử dụng các component trong dự án React của bạn.

## Các Loại Component

### 1. Functional Component (Component Hàm)

Functional components là cách hiện đại để tạo component trong ReactJS. Chúng là các hàm JavaScript đơn giản trả về JSX.

#### Ví dụ:

```javascript
import React from "react";

const MyComponent = () => {
  return (
    <div>
      <h1>Xin chào, đây là MyComponent!</h1>
    </div>
  );
};

export default MyComponent;
```

#### Điểm chính:

- Sử dụng một hàm để định nghĩa component.
- Sử dụng cú pháp JSX để mô tả giao diện.
- Component được xuất ra bằng `export default`.

---

### 2. Class Component (Component Lớp)

Class components sử dụng cú pháp class của ES6. Mặc dù vẫn được hỗ trợ, nhưng functional components được ưu tiên trong các ứng dụng React hiện đại.

#### Ví dụ:

```javascript
import React, { Component } from "react";

class MyComponent extends Component {
  render() {
    return (
      <div>
        <h1>Xin chào, đây là MyComponent!</h1>
      </div>
    );
  }
}

export default MyComponent;
```

#### Điểm chính:

- Kế thừa từ lớp `React.Component`.
- Định nghĩa phương thức `render` để trả về JSX.

---

## Sử Dụng Components

Bạn có thể sử dụng component bên trong các component khác bằng cách import và render chúng.

### Ví dụ:

```javascript
import React from "react";
import MyComponent from "./MyComponent";

const App = () => {
  return (
    <div>
      <h1>Ứng Dụng Chính</h1>
      <MyComponent />
    </div>
  );
};

export default App;
```

---

## Cấu Trúc Thư Mục cho Components

Tổ chức các component để dễ dàng mở rộng và bảo trì.

### Cấu trúc khuyến nghị:

```
src/
|-- components/
|   |-- MyComponent/
|   |   |-- MyComponent.js
|   |   |-- MyComponent.css
|   |-- AnotherComponent/
|       |-- AnotherComponent.js
|       |-- AnotherComponent.css
```

---

## Chạy Ứng Dụng React

### Các bước:

1. Cài đặt dependencies:

   ```bash
   npm install
   ```

2. Khởi chạy server phát triển:
   ```bash
   npm start
   ```

Ứng dụng React của bạn sẽ chạy trên `http://localhost:3000` theo mặc định.
