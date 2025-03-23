# Phương thức super()
- `super()` được dùng để gọi constructor của class cha

- `super.methodName()` có thể gọi phương thức của class cha.

## Ví dụ 2
```javascript
class Animal {
    speak() {
        return "Animal Sound";
    }
}

class Dog extends Animal {
    speak() {
        return super.speak() + " - Woof!";
    }
}

const myDog = new Dog();
console.log(myDog.speak());
```

### Giải thích
- `super.speak()` gọi phương thức `speak()` của class `Animal`.