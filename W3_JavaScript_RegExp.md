## JavaScript Regular Expressions

정규식은 검색 패턴을 형성하는 일련의 문자입니다.

검색 패턴은 텍스트 검색 및 텍스트 바꾸기 작업에 사용할 수 있습니다.

---

### 정규 표현식이란 무엇입니까?

정규식은 검색 패턴 을 형성하는 일련의 문자입니다 .

텍스트에서 데이터를 검색할 때 이 검색 패턴을 사용하여 검색하는 내용을 설명할 수 있습니다.

정규식은 단일 문자이거나 더 복잡한 패턴일 수 있습니다.

정규식은 모든 유형의 텍스트 검색 및 텍스트 바꾸기 작업 을 수행하는 데 사용할 수 있습니다 .

    sytax:
    /pattern/modifiers;

    예시
    /w3schools/i;

---

### 문자열 메서드 사용

자바 스크립트에서 정규 표현식은 종종 이 두개의 메소드와 함께 사용된다. : search()와 replace().

search()메서드는 표현식을 사용하여 일치 항목을 검색하고 일치 항목의 위치를 ​​반환합니다.

replace()메서드는 패턴이 대체된 수정된 문자열을 반환합니다.

---

### 문자열과 함께 문자열 search() 사용

이 search()메서드는 문자열에서 지정된 값을 검색하고 일치하는 위치를 반환합니다.

    예시
    문자열을 사용하여 문자열에서 "W3schools"를 검색합니다.

    let text = "Visit W3Schools!";
    let n = text.search("W3Schools");

    n 의 결과 는 다음과 같습니다.
    6

---

### 정규 표현식과 함께 문자열 search() 사용

    예시
    정규식을 사용하여 문자열에서 "w3schools"에 대해 대소문자를 구분하지 않고 검색합니다.

    let text = "Visit W3Schools";
    let n = text.search(/w3schools/i);

    n 의 결과 는 다음과 같습니다.
    6

---

### 문자열과 함께 문자열 replace() 사용

이 replace()메서드는 지정된 값을 문자열의 다른 값으로 바꿉니다.

    let text = "Visit Microsoft!";
    let result = text.replace("Microsoft", "W3Schools");

---

### 정규 표현식과 함께 String replace() 사용

    예시
    대소문자를 구분하지 않는 정규식을 사용하여 문자열에서 Microsoft를 W3Schools로 바꿉니다.

    let text = "Visit Microsoft!";
    let result = text.replace(/microsoft/i, "W3Schools");

    res 의 결과 는 다음과 같습니다.
    Visit W3Schools!

<br />

    눈치채셨나요?
    위의 방법에서 문자열 인수 대신 정규식 인수를 사용할 수 있습니다.
    정규식은 검색을 훨씬 더 강력하게 만들 수 있습니다(예: 대소문자 구분 안 함).

---

### 정규 표현식 패턴

대괄호 는 문자 범위를 찾는 데 사용됩니다.

| Expression | Description                                     |
| ---------- | ----------------------------------------------- |
| [abc]      | Find any of the characters between the brackets |
| [0-9]      | Find any of the digits between the brackets     |
| (x\|y)     | Find any of the alternatives separated with \|  |

메타 문자 는 특별한 의미를 가진 문자입니다.

| Metacharacter | Description                                                                                          |
| ------------- | ---------------------------------------------------------------------------------------------------- |
| \d            | Find a digit                                                                                         |
| \s            | Find a whitespace character                                                                          |
| \b            | Find a match at the beginning of a word like this: \bWORD, or at the end of a word like this: WORD\b |
| \uxxxx        | Find the Unicode character specified by the hexadecimal number xxxx                                  |

수량 자는 수량을 정의합니다.

| Quantifier | Description                                                    |
| ---------- | -------------------------------------------------------------- |
| n+         | Matches any string that contains at least one n                |
| n\*        | Matches any string that contains zero or more occurrences of n |
| n?         | Matches any string that contains zero or one occurrences of n  |

---

## RegExp 개체 사용

JavaScript에서 RegExp 개체는 미리 정의된 속성과 메서드가 있는 정규식 개체입니다.

---

### 테스트() 사용

test()방법은 정규식 표현 방법이다.

문자열에서 패턴을 검색하고 결과에 따라 true 또는 false를 반환합니다.

다음 예에서는 문자열에서 "e" 문자를 검색합니다.

    예시
    const pattern = /e/;
    pattern.test("The best things in life are free!");

    문자열에 "e"가 있으므로 위 코드의 출력은 다음과 같습니다.
    true

정규 표현식을 변수에 먼저 넣을 필요는 없습니다. 위의 두 줄을 하나로 줄일 수 있습니다.

    /e/.test("The best things in life are free!");

---

### exec() 사용

exec()방법은 정규식 표현 방법이다.

지정된 패턴에 대한 문자열을 검색하고 찾은 텍스트를 객체로 반환합니다.

일치하는 항목이 없으면 빈 (null) 개체를 반환 합니다.

다음 예에서는 문자열에서 "e" 문자를 검색합니다.

    예시
    /e/.exec("The best things in life are free!");
