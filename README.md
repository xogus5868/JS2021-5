# 김태현 [201740113]

## [5월25일]
>요청과 응답<br>
express 모듈 메서드<br>
express()서버 어플 객체 생성<br>
app.use()요청이 왔을때 실행할 함수 지정<br>
app.listen()서버 실행<br><br>
//모듈 추출<br>
const express=require('express');<br>
//서버 생성<br>
const app=express();<br>
//request이벤트 리스너 설정<br>
app.use((request,response)=>{<br>
    response.send('<h1>Hello express</h1>');<br>
});<br>
//서버 실행<br>
app.listen(52273,()=>{<br>
    console.log('Server running at http://127.0.0.1:52273');<br>
});

<br><br>
>페이지 라우팅<br>
get(path.callback)Get 요청 발생 이벤트 리스너 지정<br>
post'',put'',delete'',add''(모든 요청 발생 이벤트 리스너 지정)<br>
':<토큰 이름>'형태로 설정,토큰은 다른 문자열로 변환 입력 가능,request 객체 params 속성으로 전달<br><br>

>response 객체<br>
send() 데이터 본문 제공<br>
status()상태 코드 제공<br>
set() 헤더 설정<br><br>

>content-Type<br>
서버가''제공:웹 브라우저 헤더 확인,제공된 데이터의 형태 확인(MIME라는 문자열로 제공)<br>
text/plain:기본적인 텍스트, text/html:html 데이터 의미<br>
image/png:png 데이터 의미, audio/mpe:MP3 음악 파일 의미<br>
video/mpeg: MPEG 비디오 파일 의미, application/json:json데이터 의미, multupart/form-data:입력양식 데이터
<br><br>

//request 이벤트 리스너 설정<br>
app.get('/image',(request,response)=>{<br>
    fs.readFile('image.png',(error,data)=>{<br>
        //이미지 파일 제공<br>
        response.type('image/png');<br>
        response.send(data);<br>
    });<br>
});<br>
//서버 실행<br>
app.listen(52273,()=>{<br>
    console.log('Server running at http://127.0.0.1:52273');<br>
});<br>

## [5월11일]
>TypeError기본 예외 처리<br><br>
예외 상황확인:undefined 자료형을 일반적인 객체 또는 함수처럼 다루면 TypeError예외 발생.<br>
//함수 선언<br>
function callThreeTimes(callback){<br>
    for(let i=0;i<3;i++){<br>
        callback();<br>
    }<br>
}<br>
//정상<br>
callThreeTimes(function(){console.log('안녕하세요');<br>
//예외<br>
callThreeTimes();<br><br>

>기본예외처리:사전에 해당 데이터가 undefined인지 조건문 확인<br><br>
-try catch finally구문<br>
try{<br>
    //예외가 발생하면<br>
}catch(exception){<br>
    //여기서 처리<br>
}finally{<br>
    //여기는 무조건 실행<br>
}<br>
-catch구문,finally구문 생략 가능<br>
try{<br>
    //예외가 발생하면<br>
}catch(exception){<br>
    //여기서 처리<br>
}<br><br>
try{<br>
    //예외가 발생<br>
}finally{<br>
    //무조건 실행<br>
}<br>


## [5월4일]
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
let nullValue=null;<br>.
0

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



## [4월27일]
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