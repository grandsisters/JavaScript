## 자바스크립트 객체

JavaScript에서 객체는 왕입니다. 객체를 이해하면 JavaScript를 이해합니다.

---

JavaScript에서 거의 "모든 것"은 객체입니다.

- 불린은 객체가 될 수 있습니다( new키워드로 정의된 경우 )
- 숫자는 객체일 수 있습니다( new키워드로 정의된 경우 )
- 문자열은 객체가 될 수 있습니다( new키워드로 정의된 경우 )
- 날짜는 항상 객체입니다
- 수학은 항상 객체다
- 정규식은 항상 객체입니다.
- 배열은 항상 객체입니다
- 함수는 항상 객체입니다 -개체는 항상 개체입니다.

프리미티브를 제외한 모든 JavaScript 값은 객체입니다.

---

### 자바스크립트 프리미티브

프리미티브 값은 어떤 특성 또는 method가 없는 값이다.

기본 데이터 형식은 원시 값을 갖는 데이터이다.

JavaScript는 5가지 유형의 기본 데이터 유형을 정의합니다.

- string
- number
- boolean
- null
- undefined

기본 값은 변경할 수 없습니다(하드코딩되어 있으므로 변경할 수 없음).

    만약 x = 3.14이면 x 값을 변경할 수 있습니다. 그러나 3.14의 값은 변경할 수 없습니다.

---

### 객체는 변수입니다

JavaScript 변수에는 단일 값이 포함될 수 있습니다.

    예시
    let person = "John Doe";

JavaScript 변수에는 많은 값이 포함될 수도 있습니다.

객체도 변수입니다. 그러나 개체에는 많은 값이 포함될 수 있습니다.

개체 값은 이름 : 값 쌍(콜론으로 구분된 이름과 값)으로 작성됩니다.

    예시
    let person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};

<br />

    JavaScript 객체는 명명된 값 의 모음입니다.

<br />

const키워드를 사용하여 개체를 선언하는 것이 일반적 입니다.

    예시
    const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};

---

### 객체 속성(property)

JavaScript 객체에서 명명된 값을 속성 이라고 합니다 .

이름 값 쌍으로 작성된 객체는 다음과 유사합니다.

- PHP의 연관 배열
- 파이썬의 딕셔너리
- C의 해시 테이블
- Java의 해시 맵
- Ruby 및 Perl의 해시

---

### 객체 메서드

메서드는 객체에 들어있는 수행할 수 있는 작업 입니다.

객체 속성은 기본 값, 기타 객체 및 함수가 될 수 있습니다.

JavaScript 객체는 속성 및 메서드라고 하는 명명된 값의 컨테이너입니다.

---

### 자바스크립트 객체 생성

JavaScript를 사용하여 고유한 개체를 정의하고 만들 수 있습니다.

새 개체를 만드는 방법에는 여러 가지가 있습니다.

- 개체 리터럴을 사용하여 단일 개체를 만듭니다.
- new 키워드를 사용하여 단일 개체를 만듭니다.
- 개체 생성자를 정의한 다음 생성된 형식의 개체를 만듭니다.
- Object.create()를 사용하여 객체를 생성합니다 .

---

### 객체 리터럴 사용

이것은 JavaScript 객체를 생성하는 가장 쉬운 방법입니다.

객체 리터럴을 사용하면 하나의 명령문에서 객체를 정의하고 생성할 수 있습니다.

객체 리터럴은 중괄호 {} 안에 있는 이름:값 쌍(예: age:50)의 목록입니다.

다음 예제에서는 4개의 속성이 있는 새 JavaScript 객체를 만듭니다.

    예시
    const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};

공백과 줄 바꿈은 중요하지 않습니다. 객체 정의는 여러 줄에 걸쳐 있을 수 있습니다.

    예시
    const person = {
    firstName: "John",
    lastName: "Doe",
    age: 50,
    eyeColor: "blue"
    };

이 예제에서는 빈 JavaScript 개체를 만든 다음 4개의 속성을 추가합니다.

    예시
    const person = {};
    person.firstName = "John";
    person.lastName = "Doe";
    person.age = 50;
    person.eyeColor = "blue";

---

### JavaScript 키워드 new 사용하기

다음 예제에서는 를 사용하여 새 JavaScript 객체를 new Object()만든 다음 4개의 속성을 추가합니다.

    예시
    const person = new Object();
    person.firstName = "John";
    person.lastName = "Doe";
    person.age = 50;
    person.eyeColor = "blue";

위의 예는 정확히 동일합니다.

그러나 new Object()를 사용할 필요가 없습니다 .

가독성, 단순성 및 실행 속도를 위해 객체 리터럴 방법을 사용하십시오.

---

### JavaScript 객체는 변경 가능합니다.

객체는 변경 가능합니다. 객체는 값이 아닌 참조로 처리됩니다.

person이 객체인 경우 다음 명령문은 person의 복사본을 생성하지 않습니다.

    const x = person; // Will not create a copy of person.

개체 x는 person 의 복사본 이 아닙니다 . 그것은 person입니다. x와 person은 같은 객체입니다.

x와 person은 같은 대상이기 때문에 x에 대한 모든 변경은 person도 변경합니다.

    예시
    const person = {
    firstName:"John",
    lastName:"Doe",
    age:50, eyeColor:"blue"
    }

    const x = person;
    x.age = 10; // Will change both x.age and person.age
