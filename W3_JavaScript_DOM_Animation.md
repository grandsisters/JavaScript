## JavaScript HTML DOM Animation

JavaScript를 사용하여 HTML 애니메이션을 만드는 방법을 배웁니다.

---

### 기본 웹 페이지

JavaScript로 HTML 애니메이션을 만드는 방법을 보여주기 위해 간단한 웹 페이지를 사용할 것입니다.

    예시

    <!DOCTYPE html>
    <html>
    <body>

    <h1>My First JavaScript Animation</h1>

    <div id="animation">My animation will go here</div>

    </body>
    </html>

---

### 애니메이션 컨테이너 만들기

모든 애니메이션은 컨테이너 요소에 상대적이어야 합니다.

    예시

    <div id ="container">
      <div id ="animate">My animation will go here</div>
    </div>

---

### 요소 스타일 지정

컨테이너 요소는 style = " position: relative" 로 생성되어야 합니다 .

애니메이션 요소는 style = " position: absolute" 로 생성되어야 합니다 .

    예시
    #container {
    width: 400px;
    height: 400px;
    position: relative;
    background: yellow;
    }
    #animate {
    width: 50px;
    height: 50px;
    position: absolute;
    background: red;
    }

---

### 애니메이션 코드

JavaScript 애니메이션은 요소 스타일의 점진적인 변경을 프로그래밍하여 수행됩니다.

변경 사항은 타이머에 의해 호출됩니다. 타이머 간격이 작으면 애니메이션이 연속적으로 보입니다.

기본 코드는 다음과 같습니다.

    예시
    id = setInterval(frame, 5);

    function frame() {
    if (/_ test for finished _/) {
    clearInterval(id);
    } else {
    /_ code to change the element style _/
    }
    }
