## AJAX ASP Example

AJAX는 더 많은 대화형 응용 프로그램을 만드는 데 사용됩니다.

---

### AJAX ASP 예제

다음 예는 사용자가 입력 필드에 문자를 입력하는 동안 웹 페이지가 웹 서버와 통신하는 방법을 보여줍니다.

[Ajax ASP 예제](./W3_JavaScript_Ajax_ASP.html)

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
      xmlhttp.open("GET", "gethint.asp?q=" + str);
      xmlhttp.send();
      }
    }
    </script>

코드 설명:

먼저 입력 필드가 비어 있는지 확인합니다(str.length == 0). 그렇다면 txtHint 자리 표시자의 내용을 지우고 함수를 종료합니다.

그러나 입력 필드가 비어 있지 않으면 다음을 수행하십시오.

- XMLHttpRequest 객체 생성
- 서버 응답이 준비되었을 때 실행할 함수 생성
- 서버의 ASP 파일(gethint.asp)로 요청 보내기
- q 매개변수가 gethint.asp?q="+str 추가되었습니다.
- str 변수는 입력 필드의 내용을 보유합니다.

---

### ASP 파일 - "gethint.asp"

ASP 파일은 이름 배열을 확인하고 해당 이름을 브라우저에 반환합니다.

    <%
    response.expires=-1
    dim a(30)
    'Fill up array with names
    a(1)="Anna"
    a(2)="Brittany"
    a(3)="Cinderella"
    a(4)="Diana"
    a(5)="Eva"
    a(6)="Fiona"
    a(7)="Gunda"
    a(8)="Hege"
    a(9)="Inga"
    a(10)="Johanna"
    a(11)="Kitty"
    a(12)="Linda"
    a(13)="Nina"
    a(14)="Ophelia"
    a(15)="Petunia"
    a(16)="Amanda"
    a(17)="Raquel"
    a(18)="Cindy"
    a(19)="Doris"
    a(20)="Eve"
    a(21)="Evita"
    a(22)="Sunniva"
    a(23)="Tove"
    a(24)="Unni"
    a(25)="Violet"
    a(26)="Liza"
    a(27)="Elizabeth"
    a(28)="Ellen"
    a(29)="Wenche"
    a(30)="Vicky"

    'get the q parameter from URL
    q=ucase(request.querystring("q"))

    'lookup all hints from array if length of q>0
    if len(q)>0 then
      hint=""
      for i=1 to 30
        if q=ucase(mid(a(i),1,len(q))) then
          if hint="" then
            hint=a(i)
          else
            hint=hint & " , " & a(i)
          end if
        end if
      next
    end if

    'Output "no suggestion" if no hint were found
    'or output the correct values
    if hint="" then
      response.write("no suggestion")
    else
      response.write(hint)
    end if
    %>
