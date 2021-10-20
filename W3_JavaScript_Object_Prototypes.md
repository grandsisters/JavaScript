## JavaScript Object Prototypes

모든 JavaScript 객체는 프로토타입에서 속성과 메서드를 상속합니다.

이전 장에서 객체 생성자 를 사용하는 방법을 배웠습니다 .

    예시
    function Person(first, last, age, eyecolor) {
      this.firstName = first;
      this.lastName = last;
      this.age = age;
      this.eyeColor = eyecolor;
    }

    const myFather = new Person("John", "Doe", 50, "blue");
    const myMother = new Person("Sally", "Rally", 48, "green");

또한 기존 객체 생성자에 새 속성을 추가 할 수 없다는 것도 배웠습니다 .

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

---

### 프로토타입 상속

모든 JavaScript 객체는 프로토타입에서 속성과 메서드를 상속합니다.

- Date 객체는 Date.prototype을 상속
- Array 객체는 Array.prototype을 상속
- Person 객체는 Person.prototype을 상속

Object.prototype은 프로토 타입 상속 체인의 상단에 있습니다 :

Date개체, Array개체 및 Person개체는 Object.prototype에서 상속됩니다.

---

### 객체에 속성 및 메서드 추가

주어진 유형의 모든 기존 개체에 새 속성(또는 메서드)을 추가하려는 경우가 있습니다.

때로는 객체 생성자에 새 속성(또는 메서드)을 추가하고 싶을 때가 있습니다.

---

### 프로토 타입 property 사용

JavaScript prototype속성을 사용하면 객체 생성자에 새 속성을 추가할 수 있습니다.

    예시
    function Person(first, last, age, eyecolor) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.eyeColor = eyecolor;
    }

    Person.prototype.nationality = "English";

JavaScript prototype속성을 사용하면 객체 생성자에 새 메서드를 추가할 수도 있습니다.

    예시
    function Person(first, last, age, eyecolor) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.eyeColor = eyecolor;
    }

    Person.prototype.name = function() {
    return this.firstName + " " + this.lastName;
    };

<br />

    자신의 프로토타입 만 수정하십시오 . 표준 JavaScript 개체의 프로토타입을 수정하지 마십시오.
