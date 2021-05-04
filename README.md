# 김태현 [201740113]

##[4월27일]
>배열<br>
let array=['사과','바나나','망고','딸기']<br>
array[0]='사과'<br>

>객체<br>
속성(키)-name , price<br>
//객체 선언<br>
let object ={<br>
    name:'바나나',<br>
    price:1200<br>
};<br>
//출력<br>
console.log(object.name);<br>
console.log(object.price);<br>
-> c:\exampleM>node object.js<br>
   바나나<br>
   1200<br>

>속성 메소드.<br>
-요소:배열 내부에 있는 값 하나하나<br>
-속성:객체 내부에 있는 값 하나하나<br>
다양한 자료형 객체<br>
var object={<br>
    number:273,<br>
    string:'RintIanTta',<br>
    boolean:true,<br>
    array:[52,273,103,32],<br>
    method:function({<br>
<br>
    })<br>
};<br>
this키워드<br>
let object={<br>
    name:'바나나',<br>
    price:1200,<br>
    print:function(){<br>
        console.log(`${this.name}의 가격은 ${this.price}원입니다.`)<br>
    }<br>
};<br>
//호출<br>
object.print();<br>
바나나의 가격은 1200원입니다.<br><br>

>객체 지향 프로그래밍:현실의 객체를 모방해서 프로그래밍한것-배열과 객체를 사용하면 여러 개의 데이터를 쉽게 다룰 수 있음<br>
메소드를 가진 객체의 배열<br>
let products=[{<br>
    name:'바나나',<br>
    price:1200,<br>
    print:function(){<br>
        console.log(`${this.name}의 가격은 ${this.price}원입니다.`)<br>
    }<br>
}, {<br>
    name:'사과',<br>
    price:2000,<br>
    print:function(){<br>
        console.log(`${this.name}의 가격은 ${this.price}원입니다.`)<br>
}, {<br>
.<br>
.<br>
.<br>
}];<br>
//반복해서 출력<br>
for(let product of products){<br>
    product.print();<br>
}<br><br>

>함수 외부로<br>
let products=[<br>
    {name:'바나나',price:1200},<br>
    {name:'사과',price:2000},<br>
    .<br>
    .<br>
    .<br>
];<br>
//함수 선언<br>
function printProduct(product){<br>
    console.log(`${product.name}의 가격은 ${product.price}원입니다.`);<br>
}<br>
//반복 출력<br>
for(let product of products){<br>
    printProcuct(product);<br>
}<br><br>

> 생성자함수-객체를 만드는 함수,대문자로 시작하는 이름 사용<br>
> 프로토타입-생성자 함수로 만든 객체는 프로토타입 공간에 메소드를 지정하새 모든 객체가 공유하도록 함, 해당 함수를 생성자 함수로 사용했을때만 의미가 있음<br>
//생성자 함수<br>
function Product(name,price){<br>
    this.name=name;<br>
    this.price=price;<br>
}<br>
//프로토타입에 메소드 선언<br>
Product.prototype.print=function(){<br>
    console.log(`${this.name}의 가격은 ${this.price}원입니다.`);<br>
};<br>
//상품 목록 선언<br>
let product=[<br>
    new Product('바나나',1200),<br>
    new Product('사과',2000),<br>
    new Product('배',3000),<br>
    .<br>
    .<br>
    .<br>
];<br>
//반복 출력<br>
for(let product of products){<br>
    product.print();<br>
}<br><br>

바나나의 가격은 1200원입니다.<br>
사과의 가격은 2000원입니다.<br>
배의 가격은 3000원입니다.<br>
.<br>
.<br>
.<br><br>

>null<br>
console.log(null);<br>
console.log(typeof(null));<br>
-아예 값이 없는 상태-null 활용<br>
//변수 선언<br>
let zeroNumber=0;<br>
let falseBoolean='';<br>
let emptyString='';<br>
let undefinedValue;<br>
let nullValue=null;<br>
//갑이 있는지 확인<br>
if(zeroNumber==null)<br>
    console.log('0은 존재하지 않는 값입니다');<br>
if(falseBoolean==null)<br>
    console.log('false는 존재하지 않는 값입니다');<br>
if(emptyString==null)<br>
    console.log('반 문자열은 존재하지 않는 값입니다');<br>
if(undefinedValue==null)<br>
    console.log('undefinedValue는 존재하지 않는 값입니다');<br>
if(nullValue==null)<br>
    console.log('null은 존재하지 않는 값입니다');<br>
//출력<br>
undefined는 존재하지 않는 값입니다<br>
null은 존재하지 않는 값입니다<br><br><br><br>



## [4월5일]
>

## [3월23일]
>문자열-따음표
>/t-수평탭,/n-줄바꿈,/

## [3월16일]
> 오늘 배운 내용 요약 <br />
> 여러줄요약 <br>
> 3번

배운내용
자바스크립트 실행 방법

특별히 하나의 것만 커밋하고싶을때는 +를 클릭하여 스테이지를 올려 특정만 커밋

기본용어
> 키워드를 사용 안됨<br>
>특수문자는 _와 $만 허용<br>
>숫자로 시작하면 안됨<br>
>공백은 입력하면 안됨

사용규칙
>생성자 함수의 이름은 항상 대문자로 시작(카멜[낙타] 로테이션)<br>
>변수,함수,속성,메소드이 이름은 항상 소문자로 시작 <br>
>여러 단어로 된 식별자는 각 단어의 처 글자를 대문자로 함

<table>
node 다운로드, 터미널 열기 node 자바스크립트 이름 후 엔터. 확인해보기.<br>
새 파일-hello.html 이후 htnl-5로 해야함<br>
alter과 console.log의 차이
</table>