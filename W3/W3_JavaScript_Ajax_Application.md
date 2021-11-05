## XML Applications

이 장에서는 XML, HTTP, DOM 및 JavaScript를 사용하는 일부 HTML 응용 프로그램을 보여줍니다.

HTML 테이블에 XML 데이터 표시
이 예는 각 \<CD> 요소를 반복하고 HTML 테이블에 \<ARTIST> 및 \<TITLE> 요소의 값을 표시합니다.

    예시

    <table id="demo"></table>

    <script>
    function loadXMLDoc() {
      const xmlhttp = new XMLHttpRequest();
      xmlhttp.onload = function() {
        const xmlDoc = xml.responseXML;
        const cd = xmlDoc.getElementsByTagName("CD");
        myFunction(cd);
      }
      xmlhttp.open("GET", "cd_catalog.xml");
      xmlhttp.send();
    }

    function myFunction(cd) {
      let table="<tr><th>Artist</th><th>Title</th></tr>";
      for (let i = 0; i < cd.length; i++) {
        table += "<tr><td>" +
        cd[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue +
        "</td><td>" +
        cd[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue +
        "</td></tr>";
      }
      document.getElementById("demo").innerHTML = table;
    }
    </script>

    </body>
    </html>

---

### HTML div 요소에 첫 번째 CD 표시

이 예에서는 id="showCD"인 HTML 요소의 첫 번째 CD 요소를 표시하는 함수를 사용합니다.

    예시
    const xhttp = new XMLHttpRequest();
    xhttp.onload = function() {
      const xmlDoc = xhttp.responseXML;
      const cd = xmlDoc.getElementsByTagName("CD");
      myFunction(cd, 0);
    }
    xhttp.open("GET", "cd_catalog.xml");
    xhttp.send();

    function myFunction(cd, i) {
      document.getElementById("showCD").innerHTML =
      "Artist: " +
      cd[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue +
      "<br>Title: " +
      cd[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue +
      "<br>Year: " +
      cd[i].getElementsByTagName("YEAR")[0].childNodes[0].nodeValue;
    }

---

### CD 간 탐색

위의 예에서 CD 사이를 탐색하려면 next()and previous()함수를 만듭니다 .

    예시
    function next() {
      // display the next CD, unless you are on the last CD
      if (i < len-1) {
        i++;
        displayCD(i);
      }
    }

    function previous() {
      // display the previous CD, unless you are on the first CD
      if (i > 0) {
        i--;
        displayCD(i);
      }
    }

---

### CD를 클릭하면 앨범 정보 표시

마지막 예는 사용자가 CD를 클릭할 때 앨범 정보를 표시하는 방법을 보여줍니다.

    예시
    function displayCD(i) {
      document.getElementById("showCD").innerHTML =
      "Artist: " +
      cd[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue +
      "<br>Title: " +
      cd[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue +
      "<br>Year: " +
      cd[i].getElementsByTagName("YEAR")[0].childNodes[0].nodeValue;
    }
