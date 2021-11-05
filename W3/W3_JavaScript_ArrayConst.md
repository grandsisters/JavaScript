## JavaScript Array Const

---

### 재할당할 수 없음

const로 선언된 배열은 재할당할 수 없습니다.

    예시
    const cars = ["Saab", "Volvo", "BMW"];
    cars = ["Toyota", "Volvo", "Audi"]; // ERROR

---

### 배열은 상수가 아닙니다

키워드 const가 약간 오해의 소지가 있습니다.

상수 배열을 정의하지 않습니다. 배열에 대한 상수 참조를 정의합니다.

이 때문에 우리는 여전히 상수 배열의 요소를 변경할 수 있습니다.

---

### 요소를 재할당할 수 있음

상수 배열의 요소를 변경할 수 있습니다.

    예시
    // You can create a constant array:
    const cars = ["Saab", "Volvo", "BMW"];

    // You can change an element:
    cars[0] = "Toyota";

    // You can add an element:
    cars.push("Audi");

---

### 선언 시 할당됨

JavaScript const변수는 선언될 때 값을 할당해야 합니다.

의미: 로 선언된 배열은 선언 const될 때 초기화되어야 합니다.

const배열을 초기화하지 않고 사용하면 구문 오류가 발생합니다.

    예시
    이것은 작동하지 않습니다:

    const cars;
    cars = ["Saab", "Volvo", "BMW"];

var로 선언된 배열은 언제든지 초기화할 수 있습니다.

선언하기 전에 배열을 사용할 수도 있습니다.

    예시

    cars = ["Saab", "Volvo", "BMW"];
    var cars;

---

### Const 블록 범위

const로 선언된 배열 에는 블록 범위가 있습니다.

블록에서 선언된 배열은 블록 외부에서 선언된 배열과 동일하지 않습니다.

    예시
    const cars = ["Saab", "Volvo", "BMW"];
    // Here cars[0] is "Saab"
    {
    const cars = ["Toyota", "Volvo", "BMW"];
    // Here cars[0] is "Toyota"
    }
    // Here cars[0] is "Saab"

var로 선언된 배열 에는 블록 범위가 없습니다.

    예시
    var cars = ["Saab", "Volvo", "BMW"];
    // Here cars[0] is "Saab"
    {
    var cars = ["Toyota", "Volvo", "BMW"];
    // Here cars[0] is "Toyota"
    }
    // Here cars[0] is "Toyota"

---

### 배열 재선언

var로 선언된 배열을 다시 선언하는 것은 프로그램의 어느 곳에서나 허용됩니다.

    예시
    var cars = ["Volvo", "BMW"]; // Allowed
    var cars = ["Toyota", "BMW"]; // Allowed
    cars = ["Volvo", "Saab"]; // Allowed

const동일한 범위 또는 동일한 블록에서 배열을 재선언하거나 재할당하는 것은 허용되지 않습니다.

    예시
    var cars = ["Volvo", "BMW"]; // Allowed
    const cars = ["Volvo", "BMW"]; // Not allowed
    {
    var cars = ["Volvo", "BMW"]; // Allowed
    const cars = ["Volvo", "BMW"]; // Not allowed
    }

const동일한 범위 또는 동일한 블록에서 기존 배열을 재선언하거나 재할당하는 것은 허용되지 않습니다.

    예시
    const cars = ["Volvo", "BMW"]; // Allowed
    const cars = ["Volvo", "BMW"]; // Not allowed
    var cars = ["Volvo", "BMW"]; // Not allowed
    cars = ["Volvo", "BMW"]; // Not allowed

    {
    const cars = ["Volvo", "BMW"]; // Allowed
    const cars = ["Volvo", "BMW"]; // Not allowed
    var cars = ["Volvo", "BMW"]; // Not allowed
    cars = ["Volvo", "BMW"]; // Not allowed
    }

const다른 범위 또는 다른 블록에서 를 사용 하여 배열을 다시 선언하는 것은 허용됩니다.

    예시
    const cars = ["Volvo", "BMW"]; // Allowed
    {
    const cars = ["Volvo", "BMW"]; // Allowed
    }
    {
    const cars = ["Volvo", "BMW"]; // Allowed
    }
