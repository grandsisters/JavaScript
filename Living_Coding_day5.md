***
## 배열
***
배열은 아이템에 대한 식별자로 숫자를 사용했다. 데이터가 추가되면 배열 전체에서 중복되지 않는 인덱스가 자동으로 만들어져서 추가된 데이터에 대한 식별자가 된다. 이 인덱스를 이용해서 데이터를 가져오게 되는 것이다. 만약 인덱스로 문자를 사용하고 싶다면 객체(dictionary)를 사용해야 한다. 다른 언어에서는 연관배열(associative array) 또는 맵( map), 딕셔너리(Dictionary)라는 데이터 타입이 객체에 해당한다.

***
## 객체를 다루는 법
***
객체는 배열과 달리 인덱스가 없고 key와 value가 존재한다<br>
<br>

- for in 을 이용해 보자

다음과 같이 for in 문을 이용하면 객체안에 들어있는 키와 밸류의 값들을 알 수 있다

for(key in grades) { <br>
    document.write("key : "+key+" value : "+grades[key]+"\<br />"); <br>
}
<br>
<br>

- 객체안의 객체, 객체안의 함수

var grades4 = { <br>
            'list' : {'he' : 2, 'is' : 4, 'man' : 6}, <br>
            'show' : function(){ <br>
                alert('Hello World'); <br>
            } <br>
        } <br>
<br>
<br>
객체안에 객체를 호출 <br>

document.write(grades4['list']['he']);


<br>
개체안의 함수를 호출 <br>
document.write(grades4['show']()); <br>
<br>

개체안의 함수를 호출 2 <br>
grades4\['show'](); 

개체안의 함수를 호출 3 <br>
grades4.show();

***
## this
this는 함수 내에서 함수 호출 맥락(context)를 의미한다. 맥락이라는 것은 상황에 따라서 달라진다는 의미인데 즉 함수를 어떻게 호출하느냐에 따라서 this가 가리키는 대상이 달라진다는 뜻이다. 함수와 객체의 관계가 느슨한 자바스크립트에서 this는 이 둘을 연결시켜주는 실질적인 연결점의 역할을 한다.
***
이 함수가 속해있는 객체를 가르키는 변수
***