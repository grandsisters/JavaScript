## 연산자 알아보기

<br>

연산자(operator)란 프로그램에서 특정한 동작을하도록 지시하는 기호이다.

프로그래밍에서 '연산'이란 사칙연산은 물론 문자열고 ㅏ문자열을 연결해서 새로운 문자열을 만들고 값의 크기를 비교하는 등 여러 가지 동작을 의미한다.

그리고 이런 연산을 지시하는 기호가 연산자이다.

***
### 산술 연산자

<br>

산술 연산자는 우리가 잘 알고 있는 수학 계산을 할 떄 사용하는 연산자이다.

연산자의 왼쪽이나 오른쪽에 있는 연산 대상이 '피연산자'라고 하는데, 산술 연산자에서 피연산자는 숫자나 변수가 온다.

    예) age = currentYear - birthYear + 1

위의 예시에서 age, currentYear, birthYear, 1이 연산 대상이고 '피연산자'이다.

그리고 피연산자를 제외한 +, -는 '연산자'이다.

|종류|설명|예시|
|----|----|----|
|+|두 피연산자의 값을 더한다.|c = a + b|
|-|첫 번째 피연산자 값에서 두 번째 피연산자 값을 뺀다.|c = a - b|
|*|두 피연산자의 값을 곱한다.|c = a * b|
|/|첫 번째 피연산자 값을 두 번째 피연산자 값으로 나눈다.|c = a / b|
|%|첫 번째 피연산자 값을 두 번째 피연산자 값으로 나눈 나머지를 구한다.|c = a % b|
|++|피연산자를 1 증가 시킨다.|a++|
|--|피연산자를 1 감소 시킨다.|b--|

<br>

자주 헷갈리는 /(나누기), %(나머지)를 살펴보자.

나누기 연산자의 결괏값은 나눈 값 자체이며, 나머지 연산자의 결괏값은 나눈 후에 남은 나머지 값이 된다.

예를 들어 다음 연산식에서 numberOne은 15를 2로 나눈 몫인 7이고, numberTwo는 15를 2로 나눈 나머지인 1이 된다.

    var numberOne = 15 / 2;
    var numberTwo = 15 % 2;

다음으로 살펴볼 산술 연산자는 ++(증가), --(감소) 연산자이다.

이 두 연산자는 변수를 사용하기 전후에 변숫값을 1만큼 증가시키거나 감소시킨다.

그리고 증가, 감소 연산자를 변수 앞 또는 뒤에 붙였을 때 서로 다른 결괏값을 보여 준다.

    var a = 10
    var b = a++ + 5

a++는 연산식을 먼저 실행한 후 a에 1을 증가시킨다.

그래서 변수 b와 a의 값을 확인하면 변수 b는 15가 되고, a는 1이 증가되어 11이 된다.

그러면 ++(증가 연산자)를 변수 앞에 붙이면 어떤 결과가 나올까?

    var c = 10
    var d = ++c + 5

++c는 변수 c에 1을 증가시킨 후 연산식을 실행한다.

그래서 변수 d와 c의 값을 확인하면 변수 d는 16이 되고, c는 11이 된다.

이렇듯 증가, 감소 연산자가 피연산자 뒤에 있을 때는 연산식의 처리를 끝낸 다음에 적용된다.

반대로 피연산자 앞에 있을 때는 연산식을 처리하기 전에 적용된다.

즉, 앞의 두 예제에서 a++는 기존의 a값(10)과 5를 더하여 b에 할당한 다음에 비로소 a값을 1만큼 증가시켰지만,

++c는 c값을 1만큼 증가시킨 다음에 5를 더하여 d에 할당한다.

비슷해 보이는 연산식이지만 증가, 감소 연산자를 피연산자 앞뒤 어디에 붙이느냐에 따라 큰 차이가 있다.
