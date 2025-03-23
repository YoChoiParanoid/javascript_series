# Kế thừa Class
- Sử dụng từ khóa `extends` để kế thừa một class trong JS

- Một class được tạo bằng kế thừa sẽ thừa hưởng tất cả phương thức từ class cha.

- Lợi ích của kế thừa
    - Giúp tái sử dụng code bằng cách không cần viết lại các phương thức chung.

    - Dễ mở rộng tính năng cho class con.

## Ví dụ 1
```javascript
class Car {
    constructor(brand) {
        this.carname = brand;
    }

    present() {
        return 'I have a ' + this.carname;
    }
}

class Model extends Car {
    constructor(brand, mod) {
        super(brand);
        this.model = mod;
    }

    show() {
        return this.present() + ", it is a " + this.model;
    }
}

let myCar = newModel("Ford", "Mustang");
document.getElementById("demo").innerHTML = myCar.show();
```

### Giải thích
- `Model` kế thừa từ `Car` bằng `extends Car`.

- Phương thức `super(brand);` trong constructor của `Model` gọi constructor của class `Car`, giúp kế thừa thuộc tính `carname`.

- Phương thức `present()` từ `Car` cũng được kế thừa trong `Model`.

- Phương thức `show()` kết hợp `present()` với thuộc tính `model` để tạo ra một chuỗi mô tả xe.