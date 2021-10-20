## JavaScript Display Objects

---

### JavaScript 개체를 표시하는 방법?

JavaScript 객체를 표시하면 [object Object] 가 출력됩니다 .

    예시
    const person = {
    name: "John",
    age: 30,
    city: "New York"
    };

    document.getElementById("demo").innerHTML = person;

JavaScript 개체를 표시하는 몇 가지 일반적인 솔루션은 다음과 같습니다.

- 이름으로 개체 속성 표시
- 루프에서 객체 속성 표시하기
- Object.values()를 사용하여 객체 표시
- JSON.stringify()를 사용하여 객체 표시

---

### 개체 속성 표시

객체의 속성은 문자열로 표시할 수 있습니다.

    예시
    const person = {
    name: "John",
    age: 30,
    city: "New York"
    };

    document.getElementById("demo").innerHTML =
    person.name + "," + person.age + "," + person.city;

JavaScript 개체를 표시하는 몇 가지 일반적인 솔루션은 다음과 같습니다.

- 이름으로 개체 속성 표시
- 루프에서 객체 속성 표시하기
- Object.values()를 사용하여 객체 표시
- JSON.stringify()를 사용하여 객체 표시

---

### 개체 속성 표시

객체의 속성은 문자열로 표시할 수 있습니다.

    예시
    const person = {
    name: "John",
    age: 30,
    city: "New York"
    };

    document.getElementById("demo").innerHTML =
    person.name + "," + person.age + "," + person.city;

---

### 루프에 객체 표시하기

객체의 속성은 루프에서 수집할 수 있습니다.

    예시
    const person = {
    name: "John",
    age: 30,
    city: "New York"
    };

    let txt = "";
    for (let x in person) {
    txt += person[x] + " ";
    };

    document.getElementById("demo").innerHTML = txt;

<br />

    루프에서 person[x] 를 사용해야 합니다 .

    person.x 는 작동하지 않습니다( x 는 변수 이기 때문에 ).

---

### Object.values() 사용

모든 JavaScript 객체는 다음을 사용하여 배열로 변환할 수 있습니다 Object.values().

    const person = {
    name: "John",
    age: 30,
    city: "New York"
    };

    const myArray = Object.values(person);

myArray 이제 표시할 준비가 된 JavaScript 배열입니다.

    예시
    const person = {
      name: "John",
      age: 30,
      city: "New York"
    };

    const myArray = Object.values(person);
    document.getElementById("demo").innerHTML = myArray;

---

### JSON.stringify() 사용

JavaScript는 JSON.stringify()함수를 사용하여 모든 JavaScript 객체를 문자열화(문자열로 변환)할 수 있습니다 .

    const person = {
    name: "John",
    age: 30,
    city: "New York"
    };

    let myString = JSON.stringify(person);

myString는 이제 표시할 준비가 된 JavaScript 문자열입니다.

    예시
    const person = {
    name: "John",
    age: 30,
    city: "New York"
    };

    let myString = JSON.stringify(person);
    document.getElementById("demo").innerHTML = myString;

결과는 JSON 표기법을 따르는 문자열입니다.

{"name":"John","age":50,"city":"뉴욕"}

---

### 날짜 문자열화

JSON.stringify 날짜를 문자열로 변환:

    예시
    const person = {
    name: "John",
    today: new Date()
    };

    let myString = JSON.stringify(person);
    document.getElementById("demo").innerHTML = myString;

---

### 문자열화 함수

JSON.stringify 함수를 문자열화하지 않습니다:

    예시
    const person = {
    name: "John",
    age: function () {return 30;}
    };

    let myString = JSON.stringify(person);
    document.getElementById("demo").innerHTML = myString;

문자열화하기 전에 함수를 문자열로 변환하면 "고정"될 수 있습니다.

    예시
    const person = {
    name: "John",
    age: function () {return 30;}
    };
    person.age = person.age.toString();

    let myString = JSON.stringify(person);
    document.getElementById("demo").innerHTML = myString;

---

### 배열 문자열화

JavaScript 배열을 문자열화하는 것도 가능합니다:

    예시
    const arr = ["John", "Peter", "Sally", "Jane"];

    let myString = JSON.stringify(arr);
    document.getElementById("demo").innerHTML = myString;

결과는 JSON 표기법을 따르는 문자열입니다.
