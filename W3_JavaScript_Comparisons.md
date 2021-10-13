## JavaScript Comparison and Logical Operators

비교 및 논리 연산자는 true 또는 false 를 테스트하는 데 사용됩니다 .

---

### 비교 연산자

비교 연산자는 논리문에서 변수 또는 값 간의 같음 또는 차이를 결정하는 데 사용됩니다.

이를 감안할 때 x = 5아래 표에서는 비교 연산자에 대해 설명합니다.

<img src='./img/js_comparisons.png'>

---

### 어떻게 사용할 수 있습니까?

조건문에서 비교 연산자를 사용하여 값을 비교하고 결과에 따라 조치를 취할 수 있습니다.

    if (age < 18) text = "Too young to buy alcohol";

---

### 논리 연산자

논리 연산자는 변수 또는 값 간의 논리를 결정하는 데 사용됩니다.

점을 감안 x = 6하고 y = 3, 아래 표는 논리 연산자를 설명합니다 :

| Operator | Description | Example                       |
| -------- | ----------- | ----------------------------- |
| &&       | and         | (x < 10 && y > 1) is true     |
| \|\|     | or          | (x == 5 \|\| y == 5) is false |
| !        | not         | !(x == y) is true             |

---

### 조건부(삼항) 연산자

JavaScript에는 일부 조건에 따라 변수에 값을 할당하는 조건 연산자도 포함되어 있습니다.

    syntax
    variablename = (condition) ? value1:value2

    예시
    let voteable = (age < 18) ? "Too young":"Old enough";

age 변수가 18보다 작은 값이면 voteable 변수의 값은 "Too young"이 되고, 그렇지 않으면 voteable 값은 "Old enough"가 됩니다.

---

### 다른 유형 비교

다른 유형의 데이터를 비교하면 예기치 않은 결과가 나타날 수 있습니다.

문자열을 숫자와 비교할 때 JavaScript는 비교할 때 문자열을 숫자로 변환합니다. 빈 문자열은 0으로 변환됩니다. 숫자가 아닌 문자열 NaN은 항상 false으로 변환됩니다.

| Case        | Value |
| ----------- | ----- |
| 2 < 12      | true  |
| 2 < "12"    | true  |
| 2 < "John"  | false |
| 2 > "John"  | false |
| 2 == "John" | false |
| "2" < "12"  | false |
| "2" > "12"  | true  |
| "2" == "12" | false |

두 문자열을 비교할 때 "2"는 "12"보다 큽니다. (알파벳 순으로) 1은 2보다 작기 때문입니다.

적절한 결과를 얻으려면 비교 전에 변수를 적절한 유형으로 변환해야 합니다.

    age = Number(age);
    if (isNaN(age)) {
    voteable = "Input is not a number";
    } else {
    voteable = (age < 18) ? "Too young" : "Old enough";
    }
