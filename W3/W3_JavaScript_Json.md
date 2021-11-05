## JavaScript JSON

JSON은 데이터를 저장하고 전송하는 형식입니다.

JSON은 서버에서 웹 페이지로 데이터를 보낼 때 자주 사용됩니다.

---

### JSON이란 무엇입니까?

- JSON은 Java Script Object Notation의 약자 입니다.
- JSON은 경량 데이터 교환 형식입니다.
- JSON은 언어에 독립적입니다 \*
- JSON은 "자체 설명"이며 이해하기 쉽습니다.

JSON 구문은 JavaScript 객체 표기법 구문에서 파생되지만 JSON 형식은 텍스트 전용입니다. JSON 데이터를 읽고 생성하기 위한 코드는 모든 프로그래밍 언어로 작성할 수 있습니다.

---

### JSON 예제

이 JSON 구문은 직원 객체를 정의합니다. 3개의 직원 레코드(객체) 배열:

    JSON 예제
    {
    "employees":[
    {"firstName":"John", "lastName":"Doe"},
    {"firstName":"Anna", "lastName":"Smith"},
    {"firstName":"Peter", "lastName":"Jones"}
    ]
    }

---

### JSON 형식은 JavaScript 개체를 평가합니다.

JSON 형식은 JavaScript 객체를 생성하기 위한 코드와 구문적으로 동일합니다.

이러한 유사성 때문에 JavaScript 프로그램은 JSON 데이터를 기본 JavaScript 객체로 쉽게 변환할 수 있습니다.

---

### JSON 구문 규칙

- 데이터는 이름/값 쌍에 있습니다.
- 데이터는 쉼표로 구분됩니다.
- 중괄호는 객체를 보유합니다.
- 대괄호는 배열을 포함합니다.

---

### JSON 데이터 - 이름과 값

JSON 데이터는 JavaScript 객체 속성과 마찬가지로 이름/값 쌍으로 작성됩니다.

이름/값 쌍은 필드 이름(큰따옴표), 콜론, 값으로 구성됩니다.

    "firstName":"John"

JSON 이름에는 큰따옴표가 필요합니다. JavaScript 이름은 그렇지 않습니다.

---

### JSON 객체

JSON 객체는 중괄호 안에 작성됩니다.

JavaScript와 마찬가지로 객체에는 여러 이름/값 쌍이 포함될 수 있습니다.

    {"firstName":"John", "lastName":"Doe"}

---

### JSON 배열

JSON 배열은 대괄호 안에 작성됩니다.

JavaScript와 마찬가지로 배열에는 객체가 포함될 수 있습니다.

    "employees":[
      {"firstName":"John", "lastName":"Doe"},
      {"firstName":"Anna", "lastName":"Smith"},
      {"firstName":"Peter", "lastName":"Jones"}
    ]

위의 예에서 "employees" 개체는 배열입니다. 여기에는 세 개의 개체가 포함됩니다.

각 개체는 사람의 기록입니다(이름과 성을 포함).

---

### JSON 텍스트를 JavaScript 객체로 변환

JSON의 일반적인 용도는 웹 서버에서 데이터를 읽고 웹 페이지에 데이터를 표시하는 것입니다.

단순함을 위해 문자열을 입력으로 사용하여 설명할 수 있습니다.

먼저 JSON 구문이 포함된 JavaScript 문자열을 만듭니다.

    let text = '{ "employees" : [' +
    '{ "firstName":"John" , "lastName":"Doe" },' +
    '{ "firstName":"Anna" , "lastName":"Smith" },' +
    '{ "firstName":"Peter" , "lastName":"Jones" } ]}';

그런 다음 JavaScript 내장 함수 JSON.parse()를 사용하여 문자열을 JavaScript 객체로 변환합니다.

const obj = JSON.parse(text);
마지막으로 페이지에서 새 JavaScript 객체를 사용합니다.

    예시
    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML =
    obj.employees[1].firstName + " " + obj.employees[1].lastName;
    </script>
