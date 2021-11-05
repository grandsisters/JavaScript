## JavaScript Timing Events

---

### 타이밍 이벤트

window개체가 지정된 시간 간격 코드의 실행을 할 수 있습니다.

이러한 시간 간격을 타이밍 이벤트라고 합니다.

JavaScript와 함께 사용하는 두 가지 주요 방법은 다음과 같습니다.

    setTimeout(function, milliseconds)
    지정된 밀리초 동안 기다린 후 함수를 실행합니다.

<br />

    setInterval(function, milliseconds)
    setTimeout()과 동일하지만 계속해서 함수의 실행을 반복합니다.

setTimeout()및 setInterval()HTML DOM 창 개체의 두 가지 방법입니다.

---

### setTimeout() 메서드

    window.setTimeout(function, milliseconds);

window.setTimeout()방법은 윈도우 접두사없이 작성 할 수 있습니다.

첫 번째 매개변수는 실행할 함수입니다.

두 번째 매개변수는 실행 전의 밀리초 수를 나타냅니다.

    예시
    버튼을 클릭합니다. 3초 기다리면 페이지에 "Hello"가 표시됩니다.

    <button onclick="setTimeout(myFunction, 3000)">Try it</button>

    <script>
    function myFunction() {
      alert('Hello');
    }
    </script>

---

### 실행을 중지하는 방법?

이 clearTimeout()메서드는 setTimeout()에 지정된 함수의 실행을 중지합니다.

    window.clearTimeout(timeoutVariable)

window.clearTimeout()방법은 윈도우 접두사없이 작성 할 수 있습니다.

이 clearTimeout()메서드는 setTimeout()에서 반환된 변수를 사용합니다 .

    myVar = setTimeout(function, milliseconds);
    clearTimeout(myVar);

함수가 아직 실행되지 않은 경우 clearTimeout() 메서드 를 호출하여 실행을 중지할 수 있습니다 .

    예시 - 위와 같은 예이지만 "중지" 버튼이 추가되었습니다.

    <button onclick="myVar = setTimeout(myFunction, 3000)">Try it</button>

    <button onclick="clearTimeout(myVar)">Stop it</button>

---

### setInterval() 메서드

이 setInterval()메서드는 지정된 시간 간격마다 지정된 기능을 반복합니다.

    window.setInterval(function, milliseconds);

window.setInterval()방법은 윈도우 접두사없이 작성 할 수 있습니다.

첫 번째 매개변수는 실행할 함수입니다.

두 번째 매개변수는 각 실행 사이의 시간 간격의 길이를 나타냅니다.

이 예제는 1초에 한 번씩 "myTimer"라는 함수를 실행합니다(예: 디지털 시계).

    예시 - 현재 시간 표시:

    setInterval(myTimer, 1000);

    function myTimer() {
      const d = new Date();
      document.getElementById("demo").innerHTML = d.toLocaleTimeString();
    }

---

### 실행을 중지하는 방법?

이 clearInterval()메서드는 setInterval() 메서드에 지정된 함수의 실행을 중지합니다.

    window.clearInterval(timerVariable)

window.clearInterval()방법은 윈도우 접두사없이 작성 할 수 있습니다.

이 clearInterval()메서드는 setInterval()에서 반환된 변수를 사용합니다 .

    let myVar = setInterval(function, milliseconds);
    clearInterval(myVar);

<br />

    예시 - 위와 같은 예이지만 "시간 중지" 버튼을 추가했습니다.

    <p id="demo"></p>

    <button onclick="clearInterval(myVar)">Stop time</button>

    <script>
    let myVar = setInterval(myTimer, 1000);
    function myTimer() {
      const d = new Date();
      document.getElementById("demo").innerHTML = d.toLocaleTimeString();
    }
    </script>
