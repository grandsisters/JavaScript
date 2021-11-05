## JavaScript While Loop

루프는 지정된 조건이 true인 한 코드 블록을 실행할 수 있습니다.

---

### while 루프

while루프 지정된 조건에 해당하는만큼의 코드 블록을 루핑.

    syntax:
    while (condition) {
    // code block to be executed
    }

다음 예제에서 루프의 코드는 변수(i)가 10보다 작은 한 계속해서 실행됩니다.

    예시
    while (i < 10) {
    text += "The number is " + i;
    i++;
    }

조건에 사용된 변수를 늘리는 것을 잊으면 루프가 끝나지 않습니다. 브라우저가 충돌합니다.

---

### Do While 루프

do while루프 while 루프의 변종이다. 이 루프는 조건이 참인지 확인하기 전에 코드 블록을 한 번 실행한 다음 조건이 참인 동안 루프를 반복합니다.

    syntax:
    do {
      // code block to be executed
    }
    while (condition);

아래 예제에서는 do while루프를 사용합니다 . 조건이 테스트되기 전에 코드 블록이 실행되기 때문에 조건이 false인 경우에도 루프는 항상 적어도 한 번 실행됩니다.

    예시
    do {
      text += "The number is " + i;
      i++;
    }
    while (i < 10);

조건에 사용된 변수를 늘리는 것을 잊지 마십시오. 그렇지 않으면 루프가 끝나지 않습니다!

---

### For and While 비교

while 루프가 문 1과 문 3이 생략된 for 루프와 거의 동일하다는 것을 알게 될 것입니다.

이 예제의 for루프 는 루프를 사용 하여 cars 배열에서 자동차 이름을 수집합니다.

    예시
    const cars = ["BMW", "Volvo", "Saab", "Ford"];
    let i = 0;
    let text = "";

    for (;cars[i];) {
    text += cars[i];
    i++;
    }

이 예제의 while루프 는 루프를 사용 하여 cars 배열에서 자동차 이름을 수집합니다.

    예시
    const cars = ["BMW", "Volvo", "Saab", "Ford"];
    let i = 0;
    let text = "";

    while (cars[i]) {
    text += cars[i];
    i++;
    }
