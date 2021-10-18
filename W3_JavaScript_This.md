## The JavaScript this Keyword

    예시
    const person = {
      firstName: "John",
      lastName : "Doe",
      id       : 5566,
      fullName : function() {
        return this.firstName + " " + this.lastName;
      }
    };

---

### this??

JavaScript this키워드는 그것이 속한 객체를 참조합니다.

사용 위치에 따라 값이 다릅니다.

- this는 메서드에서 메서드를 소유한 객체를 나타냅니다 .
- this가 단독으로 쓰일 경우 전역 객체를 참조 합니다 .
- 함수에서 this는 전역 객체를 나타냅니다 .
- 엄격 모드에서의 함수에선 this는 undefined입니다 .
- 이벤트에서 this는 이벤트를 수신한 요소를 나타냅니다 .
- call(), 및 apply()같은 메서드는 모든 객체에서 this를 참조 할 수 있습니다 .

---

### 메서드에서 this는

객체 메서드에서 this는 메서드의 " 소유자 "를 나타냅니다 .

    const person = {
      firstName: "John",
      lastName: "Doe",
      id: 5566,
      fullName : function() {
        return this.firstName + " " + this.lastName;
      }
    };

---

### 혼자 쓰이는 this는

단독으로 사용하는 경우 this의 소유자는 전역 개체이므로 전역 개체를 참조합니다.

브라우저 창에서 전역 개체는 [object Window]와 같습니다.

    예시
    let x = this;

엄격 모드에서 단독으로 사용되는 경우에도 this는 [object Window] 글로벌 객체를 참조 :

    예시
    "use strict";
    let x = this;

---

### 함수에서의 this는 (Default)

JavaScript 함수에서 함수의 소유자는 this에 대한 기본 바인딩입니다 .

따라서 함수 this에서 Global 객체를 참조합니다 [object Window].

    예시
    function myFunction() {
    return this;
    }

---

### 함수에서의 this는 (Strict)

JavaScript 엄격 모드 는 기본 바인딩을 허용하지 않습니다.

따라서 함수에서 this를 사용할 때 엄격 모드에서는 undefined입니다 .

    예시
    "use strict";
    function myFunction() {
      return this;
    }

---

### 이벤트 핸들러에서 this는

HTML 이벤트 핸들러에서 this는 이벤트를 수신한 HTML 요소를 나타냅니다.

    예시
    <button onclick="this.style.display='none'">
      Click to Remove Me!
    </button>

---

### 객체 메서드 바인딩

이 예에서 this는 person 객체입니다(person 객체는 함수의 "소유자"입니다).

    예시
    const person = {
    firstName : "John",
    lastName : "Doe",
    id : 5566,
    myFunction : function() {
    return this;
    }
    };

<br />

    예시
    const person = {
    firstName: "John",
    lastName : "Doe",
    id : 5566,
    fullName : function() {
    return this.firstName + " " + this.lastName;
    }
    };

즉, this.firstName 은 이 (person) 객체 의 firstName 속성을 의미 합니다.

---

### 명시적 함수 바인딩

call()및 apply()메소드는 자바 스크립트 메소드로 미리 정의되어 있습니다.

둘 다 다른 객체를 인수로 사용하여 객체 메서드를 호출하는 데 사용할 수 있습니다.

아래의 예에서 person2를 인자로 사용하여 person1.fullName을 호출했을때, this는 person1의 메소드 안에 있더라도 person2를 참조합니다.

    예시
    const person1 = {
      fullName: function() {
        return this.firstName + " " + this.lastName;
      }
    }
    const person2 = {
      firstName:"John",
      lastName: "Doe",
    }
    person1.fullName.call(person2);  // Will return "John Doe"
