## JavaScript Maps

Map은 키가 모든 데이터 유형이 될 수 있는 키-값 쌍을 보유합니다.

Map은 키의 원래 삽입 순서를 기억합니다.

---

### Essensial Map Methods

| Method    | Description                                              |
| --------- | -------------------------------------------------------- |
| new Map() | Creates a new Map                                        |
| set()     | Sets the value for a key in a Map                        |
| get()     | Gets the value for a key in a Map                        |
| delete()  | Removes a Map element specified by the key               |
| has()     | Returns true if a key exists in a Map                    |
| forEach() | Calls a function for each key/value pair in a Map        |
| entries() | Returns an iterator with the [key, value] pairs in a Map |

| Property | Description                             |
| -------- | --------------------------------------- |
| size     | Returns the number of elements in a Map |

---

### Map을 만드는 방법

다음을 통해 JavaScript 맵을 만들 수 있습니다.

- 배열 전달 new Map()
- map을 만들고 사용 Map.set()

---

### new Map() 메서드

new Map()생성자에 배열을 전달하여 맵을 만들 수 있습니다 .

    예시
    // Create a Map
    const fruits = new Map([
      ["apples", 500],
      ["bananas", 300],
      ["oranges", 200]
    ]);

---

### set() 메서드

다음 set()방법 을 사용하여 맵에 요소를 추가할 수 있습니다 .

    예시
    // Create a Map
    const fruits = new Map();

    // Set Map Values
    fruits.set("apples", 500);
    fruits.set("bananas", 300);
    fruits.set("oranges", 200);

이 set()방법을 사용하여 기존 Map 값을 변경할 수도 있습니다.

    예시
    fruits.set("apples", 500);

---

### get() 메서드

이 get()메서드는 Map의 키 값을 가져옵니다.

    예시
    fruits.get("apples"); // Returns 500

---

### 크기 속성

이 size속성은 Map의 요소 수를 반환합니다.

    예시
    fruits.size;

---

### delete() 메서드

이 delete()메서드는 Map 요소를 제거합니다.

    예시
    fruits.delete("apples");

---

### has() 메서드

has()키가 맵에 존재하는 경우 메소드는 true를 돌려줍니다 :

    예시
    fruits.has("apples");

    존재하지 않는다면 false:
    fruits.delete("apples");
    fruits.has("apples");

---

### JavaScript Objects vs Maps

객체와 맵의 차이점

| -       | 물체                                | 지도                                    |
| ------- | ----------------------------------- | --------------------------------------- |
| 반복    | 가능 직접 반복할 수 없음            | 직접 반복 가능                          |
| 크기    | 크기 속성이 없습니다.               | 크기 속성이 있습니다.                   |
| 키 유형 | 키는 문자열 또는 심볼이어야 합니다. | 키는 모든 데이터 유형이 될 수 있습니다. |
| 키 순서 | 키가 잘 정렬되어 있지 않습니다.     | 키는 삽입 순서로 정렬됩니다.            |
| 기본값  | 기본 키 보유                        | 기본 키가 없습니다                      |

---

### forEach() 메서드

이 forEach()메서드는 Map의 각 키/값 쌍에 대한 함수를 호출합니다.

    예시
    // List all entries
    let text = "";
    fruits.forEach (function(value, key) {
    text += key + ' = ' + value;
    })

---

### entries() 메서드

이 entries()메서드는 Map에 [key, values]가 있는 반복자 객체를 반환합니다.

    예시
    // List all entries
    let text = "";
    for (const x of fruits.entries()) {
    text += x;
    }
