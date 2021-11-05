## JavaScript HTML DOM EventListener

---

### addEventListener() 메서드

    예시
    사용자가 버튼을 클릭할 때 발생하는 이벤트 리스너를 추가합니다.

    document.getElementById("myBtn").addEventListener("click", displayDate);

addEventListener() 메서드는 지정된 요소에 이벤트 핸들러를 연결합니다.

addEventListener() 메소드는 기존 이벤트 핸들러를 덮어쓰지 않고 요소에 이벤트 핸들러를 연결합니다.

하나의 요소에 많은 이벤트 핸들러를 추가할 수 있습니다.

동일한 유형의 여러 이벤트 핸들러를 하나의 요소에 추가할 수 있습니다(예: 두 개의 "클릭" 이벤트).

이벤트 수신기를 HTML 요소뿐만 아니라 창 객체에도 추가할 수 있습니다.

addEventListener() 메소드를 사용하면 이벤트가 버블링에 반응하는 방식을 쉽게 제어할 수 있습니다.

addEventListener() 메소드를 사용할 때 가독성을 높이기 위해 JavaScript는 HTML 마크업과 분리되어 있으며 HTML 마크업을 제어하지 않더라도 이벤트 수신기를 추가할 수 있습니다.

removeEventListener() 방법을 사용하여 이벤트 수신기를 쉽게 제거할 수 있습니다.

---

### Syntax

    element.addEventListener(event, function, useCapture);

첫 번째 매개변수는 이벤트 유형(예: " click" 또는 " mousedown" 또는 기타 HTML DOM 이벤트 ) 입니다.

두 번째 매개변수는 이벤트가 발생할 때 호출하려는 함수입니다.

세 번째 매개변수는 이벤트 버블링 또는 이벤트 캡처를 사용할지 여부를 지정하는 부울 값입니다. 이 매개변수는 선택 사항입니다.

이벤트에 "on" 접두사를 사용하지 않습니다. "onclick"대신에 " click"을 사용하십시오.

---

### 요소에 이벤트 처리기 추가

    예시
    "Hello World!" 경고 사용자가 요소를 클릭할 때:

    element.addEventListener("click", function(){ alert("Hello World!"); });

외부 "명명된" 함수를 참조할 수도 있습니다.

    예시
    "Hello World!" 경고 사용자가 요소를 클릭할 때:

    element.addEventListener("click", myFunction);

    function myFunction() {
    alert ("Hello World!");
    }

---

### 동일한 요소에 많은 이벤트 핸들러 추가

이 addEventListener()방법을 사용하면 기존 이벤트를 덮어쓰지 않고 동일한 요소에 많은 이벤트를 추가할 수 있습니다.

    예시
    element.addEventListener("click", myFunction);
    element.addEventListener("click", mySecondFunction);

동일한 요소에 다른 유형의 이벤트를 추가할 수 있습니다.

    예시
    element.addEventListener("mouseover", myFunction);
    element.addEventListener("click", mySecondFunction);
    element.addEventListener("mouseout", myThirdFunction);

---

### 창 개체에 이벤트 처리기 추가

이 addEventListener()메서드를 사용하면 HTML 요소, HTML 문서, 창 객체 등등 xmlHttpRequest 객체와 같이 이벤트를 지원하는 HTML DOM 객체에 이벤트 리스너를 추가할 수 있습니다 .

    예시
    사용자가 창 크기를 조정할 때 발생하는 이벤트 리스너를 추가합니다.

    window.addEventListener("resize", function(){
    document.getElementById("demo").innerHTML = sometext;
    });

---

### 매개변수 전달

매개변수 값을 전달할 때 매개변수와 함께 지정된 함수를 호출하는 "익명 함수"를 사용하십시오.

    예시
    element.addEventListener("click", function(){ myFunction(p1, p2); });

---

### 이벤트 버블링 또는 이벤트 캡처?

HTML DOM에서 이벤트 전파에는 버블링과 캡처의 두 가지 방법이 있습니다.

이벤트 전파는 이벤트가 발생할 때 요소 순서를 정의하는 방법입니다. \<div> 요소 안에 \<p> 요소가 있고 사용자가 \<p> 요소를 클릭하면 어떤 요소의 "click" 이벤트가 먼저 처리되어야 합니까?

에서 버블 링 내부 대부분의 요소의 이벤트는 먼저 다음 외부 처리됩니다의 \<p> 요소의 클릭 이벤트가 먼저 다음 \<DIV> 요소의 클릭 이벤트를 처리합니다.

에서는 촬상 가장 외부 요소의 경우 1 및 그 내부 처리 다음 \<div> 요소의 클릭 이벤트가 제 다음 \<p> 요소의 클릭 이벤트를 처리한다.

addEventListener() 메서드를 사용하면 "useCapture" 매개변수를 사용하여 전파 유형을 지정할 수 있습니다.

    addEventListener(event, function, useCapture);

기본값은 버블링 전파를 사용하는 false이며 값이 true로 설정되면 이벤트는 캡처 전파를 사용합니다.

    예시
    document.getElementById("myP").addEventListener("click", myFunction, true);
    document.getElementById("myDiv").addEventListener("click", myFunction, true);

---

### emoveEventListener() 메서드

removeEventListener()메서드는 addEventListener() 메서드로 연결된 이벤트 핸들러를 제거합니다.

    예시
    element.removeEventListener("mousemove", myFunction);
