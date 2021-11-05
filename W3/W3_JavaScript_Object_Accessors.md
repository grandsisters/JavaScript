## JavaScript Object Accessors

---

### JavaScript 접근자(getter 및 setter)

ECMAScript 5(ES5 2009)는 Getter와 Setter를 도입했습니다.

Getter 및 setter를 사용하면 개체 접근자(계산된 속성)를 정의할 수 있습니다.

---

### JavaScript Getter(get 키워드)

이 예제에서는 lang속성 get 값에 속성을 사용 language합니다.

    예시
    // Create an object:
    const person = {
    firstName: "John",
    lastName: "Doe",
    language: "en",
    get lang() {
    return this.language;
    }
    };

    // Display data from the object using a getter:
    document.getElementById("demo").innerHTML = person.lang;

---

### JavaScript Setter(설정 키워드)

이 예제에서는 lang속성 set 값에 속성을 사용 language합니다.

    예시
    const person = {
    firstName: "John",
    lastName: "Doe",
    language: "",
    set lang(lang) {
    this.language = lang;
    }
    };

    // Set an object property using a setter:
    person.lang = "en";

    // Display data from the object:
    document.getElementById("demo").innerHTML = person.language;

---

### JavaScript 함수 또는 Getter?

이 두 예의 차이점은 무엇입니까?

    실시예 1
    const person = {
    firstName: "John",
    lastName: "Doe",
    fullName: function() {
    return this.firstName + " " + this.lastName;
    }
    };

    // Display data from the object using a method:
    document.getElementById("demo").innerHTML = person.fullName();

<br />

    실시예 2
    const person = {
    firstName: "John",
    lastName: "Doe",
    get fullName() {
    return this.firstName + " " + this.lastName;
    }
    };

    // Display data from the object using a getter:
    document.getElementById("demo").innerHTML = person.fullName;

예 1 함수로 fullName에 액세스: person.fullName().

예 2: person.fullName 속성으로 fullName에 액세스합니다.

두 번째 예는 더 간단한 구문을 제공합니다.

---

### 데이터 품질

JavaScript는 getter 및 setter를 사용할 때 더 나은 데이터 품질을 확보할 수 있습니다.

lang이 예에서 속성을 사용하면 속성 값이 language대문자로 반환됩니다 .

    예시
    // Create an object:
    const person = {
    firstName: "John",
    lastName: "Doe",
    language: "en",
    get lang() {
    return this.language.toUpperCase();
    }
    };

    // Display data from the object using a getter:
    document.getElementById("demo").innerHTML = person.lang;

lang이 예에서 속성을 사용하여 속성에 대문자 값을 저장합니다 language.

    예시
    const person = {
    firstName: "John",
    lastName: "Doe",
    language: "",
    set lang(lang) {
    this.language = lang.toUpperCase();
    }
    };

    // Set an object property using a setter:
    person.lang = "en";

    // Display data from the object:
    document.getElementById("demo").innerHTML = person.language;

---

### 게터와 세터를 사용하는 이유

- 더 간단한 구문을 제공합니다.
- 속성 및 메서드에 대해 동일한 구문을 허용합니다.
- 더 나은 데이터 품질을 확보할 수 있습니다.

---

### Object.defineProperty()

이 Object.defineProperty()메서드는 Getter 및 Setter를 추가하는 데 사용할 수도 있습니다.

    // Define object
    const obj = {counter : 0};

    // Define setters
    Object.defineProperty(obj, "reset", {
    get : function () {this.counter = 0;}
    });
    Object.defineProperty(obj, "increment", {
    get : function () {this.counter++;}
    });
    Object.defineProperty(obj, "decrement", {
    get : function () {this.counter--;}
    });
    Object.defineProperty(obj, "add", {
    set : function (value) {this.counter += value;}
    });
    Object.defineProperty(obj, "subtract", {
    set : function (value) {this.counter -= value;}
    });

    // Play with the counter:
    obj.reset;
    obj.add = 5;
    obj.subtract = 1;
    obj.increment;
    obj.decrement;
