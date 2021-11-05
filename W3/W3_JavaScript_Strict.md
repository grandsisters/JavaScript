## JavaScript Use Strict

"use strict"; JavaScript 코드가 "엄격한 모드"에서 실행되어야 함을 정의합니다.

---

### Strict mode 사용지침

이 "use strict"지시문은 ECMAScript 버전 5에서 새로 추가되었습니다.

이것은 문이 아니라 이전 버전의 JavaScript에서 무시되는 리터럴 표현식입니다.

"use strict"의 목적은 코드가 "엄격한 모드"에서 실행되어야 함을 나타내는 것입니다.

엄격 모드에서는 예를 들어 선언되지 않은 변수를 사용할 수 없습니다.

모든 최신 브라우저는 Internet Explorer 9 이하를 제외한 "엄격한 사용"을 지원합니다.

    모든 프로그램에서 엄격 모드를 사용할 수 있습니다. 선언되지 않은 변수를 사용하지 못하도록 하는 것과 같이 보다 깔끔한 코드를 작성하는 데 도움이 됩니다.

    "use strict" 는 단지 문자열이므로 IE 9는 이해하지 못하더라도 오류를 던지지 않습니다.

---

### 엄격 모드 선언

엄격 모드는 "use strict"를 추가하여 선언됩니다 . 스크립트나 함수의 시작 부분에

스크립트 시작 부분에 선언되며 전역 범위를 갖습니다(스크립트의 모든 코드는 엄격 모드에서 실행됨).

    예시
    "use strict";
    x = 3.14; // This will cause an error because x is not declared

<br />

    예시
    "use strict";
    myFunction();

    function myFunction() {
    y = 3.14; // This will also cause an error because y is not declared
    }

함수 내부에서 선언되고 로컬 범위를 갖습니다(함수 내부의 코드만 엄격 모드에 있음).

    x = 3.14; // This will not cause an error.
    myFunction();

    function myFunction() {
    "use strict";
    y = 3.14; // This will cause an error
    }

---

### The "use strict"; Syntax

엄격 모드를 선언하기 위한 구문은 이전 버전의 JavaScript와 호환되도록 설계되었습니다.

JavaScript 프로그램에서 숫자 리터럴(4 + 5;) 또는 문자열 리터럴("John Doe";)을 컴파일하면 부작용이 없습니다.

단순히 존재하지 않는 변수로 컴파일되고 죽습니다.

따라서 "use strict";의미를 "이해하는" 새로운 컴파일러에게만 중요합니다.

---

### 왜 엄격 모드인가?

엄격 모드를 사용하면 "보안" JavaScript를 더 쉽게 작성할 수 있습니다.

엄격 모드는 이전에 허용된 "잘못된 구문"을 실제 오류로 변경합니다.

예를 들어, 일반 JavaScript에서 변수 이름을 잘못 입력하면 새 전역 변수가 생성됩니다. 엄격 모드에서는 오류가 발생하여 실수로 전역 변수를 생성할 수 없습니다.

일반 JavaScript에서 개발자는 쓰기 불가능한 속성에 값을 할당하는 오류 피드백을 받지 않습니다.

엄격 모드에서 쓰기 불가능 속성, getter 전용 속성, 존재하지 않는 속성, 존재하지 않는 변수 또는 존재하지 않는 객체에 대한 할당은 오류를 발생시킵니다.

---

### 엄격 모드에서는 허용되지 않음

선언하지 않고 변수를 사용하는 것은 허용되지 않습니다.

    "use strict";
    x = 3.14; // This will cause an error

    객체도 변수입니다.

선언하지 않고 객체를 사용하는 것은 허용되지 않습니다:

    "use strict";
    x = {p1:10, p2:20}; // This will cause an error

변수(또는 개체) 삭제는 허용되지 않습니다.

    "use strict";
    let x = 3.14;
    delete x; // This will cause an error

기능 삭제는 허용되지 않습니다.

    "use strict";
    function x(p1, p2) {};
    delete x; // This will cause an error

매개변수 이름 복제는 허용되지 않습니다.

    "use strict";
    function x(p1, p1) {}; // This will cause an error

8진수 숫자 리터럴은 허용되지 않습니다.

    "use strict";
    let x = 010; // This will cause an error

8진 이스케이프 문자는 허용되지 않습니다.

    "use strict";
    let x = "\010"; // This will cause an error

읽기 전용 속성에 쓰는 것은 허용되지 않습니다.

    "use strict";
    const obj = {};
    Object.defineProperty(obj, "x", {value:0, writable:false});

    obj.x = 3.14; // This will cause an error

get-only 속성에 대한 쓰기는 허용되지 않습니다.

    "use strict";
    const obj = {get x() {return 0} };

    obj.x = 3.14; // This will cause an error

삭제할 수 없는 속성은 삭제할 수 없습니다.

    "use strict";
    delete Object.prototype; // This will cause an error

단어 eval는 변수로 사용할 수 없습니다.

    "use strict";
    let eval = 3.14; // This will cause an error

단어 arguments는 변수로 사용할 수 없습니다.

    "use strict";
    let arguments = 3.14; // This will cause an error

다음 with문장은 허용되지 않습니다.

    "use strict";
    with (Math){x = cos(2)}; // This will cause an error

보안상의 이유로 eval()은(는) 호출된 범위에서 변수를 생성할 수 없습니다.

    "use strict";
    eval ("let x = 2");
    alert (x); // This will cause an error

this함수 의 키워드는 엄격 모드에서 다르게 작동합니다.

this키워드는 함수를 호출 한 객체를 참조합니다.

객체가 지정되지 않은 경우 엄격 모드의 함수는 undefined가 반환 되고 일반 모드의 함수는 전역 객체(window)를 반환합니다.

    "use strict";
    function myFunction() {
    alert(this); // will alert "undefined"
    }
    myFunction();

향후 JavaScript 버전용으로 예약된 키워드는 엄격 모드에서 변수 이름으로 사용할 수 없습니다.

- implements
- interface
- let
- package
- private
- protected
- public
- static
- yield

<br />

    "use strict";
    let public = 1500; // This will cause an error

"use strict" 지시어는 스크립트나 함수 의 시작 부분 에서만 인식됩니다 .
