## JavaScript Date Objects

    Example
    const d = new Date();

---

### 자바스크립트 날짜 출력

기본적으로 JavaScript는 브라우저의 시간대를 사용하고 날짜를 전체 텍스트 문자열로 표시합니다.

---

### 날짜 객체 생성

Date 객체는 new Date()생성자 로 생성됩니다 .

새 날짜 개체를 만드는 방법 에는 4가지 가 있습니다.

    new Date()
    new Date(year, month, day, hours, minutes, seconds, milliseconds)
    new Date(milliseconds)
    new Date(date string)

---

### 새로운 날짜()

new Date()현재 날짜와 시간 으로 새 날짜 객체를 생성합니다 .

    예시
    const d = new Date();

    날짜 개체는 정적입니다. 컴퓨터 시간은 똑딱거리고 있지만 날짜 개체는 그렇지 않습니다.

---

### 새로운 날짜( 년, 월, ... )

new Date(year, month, ...)지정된 날짜 및 시간 으로 새 날짜 개체를 만듭니다 .

7개의 숫자는 년, 월, 일, 시, 분, 초, 밀리초(순서대로)를 지정합니다.

    예시
    const d = new Date(2018, 11, 24, 10, 33, 30, 0);

참고: JavaScript는 0 에서 11 까지의 월을 계산합니다 .

    January = 0.

    December = 11.

11보다 큰 달을 지정하면 오류가 발생하지 않지만 다음 연도에 오버플로가 추가됩니다.

    지정:
    const d = new Date(2018, 15, 24, 10, 33, 30);

    이것과 같다:
    const d = new Date(2019, 3, 24, 10, 33, 30);

최대값보다 높은 날짜를 지정하면 오류가 발생하지 않지만 다음 달에 오버플로가 추가됩니다.

    지정:
    const d = new Date(2018, 5, 35, 10, 33, 30);

    이것과 같다:
    const d = new Date(2018, 6, 5, 10, 33, 30);

---

### 6, 4, 3 또는 2개의 숫자 사용

6개의 숫자는 년, 월, 일, 시, 분, 초를 지정합니다.

    예시
    const d = new Date(2018, 11, 24, 10, 33, 30);
    5개의 숫자는 년, 월, 일, 시 및 분을 지정합니다.

    예시
    const d = new Date(2018, 11, 24, 10, 33);
    4개의 숫자는 연도, 월, 일 및 시간을 지정합니다.

    예시
    const d = new Date(2018, 11, 24, 10);
    3개의 숫자는 연도, 월, 일을 지정합니다.

    예시
    const d = new Date(2018, 11, 24);
    2개의 숫자는 연도와 월을 지정합니다.

    예시
    const d = new Date(2018, 11);

월은 생략할 수 없습니다. 매개변수를 하나만 제공하면 밀리초로 처리됩니다.

    예시
    const d = new Date(2018);

---

### 이전 세기

한 자리 및 두 자리 연도는 19xx로 해석됩니다.

    예시
    const d = new Date(99, 11, 24);

    예시
    const d = new Date(9, 11, 24);

---

### 새로운 날짜( dateString )

new Date(dateString)날짜 문자열 에서 새 날짜 개체를 만듭니다 .

    예시
    const d = new Date("October 13, 2014 11:13:00");

---

### JavaScript는 날짜를 밀리초로 저장합니다.

JavaScript는 1970년 1월 1일 00:00:00 UTC(협정 세계시) 이후의 날짜를 밀리초 단위로 저장합니다.

    0시간은 1970년 1월 1일 00:00:00 UTC입니다.

이제 시간은 1970년 1월 1일 이후 1634014259988 밀리초 입니다.

---

### 새 날짜( 밀리초 )

new Date(milliseconds)0 시간에 밀리초를 더한 새 날짜 개체를 만듭니다 .

    예시
    const d = new Date(0);

1970년 1월 1일 에 100 000 000 000밀리초를 더하면 대략 1973년 3월 3일이 됩니다.

    예시
    const d = new Date(100000000000);

1970년 1월 1일 에서 100,000,000,000밀리초를 뺀 값 은 대략 1966년 10월 31일입니다.

    예시
    const d = new Date(-100000000000);

    예시
    const d = new Date(86400000);

하루(24시간)는 86 400 000밀리초입니다.

---

### 날짜 방법

Date 개체가 생성되면 여러 메서드를 사용 하여 해당 개체에 대해 작업 할 수 있습니다.

날짜 메서드를 사용하면 현지 시간이나 UTC(유니버설 또는 GMT) 시간을 사용하여 날짜 개체의 연도, 월, 일, 시, 분, 초 및 밀리초를 가져오고 설정할 수 있습니다.

---

### 날짜 표시

JavaScript는 (기본적으로) 전체 텍스트 문자열 형식으로 날짜를 출력합니다.

Wed Mar 25 2015 09:00:00 GMT+0900 (한국 표준시)
날짜 개체를 HTML로 표시하면 toString()메서드 를 사용하여 자동으로 문자열로 변환됩니다 .

    예시
    const d = new Date();
    document.getElementById("demo").innerHTML = d;

    동일:
    const d = new Date();
    document.getElementById("demo").innerHTML = d.toString();

이 toUTCString()메서드는 날짜를 UTC 문자열(날짜 표시 표준)로 변환합니다.

    예시
    const d = new Date();
    document.getElementById("demo").innerHTML = d.toUTCString();

이 toDateString()메서드는 날짜를 더 읽기 쉬운 형식으로 변환합니다.

    예시
    const d = new Date();
    document.getElementById("demo").innerHTML = d.toDateString();

이 toISOString()메서드는 ISO 표준 형식을 사용하여 Date 객체를 문자열로 변환합니다.

    예시
    const d = new Date();
    document.getElementById("demo").innerHTML = d.toISOString();
