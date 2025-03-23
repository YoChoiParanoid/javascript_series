# Getters và Setters trong Class
- Trong JavaScript, getters và setters là các phương thức đặc biệt giúp kiểm soát truy cập vào thuộc tính của đối tượng.
    - Getter (get): Dùng để lấy giá trị của một thuộc tính.

    - Setter (set): Dùng để cập nhật giá trị của một thuộc tính.

- Lợi ích:
    - Bảo vệ dữ liệu bên trong object.

    - Dễ dàng thực hiện các xử lý bổ sung khi truy xuất hoặc cập nhật dữ liệu.

    - Giúp code dễ đọc và gọn hơn.

## Cú pháp
```javascript
class Car {
    constructor(brand) {
        this._carname = brand; // Đặt "_" để phân biệt với getter/setter
    }

    get carname() {
        return this._carname;
    }

    set carname(newName) {
        if (newName.length > 0) {
            this._carname = newName;
        } else {
            console.log("Tên xe không hợp lệ!");
        }
    }
}

const myCar = new Car("Ford");

// Gọi getter (không cần dấu ngoặc)
console.log(myCar.carname); // Ford

// Gọi setter để thay đổi giá trị
myCar.carname = "Toyota";
console.log(myCar.carname); // Toyota

// Kiểm tra setter với giá trị rỗng
myCar.carname = ""; // "Tên xe không hợp lệ!"
```

## Lưu ý
- Không cần dùng dấu () khi gọi getter hoặc setter.

```javascript
console.log(myCar.carname); // Đúng
console.log(myCar.carname()); // Sai
```

- Không thể đặt getter/setter trùng tên với thuộc tính gốc.
    - Giải pháp: Dùng dấu gạch dưới `_` để tránh trùng tên.

- Chỉ dùng getter nếu không muốn thuộc tính bị thay đổi.