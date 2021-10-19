## 자바스크립트 객체 속성

속성은 모든 JavaScript 개체에서 가장 중요한 부분입니다.

---

### 자바스크립트 속성

속성은 JavaScript 객체와 연결된 값입니다.

JavaScript 객체는 순서가 지정되지 않은 속성의 모음입니다.

속성은 일반적으로 변경, 추가 및 삭제할 수 있지만 일부는 읽기 전용입니다.

JavaScript 속성 액세스
개체의 속성에 액세스하는 구문은 다음과 같습니다.

    objectName.property // person.age

또는

    objectName["property"] // person["age"]

또는

    objectName[expression] // x = "age"; person[x]

표현식은 속성 이름으로 평가되어야 합니다.

    실시예 1
    person.firstname + " is " + person.age + " years old.";

    실시예 2
    person["firstname"] + " is " + person["age"] + " years old.";

---

### JavaScript for...in 루프

JavaScript for...in문은 객체의 속성을 반복합니다.

    syntax:
    for (let variable in object) {
    // code to be executed
    }

for...in루프 내부의 코드 블록은 각 속성에 대해 한 번 실행됩니다.

객체의 속성을 통해 반복:

    예시
    const person = {
    fname:" John",
    lname:" Doe",
    age: 25
    };

    for (let x in person) {
    txt += person[x];
    }

---

### 새 속성 추가

단순히 값을 지정하여 기존 개체에 새 속성을 추가할 수 있습니다.

person 객체가 이미 존재한다고 가정합니다. 그런 다음 새 속성을 지정할 수 있습니다.

    예시
    person.nationality = "English";

---

### 속성 삭제

delete키워드는 객체로부터 속성을 삭제합니다 :

    예시
    const person = {
    firstName: "John",
    lastName: "Doe",
    age: 50,
    eyeColor: "blue"
    };

    delete person.age;

또는 person["age"] 삭제;

    예시
    const person = {
    firstName: "John",
    lastName: "Doe",
    age: 50,
    eyeColor: "blue"
    };

    delete person["age"];

delete키워드는 속성 값과 속성 자체를 모두 삭제합니다.

삭제 후 속성을 다시 추가하기 전에는 사용할 수 없습니다.

delete연산자 객체 속성에 사용되도록 설계된다. 변수나 함수에는 영향을 미치지 않습니다.

delete운영자는 미리 정의 된 자바 스크립트 객체 속성에 사용할 수 없습니다.

응용 프로그램이 충돌할 수 있습니다.

---

### 중첩된 개체

객체의 값은 다른 객체일 수 있습니다.

    예시
    myObj = {
    name:"John",
    age:30,
    cars: {
    car1:"Ford",
    car2:"BMW",
    car3:"Fiat"
    }
    }

점 표기법이나 대괄호 표기법을 사용하여 중첩된 객체에 액세스할 수 있습니다.

    예시
    myObj.cars.car2;

또는:

    예시
    myObj.cars["car2"];

또는:

    예시
    myObj["cars"]["car2"];

또는:

    예시
    let p1 = "cars";
    let p2 = "car2";
    myObj[p1][p2];

---

### 중첩 배열 및 객체

객체의 값은 배열이 될 수 있고 배열의 값은 객체가 될 수 있습니다.

    예시
    const myObj = {
    name: "John",
    age: 30,
    cars: [
    {name:"Ford", models:["Fiesta", "Focus", "Mustang"]},
    {name:"BMW", models:["320", "X3", "X5"]},
    {name:"Fiat", models:["500", "Panda"]}
    ]
    }

배열 내부의 배열에 액세스하려면 각 배열에 대해 for-in 루프를 사용하십시오.

    예시
    for (let i in myObj.cars) {
    x += "<h1>" + myObj.cars[i].name + "</h1>";
    for (let j in myObj.cars[i].models) {
    x += myObj.cars[i].models[j];
    }
    }

---

### Property Attributes

모든 속성에는 이름이 있습니다. 또한 value도 있습니다.

값은 Property Attributes 중 하나입니다.

기타 Attributes은 열거 가능, 구성 가능 및 쓰기 가능입니다.

이러한 Attributes은 Property에 액세스하는 방법을 정의합니다(읽을 수 있습니까?, 쓸 수 있습니까? 등).

JavaScript에서는 모든 Attributes을 읽을 수 있지만 value Attributes만 변경할 수 있습니다(속성이 쓰기 가능한 경우에만).

(ECMAScript 5에는 모든 속성 속성을 가져오고 설정하는 메서드가 있습니다)

---

### Prototype Properties

JavaScript 객체는 프로토타입의 속성을 상속합니다.

delete키워드는 상속 된 속성을 삭제하지 않습니다,하지만 당신은 프로토 타입 속성을 삭제하면 프로토 타입에서 상속 된 모든 객체에 영향을 미칠 것입니다.
