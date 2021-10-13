## JavaScript Math Object

JavaScript Math 개체를 사용하면 숫자에 대한 수학 작업을 수행할 수 있습니다.

    예시
    Math.PI;            // returns 3.141592653589793

---

### The Math Object

다른 객체와 달리 Math 객체에는 생성자가 없습니다.

Math 개체는 정적입니다.

Math 개체를 먼저 생성하지 않고도 모든 메서드와 속성을 사용할 수 있습니다.

---

### Math Properties(상수)

모든 Math 속성의 구문은 다음과 같습니다

    Math.property

JavaScript는 Math 속성으로 액세스할 수 있는 8개의 수학 상수를 제공합니다.

예시
Math.E // returns Euler's number
Math.PI // returns PI
Math.SQRT2 // returns the square root of 2
Math.SQRT1_2 // returns the square root of 1/2
Math.LN2 // returns the natural logarithm of 2
Math.LN10 // returns the natural logarithm of 10
Math.LOG2E // returns base 2 logarithm of E
Math.LOG10E // returns base 10 logarithm of E

---

### Math method

    Math 모든 메서드의 구문은 다음과 같습니다. Math.method.(number)

---

### 숫자를 정수로

숫자를 정수로 반올림하는 4가지 일반적인 방법이 있습니다.

    Math.round(x) - 가장 가까운 정수로 반올림된 x를 반환합니다.

    Math.ceil(x) - 가장 가까운 정수로 반올림된 x를 반환합니다.

    Math.floor(x) - 가장 가까운 정수로 내림한 x를 반환합니다.

    Math.trunc(x) - x의 정수 부분을 반환합니다( ES6의 새로운 기능 ).

---

### Math.round()

Math.round(x) 가장 가까운 정수를 반환합니다.

    예시
    Math.round(4.9); // returns 5
    Math.round(4.7); // returns 5
    Math.round(4.4); // returns 4
    Math.round(4.2); // returns 4
    Math.round(-4.2); // returns -4

---

### Math.ceil()

Math.ceil(x)x의 값은 반올림 반환 까지 의 가장 가까운 정수로 :

    예시
    Math.ceil(4.9); // returns 5
    Math.ceil(4.7); // returns 5
    Math.ceil(4.4); // returns 5
    Math.ceil(4.2); // returns 5
    Math.ceil(-4.2); // returns -4

---

### Math.floor()

Math.floor(x)가장 가까운 정수 로 내림한 x 값을 반환합니다 .

    예시
    Math.floor(4.9); // returns 4
    Math.floor(4.7); // returns 4
    Math.floor(4.4); // returns 4
    Math.floor(4.2); // returns 4
    Math.floor(-4.2); // returns -5

---

### Math.trunc()

Math.trunc(x) x의 정수 부분을 반환합니다.

    예시
    Math.trunc(4.9); // returns 4
    Math.trunc(4.7); // returns 4
    Math.trunc(4.4); // returns 4
    Math.trunc(4.2); // returns 4
    Math.trunc(-4.2); // returns -4

---

### Math.sign()

Math.sign(x) x가 음수, null 또는 양수이면 반환:

    예시
    Math.sign(-4);    // returns -1
    Math.sign(0);    // returns 0
    Math.sign(4);    // returns 1

---

### Math.pow()

Math.pow(x, y) x의 값을 y의 거듭제곱으로 반환합니다.

    예시
    Math.pow(8, 2); // returns 64

---

### Math.sqrt()

Math.sqrt(x) x의 제곱근을 반환합니다.

    예시
    Math.sqrt(64); // returns 8

---

### Math.abs()

Math.abs(x) x의 절대(양수) 값을 반환합니다.

    예시
    Math.abs(-4.7); // returns 4.7

---

### Math.sin()

Math.sin(x) 각도 x(라디안으로 지정)의 사인(-1과 1 사이의 값)을 반환합니다.

라디안 대신 도를 사용하려면 도를 라디안으로 변환해야 합니다.

라디안의 각도 = 각도(도) x PI / 180.

    예시
    Math.sin(90 * Math.PI / 180); // returns 1 (the sine of 90 degrees)

---

### Math.cos()

Math.cos(x) 각도 x(라디안으로 지정)의 코사인(-1과 1 사이의 값)을 반환합니다.

라디안 대신 도를 사용하려면 도를 라디안으로 변환해야 합니다.

라디안의 각도 = 각도(도) x PI / 180.

    예시
    Math.cos(0 * Math.PI / 180); // returns 1 (the cos of 0 degrees)

---

### Math.min() 및 Math.max()

Math.min()및 Math.max()인수 목록에서 가장 낮은 또는 높은 값을 찾을 수 있습니다 :

    예시
    Math.min(0, 150, 30, 20, -8, -200); // returns -200

    예시
    Math.max(0, 150, 30, 20, -8, -200); // returns 150

---

### Math.random()

Math.random() 0(포함)과 1(제외) 사이의 난수를 반환합니다.

    예시
    Math.random(); // returns a random number

---

### Math.log() 메서드

Math.log(x) x의 자연 로그를 반환합니다.

    예시
    Math.log(1); // returns 0

자연 로그는 특정 성장 수준에 도달하는 데 필요한 시간을 반환합니다.

Math.E와 Math.log()는 쌍둥이입니다.

10을 얻으려면 Math.E를 몇 번이나 곱해야 합니까?

    예시
    Math.log(10); // returns 2.302585092994046

---

### Math.log2() 메서드

Math.log2(x) x의 밑이 2인 로그를 반환합니다.

8을 얻으려면 2를 몇 번 곱해야 할까요?

    예시
    Math.log2(8); // returns 3

---

### Math.log10() 메서드

Math.log10(x) x의 밑이 10인 로그를 반환합니다.

1000을 얻으려면 10을 몇 번 곱해야합니까?

    예시
    Math.log10(1000); // returns 3

---

### 수학 개체 메서드

| Method               | Description                                                                   |
| -------------------- | ----------------------------------------------------------------------------- |
| abs(x                | ) Returns the absolute value of x                                             |
| acos(x)              | Returns the arccosine of x, in radians                                        |
| acosh(x)             | Returns the hyperbolic arccosine of x                                         |
| asin(x)              | Returns the arcsine of x, in radians                                          |
| asinh(x)             | Returns the hyperbolic arcsine of x                                           |
| atan(x)              | Returns the arctangent of x as a numeric value between -PI/2 and PI/2 radians |
| atan2(y, x)          | Returns the arctangent of the quotient of its arguments                       |
| atanh(x)             | Returns the hyperbolic arctangent of x                                        |
| cbrt(x)              | Returns the cubic root of x                                                   |
| ceil(x)              | Returns x, rounded upwards to the nearest integer                             |
| cos(x)               | Returns the cosine of x (x is in radians)                                     |
| cosh(x)              | Returns the hyperbolic cosine of x                                            |
| exp(x)               | Returns the value of Ex                                                       |
| floor(x)             | Returns x, rounded downwards to the nearest integer                           |
| log(x)               | Returns the natural logarithm (base E) of x                                   |
| max(x, y, z, ..., n) | Returns the number with the highest value                                     |
| min(x, y, z, ..., n) | Returns the number with the lowest value                                      |
| pow(x, y)            | Returns the value of x to the power of y                                      |
| random()             | Returns a random number between 0 and 1                                       |
| round(x)             | Rounds x to the nearest integer                                               |
| sign(x)              | Returns if x is negative, null or positive (-1, 0, 1)                         |
| sin(x)               | Returns the sine of x (x is in radians)                                       |
| sinh(x)              | Returns the hyperbolic sine of x                                              |
| sqrt(x)              | Returns the square root of x                                                  |
| tan(x)               | Returns the tangent of an angle                                               |
| tanh(x)              | Returns the hyperbolic tangent of a number                                    |
| trunc(x)             | Returns the integer part of a number (x)                                      |
