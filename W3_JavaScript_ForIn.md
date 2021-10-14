## JavaScript For In

---

### For In 루프

JavaScript for in문은 객체의 속성을 반복합니다.

    syntax:

    for (key in object) {
      // code block to be executed
    }

    예시
    const person = {fname:"John", lname:"Doe", age:25};

    let text = "";
    for (let x in person) {
      text += person[x];
    }

예시 설명

- person 개체에 대해 for 루프가 반복됩니다.
- 각 반복은 키 (x)를 반환합니다.
- 키는 키 값에 액세스하는 데 사용됩니다.
- 키 값은 person[x]입니다.

---

### For In Over Arrays

JavaScript for in문은 Array의 속성을 반복할 수도 있습니다.

    sytax:
    for (variable in array) {
      code
    }

    예시
    const numbers = [45, 4, 9, 16, 25];

    let txt = "";
    for (let x in numbers) {
      txt += numbers[x];
    }

인덱스 순서 가 중요한 경우 배열에 대해 in 을 사용하지 마십시오 .

인덱스 순서는 구현에 따라 다르며 배열 값은 예상한 순서대로 액세스하지 못할 수 있습니다.

순서가 중요하다면 forloop, for of loop, Array.forEach ()를 사용하는 것이 좋습니다.

---

### Array.forEach()

이 forEach()메서드는 각 배열 요소에 대해 한 번씩 함수(콜백 함수)를 호출합니다.

    예시
    const numbers = [45, 4, 9, 16, 25];

    let txt = "";
    numbers.forEach(myFunction);

    function myFunction(value, index, array) {
    txt += value;
    }

이 함수는 3개의 인수를 취합니다.

- The item value
- The item index
- The array itself

위의 예에서는 값 매개변수만 사용합니다. 다음과 같이 다시 작성할 수 있습니다.

    예시
    const numbers = [45, 4, 9, 16, 25];

    let txt = "";
    numbers.forEach(myFunction);

    function myFunction(value) {
    txt += value;
    }
