# 김태현 [201740113]

##[4월27일]
>배열
let array=['사과','바나나','망고','딸기']
array[0]='사과'

>객체
속성(키)-name , price
//객체 선언
let object ={
    name:'바나나',
    price:1200
};
//출력
console.log(object.name);
console.log(object.price);
-> c:\exampleM>node object.js
   바나나
   1200

>속성 메소드.
-요소:배열 내부에 있는 값 하나하나
-속성:객체 내부에 있는 값 하나하나
다양한 자료형 객체
var object={
    number:273,
    string:'RintIanTta',
    boolean:true,
    array:[52,273,103,32],
    method:function({

    })
};
this키워드
let object={
    name:'바나나',
    price:1200,
    print:function(){
        console.log(`${this.name}의 가격은 ${this.price}원입니다.`)
    }
};
//호출
object.print();
바나나의 가격은 1200원입니다.

>객체 지향 프로그래밍:현실의 객체를 모방해서 프로그래밍한것-배열과 객체를 사용하면 여러 개의 데이터를 쉽게 다룰 수 있음
메소드를 가진 객체의 배열
let products=[{
    name:'바나나',
    price:1200,
    print:function(){
        console.log(`${this.name}의 가격은 ${this.price}원입니다.`)
    }
}, {
    name:'사과',
    price:2000,
    print:function(){
        console.log(`${this.name}의 가격은 ${this.price}원입니다.`)
    }
}, {
.
.
.
}];
//반복해서 출력
for(let product of products){
    product.print();
}

>함수 외부로
let products=[
    {name:'바나나',price:1200},
    {name:'사과',price:2000},
    .
    .
    .
];
//함수 선언
function printProduct(product){
    console.log(`${product.name}의 가격은 ${product.price}원입니다.`);
}
//반복 출력
for(let product of products){
    printProcuct(product);
}

> 생성자함수-객체를 만드는 함수,대문자로 시작하는 이름 사용
> 프로토타입-생성자 함수로 만든 객체는 프로토타입 공간에 메소드를 지정하새 모든 객체가 공유하도록 함, 해당 함수를 생성자 함수로 사용했을때만 의미가 있음
//생성자 함수
function Product(name,price){
    this.name=name;
    this.price=price;
}
//프로토타입에 메소드 선언
Product.prototype.print=function(){
    console.log(`${this.name}의 가격은 ${this.price}원입니다.`);
};
//상품 목록 선언
let product=[
    new Product('바나나',1200),
    new Product('사과',2000),
    new Product('배',3000),
    .
    .
    .
];
//반복 출력
for(let product of products){
    product.print();
}

바나나의 가격은 1200원입니다.
사과의 가격은 2000원입니다.
배의 가격은 3000원입니다.
.
.
.

>null
console.log(null);
console.log(typeof(null));
-아예 값이 없는 상태-null 활용
//변수 선언
let zeroNumber=0;
let falseBoolean='';
let emptyString='';
let undefinedValue;
let nullValue=null;
//갑이 있는지 확인
if(zeroNumber==null)
    console.log('0은 존재하지 않는 값입니다');
if(falseBoolean==null)
    console.log('false는 존재하지 않는 값입니다');
if(emptyString==null)
    console.log('반 문자열은 존재하지 않는 값입니다');
if(undefinedValue==null)
    console.log('undefinedValue는 존재하지 않는 값입니다');
if(nullValue==null)
    console.log('null은 존재하지 않는 값입니다');
//출력
undefined는 존재하지 않는 값입니다
null은 존재하지 않는 값입니다



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