## JavaScript String Methods

문자열 메서드는 문자열로 작업하는 데 도움이 됩니다.

---

### 문자열 메서드 및 속성

"John Doe"와 같은 기본 값은 속성이나 메서드를 가질 수 없습니다(객체가 아니기 때문에).

그러나 JavaScript에서는 메서드와 속성을 실행할 때 JavaScript가 기본 값을 객체로 취급하기 때문에 메서드와 속성을 기본 값에도 사용할 수 있습니다.

---

### 문자열 길이

length속성은 문자열의 길이를 반환

    예시
    let txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    txt.length // Returns 26

---

### 문자열 부분 추출

문자열의 일부를 추출하는 방법에는 3가지가 있습니다.

- slice(start, end)
- substring(start, end)
- substr(start, length)

---

### slice() 메서드

slice() 문자열의 일부를 추출하고 추출된 부분을 새 문자열로 반환합니다.

이 메서드는 시작 위치와 끝 위치(끝은 포함되지 않음)의 2가지 매개변수를 사용합니다.

이 예에서는 문자열의 일부를 위치 7에서 위치 12(13-1)로 잘라냅니다.

    예시
    let str = "Apple, Banana, Kiwi";
    str.slice(7, 13) // Returns Banana

기억하십시오: JavaScript는 0부터 위치를 계산합니다. 첫 번째 위치는 0입니다.

매개변수가 음수이면 위치는 문자열 끝에서 계산됩니다.

이 예에서는 위치 -12에서 위치 -6까지 문자열의 일부를 잘라냅니다.

    예시
    let str = "Apple, Banana, Kiwi";
    str.slice(-12, -6) // Returns Banana

두 번째 매개변수를 생략하면 이 메서드는 나머지 문자열을 잘라냅니다.

    예시
    str.slice(7); // Returns Banana,Kiwi

또는 끝에서 계산:

    예시
    str.slice(-12) // Returns Banana,Kiwi

---

### substring() 메서드

substring()은 slice()와 비슷합니다

차이점은 substring()음수 인덱스를 허용할 수 없다는 것입니다.

    예시
    let str = "Apple, Banana, Kiwi";
    substring(7, 13) // Returns Banana

두 번째 매개변수를 생략 substring()하면 문자열의 나머지 부분을 잘라냅니다.

---

### substr() 메서드

substr()도 slice()와 비슷합니다 .

차이점은 두 번째 매개변수 가 추출된 부분 의 길이 를 지정한다는 것 입니다.

    예시
    let str = "Apple, Banana, Kiwi";
    str.substr(7, 6) // Returns Banana

res의 결과는 다음과 같습니다.

    Banana

두 번째 매개변수를 생략 substr()하면 문자열의 나머지 부분을 잘라냅니다.

    예시
    let str = "Apple, Banana, Kiwi";
    str.substr(7) // Returns Banana,Kiwi

첫 번째 매개변수가 음수이면 위치는 문자열 끝에서 계산됩니다.

    예시
    let str = "Apple, Banana, Kiwi";
    str.substr(-4) // Returns Kiwi

---

### 문자열 내용 바꾸기

이 replace()메서드는 지정된 값을 문자열의 다른 값으로 바꿉니다.

    예시
    let text = "Please visit Microsoft!";
    let newText = text.replace("Microsoft", "W3Schools");

replace()메서드는 호출되는 문자열을 변경하지 않습니다. 새 문자열을 반환합니다.

기본적으로 이 replace()메서드는 첫 번째 일치 항목 만 대체합니다 .

    예시
    let text = "Please visit Microsoft and Microsoft!";
    let newText = text.replace("Microsoft", "W3Schools");

기본적으로 replace()메서드는 대소문자를 구분합니다. MICROSOFT(대문자 포함) 쓰기는 작동하지 않습니다.

    예시
    let text = "Please visit Microsoft!";
    let newText = text.replace("MICROSOFT", "W3Schools");

대소문자를 구분하지 않으려면 다음 과 같이 플래그가 있는 정규식을 사용합니다 /i(비구분).

    예시
    let text = "Please visit Microsoft!";
    let newText = text.replace(/MICROSOFT/i, "W3Schools");

정규식은 따옴표 없이 작성됩니다.

모든 일치 항목을 바꾸려면 정규식 을 /g플래그(전역 일치) 와 함께 사용하십시오 .

    예시
    let text = "Please visit Microsoft and Microsoft!";
    let newText = text.replace(/Microsoft/g, "W3Schools");

---

### 대문자 및 소문자로 변환

문자열은 toUpperCase()을 사용하여 대문자로 변환됩니다 .

    예시
    let text1 = "Hello World!"; // String
    let text2 = text1.toUpperCase(); // text2 is text1 converted to upper

문자열은 다음을 사용하여 소문자로 변환됩니다 toLowerCase().

    예시
    let text1 = "Hello World!"; // String
    let text2 = text1.toLowerCase(); // text2 is text1 converted to lower

---

### concat() 메서드

concat() 두 개 이상의 문자열을 결합합니다.

    예시
    let text1 = "Hello";
    let text2 = "World";
    let text3 = text1.concat(" ", text2);

이 concat()메서드는 더하기 연산자 대신 사용할 수 있습니다. 이 두 줄은 동일한 작업을 수행합니다.

    예시1
    text = "Hello" + " " + "World!";

    예시2
    text = "Hello".concat(" ", "World!");

모든 문자열 메서드는 새 문자열을 반환합니다. 그들은 원래 문자열을 수정하지 않습니다.

    공식적으로 말하길: 문자열은 변경할 수 없습니다. 문자열은 변경할 수 없고 교체만 가능합니다.

---

### String.trim()

이 trim()메서드는 문자열의 양쪽에서 공백을 제거합니다.

    예시
    let text = " Hello World! ";
    text.trim() // Returns "Hello World!"

---

### 자바스크립트 문자열 패딩

ECMAScript 2017에는 두 개의 String 메서드가 추가되었습니다.

padStart 및 padEnd는 문자열의 시작과 끝에서 패딩을 지원합니다.

    예시
    let text = "5";
    text.padStart(4,0) // Returns 0005

    예시
    let text = "5";
    text.padEnd(4,0) // Returns 5000

---

### 문자열 문자 추출

문자열 문자를 추출하는 방법에는 3가지가 있습니다.

- charAt(position)
- charCodeAt(position)
- 속성 액세스 [ ]

---

### charAt() 메서드

이 charAt()메서드는 문자열의 지정된 인덱스(위치)에 있는 문자를 반환합니다.

    예시
    let text = "HELLO WORLD";

    text.charAt(0) // Returns H

---

### charCodeAt() 메서드

이 charCodeAt()메서드는 문자열의 지정된 인덱스에 있는 문자의 유니코드를 반환합니다.

이 메서드는 UTF-16 코드(0에서 65535 사이의 정수)를 반환합니다.

    예시
    let text = "HELLO WORLD";

    text.charCodeAt(0) // Returns 72

---

### Property Access

ECMAScript 5(2009)는 문자열에 대한 속성 액세스 [ ]를 허용합니다.

    예시
    let text = "HELLO WORLD";
    text[0]                   // returns H


    속성 액세스는 약간 예측할 수 없습니다.

    - 문자열을 배열처럼 보이게 합니다(그러나 그렇지 않습니다).
    - 문자가 없으면 [ ]는 undefined를 반환하고 charAt()는 빈 문자열을 반환합니다.
    - 읽기 전용입니다. str[0] = "A"는 오류를 표시하지 않습니다(하지만 작동하지 않습니다!)

    예시

    let text = "HELLO WORLD";
    text[0] = "A" // Gives no error, but does not work
    text[0] // returns H

문자열을 배열로 사용하려는 경우 배열로 변환할 수 있습니다.

---

### 문자열을 배열로 변환

다음 split()메소드 를 사용하여 문자열을 배열로 변환할 수 있습니다 .

    예시
    text.split(",") // Split on commas
    text.split(" ") // Split on spaces
    text.split("|") // Split on pipe

구분 기호를 생략하면 반환된 배열에 인덱스 [0]의 전체 문자열이 포함됩니다.

구분 기호가 ""이면 반환된 배열은 단일 문자 배열이 됩니다.

    예시
    text.split("") // Split in characters
