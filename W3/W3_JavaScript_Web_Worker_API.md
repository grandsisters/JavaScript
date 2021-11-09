## Web Workers API

웹 작업자는 페이지 성능에 영향을 주지 않고 백그라운드에서 실행되는 JavaScript입니다.

---

### 웹 워커란?

HTML 페이지에서 스크립트를 실행할 때 스크립트가 완료될 때까지 페이지가 응답하지 않습니다.

웹 작업자는 페이지 성능에 영향을 주지 않고 다른 스크립트와 독립적으로 백그라운드에서 실행되는 JavaScript입니다.

웹 작업자가 백그라운드에서 실행되는 동안 클릭, 항목 선택 등 원하는 작업을 계속할 수 있습니다.

---

### 웹 작업자 예제

아래 예는 백그라운드에서 숫자를 세는 간단한 웹 작업자를 만듭니다.

[Web Worker](./W3_JavaScript_Web_Worker_API.html)

---

### 웹 작업자 지원 확인

웹 작업자를 생성하기 전에 사용자의 브라우저가 웹 작업자를 지원하는지 확인하십시오.

    if (typeof(Worker) !== "undefined") {
      // Yes! Web worker support!
      // Some code.....
    } else {
      // Sorry! No Web Worker support..
    }

---

### 웹 작업자 파일 만들기

이제 외부 JavaScript에서 웹 작업자를 만들어 보겠습니다.

여기에서 계산하는 스크립트를 만듭니다. 스크립트는 "demo_workers.js" 파일에 저장됩니다.

    let i = 0;

    function timedCount() {
      i ++;
      postMessage(i);
      setTimeout("timedCount()",500);
    }

    timedCount();

위 코드의 중요한 부분은 postMessage()HTML 페이지에 메시지를 다시 게시하는 데 사용되는 메서드입니다.

참고: 일반적으로 웹 작업자는 이러한 간단한 스크립트가 아니라 CPU를 많이 사용하는 작업에 사용됩니다.

---

### 웹 작업자 개체 만들기

이제 웹 작업자 파일이 있으므로 HTML 페이지에서 호출해야 합니다.

다음 줄은 작업자가 이미 존재하는지 확인합니다. 없으면 새 웹 작업자 개체를 만들고 "demo_workers.js"에서 코드를 실행합니다.

    if (typeof(w) == "undefined") {
      w = new Worker("demo_workers.js");
    }
    그런 다음 웹 작업자로부터 메시지를 보내고 받을 수 있습니다.

    웹 작업자에 "onmessage" 이벤트 리스너를 추가합니다.

    w.onmessage = function(event){
      document.getElementById("result").innerHTML = event.data;
    };

웹 작업자가 메시지를 게시하면 이벤트 리스너 내의 코드가 실행됩니다.

웹 작업자의 데이터는 event.data에 저장됩니다.

---

### 웹 작업자 종료

웹 작업자 개체가 생성되면 종료될 때까지 (외부 스크립트가 완료된 후에도) 메시지를 계속 수신합니다.

웹 작업자를 종료하고 브라우저/컴퓨터 리소스를 해제하려면 다음 terminate()방법을 사용하세요 .

    w.terminate();

---

### 웹 워커 재사용

작업자 변수를 undefined로 설정하면 종료된 후 코드를 재사용할 수 있습니다.

    w = undefined;

---

### 웹 작업자와 DOM

웹 작업자는 외부 파일에 있으므로 다음 JavaScript 개체에 액세스할 수 없습니다.

- The window object
- The document object
- The parent object
