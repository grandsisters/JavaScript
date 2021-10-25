## JavaScript Callbacks

콜백은 다른 함수에 인수로 전달되는 함수입니다.

이 기술을 사용하면 함수가 다른 함수를 호출할 수 있습니다.

콜백 함수는 다른 함수가 완료된 후에 실행할 수 있습니다.

---

### 기능 순서

JavaScript 함수는 호출된 순서대로 실행됩니다. 정의된 순서대로가 아닙니다.

이 예에서는 "Goodbye"가 표시됩니다.

    예시
    function myFirst() {
    myDisplayer("Hello");
    }

    function mySecond() {
    myDisplayer("Goodbye");
    }

    myFirst();
    mySecond();

이 예에서는 "Hello"가 표시됩니다.

    예시
    function myFirst() {
    myDisplayer("Hello");
    }

    function mySecond() {
    myDisplayer("Goodbye");
    }

    mySecond();
    myFirst();

---

### 시퀀스 제어

때로는 함수를 실행할 때를 더 잘 제어하고 싶을 때가 있습니다.

계산을 수행한 다음 결과를 표시한다고 가정합니다.

계산기 함수( myCalculator)를 호출하고 결과를 저장한 다음 다른 함수( myDisplayer)를 호출 하여 결과를 표시할 수 있습니다.

    예시
    function myDisplayer(some) {
    document.getElementById("demo").innerHTML = some;
    }

    function myCalculator(num1, num2) {
    let sum = num1 + num2;
    return sum;
    }

    let result = myCalculator(5, 5);
    myDisplayer(result);

또는 계산기 기능( myCalculator)을 호출하고 계산기 기능 이 표시 기능( myDisplayer)을 호출하도록 할 수 있습니다 .

    예시
    function myDisplayer(some) {
    document.getElementById("demo").innerHTML = some;
    }

    function myCalculator(num1, num2) {
    let sum = num1 + num2;
    myDisplayer(sum);
    }

    myCalculator(5, 5);

위의 첫 번째 예제의 문제점은 결과를 표시하기 위해 두 개의 함수를 호출해야 한다는 것입니다.

두 번째 예의 문제는 계산기 기능이 결과를 표시하는 것을 막을 수 없다는 것입니다.

이제 콜백을 가져올 시간입니다.

---

### 자바스크립트 콜백

콜백은 다른 함수에 인수로 전달되는 함수입니다.

콜백을 사용하면 콜백 myCalculator과 함께 계산기 함수( )를 호출하고 계산이 완료된 후 계산기 함수가 콜백을 실행하도록 할 수 있습니다.

    예시
    function myDisplayer(some) {
      document.getElementById("demo").innerHTML = some;
    }

    function myCalculator(num1, num2, myCallback) {
      let sum = num1 + num2;
      myCallback(sum);
    }

    myCalculator(5, 5, myDisplayer);

위의 예에서 myDisplayer는 함수의 이름입니다.

myCalculator()인수로 전달됩니다 .

함수를 인수로 전달할 때 괄호를 사용하지 않는 것을 기억하십시오.

오른쪽: myCalculator(5, 5, myDisplayer);

잘못된: myCalculator(5, 5, myDisplayer());
