## JavaScript Arithmetic

---

### JavaScript 산술 연산자

산술 연산자는 숫자(리터럴 또는 변수)에 대해 산술을 수행합니다.

| Operator | Description             |
| -------- | ----------------------- |
| +        | Addition                |
| -        | Subtraction             |
| \*       | Multiplication          |
| \*\*     | Exponentiation (ES2016) |
| /        | Division                |
| %        | Modulus (Remainder)     |
| ++       | Increment               |
| --       | Decrement               |

---

### 산술 연산

일반적인 산술 연산은 두 개의 숫자에서 작동합니다.

두 숫자는 리터럴일 수 있습니다.

    예시
    let x = 100 + 50;

또는 변수:

    예시
    let x = a + b;

또는 표현:

    예시
    let x = (100 + 50) \* a;

---

### 연산자 및 피연산자

숫자(산술 연산에서)를 피연산자 라고 합니다 .

(두 피연산자 사이에서 수행되는) 연산은 operator 에 의해 정의됩니다 .

| 피연산자 | 운영자 | 피연산자 |
| -------- | ------ | -------- |
| 100      | +      | 50       |

---

### 첨가

가산 연산자 ( +) 번호를 추가한다

    예시
    let x = 5;
    let y = 2;
    let z = x + y;

빼기
뺄셈 연산자 ( -) 숫자를 감산한다.

    예시
    let x = 5;
    let y = 2;
    let z = x - y;

곱하기
곱셈 연산자 ( \*) 승산 번호.

    예시
    let x = 5;
    let y = 2;
    let z = x \* y;

나누기
제산 연산자 ( /) 수를 나눈다.

    예시
    let x = 5;
    let y = 2;
    let z = x / y;

나머지
계수 연산자 ( %) 분할 나머지를 반환합니다.

    예시
    let x = 5;
    let y = 2;
    let z = x % y;

증분
증가 연산자 ( ++) 수치를 증가시킨다.

    예시
    let x = 5;
    x++;
    let z = x;

감소
감량 연산자 ( --) 수를 감소시킨다.

    예시
    let x = 5;
    x--;
    let z = x;

지수화
누승 연산자 ( \*\*) 두 번째 오퍼랜드의 전력에 대한 첫 번째 피연산자를 일으킨다.

    예시
    let x = 5;
    let z = x ** 2;          // result is 25

x \*\* y는 다음과 같은 결과를 생성합니다 Math.pow(x,y).

    예시
    let x = 5;
    let z = Math.pow(x,2);   // result is 25

연산자 우선 순위
연산자 우선 순위는 산술 표현식에서 연산이 수행되는 순서를 설명합니다.

    예시
    let x = 100 + 50 * 3;

위 예제의 결과는 150 \* 3과 같습니까, 아니면 100 + 150과 같습니까?

더하기 또는 곱하기가 먼저 수행됩니까?

전통적인 학교 수학에서와 같이 곱셈이 먼저 수행됩니다.

곱하기( \*)와 나누기( /)는 더하기(+)와 빼기(-) 보다 우선 순위 가 높습니다 .

그리고 (학교 수학에서와 같이) 괄호를 사용하여 우선 순위를 변경할 수 있습니다.

    예시
    let x = (100 + 50) \* 3;

괄호를 사용할 때 괄호 안의 연산이 먼저 계산됩니다.

많은 연산이 동일한 우선 순위(예: 더하기 및 빼기)를 갖는 경우 왼쪽에서 오른쪽으로 계산됩니다.

    예시
    let x = 100 + 50 - 3;