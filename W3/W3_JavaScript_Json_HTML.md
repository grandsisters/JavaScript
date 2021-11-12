## JSON HTML

JSON은 JavaScript로 매우 쉽게 변환될 수 있습니다.

JavaScript는 웹 페이지에서 HTML을 만드는 데 사용할 수 있습니다.

---

### HTML 테이블

JSON으로 수신된 데이터로 HTML 테이블을 만듭니다.

    예시
    const dbParam = JSON.stringify({table:"customers",limit:20});
    const xmlhttp = new XMLHttpRequest();
    xmlhttp.onload = function() {
      myObj = JSON.parse(this.responseText);
      let text = "<table border='1'>"
      for (let x in myObj) {
        text += "<tr><td>" + myObj[x].name + "</td></tr>";
      }
      text += "</table>"
      document.getElementById("demo").innerHTML = text;
    }
    xmlhttp.open("POST", "json_demo_html_table.php");
    xmlhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
    xmlhttp.send("x=" + dbParam);

---

### 동적 HTML 테이블

드롭다운 메뉴의 값을 기반으로 HTML 테이블을 만듭니다.
옵션을 선택하세요:

    예시
    <select id="myselect" onchange="change_myselect(this.value)">
      <option value="">Choose an option:</option>
      <option value="customers">Customers</option>
      <option value="products">Products</option>
      <option value="suppliers">Suppliers</option>
    </select>

    <script>
    function change_myselect(sel) {
      const dbParam = JSON.stringify({table:sel,limit:20});
      const xmlhttp = new XMLHttpRequest();
      xmlhttp.onload = function() {
        const myObj = JSON.parse(this.responseText);
        let text = "<table border='1'>"
        for (let x in myObj) {
          text += "<tr><td>" + myObj[x].name + "</td></tr>";
        }
        text += "</table>"
        document.getElementById("demo").innerHTML = text;
      }
      xmlhttp.open("POST", "json_demo_html_table.php");
      xmlhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
      xmlhttp.send("x=" + dbParam);
    }
    </script>

---

### HTML 드롭다운 목록

JSON으로 수신된 데이터로 HTML 드롭다운 목록을 만듭니다.

    예시
    const dbParam = JSON.stringify({table:"customers",limit:20});
    const xmlhttp = new XMLHttpRequest();
    xmlhttp.onload = function() {
      const myObj = JSON.parse(this.responseText);
      let text = "<select>"
      for (let x in myObj) {
        text += "<option>" + myObj[x].name;
      }
      text += "</select>"
      document.getElementById("demo").innerHTML = text;
      }
    }
    xmlhttp.open("POST", "json_demo_html_table.php", true);
    xmlhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
    xmlhttp.send("x=" + dbParam);
