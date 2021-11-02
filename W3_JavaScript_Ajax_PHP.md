## AJAX PHP Example

AJAX는 더 많은 대화형 응용 프로그램을 만드는 데 사용됩니다.

---

### AJAX PHP 예제

다음 예는 사용자가 입력 필드에 문자를 입력하는 동안 웹 페이지가 웹 서버와 통신하는 방법을 보여줍니다.

[Ajax PHP 예제](./W3_JavaScript_Ajax_PHP.html)

---

### 예시 설명

위의 예에서 사용자가 입력 필드에 문자를 입력하면 호출된 함수 showHint()가 실행됩니다.

함수는 onkeyup이벤트 에 의해 트리거됩니다 .

코드는 다음과 같습니다.

    예시

    <p>Start typing a name in the input field below:</p>
    <p>Suggestions: <span id="txtHint"></span></p>

    <form>
    First name: <input type="text" onkeyup="showHint(this.value)">
    </form>

    <script>
    function showHint(str) {
      if (str.length == 0) {
        document.getElementById("txtHint").innerHTML = "";
        return;
      } else {
        const xmlhttp = new XMLHttpRequest();
        xmlhttp.onload = function() {
          document.getElementById("txtHint").innerHTML = this.responseText;
        }
      xmlhttp.open("GET", "gethint.php?q=" + str);
      xmlhttp.send();
      }
    }
    </script>

코드 설명:

먼저 입력 필드가 비어 있는지 확인합니다(str.length == 0). 그렇다면 txtHint 자리 표시자의 내용을 지우고 함수를 종료합니다.

그러나 입력 필드가 비어 있지 않으면 다음을 수행하십시오.

- XMLHttpRequest 객체 생성
- 서버 응답이 준비되었을 때 실행할 함수 생성
- 서버의 PHP 파일(gethint.php)로 요청 보내기
- q 매개변수가 gethint.php?q="+str 추가되었습니다.
- str 변수는 입력 필드의 내용을 보유합니다.

---

### PHP 파일 - "gethint.php"

PHP 파일은 이름 배열을 확인하고 해당 이름을 브라우저에 반환합니다.

    <?php
    // Array with names
    $a[] = "Anna";
    $a[] = "Brittany";
    $a[] = "Cinderella";
    $a[] = "Diana";
    $a[] = "Eva";
    $a[] = "Fiona";
    $a[] = "Gunda";
    $a[] = "Hege";
    $a[] = "Inga";
    $a[] = "Johanna";
    $a[] = "Kitty";
    $a[] = "Linda";
    $a[] = "Nina";
    $a[] = "Ophelia";
    $a[] = "Petunia";
    $a[] = "Amanda";
    $a[] = "Raquel";
    $a[] = "Cindy";
    $a[] = "Doris";
    $a[] = "Eve";
    $a[] = "Evita";
    $a[] = "Sunniva";
    $a[] = "Tove";
    $a[] = "Unni";
    $a[] = "Violet";
    $a[] = "Liza";
    $a[] = "Elizabeth";
    $a[] = "Ellen";
    $a[] = "Wenche";
    $a[] = "Vicky";

    // get the q parameter from URL
    $q = $_REQUEST["q"];

    $hint = "";

    // lookup all hints from array if $q is different from ""
    if ($q !== "") {
      $q = strtolower($q);
      $len=strlen($q);
      foreach($a as $name) {
        if (stristr($q, substr($name, 0, $len))) {
          if ($hint === "") {
            $hint = $name;
          } else {
            $hint .= ", $name";
          }
        }
      }
    }

    // Output "no suggestion" if no hint was found or output correct values
    echo $hint === "" ? "no suggestion" : $hint;
    ?>
