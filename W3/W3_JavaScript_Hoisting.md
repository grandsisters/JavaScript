## JavaScript Hoisting

호이스팅은 선언을 맨 위로 이동하는 JavaScript의 기본 동작입니다.

---

### JavaScript 선언이 호이스트됩니다.

자바스크립트에서는 변수를 사용한 후에 선언할 수 있다.

즉, 변수는 선언되기 전에 사용할 수 있습니다.

    실시예 1
    x = 5; // Assign 5 to x

    elem = document.getElementById("demo"); // Find an element
    elem.innerHTML = x;                     // Display x in the element

    var x; // Declare x


    실시예 2
    var x; // Declare x
    x = 5; // Assign 5 to x

    elem = document.getElementById("demo"); // Find an element
    elem.innerHTML = x;                     // Display x in the element

이것을 이해하려면 "호이스팅"이라는 용어를 이해해야 합니다.

호이스팅은 모든 선언을 현재 범위의 맨 위로(현재 스크립트 또는 현재 함수의 맨 위로) 이동하는 JavaScript의 기본 동작입니다.

---

### let 및 const 키워드

let및 const로 정의된 변수 는 블록의 맨 위로 호이스트되지만 초기화 되지는 않습니다 .

의미: 코드 블록은 변수를 인식하지만 선언될 때까지 사용할 수 없습니다.

let변수를 선언하기 전에 사용하면 ReferenceError.

변수는 블록 시작부터 선언될 때까지 "시간적 사각지대"에 있습니다.

    예시
    다음 결과는 ReferenceError가 발생합니다.
    carName = "Volvo";
    let carName;

const변수를 선언하기 전에 사용하는 것은 구문 오류이므로 코드가 실행되지 않습니다.

    예시
    이 코드는 실행되지 않습니다.

    carName = "Volvo";
    const carName;

---

### JavaScript 초기화가 호이스팅되지 않음

JavaScript는 초기화가 아닌 선언만 호이스트합니다.

예 1 은 예 2 와 동일한 결과를 제공 하지 않습니다 .

    실시예 1
    var x = 5; // Initialize x
    var y = 7; // Initialize y

    elem = document.getElementById("demo"); // Find an element
    elem.innerHTML = x + " " + y; // Display x and y


    실시예 2
    var x = 5; // Initialize x

    elem = document.getElementById("demo"); // Find an element
    elem.innerHTML = x + " " + y; // Display x and y

    var y = 7; // Initialize y

마지막 예에서 y가 정의되지 않은 것이 말이 됩니까?

초기화(=7)가 아닌 선언(var y)만 맨 위로 올려지기 때문입니다.

호이스팅으로 인해 y가 사용되기 전에 선언되었지만 초기화가 호이스팅되지 않았기 때문에 y의 값은 정의되지 않았습니다.

예제 2는 다음과 같이 작성하는 것과 같습니다.

    예시
    var x = 5; // Initialize x
    var y; // Declare y

    elem = document.getElementById("demo"); // Find an element
    elem.innerHTML = x + " " + y; // Display x and y

    y = 7; // Assign 7 to y

---

### 맨 위에 변수를 선언하십시오!

호이스팅은 (많은 개발자에게) JavaScript의 알려지지 않았거나 간과된 동작입니다.

개발자가 호이스팅을 이해하지 못하면 프로그램에 버그(오류)가 포함될 수 있습니다.

버그를 방지하려면 항상 모든 범위의 시작 부분에 모든 변수를 선언하십시오.

이것이 JavaScript가 코드를 해석하는 방식이므로 항상 좋은 규칙입니다.

엄격 모드의 JavaScript는 변수가 선언되지 않은 경우 사용할 수 없습니다. 다음 장에서 "use strict" 를
공부 하십시오.
