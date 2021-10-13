## JavaScript Switch Statement

switch문은 다른 조건에 따라 다른 작업을 수행하는 데 사용됩니다.

---

### JavaScript Switch 문

switch명령문을 사용하여 실행할 많은 코드 블록 중 하나를 선택하십시오.

    통사론
    switch(expression) {
    case x:
    // code block
    break;
    case y:
    // code block
    break;
    default:
    // code block
    }

작동 방식은 다음과 같습니다.

- 스위치 표현식은 한 번 평가됩니다.
- 표현식의 값은 각 경우의 값과 비교됩니다.
- 일치하는 항목이 있으면 연결된 코드 블록이 실행됩니다.
- 일치하는 항목이 없으면 기본 코드 블록이 실행됩니다.

<br />

예시

이 getDay()메서드는 0에서 6 사이의 숫자로 요일을 반환합니다.

(일요일=0, 월요일=1, 화요일=2 ..)

이 예에서는 요일 번호를 사용하여 요일 이름을 계산합니다.

    switch (new Date().getDay()) {
    case 0:
    day = "Sunday";
    break;
    case 1:
    day = "Monday";
    break;
    case 2:
    day = "Tuesday";
    break;
    case 3:
    day = "Wednesday";
    break;
    case 4:
    day = "Thursday";
    break;
    case 5:
    day = "Friday";
    break;
    case 6:
    day = "Saturday";
    }

---

### 휴식 키워드

JavaScript가 break 키워드에 도달 하면 스위치 블록에서 나옵니다.

이렇게 하면 스위치 블록 내에서 실행이 중지됩니다.

스위치 블록에서 마지막 대소문자를 구분할 필요는 없습니다. 어쨌든 블록은 거기서 끊깁니다.

    참고: break 문을 생략하면 평가가 case와 일치하지 않아도 다음 case가 실행됩니다.

---

### 기본 키워드

default키워드는 어떤 경우 일치하지 않는 경우 실행하는 코드를 지정합니다 :

<br />

예시

이 getDay()메서드는 0에서 6 사이의 숫자로 요일을 반환합니다.

오늘이 토요일(6)도 일요일(0)도 아닌 경우 기본 메시지를 작성합니다.

    switch (new Date().getDay()) {
    case 6:
    text = "Today is Saturday";
    break;
    case 0:
    text = "Today is Sunday";
    break;
    default:
    text = "Looking forward to the Weekend";
    }

default경우는 스위치 블록에서 마지막 경우 될 필요가 없습니다 :

    예시
    switch (new Date().getDay()) {
      default:
        text = "Looking forward to the Weekend";
        break;
      case 6:
        text = "Today is Saturday";
        break;
      case 0:
        text = "Today is Sunday";
    }

default의 경우 스위치 블록의 마지막 경우로 쓰이는 것이 아니라,

어떠한 경우에도 맞지 않을 상황에 작동하며 동시에 switch문을 빠져나가는 break의 기능을 가지고 있다.

---

### 공통 코드 블록

때로는 다른 스위치 케이스가 동일한 코드를 사용하기를 원할 것입니다.

이 예제의 경우 4와 5는 동일한 코드 블록을 공유하고 0과 6은 다른 코드 블록을 공유합니다.

    예시
    switch (new Date().getDay()) {
    case 4:
    case 5:
    text = "Soon it is Weekend";
    break;
    case 0:
    case 6:
    text = "It is Weekend";
    break;
    default:
    text = "Looking forward to the Weekend";
    }

---

### 스위칭 세부 사항

여러 케이스가 케이스 값과 일치하는 경우 첫 번째 케이스가 선택됩니다.

일치하는 케이스가 없으면 프로그램은 기본 레이블을 계속 사용합니다 .

기본 레이블이 없으면 프로그램은 switch 뒤의 명령문으로 계속 진행합니다 .

---

### 엄격한 비교

스위치 케이스는 엄격한 비교(===)를 사용합니다.

값은 일치하는 유형이 같아야 합니다.

엄격한 비교는 피연산자가 같은 유형인 경우에만 참일 수 있습니다.

이 예에서는 x에 대해 일치하는 항목이 없습니다.

    예시
    let x = "0";
    switch (x) {
    case 0:
    text = "Off";
    break;
    case 1:
    text = "On";
    break;
    default:
    text = "No value found";
    }
