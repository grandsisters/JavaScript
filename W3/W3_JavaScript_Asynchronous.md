## Asynchronous JavaScript

"나중에 끝낼게!"

다른 함수와 병렬로 실행되는 함수를 비동기식이라고 합니다.

좋은 예는 JavaScript setTimeout()입니다.

---

### 비동기 자바스크립트

이전 장에서 사용한 예제는 매우 단순화되었습니다.

예제의 목적은 콜백 함수의 구문을 보여주기 위한 것입니다.

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

실제 세계에서 콜백은 비동기 함수와 함께 가장 자주 사용됩니다.

대표적인 예가 자바스크립트 setTimeout()입니다.

---

### Waiting for a Timeout

JavaScript 함수 setTimeout()를 사용할 때 시간 초과 시 실행할 콜백 함수를 지정할 수 있습니다.

    예시
    setTimeout(myFunction, 3000);

    function myFunction() {
    document.getElementById("demo").innerHTML = "I love You !!";
    }

위의 예에서 myFunction는 콜백으로 사용됩니다.

함수(함수 이름)는 setTimeout()인수로 전달됩니다 .

3000은 시간 초과 전의 밀리초 수이므로 myFunction()3초 후에 호출됩니다.

    함수를 인수로 전달할 때 괄호를 사용하지 않는 것을 기억하십시오.

    오른쪽: setTimeout(myFunction, 3000);

    잘못된: setTimeout(myFunction(), 3000);

함수 이름을 다른 함수에 인수로 전달하는 대신 항상 전체 함수를 전달할 수 있습니다.

    예시
    setTimeout(function() { myFunction("I love You !!!"); }, 3000);

    function myFunction(value) {
    document.getElementById("demo").innerHTML = value;
    }

위의 예에서 function(){ myFunction("I love You !!!"); } 는 콜백으로 사용됩니다. 완전한 기능입니다. 완전한 함수는 인수로 setTimeout()에 전달됩니다.

3000은 시간 초과 전의 밀리초 수이므로 myFunction()3초 후에 호출됩니다.

---

### Waiting for Intervals:

JavaScript 함수를 사용할 때 setInterval()각 간격에 대해 실행할 콜백 함수를 지정할 수 있습니다.

    예시
    setInterval(myFunction, 1000);

    function myFunction() {
      let d = new Date();
      document.getElementById("demo").innerHTML=
      d.getHours() + ":" +
      d.getMinutes() + ":" +
      d.getSeconds();
    }

위의 예에서 myFunction는 콜백으로 사용됩니다.

함수(함수 이름)는 setInterval()인수로 전달됩니다 .

1000은 간격 사이의 밀리초 수이므로 1초 myFunction()마다 호출됩니다.

---

### Waiting for Files

스크립트나 파일과 같은 외부 리소스를 로드하는 함수를 생성하면 완전히 로드되기 전에는 콘텐츠를 사용할 수 없습니다.

이것은 콜백을 사용하기에 완벽한 시간입니다.

이 예에서는 HTML 파일( mycar.html)을 로드하고 파일이 완전히 로드된 후 HTML 파일을 웹 페이지에 표시합니다.

    Waiting for Files:
    function myDisplayer(some) {
      document.getElementById("demo").innerHTML = some;
    }

    function getFile(myCallback) {
      let req = new XMLHttpRequest();
      req.open('GET', "mycar.html");
      req.onload = function() {
        if (req.status == 200) {
          myCallback(this.responseText);
        } else {
          myCallback("Error: " + req.status);
        }
      }
      req.send();
    }

getFile(myDisplayer);

위의 예에서 myDisplayer는 콜백으로 사용됩니다.

함수(함수 이름)는 getFile()인수로 전달됩니다 .
