## JavaScript Let

Let 키워드는 ES6(2015)에 소개되었다.

let으로 정의된 변수는 재지정할 수 없습니다.

사용하기 전에 let으로 정의된 변수를 선언해야 합니다.

let 블록 범위를 사용하여 정의된 변수입니다.

---

### 재선언 불가

let로 정의된 변수는 다시 선언 할 수 없습니다 .

실수로 변수를 다시 선언할 일이 없습니다.

    예시
    let x = "John Doe";

    let x = 0;

    // SyntaxError: 'x' has already been declared

var의 경우엔 재선언이 가능

    예시
    var x = "John Doe";

    var x = 0;

---

### 블록 범위

ES6(2015) 이전에는 JavaScript에 전역 범위 와 함수 범위 만 있었습니다 .

ES6에는 두 가지 중요한 새 JavaScript 키워드인 let및 const 가 도입되었습니다 .

이 두 키워드는 JavaScript에서 블록 범위 를 제공합니다 .

{ } 블록 내부에 선언된 변수는 블록 외부에서 액세스할 수 없습니다.

    예시

    {
    let x = 2;
    }

    // x can NOT be used here

var키워드로 선언된 변수 는 블록 범위를 가질 수 없습니다.

{ } 블록 내부에 선언된 변수는 블록 외부에서 액세스할 수 있습니다.

    예시

    {
    var x = 2;
    }

    // x CAN be used here

---

### 변수 재선언

var키워드를 사용하여 변수를 다시 선언하면 문제가 발생할 수 있습니다.

블록 내부의 변수를 다시 선언하면 블록 외부의 변수도 다시 선언됩니다.

    예시

    var x = 10;
    // Here x is 10

    {
    var x = 2;
    // Here x is 2
    }

    // Here x is 2

let키워드를 사용하여 변수를 다시 선언하면 이 문제를 해결할 수 있습니다.

블록 내부의 변수를 다시 선언해도 블록 외부의 변수는 다시 선언되지 않습니다.

    예시

    let x = 10;
    // Here x is 10

    {
    let x = 2;
    // Here x is 2
    }

    // Here x is 10

---

### 재선언

var프로그램의 모든 위치에서 JavaScript 변수를 다시 선언하는 것은 허용됩니다.

    예시

    var x = 2;
    // Now x is 2

    var x = 3;
    // Now x is 3

Let은 블록의 변수를 재 선언하는 것은 허용되지 않는다 :

    예시
    var x = 2; // Allowed
    let x = 3; // Not allowed

    {
    let x = 2; // Allowed
    let x = 3 // Not allowed
    }

    {
    let x = 2; // Allowed
    var x = 3 // Not allowed
    }

let다른 블록에서 로 변수를 다시 선언하면 IS가 허용됩니다.

    예시
    let x = 2; // Allowed

    {
    let x = 3; // Allowed
    }

    {
    let x = 4; // Allowed
    }

---
