## JavaScript Scope

범위는 변수의 접근성(가시성)을 결정합니다.

JavaScript에는 3가지 유형의 범위가 있습니다.

- 전역 범위(global)
- 지역 범위(local)
  - 블록 범위
  - 함수 범위

---

### 블록 범위

ES6(2015) 이전에는 JavaScript에 전역 범위 와 함수 범위 만 있었습니다 .

ES6에는 두 가지 중요한 새 JavaScript 키워드인 let및 가 도입되었습니다 const.

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

### 로컬 범위

JavaScript 함수 내에서 선언된 변수는 함수에 대해 LOCAL 이 됩니다.

    예시
    // code here can NOT use carName

    function myFunction() {
    let carName = "Volvo";
    // code here CAN use carName
    }

    // code here can NOT use carName

<br />

    지역 변수에는 함수 범위가 있습니다 .

    함수 내에서만 액세스할 수 있습니다.

지역 변수는 함수 내에서만 인식되기 때문에 같은 이름의 변수를 다른 함수에서 사용할 수 있습니다.

지역 변수는 함수가 시작될 때 생성되고 함수가 완료되면 삭제됩니다.

---

### 함수 범위

JavaScript에는 함수 범위가 있습니다. 각 함수는 새 범위를 만듭니다.

함수 내부에 정의된 변수는 함수 외부에서 액세스할 수 없습니다(표시).

var, let 및 const로 선언된 변수는 함수 내부에서 선언할 때 매우 유사합니다.

모두 함수 범위가 있습니다 .

    function myFunction() {
    var carName = "Volvo"; // Function Scope
    }
    function myFunction() {
    let carName = "Volvo"; // Function Scope
    }
    function myFunction() {
    const carName = "Volvo"; // Function Scope
    }

---

### 전역 JavaScript 변수

함수 외부에서 선언된 변수는 GLOBAL 이 됩니다.

    예시
    let carName = "Volvo";
    // code here can use carName

    function myFunction() {
    // code here can also use carName
    }

전역 변수에는 전역 범위가 있습니다 .

웹 페이지의 모든 스크립트와 기능에서 액세스할 수 있습니다.

---

### 글로벌 범위

전역적으로 선언된 변수 (함수 외부)에는 전역 범위가 있습니다.

전역 변수는 JavaScript 프로그램의 어디에서나 액세스할 수 있습니다.

var, let 및 const로 선언된 변수는 블록 외부에서 선언할 때 매우 유사합니다.

모두 글로벌 범위가 있습니다 .

    var x = 2; // Global scope

    let x = 2; // Global scope

    const x = 2; // Global scope

---

### 자바스크립트 변수

JavaScript에서 객체와 함수도 변수입니다.

    범위는 코드의 다른 부분에서 변수, 개체 및 함수의 액세스 가능성을 결정합니다.

---

### 자동으로 전역

선언되지 않은 변수에 값을 할당하면 자동으로 GLOBAL 변수가 됩니다.

이 코드 예제는 carName값이 함수 내부에 할당된 경우에도 전역 변수를 선언 합니다.

    예시
    myFunction();

    // code here can use carName

    function myFunction() {
    carName = "Volvo";
    }

---

### 엄격한 모드(Strict mode)

모든 최신 브라우저는 "엄격한 모드"에서 JavaScript 실행을 지원합니다.

이 튜토리얼의 뒷부분에서 엄격 모드를 사용하는 방법에 대해 자세히 알아볼 것입니다.

"Strict Mode"에서 선언되지 않은 변수는 자동으로 전역적이지 않습니다.

---

### HTML의 전역 변수

JavaScript에서 전역 범위는 JavaScript 환경입니다.

HTML에서 전역 범위는 창 개체입니다.

var키워드로 정의된 전역 변수 는 창 개체에 속합니다.

    예시
    var carName = "Volvo";
    // code here can use window.carName
    let키워드로 정의된 전역 변수 는 창 개체에 속하지 않습니다.

    예시
    let carName = "Volvo";
    // code here can not use window.carName

---

### 경고

의도하지 않는 한 전역 변수를 생성하지 마십시오.

전역 변수(또는 함수)는 창 변수(또는 함수)를 덮어쓸 수 있습니다.
창 개체를 포함한 모든 함수는 전역 변수와 함수를 덮어쓸 수 있습니다.

---

### JavaScript 변수의 수명

JavaScript 변수의 수명은 선언될 때 시작됩니다.

함수(로컬) 변수는 함수가 완료되면 삭제됩니다.

웹 브라우저에서는 브라우저 창(또는 탭)을 닫으면 전역 변수가 삭제됩니다.

---

### 함수 인수

함수 인수(매개변수)는 함수 내에서 지역 변수로 작동합니다.
