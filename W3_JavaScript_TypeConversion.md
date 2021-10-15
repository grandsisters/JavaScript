## JavaScript Type Conversion

- 문자열을 숫자로 변환
- 숫자를 문자열로 변환
- 날짜를 숫자로 변환
- 숫자를 날짜로 변환
- 부울을 숫자로 변환
- 숫자를 부울로 변환

### 자바스크립트 유형 변환

JavaScript 변수는 새 변수 및 다른 데이터 유형으로 변환할 수 있습니다.

- JavaScript 기능을 사용하여
- JavaScript 자체에 의해 자동 으로

---

### 문자열을 숫자로 변환

전역 메서드 Number()는 문자열을 숫자로 변환할 수 있습니다.

숫자를 포함하는 문자열(예: "3.14")은 숫자(예: 3.14)로 변환됩니다.

빈 문자열은 0으로 변환됩니다.

다른 모든 것은 NaN(숫자가 아님) 로 변환됩니다 .

    Number("3.14") // returns 3.14
    Number(" ") // returns 0
    Number("") // returns 0
    Number("99 88") // returns NaN

---

### Number Method

| Method       | Description                                         |
| ------------ | --------------------------------------------------- |
| Number()     | Returns a number, converted from its argument       |
| parseFloat() | Parses a string and returns a floating point number |
| parseInt()   | Parses a string and returns an integer              |

---

### 단항 + 연산자

단항 + 연산자는 숫자에 변수를 변환 할 수 있습니다 :

    예시
    let y = "5"; // y is a string
    let x = + y; // x is a number

변수를 변환할 수 없는 경우에도 숫자가 되지만 값은 NaN (숫자가 아님):

    예시
    let y = "John"; // y is a string
    let x = + y; // x is a number (NaN)

---

### 숫자를 문자열로 변환

전역 메서드 String()는 숫자를 문자열로 변환할 수 있습니다.

모든 유형의 숫자, 리터럴, 변수 또는 표현식에 사용할 수 있습니다.

    예시
    String(x) // returns a string from a number variable x
    String(123) // returns a string from a number literal 123
    String(100 + 23) // returns a string from a number from an expression

Number 메서드 toString()도 마찬가지입니다.

    예시
    x.toString()
    (123).toString()
    (100 + 23).toString()

---

### more Methods

| Method          | Description                                                                              |
| --------------- | ---------------------------------------------------------------------------------------- |
| toExponential() | Returns a string, with a number rounded and written using exponential notation.          |
| toFixed()       | Returns a string, with a number rounded and written with a specified number of decimals. |
| toPrecision()   | Returns a string, with a number written with a specified length                          |

---

### 날짜를 숫자로 변환

전역 방법 Number()을 사용하여 날짜를 숫자로 변환할 수 있습니다.

    d = new Date();
    Number(d) // returns 1404568027739

날짜 방법 getTime() 도 동일합니다.

    d = new Date();
    d.getTime() // returns 1404568027739

---

### 날짜를 문자열로 변환

전역 메서드 String()는 날짜를 문자열로 변환할 수 있습니다.

    String(Date()) // returns "Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)"

Date 메서드 toString()도 마찬가지입니다.

    예시
    Date().toString() // returns "Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)"

| Method            | Description                                       |
| ----------------- | ------------------------------------------------- |
| getDate()         | Get the day as a number (1-31)                    |
| getDay()          | Get the weekday a number (0-6)                    |
| getFullYear()     | Get the four digit year (yyyy)                    |
| getHours()        | Get the hour (0-23)                               |
| getMilliseconds() | Get the milliseconds (0-999)                      |
| getMinutes()      | Get the minutes (0-59)                            |
| getMonth()        | Get the month (0-11)                              |
| getSeconds()      | Get the seconds (0-59)                            |
| getTime()         | Get the time (milliseconds since January 1, 1970) |

---

### boolean값을 숫자로 변환

전역 메서드 Number()는 boolean값을 숫자로 변환할 수도 있습니다.

    Number(false) // returns 0
    Number(true) // returns 1

---

### boolean값을 문자열로 변환

전역 메서드 String()는 boolean을 문자열로 변환할 수 있습니다.

    String(false) // returns "false"
    String(true) // returns "true"

Boolean 메서드 toString()도 마찬가지입니다.

    false.toString() // returns "false"
    true.toString() // returns "true"

---

### 자동 유형 변환

JavaScript가 "잘못된" 데이터 유형에서 작동하려고 하면 값을 "올바른" 유형으로 변환하려고 시도합니다.

결과가 항상 기대하는 것은 아닙니다.

    5 + null // returns 5 because null is converted to 0
    "5" + null // returns "5null" because null is converted to "null"
    "5" + 2 // returns "52" because 2 is converted to "2"
    "5" - 2 // returns 3 because "5" is converted to 5
    "5" * "2" // returns 10 because "5" and "2" are converted to 5 and 2

---

### 자동 문자열 변환

JavaScript toString()는 객체 또는 변수를 "출력"하려고 할 때 자동으로 변수의 기능을 호출합니다 .

    document.getElementById("demo").innerHTML = myVar;

    // if myVar = {name:"Fjohn"} // toString converts to "[object Object]"
    // if myVar = [1,2,3,4] // toString converts to "1,2,3,4"
    // if myVar = new Date() // toString converts to "Fri Jul 18 2014 09:08:55 GMT+0200"

숫자와 부울도 변환되지만 잘 보이지 않습니다.

    // if myVar = 123 // toString converts to "123"
    // if myVar = true // toString converts to "true"
    // if myVar = false // toString converts to "false"

---
