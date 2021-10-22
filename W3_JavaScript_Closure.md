## JavaScript Closures

JavaScript 변수는 로컬 또는 전역 범위에 속할 수 있습니다 .

전역 변수는 클로저를 사용 하여 로컬(비공개)로 만들 수 있습니다 .

---

### 전역 변수

function는 다음과 같이 함수 내부 에 정의된 모든 변수에 액세스할 수 있습니다 .

    예시
    function myFunction() {
    let a = 4;
    return a \* a;
    }

그러나 다음 과 같이 함수 외부 에 function정의된 변수에도 액세스할 수 있습니다 .

    예시
    let a = 4;
    function myFunction() {
    return a \* a;
    }

마지막 예에서 a 는 전역 변수입니다.

웹 페이지에서 전역 변수는 창 개체에 속합니다.

전역 변수는 페이지(및 창)의 모든 스크립트에서 사용(및 변경)할 수 있습니다.

첫 번째 예에서 a 는 지역 변수입니다.

지역 변수는 정의된 함수 내에서만 사용할 수 있습니다. 다른 기능 및 기타 스크립팅 코드에서 숨겨집니다.

같은 이름을 가진 전역 변수와 지역 변수는 다른 변수입니다. 하나를 수정해도 다른 하나는 수정되지 않습니다.

    선언 키워드(var,let,const) 없이 생성된 변수 는 함수 내부에서 생성된 경우에도 항상 전역 변수입니다.

    예시
    function myFunction() {
      a = 4;
    }

---

### 가변 수명

전역 변수는 다른 페이지로 이동하거나 창을 닫을 때와 같이 페이지가 삭제될 때까지 유지됩니다.

지역 변수는 수명이 짧습니다. 함수가 호출될 때 생성되고 함수가 완료되면 삭제됩니다.

---

### 카운터 딜레마

무언가를 계산하기 위해 변수를 사용하고 이 카운터를 모든 함수에서 사용할 수 있기를 원한다고 가정합니다.

전역 변수를 사용 하고 function 카운터를 늘릴 수 있습니다.

    예시
    // Initiate counter
    let counter = 0;

    // Function to increment counter
    function add() {
    counter += 1;
    }

    // Call add() 3 times
    add();
    add();
    add();

    // The counter should now be 3

위의 솔루션에는 문제가 있습니다. 페이지의 모든 코드는 add()를 호출하지 않고 카운터를 변경할 수 있습니다.

카운터는 다른 코드가 변경하지 못하도록 add() 함수에 대해 로컬이어야 합니다.

    예시
    // Initiate counter
    let counter = 0;

    // Function to increment counter
    function add() {
    let counter = 0;
    counter += 1;
    }

    // Call add() 3 times
    add();
    add();
    add();

    //The counter should now be 3. But it is 0

로컬 카운터 대신 글로벌 카운터를 표시하기 때문에 작동하지 않았습니다.

함수가 반환하도록 하여 전역 카운터를 제거하고 로컬 카운터에 액세스할 수 있습니다.

    예시
    // Function to increment counter
    function add() {
    let counter = 0;
    counter += 1;
    return counter;
    }

    // Call add() 3 times
    add();
    add();
    add();

    //The counter should now be 3. But it is 1.

함수를 호출할 때마다 로컬 카운터를 재설정했기 때문에 작동하지 않았습니다.

JavaScript 내부 함수는 이것을 해결할 수 있습니다.

---

### 자바스크립트 중첩 함수

모든 함수는 전역 범위에 액세스할 수 있습니다.

사실, JavaScript에서 모든 함수는 "위" 범위에 액세스할 수 있습니다.

JavaScript는 중첩 함수를 지원합니다. 중첩 함수는 "위" 범위에 액세스할 수 있습니다.

이 예에서 내부 함수 plus()는 counter상위 함수 의 변수에 액세스할 수 있습니다.

    예시
    function add() {
    let counter = 0;
    function plus() {counter += 1;}
    plus();
    return counter;
    }

plus() 외부 에서 함수에 접근할 수 있었다면 카운터 딜레마를 해결할 수 있었을 것 입니다.

또한 counter = 0한 번만 실행할 수 있는 방법을 찾아야 합니다 .

폐쇄가 필요합니다.

---

### 자바스크립트 클로저

자체 호출 기능을 기억하십니까? 이 기능은 무엇을 합니까?

예시
const add = (function () {
let counter = 0;
return function () {counter += 1; return counter}
})();

add();
add();
add();

// the counter is now 3
예시 설명
변수 add는 자체 호출 함수의 반환 값에 할당됩니다.

자체 호출 기능은 한 번만 실행됩니다. 카운터를 0으로 설정하고 함수 표현식을 반환합니다.

이렇게 하면 add 함수가 됩니다. "멋진" 부분은 상위 범위의 카운터에 액세스할 수 있다는 것입니다.

이것을 자바스크립트 클로저 라고 합니다 . 함수가 " private " 변수 를 가질 수 있도록 합니다.

카운터는 익명 함수의 범위로 보호되며 add 함수를 통해서만 변경할 수 있습니다.

클로저는 상위 함수가 닫힌 후에도 상위 범위에 액세스할 수 있는 함수입니다.
