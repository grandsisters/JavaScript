## JavaScript Const

const 키워드는 ES6(2015)에 도입되었습니다.

const로 정의된 변수는 재지정할 수 없습니다.

const로 정의된 변수는 재할당할 수 없습니다.

const로 정의된 변수에는 블록 범위가 있습니다.

---

### 재할당할 수 없음

const변수를 재 할당 할 수 없습니다

예시
const PI = 3.141592653589793;
PI = 3.14; // This will give an error
PI = PI + 10; // This will also give an error

---

### 할당되어야 함

JavaScript const변수는 선언될 때 값을 할당해야 합니다.

    옳은
    const PI = 3.14159265359;

    잘못된
    const PI;
    PI = 3.14159265359;

---

### JavaScript const는 언제 사용합니까?

일반적으로 값이 변경될지 모르는 경우가 아니면 항상 const로 변수를 선언 하십시오.

이것들을 선언할 때 const사용을 권장:

- 새로운 어레이
- 새로운 객체
- 새로운 함수
- 새로운 정규 표현식

---

### Constant Arrays

const array의 요소를 변경할 수 있다.

    예시
    // You can create a constant array:
    const cars = ["Saab", "Volvo", "BMW"];

    // You can change an element:
    cars[0] = "Toyota";

    // You can add an element:
    cars.push("Audi");

그러나 어레이를 재할당할 수는 없습니다.

    예시
    const cars = ["Saab", "Volvo", "BMW"];

    cars = ["Toyota", "Volvo", "Audi"];    // ERROR

---

### 상수 객체

상수 객체의 속성을 변경할 수 있습니다.

    예시
    // You can create a const object:
    const car = {type:"Fiat", model:"500", color:"white"};

    // You can change a property:
    car.color = "red";

    // You can add a property:
    car.owner = "Johnson";

그러나 개체를 재할당할 수는 없습니다.

    예시
    const car = {type:"Fiat", model:"500", color:"white"};

    car = {type:"Volvo", model:"EX60", color:"red"}; // ERROR

---

### 블록 범위

const로 변수를 선언하는 것의 블록 범위는 let와 유사합니다 .

이 예에서 블록에서 선언된 x는 블록 외부에서 선언된 x와 동일하지 않습니다.

    예시
    const x = 10;
    // Here x is 10

    {
    const x = 2;
    // Here x is 2
    }

    // Here x is 10

---

### 재선언

JavaScript var변수를 다시 선언하는 것은 프로그램 어디에서나 허용됩니다.

    예시
    var x = 2; // Allowed
    var x = 3; // Allowed
    x = 4; // Allowed

동일한 범위에서 기존 var또는 let 변수를 const로 다시 선언하는 것은 허용되지 않습니다.

    예시
    var x = 2; // Allowed
    const x = 2; // Not allowed

    {
    let x = 2; // Allowed
    const x = 2; // Not allowed
    }

    {
    const x = 2; // Allowed
    const x = 2; // Not allowed
    }

const동일한 범위에서 기존 변수를 재할당하는 것은 허용되지 않습니다.

    예시
    const x = 2;     // Allowed
    x = 2;           // Not allowed
    var x = 2;       // Not allowed
    let x = 2;       // Not allowed
    const x = 2;     // Not allowed

    {
    const x = 2;   // Allowed
    x = 2;         // Not allowed
    var x = 2;     // Not allowed
    let x = 2;     // Not allowed
    const x = 2;   // Not allowed
    }

const다른 범위 또는 다른 블록에서 ,를 사용 하여 변수를 다시 선언하는 것은 허용됩니다.

    예시
    const x = 2;       // Allowed

    {
    const x = 3;   // Allowed
    }

    {
    const x = 4;   // Allowed
    }
