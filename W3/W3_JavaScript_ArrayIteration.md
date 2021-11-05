## JavaScript Array Iteration

배열 반복 방법은 모든 배열 항목에서 작동합니다.

---

### Array.forEach()

이 forEach()메서드는 각 배열 요소에 대해 한 번씩 함수(콜백 함수)를 호출합니다.

    예시
    const numbers = [45, 4, 9, 16, 25];
    let txt = "";
    numbers.forEach(myFunction);

    function myFunction(value, index, array) {
    txt += value + "<br>";
    }

이 함수는 3개의 인수를 취합니다.

- The item value
- The item index
- The array itself

위의 예에서는 값 매개변수만 사용합니다. 예제는 다음과 같이 다시 작성할 수 있습니다.

    예시
    const numbers = [45, 4, 9, 16, 25];
    let txt = "";
    numbers.forEach(myFunction);

    function myFunction(value) {
    txt += value + "<br>";
    }

---

### Array.map()

이 map()메서드는 각 배열 요소에 대해 함수를 수행하여 새 배열을 만듭니다.

이 map()메서드는 값이 없는 배열 요소에 대해 함수를 실행하지 않습니다.

이 map()방법은 원래 배열을 변경하지 않습니다.

이 예에서는 각 배열 값에 2를 곱합니다.

    예시
    const numbers1 = [45, 4, 9, 16, 25];
    const numbers2 = numbers1.map(myFunction);

    function myFunction(value, index, array) {
      return value * 2;
    }

이 함수는 3개의 인수를 취합니다.

- The item value
- The item index
- The array itself

콜백 함수가 값 매개변수만 사용하는 경우 인덱스 및 배열 매개변수를 생략할 수 있습니다.

    예시
    const numbers1 = [45, 4, 9, 16, 25];
    const numbers2 = numbers1.map(myFunction);

    function myFunction(value) {
      return value * 2;
    }

---

### Array.filter()

이 filter()메서드는 테스트를 통과한 배열 요소로 새 배열을 만듭니다.

이 예에서는 값이 18보다 큰 요소에서 새 배열을 만듭니다.

    예시
    const numbers = [45, 4, 9, 16, 25];
    const over18 = numbers.filter(myFunction);

    function myFunction(value, index, array) {
    return value > 18;
    }

이 함수는 3개의 인수를 취합니다.

- The item value
- The item index
- The array itself

위의 예에서 콜백 함수는 인덱스 및 배열 매개변수를 사용하지 않으므로 생략할 수 있습니다.

    예시
    const numbers = [45, 4, 9, 16, 25];
    const over18 = numbers.filter(myFunction);

    function myFunction(value) {
    return value > 18;
    }

---

### Array.reduce()

이 reduce()메서드는 각 배열 요소에 대해 함수를 실행하여 단일 값을 생성(축소)합니다.

이 reduce()방법은 배열에서 왼쪽에서 오른쪽으로 작동합니다. reduceRight()도 참조하십시오 .

이 reduce()방법은 원래 배열을 줄이지 않습니다.

이 예에서는 배열에 있는 모든 숫자의 합을 찾습니다.

    예시
    const numbers = [45, 4, 9, 16, 25];
    let sum = numbers.reduce(myFunction);

    function myFunction(total, value, index, array) {
    return total + value;
    }

이 함수는 4개의 인수를 취합니다.

- The total (the initial value / previously returned value)
- The item value
- The item index
- The array itself

위의 예에서는 인덱스 및 배열 매개변수를 사용하지 않습니다. 다음과 같이 다시 작성할 수 있습니다.

    예시
    const numbers = [45, 4, 9, 16, 25];
    let sum = numbers.reduce(myFunction);

    function myFunction(total, value) {
    return total + value;
    }

이 reduce()메서드는 초기 값을 받아들일 수 있습니다.

    예시
    const numbers = [45, 4, 9, 16, 25];
    let sum = numbers.reduce(myFunction, 100);

    function myFunction(total, value) {
    return total + value;
    }

---

### Array.reduceRight()

이 reduceRight()메서드는 각 배열 요소에 대해 함수를 실행하여 단일 값을 생성(축소)합니다.

reduceRight()에서 작품 배열의 오른쪽이 왼쪽. 도 참조하십시오 reduce().

이 reduceRight()방법은 원래 배열을 줄이지 않습니다.

이 예에서는 배열에 있는 모든 숫자의 합을 찾습니다.

    예시
    const numbers = [45, 4, 9, 16, 25];
    let sum = numbers1.reduceRight(myFunction);

    function myFunction(total, value, index, array) {
    return total + value;
    }

이 함수는 4개의 인수를 취합니다.

- The total (the initial value / previously returned value)
- The item value
- The item index
- The array itself

위의 예에서는 인덱스 및 배열 매개변수를 사용하지 않습니다. 다음과 같이 다시 작성할 수 있습니다.

    예시
    const numbers = [45, 4, 9, 16, 25];
    let sum = numbers1.reduceRight(myFunction);

    function myFunction(total, value) {
    return total + value;
    }

---

### Array.every()

every() 메서드는 모든 배열 값이 테스트를 통과하는지 확인합니다.

이 예에서는 모든 배열 값이 18보다 큰지 확인합니다.

    예시
    const numbers = [45, 4, 9, 16, 25];
    let allOver18 = numbers.every(myFunction);

    function myFunction(value, index, array) {
    return value > 18;
    }

이 함수는 3개의 인수를 취합니다.

- The item value
- The item index
- The array itself

콜백 함수가 첫 번째 매개변수(값)만 사용하는 경우 다른 매개변수는 생략할 수 있습니다.

    예시
    const numbers = [45, 4, 9, 16, 25];
    let allOver18 = numbers.every(myFunction);

    function myFunction(value) {
    return value > 18;
    }

---

### Array.some()

some()있어서 검사 일부 배열 값 테스트를 통과하는 경우.

이 예에서는 일부 배열 값이 18보다 큰지 확인합니다.

    예시
    const numbers = [45, 4, 9, 16, 25];
    let someOver18 = numbers.some(myFunction);

    function myFunction(value, index, array) {
    return value > 18;
    }

이 함수는 3개의 인수를 취합니다.

- The item value
- The item index
- The array itself

---

### Array.indexOf()

이 indexOf()메서드는 배열에서 요소 값을 검색하고 해당 위치를 반환합니다.

참고: 첫 번째 항목의 위치는 0이고 두 번째 항목의 위치는 1입니다.

    예시
    "Apple" 항목에 대한 배열 검색:

    const fruits = ["Apple", "Orange", "Apple", "Mango"];
    let position = fruits.indexOf("Apple") + 1;

### sytax

    array.indexOf(item, start)

| -     | -                                                                                                                                   |
| ----- | ----------------------------------------------------------------------------------------------------------------------------------- |
| item  | Required. The item to search for.                                                                                                   |
| start | Optional. Where to start the search. Negative values will start at the given position counting from the end, and search to the end. |

Array.indexOf() 항목을 찾을 수 없으면 -1을 반환합니다.

항목이 두 번 이상 있으면 첫 번째 항목의 위치를 ​​반환합니다.

---

### Array.lastIndexOf()

Array.lastIndexOf()와 동일 Array.indexOf()하지만 지정된 요소가 마지막으로 발생한 위치를 반환합니다.

    예시
    "Apple" 항목에 대한 배열 검색:

    const fruits = ["Apple", "Orange", "Apple", "Mango"];
    let position = fruits.lastIndexOf("Apple") + 1;

sytax

    array.lastIndexOf(item, start)

| -     | -                                                                                                                                        |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| item  | Required. The item to search for                                                                                                         |
| start | Optional. Where to start the search. Negative values will start at the given position counting from the end, and search to the beginning |

---

### Array.includes()

ECMAScript 2016 Array.includes()이 어레이에 도입 되었습니다.

이를 통해 요소가 배열에 있는지 확인할 수 있습니다(indexOf와 달리 NaN 포함).

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];

    fruits.includes("Mango"); // is true

syntax

    array.includes(search-item)

Array.includes()를 사용하면 NaN 값을 확인할 수 있습니다. Array.indexOf()와 다릅니다.

---

### Array.find()

이 find()메서드는 테스트 함수를 통과하는 첫 번째 배열 요소의 값을 반환합니다.

이 예에서는 18보다 큰 첫 번째 요소를 찾습니다(값 반환).

    예시
    const numbers = [4, 9, 16, 25, 29];
    let first = numbers.find(myFunction);

    function myFunction(value, index, array) {
    return value > 18;
    }

이 함수는 3개의 인수를 취합니다.

- The item value
- The item index
- The array itself

---

### Array.findIndex()

이 findIndex()메서드는 테스트 함수를 통과하는 첫 번째 배열 요소의 인덱스를 반환합니다.

이 예에서는 18보다 큰 첫 번째 요소의 인덱스를 찾습니다.

    예시
    const numbers = [4, 9, 16, 25, 29];
    let first = numbers.findIndex(myFunction);

    function myFunction(value, index, array) {
    return value > 18;
    }

이 함수는 3개의 인수를 취합니다.

- The item value
- The item index
- The array itself

---

### Array.from()

이 Array.from()메서드는 길이 속성이 있는 개체 또는 반복 가능한 개체에서 Array 개체를 반환합니다.

    예시
    문자열에서 배열 만들기:

    Array.from("ABCDEFG") // Returns [A,B,C,D,E,F,G]

---

### Array.Keys()

이 Array.keys()메서드는 배열 키가 있는 Array Iterator 객체를 반환합니다.

    예시
    배열의 키를 포함하는 Array Iterator 객체를 만듭니다.

    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    const keys = fruits.keys();

    for (let x of keys) {
    text += x + "<br>";
    }
