## JavaScript Get Date Method

다음 메서드는 날짜 개체에서 정보를 얻는 데 사용할 수 있습니다.

| Method            | Description                                       |
| ----------------- | ------------------------------------------------- |
| getFullYear()     | Get the year as a four digit number (yyyy)        |
| getMonth()        | Get the month as a number (0-11)                  |
| getDate()         | Get the day as a number (1-31)                    |
| getHours()        | Get the hour (0-23)                               |
| getMinutes()      | Get the minute (0-59)                             |
| getSeconds()      | Get the second (0-59)                             |
| getMilliseconds() | Get the millisecond (0-999)                       |
| getTime()         | Get the time (milliseconds since January 1, 1970) |
| getDay()          | Get the weekday as a number (0-6)                 |
| Date.now()        | Get the time. ECMAScript 5.                       |

---

### getTime() 메서드

이 getTime()메서드는 1970년 1월 1일 이후의 밀리초 수를 반환합니다.

    예시
    const d = new Date();
    document.getElementById("demo").innerHTML = d.getTime();

---

### getFullYear() 메서드

이 getFullYear()메서드는 날짜의 연도를 4자리 숫자로 반환합니다.

    예시
    const d = new Date();
    document.getElementById("demo").innerHTML = d.getFullYear();

---

### getMonth() 메서드

이 getMonth()메서드는 날짜의 월을 숫자(0-11)로 반환합니다.

    예시
    const d = new Date();
    document.getElementById("demo").innerHTML = d.getMonth();

JavaScript에서 첫 번째 달(1월)은 0번째 달이므로 12월은 11번째 달을 반환합니다.

이름 배열을 사용 getMonth()하고 월을 이름으로 반환 할 수 있습니다 .

    예시
    const d = new Date();
    const months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
    document.getElementById("demo").innerHTML = months[d.getMonth()];

---

### getDate() 메서드

이 getDate()메서드는 날짜의 날짜를 숫자(1-31)로 반환합니다.

    예시
    const d = new Date();
    document.getElementById("demo").innerHTML = d.getDate();

---

### getHours() 메서드

이 getHours()메서드는 날짜의 시간을 숫자(0-23)로 반환합니다.

    예시
    const d = new Date();
    document.getElementById("demo").innerHTML = d.getHours();

---

### getMinutes() 메서드

이 getMinutes()메서드는 날짜의 분을 숫자(0-59)로 반환합니다.

    예시
    const d = new Date();
    document.getElementById("demo").innerHTML = d.getMinutes();

---

### getSeconds() 메서드

이 getSeconds()메서드는 날짜의 초를 숫자(0-59)로 반환합니다.

    예시
    const d = new Date();
    document.getElementById("demo").innerHTML = d.getSeconds();

---

### getMilliseconds() 메서드

이 getMilliseconds()메서드는 날짜의 밀리초를 숫자(0-999)로 반환합니다.

    예시
    const d = new Date();
    document.getElementById("demo").innerHTML = d.getMilliseconds();

---

### getDay() 메서드

이 getDay()메서드는 날짜의 요일을 숫자(0-6)로 반환합니다.

    예시
    const d = new Date();
    document.getElementById("demo").innerHTML = d.getDay();

JavaScript에서 요일(0)은 '일요일'을 의미하지만, 일부 국가에서는 요일을 '월요일'로 간주합니다.

이름 배열을 사용 getDay()하고 요일을 이름으로 반환 할 수 있습니다 .

    예시
    const d = new Date();
    const days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
    document.getElementById("demo").innerHTML = days[d.getDay()];

---

### UTC 날짜 방법

UTC 날짜 방법은 UTC 날짜(Universal Time Zone 날짜) 작업에 사용됩니다.

| Method               | Description                                                 |
| -------------------- | ----------------------------------------------------------- |
| getUTCDate()         | Same as getDate(), but returns the UTC date                 |
| getUTCDay()          | Same as getDay(), but returns the UTC day                   |
| getUTCFullYear()     | Same as getFullYear(), but returns the UTC year             |
| getUTCHours()        | Same as getHours(), but returns the UTC hour                |
| getUTCMilliseconds() | Same as getMilliseconds(), but returns the UTC milliseconds |
| getUTCMinutes()      | Same as getMinutes(), but returns the UTC minutes           |
| getUTCMonth()        | Same as getMonth(), but returns the UTC month               |
| getUTCSeconds()      | Same as getSeconds(), but returns the UTC seconds           |
