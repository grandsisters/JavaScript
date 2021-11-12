## JSON PHP

JSON의 일반적인 용도는 웹 서버에서 데이터를 읽고 웹 페이지에 데이터를 표시하는 것입니다.

이 장에서는 클라이언트와 PHP 서버 간에 JSON 데이터를 교환하는 방법을 설명합니다.

---

### PHP 파일

PHP에는 JSON을 처리하는 몇 가지 내장 함수가 있습니다.

PHP의 객체는 PHP 함수 json_encode()를 사용하여 JSON으로 변환할 수 있습니다 .

    PHP 파일
    <?php
    $myObj->name = "John";
    $myObj->age = 30;
    $myObj->city = "New York";

    $myJSON = json_encode($myObj);

    echo $myJSON;
    ?>

---

### 클라이언트 자바스크립트

다음은 AJAX 호출을 사용하여 위의 예에서 PHP 파일을 요청하는 클라이언트의 JavaScript입니다.

    예시
    JSON.parse()를 사용하여 결과를 JavaScript 객체로 변환합니다.

    const xmlhttp = new XMLHttpRequest();
    xmlhttp.onload = function() {
      const myObj = JSON.parse(this.responseText);
      document.getElementById("demo").innerHTML = myObj.name;
    }
    xmlhttp.open("GET", "demo_file.php");
    xmlhttp.send();

---

### PHP 배열

PHP의 배열은 PHP 함수 json_encode()를 사용할 때도 JSON으로 변환됩니다 .

    PHP 파일
    <?php
    $myArr = array("John", "Mary", "Peter", "Sally");

    $myJSON = json_encode($myArr);

    echo $myJSON;
    ?>

---

### 클라이언트 자바스크립트

다음은 AJAX 호출을 사용하여 위의 배열 예제에서 PHP 파일을 요청하는 클라이언트의 JavaScript입니다.

    예시
    JSON.parse()를 사용하여 결과를 JavaScript 배열로 변환합니다.

    var xmlhttp = new XMLHttpRequest();
    xmlhttp.onload = function() {
      const myObj = JSON.parse(this.responseText);
      document.getElementById("demo").innerHTML = myObj[2];
    }
    xmlhttp.open("GET", "demo_file_array.php", true);
    xmlhttp.send();

---

### PHP 데이터베이스

PHP는 서버 측 프로그래밍 언어이며 데이터베이스에 액세스하는 데 사용할 수 있습니다.

서버에 데이터베이스가 있고 "customers"라는 테이블의 첫 번째 행 10개를 요청하는 클라이언트에서 데이터베이스에 요청을 보내려고 한다고 상상해 보십시오.

클라이언트에서 반환하려는 행 수를 설명하는 JSON 개체를 만듭니다.

서버에 요청을 보내기 전에 JSON 개체를 문자열로 변환하고 PHP 페이지의 URL에 매개변수로 보냅니다.

    예시
    JSON.stringify()를 사용하여 JavaScript 객체를 JSON으로 변환합니다.

    const limit = {"limit":10};
    const dbParam = JSON.stringify(limit);
    xmlhttp = new XMLHttpRequest();
    xmlhttp.onload = function() {
      document.getElementById("demo").innerHTML = this.responseText;
    }
    xmlhttp.open("GET","json_demo_db.php?x=" + dbParam);
    xmlhttp.send();

설명된 예:

- "한계" 속성 및 값을 포함하는 개체를 정의합니다.
- 객체를 JSON 문자열로 변환합니다.
- JSON 문자열을 매개변수로 사용하여 PHP 파일에 요청을 보냅니다.
- 요청이 결과(JSON으로)와 함께 반환될 때까지 기다립니다.
- PHP 파일에서 받은 결과를 표시합니다.

PHP 파일을 살펴보십시오.

    PHP 파일
    <?php
    header("Content-Type: application/json; charset=UTF-8");
    $obj = json_decode($_GET["x"], false);

    $conn = new mysqli("myServer", "myUser", "myPassword", "Northwind");
    $stmt = $conn->prepare("SELECT name FROM customers LIMIT ?");
    $stmt->bind_param("s", $obj->limit);
    $stmt->execute();
    $result = $stmt->get_result();
    $outp = $result->fetch_all(MYSQLI_ASSOC);

    echo json_encode($outp);
    ?>

PHP 파일 설명:

- PHP 함수 json_decode() 를 사용하여 요청을 객체로 변환합니다 .
- 데이터베이스에 액세스하고 요청된 데이터로 배열을 채웁니다.
- 객체에 배열을 추가하고 json_encode() 함수를 사용하여 객체를 JSON으로 반환합니다 .

---

### 데이터 사용

    예시
    xmlhttp.onload = function() {
      const myObj = JSON.parse(this.responseText);
      let text = "";
      for (let x in myObj) {
        text += myObj[x].name + "<br>";
      }
      document.getElementById("demo").innerHTML = text;
    }

---

### PHP 메소드 = POST

서버에 데이터를 보낼 때 HTTP POST방법 을 사용하는 것이 가장 좋습니다 .

POST메소드를 사용하여 AJAX 요청을 보내려면 메소드와 올바른 헤더를 지정하십시오.

이제 서버로 전송된 데이터는 send()메서드에 대한 인수여야 합니다 .

    예시
    const dbParam = JSON.stringify({"limit":10});
    const xmlhttp = new XMLHttpRequest();
    xmlhttp.onload = function() {
      const myObj = JSON.parse(this.responseText);
      let text ="";
      for (let x in myObj) {
        text += myObj[x].name + "<br>";
      }
      document.getElementById("demo").innerHTML = text;
    }
    xmlhttp.open("POST", "json_demo_db_post.php");
    xmlhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
    xmlhttp.send("x=" + dbParam);

PHP 파일의 유일한 차이점은 전송된 데이터를 가져오는 방법입니다.

    PHP 파일
    $_GET 대신 $_POST 사용:

    <?php
    header("Content-Type: application/json; charset=UTF-8");
    $obj = json_decode($_POST["x"], false);

    $conn = new mysqli("myServer", "myUser", "myPassword", "Northwind");
    $stmt = $conn->prepare("SELECT name FROM customers LIMIT ?");
    $stmt->bind_param("s", $obj->limit);
    $stmt->execute();
    $result = $stmt->get_result();
    $outp = $result->fetch_all(MYSQLI_ASSOC);

    echo json_encode($outp);
    ?>
