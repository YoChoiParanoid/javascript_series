# JavaScript Classes
ECMAScript 2015 (ES6) đã giới thiệu JS Classes, giúp tạo các JS Object theo khuôn mẫu có sẵn.

## Cú pháp
- Sử dụng `class` keyword và `constructor()` method

    ```javascript
    class ClassName {
        constructor() {
            ...
        }
    }
    ```

- VD:
    - Tạo một class có tên là Car với hai thuộc tính:
        - name (tên xe)

        - year (năm sản xuất).

    ```javascript
    class Car {
        constructor(name, year) {
            this.name = name;
            this.year = year;
        }
    }
    ```

## Sử dụng class
- Dùng class thông qua việc tạo các đối tượng

    ```javascript
    const myCar1 = new Car("Ford", 2014);
    const myCar2 = new Car("Audi", 2019);
    ```

    - Khi một đối tượng mới được tạo từ class Car:
        - Phương thức constructor() sẽ được gọi tự động để khởi tạo giá trị cho các thuộc tính.

## Phương thức constructor()
- Tên phương thức bắt buộc là `constructor`

- Tự động chạy khi một đối tượng mới được khởi tạo

- Dùng để khởi tạo các thuộc tính của đối tượng

- Nếu không khai báo constructor(), JS sẽ tự thêm một constructor rỗng

## Phương thức trong Class
- Các phương thức trong class được khai báo giống nhưu một object

#### Cú pháp

```javascript
class ClassName {
    constructor() {

    }

    method_1() {

    }

    method_2() {

    }

    method_3() {

    }
}
```

#### Ví dụ
```javascript
class Car {
    constructor(name, year) {
        this.name = name;
        this.year = year;
    }

    age_v1() {
        const date = new Date();
        return date.getFullYear() - this.year;
    }

    age_v2(currentYear) {
        return currentYear - this.year;
    }
}

// age() version 1
const myCar1 = new Car("Ford", 2014);
document.getElementById("demo").innerHTML = "My car is " + myCar1.age() + " years old.";

// age() version 2
const date = new Date();
let year = date.getFullYear();
const myCar2 = new Car("Ford", 2014);
document.getElementById("demo").innerHTML = "My car is " + myCar2.age(year) + " years old.";
```

## Chế độ `Strict Mode`
- JavaScript Classes luôn hoạt động trong chế độ nghiêm ngặt ("use strict").

- Nếu không tuân theo quy tắc, chương trình sẽ báo lỗi.

- Ví dụ:
    - Khi không khai báo biến với const, let, hoặc var, chương trình sẽ báo lỗi.

    ```javascript
    class Car {
        constructor(name, year) {
            this.name = name;
            this.year = year;
        }
        age() {
            // date = new Date();  // Lỗi vì biến không được khai báo
            const date = new Date(); // Đúng
            return date.getFullYear() - this.year;
        }
    }
    ```