## JSON Object Literals

이것은 JSON 문자열입니다.

    '{"name":"John", "age":30, "car":null}'

JSON 문자열 내부에는 JSON 객체 리터럴이 있습니다.

    {"name":"John", "age":30, "car":null}

JSON 객체 리터럴은 중괄호 {}로 둘러싸여 있습니다.

JSON 객체 리터럴에는 키/값 쌍이 포함됩니다.

키와 값은 콜론으로 구분됩니다.

키는 문자열이어야 하고 값은 유효한 JSON 데이터 유형이어야 합니다.

- string
- number
- object
- array
- boolean
- null

각 키/값 쌍은 쉼표로 구분됩니다.

JSON 객체 리터럴을 "JSON 객체"라고 부르는 것은 일반적인 실수입니다.

JSON은 객체가 될 수 없습니다. JSON은 문자열 형식입니다.

데이터는 문자열 형식인 경우에만 JSON입니다. JavaScript 변수로 변환되면 JavaScript 객체가 됩니다.

---

### 자바스크립트 객체

JSON 객체 리터럴에서 JavaScript 객체를 생성할 수 있습니다.

    예시
    myObj = {"name":"John", "age":30, "car":null};

일반적으로 JSON 문자열을 구문 분석하여 JavaScript 객체를 생성합니다.

    예시
    myJSON = '{"name":"John", "age":30, "car":null}';
    myObj = JSON.parse(myJSON);

---

### 개체 값 액세스

점(.) 표기법을 사용하여 객체 값에 액세스할 수 있습니다.

    예시
    const myJSON = '{"name":"John", "age":30, "car":null}';
    const myObj = JSON.parse(myJSON);
    x = myObj.name;

대괄호([]) 표기법을 사용하여 객체 값에 액세스할 수도 있습니다.

    예시
    const myJSON = '{"name":"John", "age":30, "car":null}';
    const myObj = JSON.parse(myJSON);
    x = myObj["name"];

---

### 객체 루핑

for-in 루프를 사용하여 객체 속성을 반복할 수 있습니다.

    예시 - 키값 가져오기
    const myJSON = '{"name":"John", "age":30, "car":null}';
    const myObj = JSON.parse(myJSON);

    let text = "";
    for (const x in myObj) {
      text += x + ", ";
    }

for-in 루프에서 대괄호 표기법을 사용하여 속성 값 에 액세스 합니다 .

    예시 - 밸류값 가져오기
    const myJSON = '{"name":"John", "age":30, "car":null}';
    const myObj = JSON.parse(myJSON);

    let text = "";
    for (const x in myObj) {
      text += myObj[x] + ", ";
    }
