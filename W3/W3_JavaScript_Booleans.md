## JavaScript Booleans

JavaScript Boolean은 true 또는 false 의 두 값 중 하나를 나타냅니다 .

---

### Boolean Values

매우 자주, 프로그래밍에서 다음과 같이 두 값 중 하나만 가질 수 있는 데이터 유형이 필요합니다.

- YES / NO
- ON / OFF
- TRUE / FALSE

이를 위해 JavaScript에는 Boolean 데이터 유형이 있습니다. true 또는 false 값만 사용할 수 있습니다 .

<br />

Boolean()함수를 사용하여 표현식(또는 변수)이 참인지 확인할 수 있습니다.

    예시
    Boolean(10 > 9) // returns true


    또는 더 쉽게:

    예시
    (10 > 9) // also returns true
    10 > 9 // also returns true

---

### "value"가 있는 모든 것은 True입니다.

    예시

    100

    3.14

    -15

    "Hello"

    "false"

    7 + 1 + 3.14

---

### "value"가 없는 것은 모두 거짓이다

    0 (영) 의 boolean 값 은 false입니다 .
    let x = 0;
    Boolean(x); // returns false

    -0 (마이너스 0) 의 boolean 값 은 false입니다 .
    let x = -0;
    Boolean(x); // returns false

    "" (빈 문자열) 의 boolean 값 은 false입니다 .
    let x = "";
    Boolean(x); // returns false

    undefined 의 boolean 값 은 false입니다 .
    let x;
    Boolean(x); // returns false

    null 의 boolean 값 은 false입니다 .
    let x = null;
    Boolean(x); // returns false

    false 의 boolean 값 은 (당신이 짐작했겠지만) false입니다 .
    let x = false;
    Boolean(x); // returns false

    NaN 의 boolean 값 은 false입니다 .
    let x = 10 / "Hallo";
    Boolean(x); // returns false

---

### boolean은 객체가 될 수 있습니다

일반적으로 JavaScript boolean은 리터럴에서 생성된 기본 값입니다.

    let x = false;

그러나 boolean은 new 키워드를 사용하여 객체로 정의할 수도 있습니다 .

    let y = new Boolean(false);

    예시
    let x = false;
    let y = new Boolean(false);

    // typeof x returns boolean
    // typeof y returns object

boolean 개체를 만들지 마십시오. 실행 속도가 느려집니다.

이 new키워드는 코드를 복잡하게 만듭니다. 이로 인해 예기치 않은 결과가 발생할 수 있습니다.

==연산자를 사용할 때 boolean은 같음:

    예시
    let x = false;
    let y = new Boolean(false);

    // (x == y) is true because x and y have equal values

===연산자를 사용할 때 ===연산자는 유형과 값 모두에서 평등을 기대 하기 때문에 동일한 값일 지라도 boolean은 같지 않습니다 .

    예시
    let x = false;
    let y = new Boolean(false);

    // (x === y) is false because x and y have different types

또는 더 나쁜것은 객체를 비교할 수 없다는 것입니다.

    예시
    let x = new Boolean(false);
    let y = new Boolean(false);

    // (x == y) is false because objects cannot be compared

(x==y)와 (x===y)의 차이점에 주목하세요.
두 JavaScript 객체를 비교하면 항상 false가 반환됩니다.
