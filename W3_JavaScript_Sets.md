## JavaScript Sets

JavaScript 세트는 고유한 값의 모음입니다.

각 값은 세트에서 한 번만 발생할 수 있습니다.

### 필수 세트 방법

| Method    | Description                                      |
| --------- | ------------------------------------------------ |
| new Set() | Creates a new Set                                |
| add()     | Adds a new element to the Set                    |
| delete()  | Removes an element from a Set                    |
| has()     | Returns true if a value exists in the Set        |
| forEach() | Invokes a callback for each element in the Set   |
| values()  | Returns an iterator with all the values in a Set |

| Property | Description                             |
| -------- | --------------------------------------- |
| size     | Returns the number of elements in a Set |

### 세트를 만드는 방법

다음을 통해 JavaScript 세트를 만들 수 있습니다.

배열 전달 new Set()
새 집합 add()을 만들고 값을 추가 하는 데 사용
새 집합 add()을 만들고 변수를 추가 하는 데 사용

---

### 새로운 Set() 메서드

new Set()생성자에 배열을 전달합니다 .

    예시
    // Create a Set
    const letters = new Set(["a","b","c"]);

집합을 만들고 값을 추가합니다.

    예시
    // Create a Set
    const letters = new Set();

    // Add Values to the Set
    letters.add("a");
    letters.add("b");
    letters.add("c");

집합을 만들고 변수를 추가합니다.

    예시
    // Create a Set
    const letters = new Set();

    // Create Variables
    const a = "a";
    const b = "b";
    const c = "c";

    // Add Variables to the Set
    letters.add(a);
    letters.add(b);
    letters.add(c);

---

### add() 메서드

    예시
    letters.add("d");
    letters.add("e");

동일한 요소를 추가하면 첫 번째 요소만 저장됩니다.

    예시
    letters.add("a");
    letters.add("b");
    letters.add("c");
    letters.add("c");
    letters.add("c");
    letters.add("c");
    letters.add("c");
    letters.add("c");

---

### forEach() 메서드

이 forEach()메서드는 각 Set 요소에 대한 함수를 호출(호출)합니다.

    예시
    // Create a Set
    const letters = new Set(["a","b","c"]);

    // List all Elements
    let text = "";
    letters.forEach (function(value) {
    text += value;
    })

---

### values() 메서드

이 values()메서드는 Set의 모든 값을 포함하는 새 반복자 객체를 반환합니다.

    예시
    letters.values() // Returns [object Set Iterator]

이제 Iterator 객체를 사용하여 요소에 액세스할 수 있습니다.

    예시
    // List all Elements
    let text = "";
    for (const x of letters.values()) {
    text += x;
    }
