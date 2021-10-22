## JavaScript Function Invocation

JavaScript 내부의 코드 function는 "무언가"가 이를 호출할 때 실행됩니다.

---

### JavaScript 함수 호출

함수 내부의 코드는 함수가 정의 될 때 실행되지 않습니다 .

함수 내부의 코드는 함수가 호출 될 때 실행 됩니다 .

또한 "함수 호출", "함수 시작" 또는 "함수 실행"이라고 말하는 것이 일반적입니다.

---

### 함수를 함수로 호출하기

    예시
    function myFunction(a, b) {
    return a \* b;
    }
    myFunction(10, 2); // Will return 20

위의 함수는 어떤 객체에도 속하지 않습니다. 그러나 JavaScript에는 항상 기본 전역 객체가 있습니다.

HTML에서 기본 전역 개체는 HTML 페이지 자체이므로 위의 함수는 HTML 페이지에 "속합니다".

브라우저에서 페이지 개체는 브라우저 창입니다. 위의 함수는 자동으로 윈도우 함수가 됩니다.

myFunction() 및 window.myFunction()은 동일한 함수입니다.

    예시
    function myFunction(a, b) {
    return a \* b;
    }
    window.myFunction(10, 2); // Will also return 20

이것은 JavaScript 함수를 호출하는 일반적인 방법이지만 그다지 좋은 방법은 아닙니다.

전역 변수, 메서드 또는 함수는 전역 개체에서 이름 충돌과 버그를 쉽게 만들 수 있습니다.

---

### this 키워드

JavaScript에서 this라는 것은 현재 코드를 "소유"하는 객체입니다.

this의 값은 함수에서 사용될 때 함수를 "소유하는" 객체입니다.

this가 변수가 아니라는 점에 유의하십시오 . 키워드입니다. this의 값을 변경할 수 없습니다 .

---

### 전역 개체

소유자 객체 없이 함수를 호출하면 this의 값이 전역 객체가 됩니다.

웹 브라우저에서 전역 개체는 브라우저 창입니다.

이 예제는 this가 window 객체를 값으로 반환합니다 .

    예시
    let x = myFunction(); // x will be the window object

    function myFunction() {
    return this;
    }

함수를 전역 함수로 호출하면 this 의 값 이 전역 객체가 됩니다.

window 객체를 변수로 사용하면 프로그램이 쉽게 충돌할 수 있습니다.

---

### 함수를 메서드로 호출하기

JavaScript에서는 함수를 객체 메서드로 정의할 수 있습니다.

다음 예제에서는 두 개의 속성( firstName 및 lastName )과 메서드( fullName ) 가 있는 객체( myObject ) 를 만듭니다 .

    예시
    const myObject = {
    firstName:"John",
    lastName: "Doe",
    fullName: function () {
    return this.firstName + " " + this.lastName;
    }
    }
    myObject.fullName(); // Will return "John Doe"

fullName의의 메서드는 함수이다. 함수는 객체에 속합니다. myObject 는 함수의 소유자입니다.

JavaScript에서 this라는 것은 코드를 "소유"하는 객체입니다. 이 경우 this의 값 은 myObject 입니다.

테스트! 다음 값을 반환 하도록 this를 이용해 fullName 메서드를 변경합니다 .

    예시
    const myObject = {
    firstName:"John",
    lastName: "Doe",
    fullName: function () {
    return this;
    }
    }

    // This will return [object Object] (the owner object)
    myObject.fullName();

함수를 객체 메서드로 호출하면 this의 값이 개체 자체가 됩니다.

---

### 함수 생성자로 함수 호출

함수 호출 앞에 new키워드가 있으면 생성자 호출입니다.

새 함수를 만드는 것처럼 보이지만 JavaScript 함수는 객체이기 때문에 새 객체를 만듭니다.

    예시
    // This is a function constructor:
    function myFunction(arg1, arg2) {
    this.firstName = arg1;
    this.lastName = arg2;
    }

    // This creates a new object
    const myObj = new myFunction("John", "Doe");

    // This will return "John"
    myObj.firstName;

생성자 호출은 새 객체를 만듭니다. 새 객체는 생성자에서 속성과 메서드를 상속합니다.

생성자 의 this키워드에 값이 없습니다.

this의 값은 함수가 호출될 때 생성되는 새 객체입니다.
