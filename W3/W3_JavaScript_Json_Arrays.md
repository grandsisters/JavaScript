## JSON Array Litterals

이것은 JSON 문자열입니다.

    '["Ford", "BMW", "Fiat"]'

JSON 문자열 내부에는 JSON 배열 리터럴이 있습니다.

    ["Ford", "BMW", "Fiat"]

JSON의 배열은 JavaScript의 배열과 거의 동일합니다.

JSON에서 배열 값은 string, number, object, array, boolean 또는 null 유형이어야 합니다 .

JavaScript에서 배열 값은 위의 모든 값과 함께 함수, 날짜 및 정의되지 않은 기타 유효한 JavaScript 표현식이 될 수 있습니다 .

---

### 자바스크립트 배열

리터럴에서 JavaScript 배열을 만들 수 있습니다.

    예시
    myArray = ["Ford", "BMW", "Fiat"];

JSON 문자열을 구문 분석하여 JavaScript 배열을 만들 수 있습니다.

    예시
    myJSON = '["Ford", "BMW", "Fiat"]';
    myArray = JSON.Parse(myJSON);

---

### 배열 값 액세스

인덱스별로 배열 값에 액세스합니다.

    예시
    myArray[0];

---

### 객체의 배열

객체는 배열을 포함할 수 있습니다.

    예시
    {
    "name":"John",
    "age":30,
    "cars":["Ford", "BMW", "Fiat"]
    }

인덱스별로 배열 값에 액세스합니다.

    예시
    myObj.cars[0];

---

### 배열을 통한 루핑

for in루프 를 사용하여 배열 값에 액세스할 수 있습니다 .

    예시
    for (let i in myObj.cars) {
      x += myObj.cars[i];
    }

또는 for루프를 사용할 수 있습니다 .

    예시
    for (let i = 0; i < myObj.cars.length; i++) {
      x += myObj.cars[i];
    }
