## JavaScript For Of

---

### The For Of Loop

JavaScript for of문은 반복 가능한 객체의 값을 반복합니다.

배열, 문자열, 지도, NodeList 등과 같은 반복 가능한 데이터 구조를 반복할 수 있습니다.

    sytax:

    for (variable of iterable) {
    // code block to be executed
    }

variable - 모든 반복에 대해 다음 속성의 값이 변수에 할당됩니다. 변수 는 const, let, 또는 var로 선언할 수 있습니다.

iterable - iterable 속성이 있는 객체입니다.

---

### 배열에 대한 루핑

    예시
    const cars = ["BMW", "Volvo", "Mini"];

    let text = "";
    for (let x of cars) {
    text += x;
    }

문자열 반복

    예시
    let language = "JavaScript";

    let text = "";
    for (let x of language) {
    text += x;
    }
