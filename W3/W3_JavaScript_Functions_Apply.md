## JavaScript Function Apply

---

### 메소드 재사용

apply()메소드를 사용해서, 당신은 다른 객체에 사용할 수 있는 방법을 쓸 수 있습니다.

---

### 자바스크립트 apply() 메서드

apply()메서드는 call()과 비슷합니다

이 예에서는 person의 fullName를 apply()를 이용해 person1에 사용합니다.

예시
const person = {
fullName: function() {
return this.firstName + " " + this.lastName;
}
}

const person1 = {
firstName: "Mary",
lastName: "Doe"
}

// This will return "Mary Doe":
person.fullName.apply(person1);

---

### call()과 apply()의 차이점

차이점은 다음과 같습니다.

call()메서드는 인수를 별도로 사용 합니다.

apply()메서드는 인수를 배열로 사용 합니다.

    apply() 메서드는 인수 목록 대신 배열을 사용하려는 경우 매우 편리합니다.

---

### 인수가 있는 apply() 메서드

이 apply()메서드는 배열의 인수를 허용합니다.

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

    person.fullName.apply(person1, ["Oslo", "Norway"]);

call()방법 과 비교 :

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

---

### 배열에 대한 Max 메서드 시뮬레이션

다음 Math.max()방법을 사용하여 (숫자 목록에서) 가장 큰 숫자를 찾을 수 있습니다 .

    예시
    Math.max(1,2,3); // Will return 3

JavaScript 배열 에는 max() 메서드가 없으므로 Math.max()대신 메서드를 적용할 수 있습니다 .

    예시
    Math.max.apply(null, [1,2,3]); // Will also return 3

첫 번째 인수(null)는 중요하지 않습니다. 이 예에서는 사용되지 않습니다.

다음 예제는 동일한 결과를 제공합니다.

    예시
    Math.max.apply(Math, [1,2,3]); // Will also return 3

    예시
    Math.max.apply(" ", [1,2,3]); // Will also return 3

    예시
    Math.max.apply(0, [1,2,3]); // Will also return 3

---

### 자바스크립트 엄격 모드

JavaScript 엄격 모드에서 apply()메서드의 첫 번째 인수가 객체가 아니면 호출된 함수의 소유자(객체)가 됩니다.

"비 엄격" 모드에서는 전역 개체가 됩니다.
