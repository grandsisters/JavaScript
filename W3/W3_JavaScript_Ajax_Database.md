## AJAX Database Example

AJAX는 데이터베이스와의 대화식 통신에 사용할 수 있습니다.

---

### AJAX 데이터베이스 예

다음 예는 웹 페이지가 AJAX를 사용하여 데이터베이스에서 정보를 가져오는 방법을 보여줍니다.

[Ajax Database 예제](./W3_JavaScript_Ajax_Database.html)

---

### 예제 설명 - showCustomer() 함수

사용자가 위의 드롭다운 목록에서 고객을 선택하면 이라는 함수 showCustomer()가 실행됩니다. 함수는 onchange이벤트 에 의해 트리거됩니다 .

    예제
    function showCustomer(str) {
      if (str == "") {
        document.getElementById("txtHint").innerHTML = "";
        return;
      }
      const xhttp = new XMLHttpRequest();
      xhttp.onload = function() {
        document.getElementById("txtHint").innerHTML = this.responseText;
      }
      xhttp.open("GET", "getcustomer.php?q="+str);
      xhttp.send();
    }

이 showCustomer()함수는 다음을 수행합니다.

- customerrk 선택되었는지 확인
- XMLHttpRequest 객체 생성
- 서버 응답이 준비되었을 때 실행할 함수 생성
- 서버의 파일로 요청 보내기
- URL에 매개변수(q)가 추가되었습니다(드롭다운 목록의 내용 포함).

---

### AJAX 서버 페이지

위 자바스크립트가 호출한 서버의 페이지는 "getcustomer.php"라는 PHP 파일입니다.

"getcustomer.php"의 소스 코드는 데이터베이스에 대해 쿼리를 실행하고 HTML 테이블에 결과를 반환합니다.

    <?php
    $mysqli = new mysqli("servername", "username", "password", "dbname");
    if($mysqli->connect_error) {
      exit('Could not connect');
    }

    $sql = "SELECT customerid, companyname, contactname, address, city, postalcode, country
    FROM customers WHERE customerid = ?";

    $stmt = $mysqli->prepare($sql);
    $stmt->bind_param("s", $_GET['q']);
    $stmt->execute();
    $stmt->store_result();
    $stmt->bind_result($cid, $cname, $name, $adr, $city, $pcode, $country);
    $stmt->fetch();
    $stmt->close();

    echo "<table>";
    echo "<tr>";
    echo "<th>CustomerID</th>";
    echo "<td>" . $cid . "</td>";
    echo "<th>CompanyName</th>";
    echo "<td>" . $cname . "</td>";
    echo "<th>ContactName</th>";
    echo "<td>" . $name . "</td>";
    echo "<th>Address</th>";
    echo "<td>" . $adr . "</td>";
    echo "<th>City</th>";
    echo "<td>" . $city . "</td>";
    echo "<th>PostalCode</th>";
    echo "<td>" . $pcode . "</td>";
    echo "<th>Country</th>";
    echo "<td>" . $country . "</td>";
    echo "</tr>";
    echo "</table>";
    ?>
