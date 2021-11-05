## JavaScript Array Methods

### 배열을 문자열로 변환

JavaScript 메서드 toString()는 배열을 (쉼표로 구분된) 배열 값의 문자열로 변환합니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    document.getElementById("demo").innerHTML = fruits.toString();

    결과:
    Banana,Orange,Apple,Mango

이 join()메서드는 또한 모든 배열 요소를 문자열로 결합합니다.

toString() 처럼 작동하지만 추가로 구분 기호를 지정할 수 있습니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    document.getElementById("demo").innerHTML = fruits.join(" * ");

    결과:
    Banana * Orange * Apple * Mango

---

### Popping and Pushing

<br/>

### Popping

pop()메서드는 배열에서 마지막 요소를 제거합니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.pop(); // Removes "Mango" from fruits

pop()메서드는 "팝아웃"된 값을 반환합니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    let x = fruits.pop(); // x = "Mango"

<br />

### Pushing

push()메서드는 배열에 새 요소를 추가합니다(마지막에).

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.push("Kiwi");   // Adds "Kiwi" to fruits

push()메서드는 새 배열 길이를 반환합니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    let x = fruits.push("Kiwi");   //  x = 5

---

### Shifting Elements

시프팅은 팝핑과 동일하며 마지막 요소 대신 첫 번째 요소에서 작업합니다.

이 shift()메서드는 첫 번째 배열 요소를 제거하고 다른 모든 요소를 ​​더 낮은 인덱스로 "이동"합니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.shift(); // Removes "Banana" from fruits

이 shift()메서드는 "이동된" 값을 반환합니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    let x = fruits.shift(); // x = "Banana"

이 unshift()메서드는 배열에 새 요소를 추가하고(처음에) 이전 요소를 "이동 해제"합니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.unshift("Lemon"); // Adds "Lemon" to fruits

이 unshift()메서드는 새 배열 길이를 반환합니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.unshift("Lemon"); // Returns 5

---

### 요소 변경

배열 요소는 인덱스 번호를 사용하여 액세스합니다 .

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits[0] = "Kiwi"; // Changes the first element of fruits to "Kiwi"

이 length속성은 배열에 새 요소를 추가하는 쉬운 방법을 제공합니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits[fruits.length] = "Kiwi"; // Appends "Kiwi" to fruits

---

### 요소 삭제

JavaScript 배열은 객체이므로 JavaScript 연산자 delete를 사용하여 요소를 삭제할 수 있습니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    delete fruits[0]; // Changes the first element in fruits to undefined

delete를 사용 하면 배열에 정의되지 않은 구멍이 남을 수 있습니다. 대신 pop() 또는 shift()를 사용하십시오.

---

### Splicing an Array

splice()메서드는 배열에 새 항목을 추가하는 데 사용할 수 있습니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.splice(2, 0, "Lemon", "Kiwi");

첫번째 파라미터 (2)의 위치를 정의하는 새로운 요소가되어야 첨가 (에 접합 참조).

두 번째 매개변수(0)는 제거 해야 하는 요소의 수를 정의 합니다 .

나머지 매개변수("Lemon" , "Kiwi")는 추가 할 새 요소를 정의합니다 .

이 splice()메서드는 삭제된 항목이 있는 배열을 반환합니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.splice(2, 2, "Lemon", "Kiwi");

---

### splice()를 사용하여 요소 제거

영리한 매개변수 설정을 사용 splice()하면 배열에 "구멍"을 남기지 않고 요소를 제거 하는 데 사용할 수 있습니다 .

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.splice(0, 1); // Removes the first element

첫 번째 매개변수(0)는 새 요소를 추가 (연결) 해야 하는 위치를 정의합니다 .

두 번째 매개변수(1)는 제거 해야 하는 요소의 수를 정의 합니다 .

나머지 매개변수는 생략됩니다. 새로운 요소가 추가되지 않습니다.

---

### Merging (Concatenating) Arrays

이 concat()메서드는 기존 배열을 병합(연결)하여 새 배열을 만듭니다.

    예시(두 배열 병합)
    const myGirls = ["Cecilie", "Lone"];
    const myBoys = ["Emil", "Tobias", "Linus"];

    // Concatenate (join) myGirls and myBoys
    const myChildren = myGirls.concat(myBoys);

이 concat()방법은 기존 어레이를 변경하지 않습니다. 항상 새 배열을 반환합니다.

이 concat()메서드는 배열 인수를 원하는 만큼 사용할 수 있습니다.

    예시(3개의 배열 병합)
    const arr1 = ["Cecilie", "Lone"];
    const arr2 = ["Emil", "Tobias", "Linus"];
    const arr3 = ["Robin", "Morgan"];
    const myChildren = arr1.concat(arr2, arr3);

이 concat()메서드는 문자열을 인수로 사용할 수도 있습니다.

    예시(값과 배열 병합)
    const arr1 = ["Emil", "Tobias", "Linus"];
    const myChildren = arr1.concat("Peter");

---

### Slicing an Array

이 slice()메서드는 배열의 일부를 새 배열로 잘라냅니다.

이 예에서는 배열 요소 1("주황색")에서 시작하는 배열의 일부를 잘라냅니다.

    예시
    const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
    const citrus = fruits.slice(1);

이 slice()메서드는 새 배열을 만듭니다. 소스 배열에서 요소를 제거하지 않습니다.

이 예에서는 배열 요소 3("Apple")에서 시작하는 배열의 일부를 잘라냅니다.

    예시
    const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
    const citrus = fruits.slice(3);

이 slice()메서드는 와 같은 두 개의 인수를 사용할 수 있습니다 slice(1, 3).

그런 다음 메서드는 시작 인수에서 끝 인수까지(포함하지 않음) 요소를 선택합니다.

    예시
    const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
    const citrus = fruits.slice(1, 3);

첫 번째 예와 같이 end 인수가 생략되면 이 slice() 메서드는 배열의 나머지 부분을 잘라냅니다.

    예시
    const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
    const citrus = fruits.slice(2);

---

### Automatic toString()

JavaScript는 기본 값이 예상되는 경우 배열을 쉼표로 구분된 문자열로 자동 변환합니다.

이것은 배열을 출력하려고 할 때 항상 그렇습니다.

이 두 예는 동일한 결과를 생성합니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    document.getElementById("demo").innerHTML = fruits.toString();

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    document.getElementById("demo").innerHTML = fruits;

모든 JavaScript 객체에는 toString() 메서드가 있습니다.

---

### Complete Array Reference

전체 참조를 보려면 [전체 JavaScript 배열 참조](https://www.w3schools.com/jsref/jsref_obj_array.asp)로 이동하십시오 .

참조에는 모든 Array 속성 및 메서드에 대한 설명과 예가 포함되어 있습니다.
