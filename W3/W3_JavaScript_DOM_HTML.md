## JavaScript HTML DOM - Changing HTML

HTML DOM을 사용하면 JavaScript가 HTML 요소의 내용을 변경할 수 있습니다.

---

### HTML 콘텐츠 변경

HTML 요소의 내용을 수정하는 가장 쉬운 방법은 innerHTML속성 을 사용하는 것 입니다.

HTML 요소의 내용을 변경하려면 다음 구문을 사용하십시오.

    document.getElementById(id).innerHTML = new HTML

<br />

    예시 - 이 예에서는 <p>요소 의 내용을 변경합니다 .

    <html>
    <body>

    <p id="p1">Hello World!</p>

    <script>
    document.getElementById("p1").innerHTML = "New text!";
    </script>

    </body>
    </html>

설명된 예:

- id='p1'인 p태그 요소가 있는 HTML 문서
- HTML DOM을 사용하여 id가 "p1"인 요소를 가져옵니다.
- JavaScript innerHTML는 해당 요소 의 내용을 "New text!"로 변경합니다.

      예시 - 이 예에서는 <h1>요소 의 내용을 변경합니다 .

        <!DOCTYPE html>
        <html>
        <body>

        <h1 id="id01">Old Heading</h1>

        <script>
        const element = document.getElementById("id01");
        element.innerHTML = "New Heading";
        </script>

        </body>
        </html>

설명된 예:

- id='id01'인 h1태그 요소가 있는 HTML 문서
- HTML DOM을 사용하여 id가 "id01"인 요소를 가져옵니다.
- JavaScript innerHTML는 해당 요소 의 내용을 "New Heading"으로 변경합니다.

---

### 속성 값 변경

HTML 속성의 값을 변경하려면 다음 구문을 사용하십시오.

    document.getElementById(id).attribute = new value

<br />

    예시 - 이 예에서는 <img>요소 의 src 속성 값을 변경합니다 .

    <!DOCTYPE html>
    <html>
    <body>

    <img id="myImage" src="smiley.gif">

    <script>
    document.getElementById("myImage").src = "landscape.jpg";
    </script>

    </body>
    </html>

설명된 예:

- id='myImage'인 img태그 요소가 있는 HTML 문서
- HTML DOM을 사용하여 id가 "myImage"인 요소를 가져옵니다.
- JavaScript src는 해당 요소 의 속성을 "smiley.gif"에서 "landscape.jpg"로 변경합니다.

---

### 동적 HTML 콘텐츠

JavaScript는 동적 HTML 콘텐츠를 만들 수 있습니다.

Date : Wed Oct 27 2021 15:00:10 GMT+0900 (한국 표준시)

    예시

    <!DOCTYPE html>
    <html>
    <body>

    <script>
    document.getElementById("demo").innerHTML = "Date : " + Date(); </script>

    </body>
    </html>

---

### document.write()

JavaScript document.write()에서 HTML 출력 스트림에 직접 쓰는 데 사용할 수 있습니다.

    예시
    <!DOCTYPE html>
    <html>
    <body>

    <p>Bla bla bla</p>

    <script>
    document.write(Date());
    </script>

    <p>Bla bla bla</p>

    </body>
    </html>

document.write()문서를 로드한 후에는 사용하지 마십시오 . 문서를 덮어씁니다.
