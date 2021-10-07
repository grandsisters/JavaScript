## JavaScript Objects

---

### Real Life Objects, Properties, and Methods

실생활에서 자동차는 Object 입니다.

자동차에는 무게와 색상과 같은 property와 시작 및 정지와 같은 method 가 있습니다.

<img src='./img/js_object.png'>

모든 자동차는 동일한 속성을 가지고 있지만 속성 값 은 자동차마다 다릅니다.

모든 자동차는 동일한 메소드를 가지고 있지만 메소드는 다른 시간에 수행 됩니다 .

---

### 자바스크립트 객체

JavaScript 변수는 데이터 값의 컨테이너라는 것을 이미 배웠습니다.

이 코드 는 car라는 변수에 간단한 값 (Fiat)을 할당합니다 .

    let car = "Fiat";

객체도 변수입니다. 그러나 개체에는 많은 값이 포함될 수 있습니다.

이 코드 는 car라는 변수에 많은 값 (Fiat, 500, 흰색)을 할당합니다 .

    const car = {type:"Fiat", model:"500", color:"white"};

값은 이름:값 쌍(콜론으로 구분된 이름과 값)으로 작성됩니다.

const 키워드를 사용하여 객체를 선언하는 것이 일반적 입니다.

---

### 객체 정의

객체 리터럴을 사용하여 JavaScript 객체를 정의(및 생성)합니다.

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

---

### 객체 속성

JavaScript 객체 의 이름:값 쌍을 속성 이라고 합니다 .

| Property  | Property Value |
| --------- | -------------- |
| firstName | John           |
| lastName  | Doe            |
| age       | 50             |
| eyeColor  | blue           |

---

### 개체 속성 액세스

다음 두 가지 방법으로 개체 속성에 액세스할 수 있습니다.

    objectName.propertyName

    또는

    objectName["propertyName"]

    예1
    person.lastName;

    예2
    person["lastName"];

JavaScript 객체는 속성이라고 하는 명명된 값의 컨테이너입니다 .

---

### 객체 메서드

객체는 또한 메소드 를 가질 수 있습니다 .

메서드는 객체에 대해 수행할 수 있는 작업 입니다.

메서드는 속성에 함수 정의 로 저장됩니다 .

| Property  | Property Value                                            |
| --------- | --------------------------------------------------------- |
| firstName | John                                                      |
| lastName  | Doe                                                       |
| age       | 50                                                        |
| eyeColor  | blue                                                      |
| fullName  | function() {return this.firstName + " " + this.lastName;} |

메서드는 속성으로 저장된 함수입니다.

    예시
    const person = {
    firstName: "John",
    lastName : "Doe",
    id : 5566,
    fullName : function() {
    return this.firstName + " " + this.lastName;
    }
    };

---

### The this Keyword

함수 정의에서 this는 함수의 "소유자"를 나타냅니다.

위의 예에서는 전체 이름 함수를 "소유"하는 사용자 객체입니다.

다른 말로 하면, this.firstName은 이 객체의 firstName 속성을 의미합니다.

---

### 개체 메서드 액세스

다음 구문을 사용하여 개체 메서드에 액세스합니다.

    objectName.methodName()

    예시
    name = person.fullName();

() 괄호 없이 메서드에 액세스 하면 함수 정의 가 반환 됩니다 .

    예시
    name = person.fullName;

---

### 문자열, 숫자 및 불린을 객체로 선언하지 마십시오!

JavaScript 변수가 키워드 " new"로 선언 되면 변수는 객체로 생성됩니다.

    x = new String(); // Declares x as a String object
    y = new Number(); // Declares y as a Number object
    z = new Boolean(); // Declares z as a Boolean object

문자열, 숫자 및 불린 객체를 피합니다. 코드가 복잡해지고 실행 속도가 느려집니다.
