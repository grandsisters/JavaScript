## JSON Syntax

JSON 구문은 JavaScript 구문의 하위 집합입니다.

---

### JSON 구문 규칙

JSON 구문은 JavaScript 객체 표기법 구문에서 파생됩니다.

- 데이터는 이름/값 쌍에 있습니다.
- 데이터는 쉼표로 구분됩니다.
- 중괄호는 객체를 보유합니다.
- 대괄호는 배열을 포함합니다.

---

### JSON 데이터 - 이름과 값

JSON 데이터는 이름/값 쌍(일명 키/값 쌍)으로 작성됩니다.

이름/값 쌍은 필드 이름(큰따옴표), 콜론, 값으로 구성됩니다.

    예시
    "name":"John"

JSON 이름에는 큰따옴표가 필요합니다.

---

### JSON - JavaScript 객체로 평가

JSON 형식은 JavaScript 개체와 거의 동일합니다.

JSON에서 키 는 큰따옴표로 작성된 문자열이어야 합니다.

    JSON
    {"name":"John"}

JavaScript에서 키는 문자열, 숫자 또는 식별자 이름이 될 수 있습니다.

    자바스크립트
    {name:"John"}

---

### JSON 값

JSON에서, 값은 다음과 같은 데이터 유형 중 하나 여야합니다 :

- 문자열
- 숫자
- 객체
- 배열
- 참이나 거짓
- null

JSON에서 자바 스크립트 값을 포함하여 위의 플러스 기타 유효한 JavaScript 표현식을 모두 할 수 있습니다 :

- function
- date
- undefined

JSON에서 문자열 값 은 큰따옴표로 작성해야 합니다.

    JSON
    {"name":"John"}

JavaScript에서는 큰 따옴표 나 작은따옴표로 문자열 값을 작성할 수 있습니다 .

    자바스크립트
    {name:'John'}

---

### 자바스크립트 객체

JSON 구문은 JavaScript 객체 표기법에서 파생되기 때문에 JavaScript 내에서 JSON을 사용하는 데 필요한 추가 소프트웨어는 거의 없습니다.

JavaScript를 사용하면 다음과 같이 개체를 만들고 데이터를 할당할 수 있습니다.

    예시
    person = {name:"John", age:31, city:"New York"};

다음과 같이 JavaScript 객체에 액세스할 수 있습니다.

    예시
    // returns John
    person.name;

다음과 같이 액세스할 수도 있습니다.

    예시
    // returns John
    person["name"];

데이터는 다음과 같이 수정할 수 있습니다.

    예시
    person.name = "Gilbert";

다음과 같이 수정할 수도 있습니다.

    예시
    person["name"] = "Gilbert";

---

### JavaScript 배열을 JSON으로

JavaScript 객체를 JSON으로 작성할 수 있는 것과 같은 방식으로 JavaScript 배열도 JSON으로 작성할 수 있습니다.
