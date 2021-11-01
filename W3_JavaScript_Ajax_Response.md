## AJAX - Server Response

---

### 서버 응답 속성

| Property     | Description                       |
| ------------ | --------------------------------- |
| responseText | get the response data as a string |
| responseXML  | get the response data as XML data |

---

### responseText 속성

이 responseText속성은 서버 응답을 JavaScript 문자열로 반환하며 이에 따라 사용할 수 있습니다.

    예시
    document.getElementById("demo").innerHTML = xhttp.responseText;

---

### responseXML 속성

XMLHttpRequest 객체에는 내장된 XML 파서가 있습니다.

이 responseXML속성은 서버 응답을 XML DOM 개체로 반환합니다.

이 속성을 사용하면 응답을 XML DOM 객체로 구문 분석할 수 있습니다.

    예시
    cd_catalog.xml 파일을 요청하고 응답을 구문 분석합니다.

    const xmlDoc = xhttp.responseXML;
    const x = xmlDoc.getElementsByTagName("ARTIST");

    let txt = "";
    for (let i = 0; i < x.length; i++) {
    txt += x[i].childNodes[0].nodeValue + "<br>";
    }
    document.getElementById("demo").innerHTML = txt;

    xhttp.open("GET", "cd_catalog.xml");
    xhttp.send();

---

### 서버 응답 메서드

| Me-thod                 | Description                                                  |
| ----------------------- | ------------------------------------------------------------ |
| getResponseHeader()     | Returns specific header information from the server resource |
| getAllResponseHeaders() | Returns all the header information from the server resource  |

---

### getAllResponseHeaders() 메서드

이 getAllResponseHeaders()메서드는 서버 응답에서 모든 헤더 정보를 반환합니다.

    예시
    const xhttp = new XMLHttpRequest();
    xhttp.onload = function() {
    document.getElementById("demo").innerHTML =
    this.getAllResponseHeaders();
    }
    xhttp.open("GET", "ajax_info.txt");
    xhttp.send();

---

### getResponseHeader() 메서드

이 getResponseHeader()메서드는 서버 응답에서 특정 헤더 정보를 반환합니다.

    예시
    const xhttp = new XMLHttpRequest();
    xhttp.onload = function() {
    document.getElementById("demo").innerHTML =
    this.getResponseHeader("Last-Modified");
    }
    xhttp.open("GET", "ajax_info.txt");
    xhttp.send();
