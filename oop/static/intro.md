# Static Methods
- Là các phương thức được khai báo trên class chứ không phải trên các đối tượng được tạo ra từ lớp đó.

- Có nghĩa là không thể gọi `static method` trên một đối tượng, mà chỉ có thể gọi nó từ chính lớp.

## Khai báo
- Phương thức tĩnh được định nghĩa bằng cách sử dụng từ khóa static trước tên của phương thức.

```javascript
class Car {
    constructor(name) {
        this.name = name;
    }
    static hello() {
        return "Hello!!";
    }
}

const myCar = new Car("Ford");

// Gọi phương thức tĩnh trên lớp Car
document.getElementById("demo").innerHTML = Car.hello(); // Hợp lệ

// Gọi phương thức tĩnh trên một đối tượng sẽ gây lỗi!
document.getElementById("demo").innerHTML = myCar.hello(); // Lỗi!
```

## Sử dụng
- Mặc dù phương thức tĩnh không thể truy cập trực tiếp vào thuộc tính của đối tượng, nhưng có thể truyền đối tượng vào như một tham số.

```javascript
class Car {
    constructor(name) {
        this.name = name;
    }

    static hello(x) {
        return "Hello " + x.name;
    }
}

const myCar = new Car("Ford");

document.getElementById("demo").innerHTML = Car.hello(myCar); // ✅ Hợp lệ
```

## Ứng dụng
- Tạo các tiện ích (utility methods) mà không cần khởi tạo đối tượng.

- Xử lý dữ liệu chung mà không gắn với một đối tượng cụ thể.

- Thao tác với class-level dữ liệu
    - Ví dụ: đếm số lượng đối tượng được tạo.

```javascript
class Car {
    static count = 0; // Biến tĩnh

    constructor(name) {
        this.name = name;
        Car.count++; // Mỗi lần tạo xe, tăng count
    }

    static getCount() {
        return `Total Cars: ${Car.count}`;
    }
}

const car1 = new Car("Toyota");
const car2 = new Car("Honda");

console.log(Car.getCount()); // ✅ Output: "Total Cars: 2"
```