## JavaScript Style Guide

모든 JavaScript 프로젝트에 대해 항상 동일한 코딩 규칙을 사용하십시오.

---

### 자바스크립트 코딩 규칙

코딩 규칙은 프로그래밍을 위한 스타일 지침입니다 . 일반적으로 다음을 다룹니다.

- 변수 및 함수에 대한 명명 및 선언 규칙.
- 공백, 들여쓰기 및 주석 사용에 대한 규칙.
- 프로그래밍 관행 및 원칙

코딩 규칙은 품질을 보장합니다 .

- 코드 가독성 향상
- 코드 유지 관리가 쉬워집니다.

코딩 규칙은 팀이 따라야 하는 문서화된 규칙이거나 개인의 코딩 관행일 수 있습니다.

---

### 변수 이름

W3schools에서는 식별자 이름(변수 및 함수)에 camelCase 를 사용 합니다.

모든 이름은 문자로 시작합니다 .

이 페이지의 맨 아래에서 명명 규칙에 대한 광범위한 논의를 찾을 수 있습니다.

    firstName = "John";
    lastName = "Doe";

    price = 19.90;
    tax = 0.20;

    fullPrice = price + (price \* tax);

---

### 오퍼레이터 주변의 공간

항상 연산자( = + - \* / )와 쉼표 뒤에 공백을 넣으십시오.

    예:
    let x = y + z;
    const myArray = ["Volvo", "Saab", "Fiat"];

---

### 코드 들여쓰기

코드 블록의 들여쓰기에는 항상 2개의 공백을 사용하십시오.

    함수:
    function toCelsius(fahrenheit) {
    return (5 / 9) \* (fahrenheit - 32);
    }

들여쓰기에 탭(tabulator)을 사용하지 마십시오. 각각의 에디터는 탭을 다르게 해석합니다.

---

### statement 룰

간단한 문장에 대한 일반 규칙:

간단한 문장은 항상 세미콜론으로 끝내십시오.

    예:
    const cars = ["Volvo", "Saab", "Fiat"];

    const person = {
      firstName: "John",
      lastName: "Doe",
      age: 50,
      eyeColor: "blue"
    };

복잡한(복합) 문에 대한 일반 규칙:

- 여는 브래킷을 첫 번째 줄 끝에 놓습니다.
- 여는 대괄호 앞에 공백을 하나 사용하십시오.
- 선행 공백 없이 닫는 대괄호를 새 줄에 넣습니다.
- 복잡한 문장을 세미콜론으로 끝내지 마십시오.

### 함수:

    function toCelsius(fahrenheit) {
    return (5 / 9) \* (fahrenheit - 32);
    }

### 루프:

    for (let i = 0; i < 5; i++) {
    x += i;
    }

### 조건부:

    if (time < 20) {
    greeting = "Good day";
    } else {
    greeting = "Good evening";
    }

---

### 개체 규칙

객체 정의에 대한 일반 규칙:

- 여는 괄호를 개체 이름과 같은 줄에 놓습니다.
- 콜론과 각 속성과 해당 값 사이에 공백 하나를 사용합니다.
- 숫자 값이 아닌 문자열 값 주위에 따옴표를 사용하십시오.
- 마지막 속성-값 쌍 뒤에 쉼표를 추가하지 마십시오.
- 선행 공백 없이 새 줄에 닫는 대괄호를 놓습니다.
- 항상 세미콜론으로 개체 정의를 끝내십시오.

      예시
      const person = {
      firstName: "John",
      lastName: "Doe",
      age: 50,
      eyeColor: "blue"
      };

짧은 개체는 다음과 같이 속성 사이에만 공백을 사용하여 한 줄에 압축하여 쓸 수 있습니다.

    const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};

---

### 줄 길이 < 80

가독성을 위해 80자보다 긴 줄은 사용하지 마십시오.

JavaScript 문이 한 줄에 맞지 않는 경우 가장 좋은 위치는 연산자 또는 쉼표 뒤입니다.

    예시
    document.getElementById("demo").innerHTML =
    "Hello Dolly.";

---

### 명명 규칙

모든 코드에 대해 항상 동일한 명명 규칙을 사용하십시오. 예를 들어:

- camelCase로 작성된 변수 및 함수 이름
- 대문자로 작성된 전역 변수 (우리는 그렇지 않지만 꽤 일반적입니다)
- 대문자로 작성된 상수(예: PI)

하이픈 , 낙타 표기법 , 또는 under_scores 중 변수 이름에 어떤 것을 사용해야 할까?

이것은 프로그래머가 자주 논의하는 질문입니다. 대답은 누구에게 묻는가에 따라 다릅니다.

<br />

### HTML 및 CSS의 하이픈:

HTML5 속성은 data-(data-quantity, data-price)로 시작할 수 있습니다.

CSS는 속성 이름(글꼴 크기)에 하이픈을 사용합니다.

    하이픈은 빼기 시도로 오인될 수 있습니다. JavaScript 이름에는 하이픈을 사용할 수 없습니다.

<br />

### under_scores:

많은 프로그래머는 특히 SQL 데이터베이스에서 밑줄(date_of_birth)을 사용하는 것을 선호합니다.

밑줄은 PHP 문서에서 자주 사용됩니다.

<br />

### 파스칼케이스:

PascalCase는 종종 C 프로그래머가 선호합니다.

<br />

### 낙타 케이스:

camelCase는 JavaScript 자체, jQuery 및 기타 JavaScript 라이브러리에서 사용됩니다.

    $ 기호로 이름을 시작하지 마십시오. 많은 JavaScript 라이브러리 이름과 충돌하게 됩니다.

---

### HTML에서 JavaScript 로드

외부 스크립트를 로드하는 데 간단한 구문을 사용합니다(유형 속성은 필요하지 않음).

    <script src="myscript.js"></script>

---

### HTML 요소 액세스

"정확하지 않은" HTML 스타일을 사용하면 JavaScript 오류가 발생할 수 있습니다.

이 두 JavaScript 문은 다른 결과를 생성합니다.

    const obj = getElementById("Demo")

    const obj = getElementById("demo")

가능하면 HTML에서 동일한 명명 규칙(JavaScript와 같이)을 사용하십시오.

---

### 파일 확장자

HTML 파일에는 .html 확장자 가 있어야 합니다 ( .htm 허용).

CSS 파일의 확장자 는 .css 여야 합니다.

JavaScript 파일에는 .js 확장자 가 있어야 합니다 .

---

### 소문자 파일 이름 사용

대부분의 웹 서버(Apache, Unix)는 파일 이름에 대해 대소문자를 구분합니다.

london.jpg는 London.jpg로 액세스할 수 없습니다.

다른 웹 서버(Microsoft, IIS)는 대소문자를 구분하지 않습니다.

london.jpg는 London.jpg 또는 london.jpg로 액세스할 수 있습니다.

대문자와 소문자를 혼합하여 사용하는 경우 매우 일관성이 있어야 합니다.

대소문자를 구분하지 않는 서버에서 대소문자를 구분하는 서버로 이동하면 작은 오류로도 웹 사이트가 손상될 수 있습니다.

이러한 문제를 방지하려면 항상 소문자 파일 이름을 사용하십시오(가능한 경우).

---

코딩 규칙은 컴퓨터에서 사용되지 않습니다. 대부분의 규칙은 프로그램 실행에 거의 영향을 미치지 않습니다.

들여쓰기 및 추가 공백은 작은 스크립트에서 중요하지 않습니다.

개발 중인 코드의 경우 가독성이 우선되어야 합니다. 더 큰 프로덕션 스크립트는 최소화해야 합니다.
