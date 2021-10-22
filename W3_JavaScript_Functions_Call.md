## JavaScript Function Call

---

### 메소드 재사용

call()를 이용해서, 당신은 다른 객체에 사용할 수 있는 메소드를 쓸 수 있습니다.

---

### 모든 함수는 메서드입니다

JavaScript에서 모든 함수는 객체 메서드입니다.

함수가 JavaScript 객체의 메소드가 아닌 경우 전역 객체의 함수입니다.

아래 예에서는 firstName, lastName, fullName의 3가지 속성이 있는 개체를 만듭니다.

    예시
    const myObject = {
    firstName:"John",
    lastName: "Doe",
    fullName: function () {
    return this.firstName + " " + this.lastName;
    }
    }

    // This will return "John Doe":
    myObject.fullName();

---

### 자바스크립트 call() 메소드

call()메소드는 미리 정의 된 자바 스크립트 메소드다.

소유자 객체를 인수(매개변수)로 사용하여 메서드를 호출(호출)하는 데 사용할 수 있습니다.

call()를 사용 하면 객체가 다른 객체에 속한 메서드를 사용할 수 있습니다.

이 예 에서는 person1 에서 이를 사용하여 person 의 fullName 메서드 를 호출합니다 .

    예시
    const person = {
    fullName: function() {
    return this.firstName + " " + this.lastName;
    }
    }
    const person1 = {
    firstName:"John",
    lastName: "Doe"
    }
    const person2 = {
    firstName:"Mary",
    lastName: "Doe"
    }

    // This will return "John Doe":
    person.fullName.call(person1);

이 예 에서는 person2 에서 이를 사용하여 person 의 fullName 메서드 를 호출합니다 .

    예시
    const person = {
    fullName: function() {
    return this.firstName + " " + this.lastName;
    }
    }
    const person1 = {
    firstName:"John",
    lastName: "Doe"
    }
    const person2 = {
    firstName:"Mary",
    lastName: "Doe"
    }

    // This will return "Mary Doe"
    person.fullName.call(person2);

---

### 인수가 있는 call() 메서드

이 call()메서드는 인수를 받아들일 수 있습니다.

    예시
    const person = {
    fullName: function(city, country) {
    return this.firstName + " " + this.lastName + "," + city + "," + country;
    }
    }

    const person1 = {
    firstName:"John",
    lastName: "Doe"
    }

    person.fullName.call(person1, "Oslo", "Norway");
