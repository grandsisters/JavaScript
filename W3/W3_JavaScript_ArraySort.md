## JavaScript Sorting Arrays

---

### 배열 정렬

이 sort()메서드는 배열을 알파벳순으로 정렬합니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.sort(); // Sorts the elements of fruits

---

### 배열 반전

이 reverse()메서드는 배열의 요소를 뒤집습니다.

내림차순으로 배열을 정렬하는 데 사용할 수 있습니다.

    예시
    const fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.sort(); // First sort the elements of fruits
    fruits.reverse(); // Then reverse the order of the elements

---

### 숫자 정렬

기본적으로 sort()함수는 값을 문자열 로 정렬합니다 .

이것은 문자열에 대해 잘 작동합니다("Apple"는 "Banana" 앞에 옵니다).

그러나 숫자를 문자열로 정렬하면 "2"가 "1"보다 크므로 "25"가 "100"보다 큽니다.

이 때문에 이 sort()메서드는 숫자를 정렬할 때 잘못된 결과를 생성합니다.

비교 기능 을 제공하여 이 문제를 해결할 수 있습니다 .

    예시
    const points = [40, 100, 1, 5, 25, 10];
    points.sort(function(a, b){return a - b});

동일한 트릭을 사용하여 배열을 내림차순으로 정렬합니다.

    예시
    const points = [40, 100, 1, 5, 25, 10];
    points.sort(function(a, b){return b - a});

---

### 비교 기능

비교 기능의 목적은 대체로 정렬 순서를 정의하는 것입니다.

비교 함수는 인수에 따라 음수, 0 또는 양수 값을 반환해야 합니다.

    function(a, b){return a - b}

sort() 함수는 두 값을 비교할 때 값을 비교 함수로 전송하고 반환된 값(음수, 0, 양수)에 따라 값을 정렬합니다.

결과가 음수인 a의 경우 b 앞에 정렬됩니다.

결과가 양수인 b의 경우 a 앞에 정렬됩니다.

결과가 0이면 두 값의 정렬 순서가 변경되지 않습니다.

예시:

비교 함수는 배열의 모든 값을 한 번에 두 개의 값으로 비교합니다 (a, b).

40과 100을 비교할 때 sort()메소드는 비교 함수(40, 100)를 호출합니다.

이 함수는 40 - 100 을 계산 (a - b)하고 결과가 음수(-60)이므로 정렬 함수는 40을 100보다 작은 값으로 정렬합니다.

이 코드 조각을 사용하여 숫자 및 알파벳순 정렬을 실험할 수 있습니다.

    <button onclick="myFunction1()">Sort Alphabetically</button>
    <button onclick="myFunction2()">Sort Numerically</button>

    <p id="demo"></p>

    <script>
    const points = [40, 100, 1, 5, 25, 10];
    document.getElementById("demo").innerHTML = points;

    function myFunction1() {
      points.sort();
      document.getElementById("demo").innerHTML = points;
    }

    function myFunction2() {
      points.sort(function(a, b){return a - b});
      document.getElementById("demo").innerHTML = points;
    }
    </script>

---

### 무작위 순서로 배열 정렬하기

    예시
    const points = [40, 100, 1, 5, 25, 10];
    points.sort(function(a, b){return 0.5 - Math.random()});

---

### 피셔 예이츠 방법

위의 예인 array .sort()는 정확하지 않으며 일부 숫자를 다른 숫자보다 선호합니다.

가장 인기 있는 올바른 방법은 Fisher Yates 셔플이라고 하며 1938년에 데이터 과학에 도입되었습니다!

JavaScript에서 메서드는 다음과 같이 번역될 수 있습니다.

    예시
    const points = [40, 100, 1, 5, 25, 10];

    for (let i = points.length -1; i > 0; i--) {
    let j = Math.floor(Math.random() * i)
    let k = points[i]
    points[i] = points[j]
    points[j] = k
    }

---

### 가장 높은(또는 가장 낮은) 배열 값 찾기

배열에서 최대값 또는 최소값을 찾기 위한 내장 함수는 없습니다.

그러나 배열을 정렬한 후에는 인덱스를 사용하여 가장 높은 값과 가장 낮은 값을 얻을 수 있습니다.

    오름차순 정렬:

    예시
    const points = [40, 100, 1, 5, 25, 10];
    points.sort(function(a, b){return a - b});
    // now points[0] contains the lowest value
    // and points[points.length-1] contains the highest value


    내림차순 정렬:

    예시
    const points = [40, 100, 1, 5, 25, 10];
    points.sort(function(a, b){return b - a});
    // now points[0] contains the highest value
    // and points[points.length-1] contains the lowest value

전체 배열을 정렬하는 것은 가장 높은(또는 가장 낮은) 값만 찾으려는 경우 매우 비효율적인 방법입니다.

---

### 배열에서 Math.max() 사용

Math.max.apply는 배열에서 가장 높은 숫자를 찾는 데 사용할 수 있습니다 .

    예시
    function myArrayMax(arr) {
      return Math.max.apply(null, arr);
    }

Math.max.apply(null, [1, 2, 3])는 Math.max(1, 2, 3)와 동일합니다 .

---

### 배열에서 Math.min() 사용

Math.min.apply배열에서 가장 낮은 숫자를 찾는 데 사용할 수 있습니다 .

    예시
    function myArrayMin(arr) {
    return Math.min.apply(null, arr);
    }

Math.min.apply(null, [1, 2, 3])는 Math.min(1, 2, 3)와 동일합니다 .

---

### 내 최소 / 최대 JavaScript 메소드

가장 빠른 해결책은 "직접 만든" 방법을 사용하는 것입니다.

이 함수는 각 값을 발견된 가장 높은 값과 비교하는 배열을 반복합니다.

    예시(최대값 찾기)

    function myArrayMax(arr) {
    let len = arr.length;
    let max = -Infinity;
    while (len--) {
    if (arr[len] > max) {
    max = arr[len];
    }
    }
    return max;
    }

이 함수는 각 값을 찾은 가장 낮은 값과 비교하는 배열을 반복합니다.

    예시(최소값 찾기)

    function myArrayMin(arr) {
    let len = arr.length;
    let min = Infinity;
    while (len--) {
    if (arr[len] < min) {
    min = arr[len];
    }
    }
    return min;
    }

---

### 객체 배열 정렬

JavaScript 배열에는 종종 객체가 포함됩니다.

    예시
    const cars = [
    {type:"Volvo", year:2016},
    {type:"Saab", year:2001},
    {type:"BMW", year:2010}
    ];

객체에 다른 데이터 유형의 속성이 있더라도 이 sort()메서드를 사용하여 배열을 정렬할 수 있습니다.

해결책은 속성 값을 비교하는 비교 함수를 작성하는 것입니다.

    예시
    cars.sort(function(a, b){return a.year - b.year});

문자열 속성을 비교하는 것은 조금 더 복잡합니다.

    예시
    cars.sort(function(a, b){
    let x = a.type.toLowerCase();
    let y = b.type.toLowerCase();
    if (x < y) {return -1;}
    if (x > y) {return 1;}
    return 0;
    });
