## JavaScript Operators

    예시
    변수에 값을 할당하고 함께 추가합니다.

    let x = 5; // assign the value 5 to x
    let y = 2; // assign the value 2 to y
    let z = x + y; // assign the value 7 to z (5 + 2)

할당 연산자 (=) 변수에 값을 할당한다.

더하기 연산자 (+)

    예시
    let x = 5;
    let y = 2;
    let z = x + y;

    곱셈 연산자 (*)

    예시
    let x = 5;
    let y = 2;
    let z = x * y;

---

### JavaScript 산술 연산자

산술 연산자는 숫자에 대한 산술을 수행하는 데 사용됩니다.

| Operator | Description                  |
| -------- | ---------------------------- |
| +        | Addition                     |
| -        | Subtraction                  |
| \*       | Multiplication               |
| \*\*     | Exponentiation (ES2016)      |
| /        | Division                     |
| %        | Modulus (Division Remainder) |
| ++       | Increment                    |
| --       | Decrement                    |

---

### JavaScript 할당 연산자

할당 연산자는 JavaScript 변수에 값을 할당합니다.

| Operator | Example   | Same As      |
| -------- | --------- | ------------ |
| =        | x = y     | x = y        |
| +=       | x += y    | x = x + y    |
| -=       | x -= y    | x = x - y    |
| \*=      | x \*= y   | x = x \* y   |
| /=       | x /= y    | x = x / y    |
| %=       | x %= y    | x = x % y    |
| \*\*=    | x \*\*= y | x = x \*\* y |

또한 할당 연산자 ( +=) 변수에 값을 추가한다.

---

### JavaScript 문자열 연산자

\+ 오퍼레이터는 (합칠) 문자열을 추가하는데 사용될 수있다.

    예시
    let text1 = "John";
    let text2 = "Doe";
    let text3 = text1 + " " + text2;
    text3의 결과는 다음과 같습니다.

    John Doe

+=할당 연산자는 (CONCATENATE) 문자열을 추가 할 수 있습니다 :

    예시
    let text1 = "What a very ";
    text1 += "nice day";
    text1의 결과는 다음과 같습니다.

    What a very nice day

문자열에 사용할 때 + 연산자를 연결 연산자라고 합니다.

---

### 문자열 및 숫자 추가

두 개의 숫자를 더하면 합계가 반환되지만 숫자와 문자열을 더하면 문자열이 반환됩니다.

    예시
    let x = 5 + 5;
    let y = "5" + 5;
    let z = "Hello" + 5;
    x , y 및 z 의 결과는 다음 과 같습니다.

    결과
    10
    55
    Hello5

숫자와 문자열을 더하면 결과는 문자열이 됩니다!

---

### JavaScript 비교 연산자

| Operator | Description                       |
| -------- | --------------------------------- |
| ==       | equal to                          |
| ===      | equal value and equal type        |
| !=       | not equal                         |
| !==      | not equal value or not equal type |
| >        | greater than                      |
| <        | less than                         |
| > =      | greater than or equal to          |
| < =      | less than or equal to             |
| ?        | ternary operator                  |

---

### JavaScript 논리 연산자

| Operator | Description |
| -------- | ----------- |
| &&       | logical and |
| \|\|     | logical or  |
| !        | logical not |

---

### JavaScript 유형 연산자

| Operator   | Description                                                |
| ---------- | ---------------------------------------------------------- |
| typeof     | Returns the type of a variable                             |
| instanceof | Returns true if an object is an instance of an object type |

---

### JavaScript 비트 연산자

비트 연산자는 32비트 숫자에서 작동합니다.

연산의 모든 숫자 피연산자는 32비트 숫자로 변환됩니다. 결과는 JavaScript 번호로 다시 변환됩니다.

| Operator | Description           | Example | Same         | as Result | Decimal |
| -------- | --------------------- | ------- | ------------ | --------- | ------- |
| &        | AND                   | 5 & 1   | 0101 & 0001  | 0001      | 1       |
| \|       | OR                    | 5 \| 1  | 0101 \| 0001 | 0101      | 5       |
| ~        | NOT                   | ~ 5     | ~0101        | 1010      | 10      |
| ^        | XOR                   | 5 ^ 1   | 0101 ^ 0001  | 0100      | 4       |
| <<       | Zero fill left shift  | 5 << 1  | 0101 << 1    | 1010      | 10      |
| >>       | Signed right shift    | 5 >> 1  | 0101 >> 1    | 0010      | 2       |
| >>>      | Zero fill right shift | 5 >>> 1 | 0101 >>> 1   | 0010      | 2       |

위의 예는 4비트의 부호 없는 예를 사용합니다. 그러나 JavaScript는 32비트 부호 있는 숫자를 사용합니다.
이 때문에 JavaScript에서 ~ 5는 10을 반환하지 않고 -6을 반환합니다.
~0000000000000000000000000000101 1111111111111111111111111111010을 반환합니다

Bitwise 연산자는 JS Bitwise 장 에 자세히 설명되어 있습니다.
