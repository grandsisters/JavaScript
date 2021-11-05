## 자바스크립트 객체 메소드

    예시
    const person = {
      firstName: "John",
      lastName: "Doe",
      id: 5566,
      fullName: function() {
        return this.firstName + " " + this.lastName;
      }
    };

---

### this 키워드

함수 정의에서 함수 this의 "소유자"를 나타냅니다.

위의 예에서, this는 fullname함수를 소유한 person 객체입니다..

즉, this.firstName 은 이 객체(person) 의 firstName 속성을 의미 합니다 .

---

### 자바스크립트 메소드

JavaScript 메서드는 개체에 대해 수행할 수 있는 작업입니다.

JavaScript 메서드 는 함수 정의를 포함하는 속성 입니다.

    메서드는 객체 속성으로 저장된 함수입니다.

---

### 객체 메서드 액세스

다음 구문을 사용하여 객체 메서드에 액세스합니다.

    objectName.methodName()

일반적으로 fullName()을 person 객체의 메서드로 설명하고 fullName을 속성으로 설명합니다.

fullName 속성은 ()와 함께 호출될 때 (함수로) 실행됩니다.

이 예 에서는 person 객체 의 fullName() 메서드 에 액세스 합니다.

    예시
    name = person.fullName();

() 없이 fullName 속성에 액세스 하면 함수 정의 가 반환 됩니다 .

    예시
    name = person.fullName;

---

### 객체에 메소드 추가

객체에 새 메서드를 추가하는 것은 쉽습니다.

    예시
    person.name = function () {
    return this.firstName + " " + this.lastName;
    };

---

### 기본 제공 방법 사용

이 예에서는 toUpperCase()String 객체 의 메서드 를 사용하여 텍스트를 대문자로 변환합니다.

    let message = "Hello world!";
    let x = message.toUpperCase();

위의 코드를 실행한 후 x의 값은 다음과 같습니다.

    HELLO WORLD!

<br />

    예시
    person.name = function () {
    return (this.firstName + " " + this.lastName).toUpperCase();
    };
