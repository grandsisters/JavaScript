## JavaScript Promises

"결과를 약속합니다!"

"Producing code"은 시간이 걸릴 수 있는 코드입니다.

"Consuming code"는 결과를 기다려야 하는 코드입니다.

Promise는 코드 생성과 코드 소비를 연결하는 JavaScript 객체입니다.

---

### 자바스크립트 프라미스 객체

JavaScript Promise 객체에는 생성 코드와 소비 코드에 대한 호출이 모두 포함됩니다.

    약속 구문
    let myPromise = new Promise(function(myResolve, myReject) {
    // "Producing Code" (May take some time)

    myResolve(); // when successful
    myReject(); // when error
    });

    // "Consuming Code" (Must wait for a fulfilled Promise)
    myPromise.then(
    function(value) { /_ code if successful _/ },
    function(error) { /_ code if some error _/ }
    );

실행 코드가 결과를 얻으면 두 콜백 중 하나를 호출해야 합니다.

| 결과 | 부르다              |
| ---- | ------------------- |
| 성공 | myResolve(결과값)   |
| 오류 | myReject(오류 객체) |

---

### Promise 객체 속성

JavaScript Promise 객체는 다음과 같을 수 있습니다.

- Pending
- Fulfilled
- Rejected

Promise 객체는 state 와 result 의 두 가지 속성을 지원합니다 .

Promise 개체가 "보류 중"(작업 중)인 동안 결과는 정의되지 않습니다.

Promise 개체가 "이행"되면 결과는 값입니다.

Promise 개체가 "거부"되면 결과는 오류 개체입니다.

| myPromise.state | myPromise.result         |
| --------------- | ------------------------ |
| "보류 중"       | 찾으시는 주소가 없습니다 |
| "성취"          | 결과 값                  |
| "거절"          | 오류 개체                |

Promise 속성 상태 및 결과에 액세스할 수 없습니다 .

Promise를 처리하려면 Promise 메서드를 사용해야 합니다.

---

### Promise How To

Promise를 사용하는 방법은 다음과 같습니다.

    myPromise.then(
      function(value) { /* code if successful */ },
      function(error) { /* code if some error */ }
    );

Promise.then()은 성공을 위한 콜백과 실패를 위한 또 다른 두 개의 인수를 취합니다.

둘 다 선택 사항이므로 성공 또는 실패에 대해서만 콜백을 추가할 수 있습니다.

    예시
    function myDisplayer(some) {
      document.getElementById("demo").innerHTML = some;
    }

    let myPromise = new Promise(function(myResolve, myReject) {
      let x = 0;

    // The producing code (this may take some time)

      if (x == 0) {
        myResolve("OK");
      } else {
        myReject("Error");
      }
    });

    myPromise.then(
      function(value) {myDisplayer(value);},
      function(error) {myDisplayer(error);}
    );

---

### JavaScript 약속의 예

### Waiting for a Timeout

    콜백 사용 예
    setTimeout(function() { myFunction("I love You !!!"); }, 3000);

    function myFunction(value) {
      document.getElementById("demo").innerHTML = value;
    }

<br/>

    Promise 사용 예
    let myPromise = new Promise(function(myResolve, myReject) {
      setTimeout(function() { myResolve("I love You !!"); }, 3000);
    });

    myPromise.then(function(value) {
      document.getElementById("demo").innerHTML = value;
    });

### Waiting for a file

    콜백 사용 예
    function getFile(myCallback) {
      let req = new XMLHttpRequest();
      req.open('GET', "mycar.html");
      req.onload = function() {
        if (req.status == 200) {
          myCallback(req.responseText);
        } else {
          myCallback("Error: " + req.status);
        }
      }
      req.send();
    }

    getFile(myDisplayer);

<br />

    Promise 사용 예
    let myPromise = new Promise(function(myResolve, myReject) {
      let req = new XMLHttpRequest();
      req.open('GET', "mycar.htm");
      req.onload = function() {
        if (req.status == 200) {
          myResolve(req.response);
        } else {
          myReject("File not Found");
        }
      };
      req.send();
    });

    myPromise.then(
      function(value) {myDisplayer(value);},
      function(error) {myDisplayer(error);}
    );
