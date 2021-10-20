## JavaScript Object Constructors

    예시
    function Person(first, last, age, eye) {
      this.firstName = first;
      this.lastName = last;
      this.age = age;
      this.eyeColor = eye;
    }

생성자 함수의 이름은 대문자로 시작하는 것이 좋습니다.

---

### Object Types (Blueprints) (Classes)

이전 장의 예제는 제한적입니다. 단일 개체만 생성합니다.

때때로 우리 는 같은 "유형"의 많은 객체를 생성하기 위해 " 청사진 "이 필요합니다 .

"객체 유형"을 만드는 방법은 객체 생성자 함수 를 사용하는 것 입니다.

위의 예에서 function Person()는 객체 생성자 함수입니다.

동일한 유형의 객체는 다음 new키워드로 생성자 함수를 호출하여 생성됩니다 .

    const myFather = new Person("John", "Doe", 50, "blue");
    const myMother = new Person("Sally", "Rally", 48, "green");

---

### this 키워드

JavaScript에서 호출되는 this는 코드를 "소유하는" 객체입니다.

this의 값은 객체에서 사용될 때 객체 자체입니다.

생성자에서 함수 this에는 값이 없습니다. 새 개체를 대체합니다. this의 값은 새 객체가 생성될 때 새 객체가 됩니다.

this변수가 아니라는 점 에 유의하십시오 . 키워드입니다. this의 값을 변경할 수 없습니다.

---

### 객체에 속성 추가

기존 객체에 새 속성을 추가하는 것은 쉽습니다.

    예시
    myFather.nationality = "English";

속성이 myMother가 아닌 myFather에 추가됩니다. (person 객체가 아님).

---

### 객체에 메소드 추가

기존 개체에 새 메서드를 추가하는 것은 쉽습니다.

    예시
    myFather.name = function () {
    return this.firstName + " " + this.lastName;
    };

속성이 myMother가 아닌 myFather에 추가됩니다. (person 객체가 아님).

---

### 생성자에 속성 추가

기존 객체에 새 속성을 추가하는 것과 같은 방식으로 객체 생성자에 새 속성을 추가할 수 없습니다.

    예시
    Person.nationality = "English";

생성자에 새 속성을 추가하려면 생성자 함수에 추가해야 합니다.

    예시
    function Person(first, last, age, eyecolor) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.eyeColor = eyecolor;
    this.nationality = "English";
    }

이런 식으로 객체 속성은 기본값을 가질 수 있습니다.

---

### 생성자에 메서드 추가

생성자 함수는 메서드를 정의할 수도 있습니다.

    예시
    function Person(first, last, age, eyecolor) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.eyeColor = eyecolor;
    this.name = function() {
    return this.firstName + " " + this.lastName;
    };
    }

기존 개체에 새 메서드를 추가하는 것과 같은 방식으로 개체 생성자에 새 메서드를 추가할 수 없습니다.

객체 생성자에 메소드를 추가하려면 생성자 함수 내에서 수행해야 합니다.

    예시
    function Person(firstName, lastName, age, eyeColor) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
    this.eyeColor = eyeColor;
    this.changeName = function (name) {
    this.lastName = name;
    };
    }

changeName() 함수는 이름 값을 사람의 lastName 속성에 할당합니다.

이제 다음을 시도할 수 있습니다.

    myMother.changeName("Doe");

---

### 내장 JavaScript 생성자

JavaScript에는 기본 개체에 대한 기본 제공 생성자가 있습니다.

    new String() // A new String object
    new Number() // A new Number object
    new Boolean() // A new Boolean object
    new Object() // A new Object object
    new Array() // A new Array object
    new RegExp() // A new RegExp object
    new Function() // A new Function object
    new Date() // A new Date object

Math()개체가 목록에 없습니다. Math전역 개체입니다. Math에서 new키워드를 사용할 수 없습니다 .

---

### Did You Know?

위에서 볼 수 있듯이 JavaScript에는 문자열, 숫자 및 불린의 기본 데이터 유형이 객체 버전으로 있습니다.

하지만 복잡한 객체를 만들 이유가 없습니다. 원시 값이 훨씬 빠릅니다.

    new string() 대신 문자열 리터럴 ""을 사용하십시오.

    new number() 대신 숫자 50을 사용하십시오.

    new boolean() 대신 불린 리터럴 true/false를 사용합니다.

    new object() 대신 객체 리터럴 {}을(를) 사용하십시오.

    new array() 대신 배열 리터럴 []을 사용합니다.

    new RegExp() 대신 패턴 리터럴 /()/을 사용하십시오.

    new function() 대신 함수식() 리터럴 {}을(를) 사용하십시오.

<br />

    Example
    let x1 = ""; // new primitive string
    let x2 = 0; // new primitive number
    let x3 = false; // new primitive boolean

    const x4 = {}; // new Object object
    const x5 = []; // new Array object
    const x6 = /()/ // new RegExp object
    const x7 = function(){}; // new function

---

### 문자열 객체

일반적으로 문자열은 기본 형식으로 생성됩니다. firstName = "John"

그러나 다음 new키워드를 사용하여 문자열을 객체로 만들 수도 있습니다 .

    firstName = new String("John")

---

### 숫자 개체

일반적으로 숫자는 기본 형식으로 생성됩니다. x = 30

그러나 다음 new키워드를 사용하여 숫자를 개체로 만들 수도 있습니다 .

    x = new Number(30)

---

### boolean 객체

일반적으로 boolean은 기본 형식으로 생성됩니다. x = false

그러나 boolean은 new키워드를 사용하여 객체로 생성할 수도 있습니다 .

    x = new Boolean(false)
