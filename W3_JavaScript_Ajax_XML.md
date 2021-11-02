## AJAX XML Example

AJAX는 XML 파일과의 대화식 통신에 사용할 수 있습니다.

---

### AJAX XML 예제

[Get CD info](./W3_JavaScript_Ajax_XML.html)

---

### 예시 설명

사용자가 위의 "CD 정보 가져오기" 버튼을 클릭하면 loadDoc() 기능이 실행됩니다.

이 loadDoc()함수는 XMLHttpRequest객체를 생성하고 , 서버 응답이 준비되었을 때 실행할 함수를 추가하고, 요청을 서버로 보냅니다.

서버 응답이 준비되면 HTML 테이블이 작성되고 XML 파일에서 노드(요소)가 추출되며 마지막으로 XML 데이터로 채워진 HTML 테이블로 "demo" 요소를 업데이트합니다.

    function loadDoc() {
    const xhttp = new XMLHttpRequest();
    xhttp.onload = function() {myFunction(this);}
    xhttp.open("GET", "cd_catalog.xml");
    xhttp.send();
    }
    function myFunction(xml) {
    const xmlDoc = xml.responseXML;
    const x = xmlDoc.getElementsByTagName("CD");
    let table="<tr><th>Artist</th><th>Title</th></tr>";
    for (let i = 0; i <x.length; i++) {
    table += "<tr><td>" +
    x[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue +
    "</td><td>" +
    x[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue +
    "</td></tr>";
    }
    document.getElementById("demo").innerHTML = table;
    }
