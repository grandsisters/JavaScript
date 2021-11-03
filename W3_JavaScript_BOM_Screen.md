## JavaScript Window Screen

window.screen 객체는 사용자의 화면에 대한 정보를 포함합니다.

---

### 윈도우 화면

window.screen객체는 윈도우 접두사없이 작성 할 수 있습니다.

속성:

- screen.width
- screen.height
- screen.availWidth
- screen.availHeight
- screen.colorDepth
- screen.pixelDepth

---

### 창 화면 너비

screen.width속성은 픽셀 단위로 방문자의 화면의 폭을 돌려줍니다.

    예시
    화면 너비를 픽셀로 표시합니다.

    document.getElementById("demo").innerHTML =
    "Screen Width: " + screen.width;

결과는 다음과 같습니다.

    Screen Width: 1920

---

### 창 화면 높이

screen.height속성은 픽셀 단위로 방문자의 화면의 높이를 반환합니다.

    예시
    화면 높이를 픽셀로 표시:

    document.getElementById("demo").innerHTML =
    "Screen Height: " + screen.height;

결과는 다음과 같습니다.

    Screen Height: 1080

---

### 창 화면 사용 가능한 너비

이 screen.availWidth속성은 Windows 작업 표시줄과 같은 인터페이스 기능을 뺀 방문자 화면의 너비를 픽셀 단위로 반환합니다.

    예시
    화면의 사용 가능한 너비를 픽셀로 표시합니다.

    document.getElementById("demo").innerHTML =
    "Available Screen Width: " + screen.availWidth;

결과는 다음과 같습니다.

    Available Screen Width: 1920

---

### 창 화면 사용 가능한 높이

screen.availHeight속성은 픽셀 단위로 방문자의 화면의 높이를 반환 뺀 인터페이스는 Windows 작업 표시 줄 같은 기능.

    예시
    화면의 사용 가능한 높이를 픽셀로 표시합니다.

    document.getElementById("demo").innerHTML =
    "Available Screen Height: " + screen.availHeight;

결과는 다음과 같습니다.

    Available Screen Height: 1080

---

### 창 화면 색 농도

screen.colorDepth속성 복귀 비트의 수는 하나 개의 컬러를 표시하기 위해 사용.

모든 최신 컴퓨터는 색상 해상도를 위해 24비트 또는 32비트 하드웨어를 사용합니다.

- 24비트 = 16,777,216개의 서로 다른 "트루 컬러"
- 32비트 = 4,294,967,296가지 "딥 컬러"

구형 컴퓨터는 16비트를 사용했습니다: 65,536개의 다른 "하이 컬러" 해상도.

아주 오래된 컴퓨터와 오래된 휴대폰은 8비트(256가지 "VGA 색상")를 사용했습니다.

    예시
    화면의 색 농도를 비트 단위로 표시합니다.

    document.getElementById("demo").innerHTML =
    "Screen Color Depth: " + screen.colorDepth;

결과는 다음과 같습니다.

    Screen Color Depth: 24

HTML에서 사용되는 #rrggbb(rgb) 값은 "트루 컬러"(16,777,216가지 다른 색상)를 나타냅니다.

---

### 창 화면 픽셀 깊이

screen.pixelDepth속성은 화면의 픽셀 깊이를 반환합니다.

    예시
    화면의 픽셀 깊이를 비트로 표시합니다.

    document.getElementById("demo").innerHTML =
    "Screen Pixel Depth: " + screen.pixelDepth;

결과는 다음과 같습니다.

    Screen Pixel Depth: 24

최신 컴퓨터의 경우 색상 깊이와 픽셀 깊이는 동일합니다.
