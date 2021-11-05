## JavaScript Arrays

JavaScript 배열은 단일 변수에 여러 값을 저장하는 데 사용됩니다.

    예시
    const cars = ["Saab", "Volvo", "BMW"];

const 키워드로 배열을 선언하는 것이 일반적 입니다.

---

### 배열이란 무엇입니까?

배열은 한 번에 둘 이상의 값을 보유할 수 있는 특수 변수입니다.

항목 목록(예: 자동차 이름 목록)이 있는 경우 자동차를 단일 변수에 저장하면 다음과 같을 수 있습니다.

    let car1 = "Saab";
    let car2 = "Volvo";
    let car3 = "BMW";

그러나 자동차를 탐색하고 특정 자동차를 찾으려면 어떻게 해야 합니까? 그리고 3대가 아니라 300대가 있다면 어떨까요?

솔루션은 배열입니다!

배열은 하나의 이름으로 많은 값을 가질 수 있으며 인덱스 번호를 참조하여 값에 액세스할 수 있습니다.

---

### 배열 생성

배열 리터럴을 사용하는 것이 JavaScript 배열을 만드는 가장 쉬운 방법입니다.

    sytax:
    const array_name = [item1, item2, ...];

    예시
    const cars = ["Saab", "Volvo", "BMW"];

공백과 줄 바꿈은 중요하지 않습니다. 선언은 여러 줄에 걸쳐 있을 수 있습니다.

    예시
    const cars = [
    	"Saab",
    	"Volvo",
    	"BMW"
    ];

배열을 만든 다음 요소를 제공할 수도 있습니다.

    예시
    const cars = [];
    cars[0]= "Saab";
    cars[1]= "Volvo";
    cars[2]= "BMW";

---

### 자바스크립트 키워드 new 사용하기

다음 예제에서는 또한 Array를 만들고 값을 할당합니다.

    예시
    const cars = new Array("Saab", "Volvo", "BMW");

위의 두 가지 예는 정확히 동일합니다.

하지만 new Array() 는사용할 필요가 없습니다 .
단순성, 가독성 및 실행 속도를 위해 첫 번째 방법(배열 리터럴 방법)을 사용합니다.

---

### 배열 요소 액세스

인덱스 번호를 참조하여 배열 요소에 액세스합니다 .

    const cars = ["Saab", "Volvo", "BMW"];
    let x = cars[0]; // x = "Saab"

참고: 배열 인덱스는 0으로 시작합니다.

[0]은 첫 번째 요소입니다. [1]은 두 번째 요소입니다.

---

### 배열 요소 변경

이 문은 다음에서 첫 번째 cars 요소의 값을 변경합니다 .

    cars[0] = "Opel";

예시

    const cars = ["Saab", "Volvo", "BMW"];
    cars[0] = "Opel";

---

### 전체 어레이에 액세스

JavaScript를 사용하면 배열 이름을 참조하여 전체 배열에 액세스할 수 있습니다.

    예시
    const cars = ["Saab", "Volvo", "BMW"];
    document.getElementById("demo").innerHTML = cars;

---

### 배열은 객체입니다

배열은 특별한 유형의 객체입니다. typeof라는 JavaScript 의 연산자는 배열에 대해 "객체"를 반환합니다.

그러나 JavaScript 배열은 굳이 객체라는 말보단 단순히 배열이란 말로 가장 잘 설명됩니다.

배열 은 "요소"에 액세스 하기 위해 숫자 를 사용 합니다 . 이 예에서 person[0] John을 반환합니다.

    정렬:
    const person = ["John", "Doe", 46];

개체는 이름을 사용하여 "구성원"에 액세스합니다. 이 예에서 person.firstName John을 반환합니다.

    물체:
    const person = {firstName:"John", lastName:"Doe", age:46};

---

### 배열 요소는 객체일 수 있음

JavaScript 변수는 객체가 될 수 있습니다. 배열은 특별한 종류의 객체입니다.

이 때문에 동일한 배열에 다른 유형의 변수를 가질 수 있습니다.

배열에 객체를 가질 수 있습니다. 배열에 함수를 가질 수 있습니다. 배열에 배열을 가질 수 있습니다.

    myArray[0] = Date.now;
    myArray[1] = myFunction;
    myArray[2] = myCars;

---

### 배열 속성 및 메서드

JavaScript 배열의 진정한 강점은 내장 배열 속성과 메서드입니다.

    cars.length // Returns the number of elements
    cars.sort() // Sorts the array

---

### 길이 속성

length배열 의 속성은 배열의 길이(배열 요소의 수)를 반환합니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.length; // Returns 4

length속성은 항상 가장 높은 배열 인덱스에 1을 더합니다.

---

### 첫 번째 배열 요소 액세스

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits[0]; // Returns "Banana"

---

### 마지막 배열 요소 액세스

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits[fruits.length - 1]; // Returns "Mango"

---

### 루프 배열 요소

배열을 반복하는 가장 안전한 방법은 루프를 사용하는 것입니다 for.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    let fLen = fruits.length;

    text = "<ul>";
    for (let i = 0; i < fLen; i++) {
    	text += "<li>" + fruits[i] + "</li>";
    }
    text += "</ul>";

다음 Array.forEach()기능을 사용할 수도 있습니다 .

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];

    let text = "<ul>";
    fruits.forEach(myFunction);
    text += "</ul>";

    function myFunction(value) {
    text += "<li>" + value + "</li>";
    }

---

### 배열 요소 추가

배열에 새 요소를 추가하는 가장 쉬운 방법은 다음 push()방법을 사용하는 것입니다.

    예시
    const fruits = ["Banana", "Orange", "Apple"];
    fruits.push("Lemon"); // Adds a new element (Lemon) to fruits

length속성을 사용하여 배열에 새 요소를 추가할 수도 있습니다 .

    예시
    const fruits = ["Banana", "Orange", "Apple"];
    fruits[fruits.length] = "Lemon"; // Adds "Lemon" to fruits

경고 !
인덱스가 높은 요소를 추가하면 배열에 정의되지 않은 "구멍"이 생길 수 있습니다.

    예시
    const fruits = ["Banana", "Orange", "Apple"];
    fruits[6] = "Lemon"; // Creates undefined "holes" in fruits

---

### 연관 배열

많은 프로그래밍 언어는 명명된 인덱스가 있는 배열을 지원합니다.

명명된 인덱스가 있는 배열을 연관 배열(또는 해시)이라고 합니다.

JavaScript는 명명된 인덱스가 있는 배열을 지원 하지 않습니다 .

JavaScript에서 배열은 항상 번호가 매겨진 인덱스를 사용 합니다 .

    예시
    const person = [];
    person[0] = "John";
    person[1] = "Doe";
    person[2] = 46;
    person.length; // Will return 3
    person[0]; // Will return "John"

경고 !!
명명된 인덱스를 사용하는 경우 JavaScript는 배열을 객체로 재정의합니다.

그 후 일부 배열 메서드 및 속성은 잘못된 결과 를 생성 합니다 .

    예시:
    const person = [];
    person["firstName"] = "John";
    person["lastName"] = "Doe";
    person["age"] = 46;
    person.length; // Will return 0
    person[0]; // Will return undefined

---

### 배열과 객체의 차이점

JavaScript에서 배열 은 번호가 매겨진 인덱스를 사용 합니다 .

JavaScript에서 객체 는 명명된 인덱스를 사용 합니다 .

배열은 번호가 매겨진 인덱스가 있는 특수한 종류의 객체입니다.

---

### 배열을 사용하는 경우. 개체를 사용하는 경우.

- JavaScript는 연관 배열을 지원하지 않습니다.
- 요소 이름을 문자열(텍스트)로 지정 하려면 객체 를 사용해야 합니다 .
- 요소 이름을 숫자로 지정 하려면 배열 을 사용해야 합니다 .

---

### 자바스크립트 새로운 Array()

JavaScript에는 new Array() 배열 생성자가 내장되어있습니다.

그러나 []대신 안전하게 사용할 수 있습니다 .

이 두 개의 다른 문은 모두 point라는 이름의 빈 배열을 새로 만듭니다.

    const points = new Array();
    const points = [];

이 두 개의 다른 명령문은 모두 6개의 숫자를 포함하는 새 배열을 만듭니다.

    const points = new Array(40, 100, 1, 5, 25, 10);
    const points = [40, 100, 1, 5, 25, 10];

new키워드는 예기치 않은 결과를 생성 할 수 있습니다 :

    // Create an array with three elements:
    const points = new Array(40, 100, 1);

    // Create an array with two elements:
    const points = new Array(40, 100);

    // Create an array with one element ???
    const points = new Array(40);

    일반적인 오류
    const points = [40];
    다음과 같지 않습니다.
    const points = New Array(40);

    // Create an array with one element:
    const points = [40];

    // Create an array with 40 undefined elements:
    const points = new Array(40);

---

### 배열을 인식하는 방법

일반적인 질문은 다음과 같습니다. 변수가 배열인지 어떻게 알 수 있습니까?

문제는 JavaScript 연산자 typeof가 " object"를 반환 한다는 것입니다 .

    const fruits = ["Banana", "Orange", "Apple"];
    typeof fruits; // returns object

JavaScript 배열이 객체이기 때문에 typeof 연산자는 객체를 반환합니다.

솔루션 1:
이 문제를 해결하기 위해 ECMAScript 5는 새로운 메소드를 정의합니다 Array.isArray().

    Array.isArray(fruits); // returns true

솔루션 2:
instanceof개체가 주어진 생성자에 의해 생성되는 경우는 true :

    const fruits = ["Banana", "Orange", "Apple"];

    fruits instanceof Array; // returns true
