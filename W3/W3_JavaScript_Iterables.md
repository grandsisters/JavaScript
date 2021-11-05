## JavaScript Iterables

Iterable은 Array와 같은 iterable 객체입니다.

Iterables는 간단하고 효율적인 코드로 액세스할 수 있습니다.

Iterables는 for..of같은 반복문 으로 반복될 수 있습니다.

---

### For 루프

JavaScript for..of문은 반복 가능한 개체의 요소를 반복합니다.

    sytax:
    for (variable of iterable) {
    // code block to be executed
    }

### 반복

반복하는 것은 이해하기 쉽습니다.

단순히 요소 시퀀스를 반복하는 것을 의미합니다.

다음은 몇 가지 쉬운 예입니다.

- 문자열 반복
- 배열 반복

---

### 문자열 반복

for..of루프를 사용하여 문자열 요소를 반복 할 수 있습니다 .

    예시
    const name = "W3Schools";

    for (const x of name) {
    // code block to be executed
    }

---

### 배열 반복

for..of루프를 사용하여 배열의 요소를 반복 할 수 있습니다 .

    예시
    const letters = ["a","b","c"];

    for (const x of letters) {
    // code block to be executed
    }

---

### 세트 반복

for..of루프를 사용하여 Set의 요소를 반복 할 수 있습니다 .

    예시
    const letters = new Set(["a","b","c"]);

    for (const x of letters) {
    // code block to be executed
    }

---

### 맵 반복

for..of루프를 사용하여 맵의 요소를 반복 할 수 있습니다 .

    예시
    const fruits = new Map([
    ["apples", 500],
    ["bananas", 300],
    ["oranges", 200]
    ]);

    for (const x of fruits) {
    // code block to be executed
    }
