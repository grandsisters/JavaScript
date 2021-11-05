## JavaScript Strings

JavaScript 문자열은 텍스트를 저장하고 조작하는 데 사용됩니다.

---

### 자바스크립트 문자열

JavaScript 문자열은 따옴표 안에 쓰여진 0개 이상의 문자입니다.

    	예시
    	let text = "John Doe";

작은따옴표나 큰따옴표를 사용할 수 있습니다.

    	예시
    	let carName1 = "Volvo XC60"; // Double quotes
    	let carName2 = 'Volvo XC60'; // Single quotes

문자열을 둘러싼 따옴표와 일치하지 않는 한 문자열 안에 따옴표를 사용할 수 있습니다.

    	예시
    	let answer1 = "It's alright";
    	let answer2 = "He is called 'Johnny'";
    	let answer3 = 'He is called "Johnny"';

---

### 문자열 길이

문자열의 길이를 찾으려면 내장 length속성을 사용하십시오 .

    	예시
    	let text = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    	text.length;    // Will return 26

---

### Escape Character

문자열은 따옴표로 묶어야 하기 때문에 JavaScript는 이 문자열을 잘못 이해합니다.

    let text = "We are the so-called "Vikings" from the north.";

문자열은 "We are the so-called " 와 " from the north."로 잘리게 될 것입니다.

이 문제를 피하기 위한 해결책은 백슬래시 이스케이프 문자 를 사용하는 것 입니다.

백슬래시( \) 이스케이프 문자는 특수 문자를 문자열 문자로 변환합니다.

| Code | Result | Description  |
| ---- | ------ | ------------ |
| \'   | '      | Single quote |
| \"   | "      | Double quote |
| \\   | \      | Backslash    |

시퀀스 \" 는 문자열에 큰따옴표를 삽입합니다.

    예시
    let text = "We are the so-called \"Vikings\" from the north.";

시퀀스 \' 는 문자열에 작은 따옴표를 삽입합니다.

    예시
    let text= 'It\'s alright.';

시퀀스 \\ 는 문자열에 백슬래시를 삽입합니다.

    예시
    let text = "The character \\ is called backslash.";

JavaScript에서는 6개의 다른 이스케이프 시퀀스가 ​​유효합니다.

| Code | Result               |
| ---- | -------------------- |
| \b   | Backspace            |
| \f   | Form Feed            |
| \n   | New Line             |
| \r   | Carriage Return      |
| \t   | Horizontal Tabulator |
| \v   | Vertical Tabulator   |

위의 6개의 이스케이프 문자는 원래 타자기, 텔레타이프 및 팩스를 제어하기 위해 설계되었습니다.

HTML에서는 의미가 없습니다.

---

### 긴 코드 줄 끊기

최고의 가독성을 위해 프로그래머는 종종 80자보다 긴 코드 라인을 피하고 싶어합니다.

JavaScript 문이 한 줄에 맞지 않는 경우 가장 좋은 위치는 연산자 다음입니다.

    예시
    document.getElementById("demo").innerHTML =
    "Hello Dolly!";

단일 백슬래시를 사용하여 텍스트 문자열 내에서 코드 줄을 나눌 수도 있습니다.

    예시
    document.getElementById("demo").innerHTML = "Hello \
    Dolly!";

이 \방법은 선호 하는 방법이 아닙니다. 보편적인 지원이 없을 수도 있습니다.
일부 브라우저는 \문자 뒤에 공백을 허용하지 않습니다 .

문자열을 분리하는 더 안전한 방법은 문자열 추가를 사용하는 것입니다.

    예시
    document.getElementById("demo").innerHTML = "Hello " +
    "Dolly!";

백슬래시로 코드 줄을 나눌 수 없습니다.

    예시
    document.getElementById("demo").innerHTML = \
    "Hello Dolly!";

---

### 문자열은 객체가 될 수 있습니다

일반적으로 JavaScript 문자열은 리터럴에서 생성된 기본 값입니다.

    let firstName = "John";

그러나 문자열은 키워드를 사용하여 객체로 정의할 수도 있습니다 new.

    let firstName = new String("John");

---

    	예시
    	let x = "John";
    	let y = new String("John");

    // typeof x will return string
    // typeof y will return object

---

    문자열을 객체로 만들지 마십시오. 실행 속도가 느려집니다.

    이 new키워드는 코드를 복잡하게 만듭니다. 이로 인해 예기치 않은 결과가 발생할 수 있습니다.

==연산자를 사용할 때 동일한 문자열은 동일합니다.

    예시

    let x = "John";
    let y = new String("John");

    // (x == y) is true because x and y have equal values

===연산자를 사용할 때 ===연산자는 데이터 유형과 값이 모두 같을 것으로 예상 하므로 동일한 값이 같지 않을 수 있습니다 .

    예시
    let x = "John";
    let y = new String("John");

    // (x === y) is false because x and y have different types (string and object)

또는 더 나쁜. 개체를 비교할 수 없습니다.

    예시1
    let x = new String("John");
    let y = new String("John");

    // (x == y) is false because x and y are objects

    예시2
    let x = new String("John");
    let y = new String("John");

    // (x === y) is false because x and y are objects

(x==y)와 의 차이점에 유의하십시오 (x===y).
또한 두 개의 자바 스크립트 객체를 비교하는 점에 유의 항상 돌아갑니다 false.
