## JSONP

JSONP는 도메인 간 문제를 걱정하지 않고 JSON 데이터를 보내는 방법입니다.

JSONP는 XMLHttpRequest객체를 사용하지 않습니다 .

JSONP는 \<script>대신 태그를 사용합니다 .

---

### JSONP 소개

JSONP는 패딩이 있는 JSON을 나타냅니다.

다른 도메인에서 파일을 요청하면 도메인 간 정책으로 인해 문제가 발생할 수 있습니다.

다른 도메인에서 외부 스크립트 를 요청하면 이 문제가 발생하지 않습니다.

JSONP는 이러한 장점을 이용하여 XMLHttpRequest객체 대신 스크립트 태그를 사용하여 파일을 요청 합니다.

    <script src="demo_jsonp.php">

<br />

### 서버 파일

서버의 파일은 함수 호출 내부에 결과를 래핑합니다.

    예시
    <?php
    $myJSON = '{ "name":"John", "age":30, "city":"New York" }';

    echo "myFunc(".$myJSON.");";
    ?>

결과는 JSON 데이터를 매개변수로 사용하여 "myFunc"라는 함수에 대한 호출을 반환합니다.

함수가 클라이언트에 있는지 확인하십시오.

<br />

### 자바스크립트 함수

"myFunc"라는 함수는 클라이언트에 있으며 JSON 데이터를 처리할 준비가 되어 있습니다.

    예시
    function myFunc(myObj) {
      document.getElementById("demo").innerHTML = myObj.name;
    }

---

### 동적 스크립트 태그 생성

위의 예는 스크립트 태그를 넣은 위치에 따라 페이지가 로드될 때 "myFunc" 함수를 실행하지만 그다지 만족스럽지 않습니다.

스크립트 태그는 필요할 때만 생성해야 합니다.

    예시
    버튼을 클릭할 때 <script> 태그를 만들고 삽입합니다.

    function clickButton() {
      let s = document.createElement("script");
      s.src = "demo_jsonp.php";
      document.body.appendChild(s);
    }

---

### 동적 JSONP 결과

위의 예는 여전히 매우 정적입니다.

JSON을 PHP 파일로 전송하여 예제를 동적으로 만들고 PHP 파일이 얻은 정보를 기반으로 JSON 객체를 반환하도록 합니다.

    PHP 파일
    <?php
    header("Content-Type: application/json; charset=UTF-8");
    $obj = json_decode($_GET["x"], false);

    $conn = new mysqli("myServer", "myUser", "myPassword", "Northwind");
    $result = $conn->query("SELECT name FROM ".$obj->$table." LIMIT ".$obj->$limit);
    $outp = array();
    $outp = $result->fetch_all(MYSQLI_ASSOC);

    echo "myFunc(".json_encode($outp).")";
    ?>

PHP 파일 설명:

- PHP 함수 json_decode() 를 사용하여 요청을 객체로 변환합니다 .
- 데이터베이스에 액세스하고 요청된 데이터로 배열을 채웁니다.
- 객체에 배열을 추가합니다.
- json_encode() 함수를 사용하여 배열을 JSON으로 변환합니다 .
- 반환 객체 주위에 "myFunc()"를 래핑합니다.

### 자바스크립트 예제

    "myFunc" 함수는 php 파일에서 호출됩니다:

    const obj = { table: "products", limit: 10 };
    let s = document.createElement("script");
    s.src = "jsonp_demo_db.php?x=" + JSON.stringify(obj);
    document.body.appendChild(s);

    function myFunc(myObj) {
      let txt = "";
      for (let x in myObj) {
        txt += myObj[x].name + "<br>";
      }
      document.getElementById("demo").innerHTML = txt;
    }
