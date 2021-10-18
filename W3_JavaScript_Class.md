## JavaScript Classes

ES6이라고도 하는 ECMAScript 2015에는 JavaScript 클래스가 도입되었습니다.

JavaScript 클래스는 JavaScript 객체용 템플릿입니다.

### 자바스크립트 클래스 구문

키워드 class를 사용하여 클래스를 만듭니다.

항상 다음과 같은 메소드를 추가하십시오 constructor().

    sytax:
    class ClassName {
      constructor() { ... }
    }

<br />

    예시
    class Car {
      constructor(name, year) {
        this.name = name;
        this.year = year;
      }
    }

위의 예는 "Car"라는 클래스를 생성합니다.

클래스에는 "이름"과 "연도"의 두 가지 초기 속성이 있습니다.

JavaScript 클래스는 객체 가 아닙니다 .

그것은 템플릿 자바 스크립트 객체입니다 .

---

### 클래스 사용

클래스가 있으면 클래스를 사용하여 객체를 만들 수 있습니다.

    예시
    let myCar1 = new Car("Ford", 2014);
    let myCar2 = new Car("Audi", 2019);

위의 예에서는 Car 클래스 를 사용하여 두 개의 Car 객체 를 만듭니다 .

생성자 메서드는 새 객체가 생성될 때 자동으로 호출됩니다.

---

### 생성자 메서드

생성자 메서드는 특수 메서드입니다.

- 정확하게 이름이 "constructor"여야 합니다.
- 새 객체가 생성되면 자동으로 실행됩니다.
- 객체 속성을 초기화하는 데 사용됩니다.

생성자 메서드를 정의하지 않으면 JavaScript는 빈 생성자 메서드를 추가합니다.

---

### 클래스 메서드

클래스 메서드는 객체 메서드와 동일한 구문으로 생성됩니다.

키워드 class를 사용하여 클래스를 만듭니다.

항상 constructor()메소드를 추가하십시오 .

그런 다음 원하는 수의 방법을 추가합니다.

    sytax:
    class ClassName {
    constructor() { ... }
    method_1() { ... }
    method_2() { ... }
    method_3() { ... }
    }

Car age를 반환하는 "age"라는 클래스 메서드를 만듭니다.

    예시
    class Car {
    constructor(name, year) {
    this.name = name;
    this.year = year;
    }
    age() {
    let date = new Date();
    return date.getFullYear() - this.year;
    }
    }

    let myCar = new Car("Ford", 2014);
    document.getElementById("demo").innerHTML =
    "My car is " + myCar.age() + " years old.";

클래스 메서드에 매개변수를 보낼 수 있습니다.

    예시
    class Car {
    constructor(name, year) {
    this.name = name;
    this.year = year;
    }
    age(x) {
    return x - this.year;
    }
    }

    let date = new Date();
    let year = date.getFullYear();

    let myCar = new Car("Ford", 2014);
    document.getElementById("demo").innerHTML=
    "My car is " + myCar.age(year) + " years old.";
