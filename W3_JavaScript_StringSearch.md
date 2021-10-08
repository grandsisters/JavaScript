## JavaScript String Search

    문자열 검색을 위한 JavaScript 메소드:

    String.indexOf()
    String.lastIndexOf()
    String.startsWith()
    String.endsWith()

---

### String.indexOf()

이 indexOf()메서드는 지정된 텍스트의 발생 인덱스(위치)를 첫 번째 문자열부터 계산해 반환 합니다.

    예시
    let str = "Please locate where 'locate' occurs!";
    str.indexOf("locate") // Returns 7

---

### String.lastIndexOf()

이 lastIndexOf()메서드는 문자열에서 지정된 텍스트가 마지막으로 나타나는 인덱스를 반환 합니다.

    예시
    let str = "Please locate where 'locate' occurs!";
    str.lastIndexOf("locate") // Returns 21

indexOf(), lastIndexOf() 둘 다 텍스트가 없으면 -1을 반환합니다.

    예시
    let str = "Please locate where 'locate' occurs!";
    str.lastIndexOf("John") // Returns -1

두 메서드 모두 검색의 시작 위치로 두 번째 매개변수를 허용합니다.

    예시
    let str = "Please locate where 'locate' occurs!";
    str.indexOf("locate", 15) // Returns 21

lastIndexOf() 메서드는 끝에서 시작까지 거꾸로 검색합니다. 즉, 두 번째 매개 변수가 15인 경우 검색은 위치 15에서 시작하여 문자열의 시작 부분을 검색합니다.

    예시
    let str = "Please locate where 'locate' occurs!";
    str.lastIndexOf("locate", 15) // Returns 7

---

### String.search()

이 search()메서드는 문자열에서 지정된 값을 검색하고 일치하는 위치를 반환합니다.

    예시
    let str = "Please locate where 'locate' occurs!";
    str.search("locate") // Returns 7

---

두 가지 메서드 indexOf(), search()는 동일합니까?

그들은 동일한 인수(매개변수)를 받아들이고 동일한 값을 반환합니까?

두 가지 방법은 동일 하지 않습니다 . 차이점은 다음과 같습니다.

- search()메서드는 두 번째 시작 위치 인수를 사용할 수 없습니다.
- 이 indexOf()메서드는 강력한 검색 값(정규 표현식)을 사용할 수 없습니다.

정규 표현식에 대한 자세한 내용은 이후 장에서 배우게 될 것입니다.

---

### String.match()

match() 메서드는 문자열에서 정규식과 일치하는 항목을 검색하고 일치 항목을 Array 객체로 반환합니다.

    예시
    "ain"에 대한 문자열 검색:

    let text = "The rain in SPAIN stays mainly in the plain";
    text.match(/ain/g) // Returns an array [ain,ain,ain]

JS RegExp 장에서 정규식에 대해 자세히 읽어보십시오 .

정규식에 g 수정자가 포함되어 있지 않으면 ( 전역 검색 을 수행하기 위해 ) match() 메서드는 문자열의 첫 번째 일치 항목만 반환합니다.

### syntax

    string.match(regexp)

| 문법     | 설명                                                                                           |
| -------- | ---------------------------------------------------------------------------------------------- |
| regexp   | 필수, 정규식으로 검색할 값입니다.                                                              |
| Returns: | 일치하는 항목이 포함된 배열, 일치하는 항목이 한 개씩 포함되거나 일치하는 항목이 없는 경우 null |

    예시
    "ain"에 대해 대소문자를 구분하지 않는 전역 검색을 수행합니다.

    let text = "The rain in SPAIN stays mainly in the plain";
    text.match(/ain/gi)   // Returns an array [ain,AIN,ain,ain]

---

### String.includes()

includes()문자열이 특정 값을 포함하는 경우 메소드는 true를 돌려줍니다.

    예시
    let text = "Hello world, welcome to the universe.";
    text.includes("world") // Returns true

### sytax

    string.includes(searchvalue, start)

| 문법        | 설명                                                                            |
| ----------- | ------------------------------------------------------------------------------- |
| searchvalue | 필수, 검색할 문자열                                                             |
| start       | 선택 사항. 기본값 0입니다. 검색을 시작할 위치                                   |
| Returns:    | 문자열에 값이 포함되어 있으면 true를 반환하고 그렇지 않으면 false를 반환합니다. |

    문자열에 "world"가 포함되어 있는지 확인하고 위치 12에서 검색을 시작합니다.

    let text = "Hello world, welcome to the universe.";
    text.includes("world", 12)    // Returns false

---

### String.startsWith()

이 startsWith()메서드는 true 문자열이 지정된 값으로 시작하면 반환 하고, 그렇지 않으면 false다음을 반환합니다 .

    예시
    let text = "Hello world, welcome to the universe.";

    text.startsWith("Hello") // Returns true

### sytax

    string.startsWith(searchvalue, start)

매개변수 값

| Parameter   | Description                                            |
| ----------- | ------------------------------------------------------ |
| searchvalue | Required. The value to search for.                     |
| start       | Optional. Default 0. The position to start the search. |

    예시
    let text = "Hello world, welcome to the universe.";

    text.startsWith("world")    // Returns false
    let text = "Hello world, welcome to the universe.";

    text.startsWith("world", 5)    // Returns false
    let text = "Hello world, welcome to the universe.";

    text.startsWith("world", 6)    // Returns true

참고 :startsWith() 방법은 대소 문자를 구분합니다.

---

### String.endsWith()

이 endsWith()메서드는 문자열이 지정된 값으로 끝나면 true를 반환 하고, 그렇지 않으면 false를 반환합니다 .

    예시
    문자열이 "Doe"로 끝나는지 확인:

    var text = "John Doe";
    text.endsWith("Doe") // Returns true

### sytax

    string.endswith(searchvalue, length)

| 매개변수    | 값                                 |
| ----------- | ---------------------------------- |
| Parameter   | Description                        |
| searchvalue | Required. The value to search for. |
| length      | Optional. The length to search.    |

"world"로 끝나는 문자열의 첫 11개 문자를 확인하십시오.

    let text = "Hello world, welcome to the universe.";
    text.endsWith("world", 11)    // Returns true

참고 :endsWith() 방법은 대소 문자를 구분합니다.
