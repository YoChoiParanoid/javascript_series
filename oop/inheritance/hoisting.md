# Hoisting
- Đối với các khai báo hàm hoặc các khai báo JS khác, sẽ không có lỗi khi ta cố gắng sử dụng trước khi khai báo
    - Bởi JS đã thực hiện hoisting (Di chuyển khai báo lên đầu)

- Không giống như các hàm và các khai báo JavaScript khác, khai báo class không được hoisting.

- Có nghĩa là ta phải khởi tạo lớp trước khi sử dụng

```javascript
// Cannot use the class yet.
// myCar = new Car("Ford") will raise an error.

class Car {
    constructor(brand) {
        this.carname = brand;
    }
}

//Now you can use the class:
const myCar = new Car("Ford")
```