## JavaScript Set Date Methods

날짜 설정 방법을 사용하면 날짜 개체에 대한 날짜 값(년, 월, 일, 시, 분, 초, 밀리초)을 설정할 수 있습니다.

---

### 날짜 방법 설정

날짜 설정 방법은 날짜의 일부를 설정하는 데 사용됩니다.

| Method                         | Description                                       |
| ------------------------------ | ------------------------------------------------- |
| setDate()                      | Set the day as a number (1-31)                    |
| setFullYear()                  | Set the year (optionally month and day)           |
| setHours() Set the hour (0-23) |
| setMilliseconds()              | Set the milliseconds (0-999)                      |
| setMinutes()                   | Set the minutes (0-59)                            |
| setMonth()                     | Set the month (0-11)                              |
| setSeconds()                   | Set the seconds (0-59)                            |
| setTime()                      | Set the time (milliseconds since January 1, 1970) |

---

### setFullYear() 메서드

이 setFullYear()메서드는 날짜 개체의 연도를 설정합니다. 이 예에서 2020년까지:

    예시
    const d = new Date();
    d.setFullYear(2020);

이 setFullYear()방법은 선택적 으로 월과 일을 설정할 수 있습니다 .

    예시
    const d = new Date();
    d.setFullYear(2020, 11, 3);

---

### setMonth() 메서드

이 setMonth()메서드는 날짜 개체의 월(0-11)을 설정합니다.

    예시
    const d = new Date();
    d.setMonth(11);

---

### setDate() 메서드

이 setDate()메서드는 날짜 개체(1-31)의 날짜를 설정합니다.

    예시
    const d = new Date();
    d.setDate(15);

이 setDate()방법을 사용하여 날짜에 날짜 를 추가 할 수도 있습니다 .

    예시
    const d = new Date();
    d.setDate(d.getDate() + 50);

일을 추가하면 월 또는 연도가 이동하는 경우 변경 사항은 Date 객체에 의해 자동으로 처리됩니다.

---

### setHours() 메서드

이 setHours()메서드는 날짜 개체의 시간(0-23)을 설정합니다.

    예시
    const d = new Date();
    d.setHours(22);

---

### setMinutes() 메서드

이 setMinutes()메서드는 날짜 개체의 분(0-59)을 설정합니다.

    예시
    const d = new Date();
    d.setMinutes(30);

---

### setSeconds() 메서드

이 setSeconds()메서드는 날짜 개체의 초를 설정합니다(0-59).

    예시
    const d = new Date();
    d.setSeconds(30);

---

### 날짜 비교

날짜를 쉽게 비교할 수 있습니다.

다음 예는 오늘 날짜를 2100년 1월 14일과 비교합니다.

    예시
    let text = "";
    const today = new Date();
    const someday = new Date();
    someday.setFullYear(2100, 0, 14);

    if (someday > today) {
    text = "Today is before January 14, 2100.";
    } else {
    text = "Today is after January 14, 2100.";
    }

JavaScript는 0에서 11까지의 월을 계산합니다. 1월은 0이고 12월은 11입니다.
