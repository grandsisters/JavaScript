## JavaScript Break and Continue

break문은 루프의 "밖으로 점프".

continue문은 루프에서 하나의 반복을 통해 점프.

---

### break

break이 자습서의 이전 장에서 사용된 명령문 을 이미 보았습니다 .

switch()성명서 에서 "break"하는 데 사용되었습니다 .

break문은 루프 밖으로 이동하는 데 사용할 수 있습니다 :

    예시
    for (let i = 0; i < 10; i++) {
    if (i === 3) { break; }
    text += "The number is " + i + "<br>";
    }

위의 예에서 break명령문은 루프 카운터(i)가 3일 때 루프를 종료합니다(루프를 "중단").

---

### continue

continue지정된 조건이 발생하고있는 경우, 해당 루프에 실행문을 중단 하고 다음 루프로 건너뜁니다.

이 예에서는 값 3을 건너뜁니다.

    예시
    for (let i = 0; i < 10; i++) {
    if (i === 3) { continue; }
    text += "The number is " + i + "<br>";
    }

---

### 자바스크립트 레이블

JavaScript 문에 레이블을 지정하려면 문 앞에 레이블 이름과 콜론을 붙입니다.

    label:
    statements

break과 continue문은 코드 블록 "밖으로 점프"할 수있는 유일한 자바 스크립트 구문입니다.

    syntax:

    break labelname;

    continue labelname;

continue 문 (또는 라벨 참조없이) 전용으로 사용할 수있는 하나의 루프 반복을 건너 뜁니다 .

break문, 라벨 참조없이 목적으로 만 할 수 있습니다 루프 또는 스위치 밖으로 뛰어 .

레이블 참조를 사용하면 break 문을 사용하여 모든 코드 블록 에서 이동할 수 있습니다 .

    예시
    const cars = ["BMW", "Volvo", "Saab", "Ford"];
    list: {
      text += cars[0] + "<br>";
      text += cars[1] + "<br>";
      break list;
      text += cars[2] + "<br>";
      text += cars[3] + "<br>";
    }

코드 블록은 {와 } 사이의 코드 블록입니다.
