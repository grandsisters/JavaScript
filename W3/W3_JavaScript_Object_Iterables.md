## JavaScript Iterables

for..of를 이용해 반복할 수 있는 객체를 iterable이라고 합니다.

기술적으로 iterables는 Symbol.iterator 메서드를 구현해야 합니다 .

---

### 문자열 반복

for..of루프를 사용하여 문자열 요소를 반복 할 수 있습니다 .

    예시
    for (const x of "W3Schools") {
    // code block to be executed
    }

---

### 배열 반복

for..of루프를 사용하여 배열의 요소를 반복 할 수 있습니다 .

    예시
    for (const x of [1,2,3,4,5] {
    // code block to be executed
    }

---

### 자바스크립트 반복자

반복자 프로토콜 농산물하는 방법을 정의하는 값의 시퀀스를 개체에서.

객체는 메서드를 구현할 때 반복자가 됩니다 next().

이 next()메서드는 두 가지 속성이 있는 개체를 반환해야 합니다.

- 값(다음 값)
- 완료(참 또는 거짓)

| -    | -                                                            |
| ---- | ------------------------------------------------------------ |
| 값   | 반복자가 반환한 값(done이 true이면 생략 가능)                |
| 완료 | 반복자가 완료한 경우 true 반복자가 새 값을 생성한 경우 false |

---

### 직접 만든 반복 가능 객체

이 반복 가능한 반환은 끝이 없습니다: 10,20,30,40,.... Everytime next()이 호출됩니다.

    예시
    // Home Made Iterable
    function myNumbers() {
    let n = 0;
    return {
    next: function() {
    n += 10;
    return {value:n, done:false};
    }
    };
    }

    // Create Iterable
    const n = myNumbers();
    n.next(); // Returns 10
    n.next(); // Returns 20
    n.next(); // Returns 30

<br />

    직접만든 반복 가능한 객체의 문제:

    JavaScript for..of문을 지원하지 않습니다 .

JavaScript iterable은 Symbol.iterator 가 있는 객체입니다 .

Symbol.iterator는 next()기능을 반환하는 함수입니다 .

iterable은 다음 코드로 반복될 수 있습니다. for (const x of iterable) { }

    예시
    // Create an Object
    myNumbers = {};

    // Make it Iterable
    myNumbers[Symbol.iterator] = function() {
    let n = 0;
    done = false;
    return {
    next() {
    n += 10;
    if (n = 100) {done = true}
    return {value:n, done:done};
    }
    };
    }

이제 for..of을 사용할 수 있습니다.

    for (const num of myNumbers) {
    // Any Code Here
    }

Symbol.iterator 메소드는 에 의해 자동으로 호출됩니다 for..of.

그러나 "수동으로" 할 수도 있습니다.

    예시
    let iterator = myNumbers[Symbol.iterator]();

    while (true) {
    const result = iterator.next();
    if (result.done) break;
    // Any Code Here
    }
