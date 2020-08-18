# javascript_selfstudy

JavaScript 입문
+ [기본정보](#BASIC)
+ [기초문법](#문법)
+ [메인(객체&모듈&UI등등)](#1)
+ [활용:함수](#2)
+ [객체지향](#3)

# BASIC
# 크롬 개발자 도구
- **즉석으로 자바 스크립트를 적용시켜보기 위함**
1. Ctrl+Shift+J (윈도우), 커멘트+Alt+J (OSX) 키를 누른다. 콘솔 탭이 선택된 상태로 개발자 도구가 실행된다.
2. alert('hello world')를 실행한다. 실행 결과 아래와 같이 경고창이 실행된다.
3.console.log(‘hello world’) alert와 비슷한 기능이나 경고 사운드가 포함 x
4.방향키^를 누르면 이전 작성코드를 불러올 수 있다. 

# 위치
-	**주로 body tag아래 위치하는걸 추천**
~~~
<body>
<script type=”text/javascript”>
Code
</script>
~~~
   
# 문법
기본: 수 연산자 and String

~~~
Math.pow(3,2); // 9, 3의 2승 
Math.round(10.6); // 11, 10.6을 반올림
Math.ceil(10.2); // 11, 10.2를 올림
Math.floor(10.6); // 10, 10.6을 내림
Math.sqrt(9); // 3, 3의 제곱근
Math.random(); // 0부터 1.0 사이의 랜덤한 숫자
~~~

-	**문자는 "(큰 따옴표) 혹은 '(작은 따옴표) 중의 하나로 감싸야 한다. 큰 따옴표로 시작하면 큰 따옴표로 끝나야하고, 작은 따옴표로 시작하면 작은 따옴표로 끝나야 한다. String이라고 한다.**
-	** “\”(역슬레시)바로 뒤의 것은 무조건 문자로 인식한다. 줄바꿈은 c++\n과 동일**
~~~
alert("coding everybody");
alert('coding everybody');
~~~

# 함수 전 기초
**Javascript의 변수는 string number모두 할당 가능**
~~~
var first = "coding";
alert(first+" everybody");

var a = 'coding', b = 'everybody';

var a=1;
alert(a+1);
~~~
+ 중요 **비교연산자 추가**
==
**동등 연산자로 좌항과 우항을 비교해서 서로 값이 같다면 true 다르다면 false가 된다. '='가 두개인 것을 주의하자. '='가 하나인 것은 대입 연산자로 우항의 값을 좌항의 변수에 대입할 때 사용하는 것으로 의미가 완전히 다르다.** 

alert(1==2) //false
alert(1==1) //true
alert("one"=="two") //false 
alert("one"=="one") //true


**일치 연산자로 === 좌항과 우항이 '정확'하게 같을 때 true 다르면 false가 된다. 여기서 정확하다는 말의 의미에 집중하자. 아래 예를보자.**
alert(1=='1'); //true
alert(1==='1'); //false

**조건문의 예시** 
If(){}; 형식 대부분의 연산자 모두 c++와 같음 ex)&& || != ect.
~~~
<script>//prompt=>입력창
id = prompt('아이디를 입력해주세요.');
if(id=='egoing'){
password = prompt('비밀번호를 입력해주세요.');
if(password==='111111'){
alert('인증 했습니다.');
} else {
alert('인증에 실패 했습니다.');
}
} else {
alert('인증에 실패 했습니다.');
}
</script>
~~~

**반복문**
~~~ 
While(조건){..};
For(var i=-;i<10;i++){…};
Break//반복문 빠져나오기
~~~ 
기존과 동일 모두 적용가능

# 함수
**예제**
Function  이름(입력){…};
이름();
~~~
//기본함수
function numbering(){//구성동작
i = 0;
while(i < 10){
document.write(i);//cout
i += 1;
} 
}
numbering();//출력

//반환함수
function get_member2(){
return 'k8805';//반환값
}

alert(get_member2());//반환값 경고창 표기

//특징(변수에 함수를 넣을수있다.)

var numbering = function (){
i = 0;
while(i < 10){
document.write(i);
i += 1;
} 
}
numbering();//함수 출력


~~~

# 배열
**변수 선언형식으로 배열도 선언하되 [..]로 구분**
~~~ 
var members; 
function get_members(){
return ['egoing', 'k8805', 'sorialgi'];
}

members = get_members();

// members.length는 배열에 담긴 값의 숫자를 알려준다. 
for(i = 0; i < members.length; i++){

// members[i].toUpperCase()는 members[i]에 담긴 문자를 대문자로 변환해준다.
document.write(members[i].toUpperCase()); 

document.write('<br />');
}

~~~ 
**배열의 추가와 제가**
~~~

/*다음은 배열의 끝에 원소를 추가하는 방법이다. push는 인자로 전달된 값을 배열(li)에 추가하는 명령이다. 배열 li의 값은 a, b, c, d, e, f가 됐다. */

var li = ['a', 'b', 'c', 'd', 'e'];
li.push('f');
alert(li);

/*다음은 복수의 원소를 배열에 추가하는 방법이다. concat은 인자로 전달된 값을 추가하는 명령이다. */

var li = ['a', 'b', 'c', 'd', 'e'];
li = li.concat(['f', 'g']);
alert(li);

/*다음은 배열의 시작점에 원소를 추가하는 방법이다. 배열 li는 z, a, b, c, d, e가 됐다. unshift는 인자로 전달한 값을 배열의 첫번째 원소로 추가하고 배열의 기존 값들의 색인을 1씩 증가시킨다. 
*/

var li = ['a', 'b', 'c', 'd', 'e'];
li.unshift('z');
alert(li);

/*만약 두번째 인덱스 뒤에 대문자 B를 넣고 싶다면 아래와 같이한다. splice는 첫번째 인자에 해당하는 원소부터 두번째 인자에 해당하는 원소의 숫자만큼의 값을 배열로부터 제거한 후에 리턴한다. 그리고 세번째 인자부터 전달된 인자들을 첫번째 인자의 원소 뒤에 추가한다.*/

 var li = ['a', 'b', 'c', 'd', 'e'];
li.splice(2, 0, 'B');
alert(li);

/*다음은 배열의 첫번째 원소를 제거하는 방법이다. shift를 사용하면 된다. 아래 결과는 b, c, d, e 다.*/
var li = ['a', 'b', 'c', 'd', 'e'];
li.shift();
alert(li);

/*다음은 배열 끝점의 원소를 배열 li에서 제거한다. 이때는 pop를 사용한다. 결과는 a, b, c, d 다.*/

var li = ['a', 'b', 'c', 'd', 'e'];
li.pop();
alert(li);

/*다음은 정렬하는 방법이다. 결과는 a, b, c, d, e 다.*/
var li = ['c', 'e', 'a', 'b', 'd'];
li.sort();
alert(li);

/*역순으로 정렬하고 싶을 때는 아래와 같이 한다.*/
var li = ['c', 'e', 'a', 'b', 'd'];
li.reverse();
alert(li);

~~~ 
# 1
# 객체(class)
**기본적으로 c++ class와 같은 느낌**
~~~ 
var grades = {'egoing': 10, 'k8805': 6, 'sorialgi': 80};
//객체의 선언
grades.’egoing’ //객체 사용 기본
grades[‘egoing’+[k8805’]//객체사용 but 프로그램적 적용가능
~~~ 
**객체 반복작업**
For in 문(for(var name in NAME))
~~~ 
var grades = {'egoing': 10, 'k8805': 6, 'sorialgi': 80};
//객체
for(key in grades) {
//key변수 생성 반복문(변수이름은 변경가능 var anothername)
document.write("key : "+key+" value : "+grades[key]+"<br />");
}//grades[key]=>배열의 순서를 이용한 것. 
/*추가로 document.write(<li>"key : "+key+" value : "+grades[key]+"<br />"</li>);
li를 추가하면 html의 기능도 구현가능하다*/


//결과
key : egoing value : 10

key : k8805 value : 6

key : sorialgi value : 80

~~~ 
** 중요) 객체에 객체 태우기**
+ 객체에 객체를 태울수 있으며 함수도 담을수있다. 아래 예문을 살펴보자
~~~ 
var grades = {
'list': {'egoing': 10, 'k8805': 6, 'sorialgi': 80},
'show' : function(){
for(var name in this.list){
document.write(name+':'+this.list[name]+"<br />");
}
}
};
grades.show();

~~~  


# MAIN
### 모듈화
**function.js**
~~~ 
function welcome(){//모듈파일
return 'Hello world';
}
~~~ 
**main.html**
~~~ 
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"/>
<script src="greeting.js"></script>//모듈파일 불러오기
</head>
<body>
<script>
alert(welcome());
</script>
</body>
</html>
~~~ 
+ 활용도 높은 코드를 별도 파일화 하여 유지보수에 용이하게 한다.


+ **UI,API**
간결하게 말해서 유저와 상호작용하는 하드웨어&소프트웨어 적 프로그램을 User Interface[Ui]
라 칭하며 API는 Application Programming Interface 직 간접적으로 만든 코드의 형식으로 만들어진 인터페이스 이다. 즉, 기본이되는 것 alert(“,,”)//경고 경고를 띄우라는 것은 사용자가 명했으나 경고차 자체 모양 출력 위치는 api가 만든것이다. 개발자는 api를 통한 제어 비개발자[사용자]는 ui를 통해 웹을 제어한다.

프로그래밍을 예로들면 코드를 작성하여 기능구현은 UI 각 코드 자체의 기능은 API이다

함수를 이용하여 원하는 출력을 하는 것 UI

함수의 기능자체를 만드는 것 API

+ 개인적인 견해로 편리하고 유용한 UI를 제공하기위해 섬세한 API가 필요하다.

# 2
# 함수(섬세)

**함수밖 선언은 전역변수 함수안 선언은 지역변수**
~~~ 
var vscope = 'global';

function fscope(){

var vscope = 'local';

alert(vscope);
}

fscope();//local 출력(지역변수)

alert(vscope);//global 출력(전역변수)
~~~ 
**불가피한 전역변수의 사용을 방지하는법**

~~~ 
(function(){//함수로 묶고 바로 실행시킨다.
var MYAPP = {}//객체 선언
MYAPP.calculator = {
'left' : null,
'right' : null
}
MYAPP.coordinate = {
'left' : null,
'right' : null
}
MYAPP.calculator.left = 10;
MYAPP.calculator.right = 20;
function sum(){
return MYAPP.calculator.left + MYAPP.calculator.right;
}
document.write(sum());
}())//끝
~~~ 
**자주할 수 있는 실수 유요범위**
+ 사용될때x 정의될때o 정해진다
~~~ 
var i = 5;
function a(){
var i = 10;
b();
}
function b(){
document.write(i);
}
a();//답은 5이다.
~~~ 
**함수는 값으로 이용될수있다**
~~~ 
function cal(func, num){
return func(num)//반환값으로 이용
}

function increase(num){
return num+1
}

function decrease(num){
return num-1
}

alert(cal(increase, 1));//함수를 값으로 전달 받을수있다.
alert(cal(decrease, 1));

~~~ 
**함수의 활용 심화**
+ 함수의 값
~~~ 
function cal(mode){
var funcs = {
'plus' : function(left, right){return left + right},
'minus' : function(left, right){return left - right}
}
return funcs[mode];
}
alert(cal('plus')(2,1));
alert(cal('minus')(2,1)); 
~~~ 

+ 배열의 값
~~~ 
var process = [
function(input){ return input + 10;},
function(input){ return input * input;},
function(input){ return input / 2;}
];
var input = 1;
for(var i = 0; i < process.length; i++){//name.length 유지보수에 용의하니 익혀두자.
input = process[i](input);
}
alert(input);
~~~ 
## 함수 콜벡(Ajex)알아보기 필수
+ 콜백은 비동기처리에서도 유용하게 사용된다. 시간이 오래걸리는 작업이 있을 때 이 작업이 완료된 후에 처리해야 할 일을 콜백으로 지정하면 해당 작업이 끝났을 때 미리 등록한 작업을 실행하도록 할 수 있다. 다음 코드는 일반적인 환경에서는 작동하지 않고 서버 환경에서만 동작한다. 동영상을 참고한다.
+ 동시 통신이 가능하다

## 클로져(내부함수,외부함수)
+ 내부함수 외부함수
~~~ 
function outter(){
var title = 'coding everybody'; 
function inner(){ /*내부함수는 외부함수의 지역변수를 가져올수있다.(정의한곳을 기준으로 하기때문)*/
alert(title);
}
inner();
}
outter();
~~~ 
**외부함수가 소멸된후에도 내부함수를 통해 접근가능**
~~~ 
function outter(){
var title = 'coding everybody'; 
return function(){ 
alert(title);
}
}
inner = outter();//외부함수 소멸
inner();//접근가능 coding everybody 출력
~~~

**설정자 접근자 클로져(필)**

~~~ 
function factory_movie(title){

return {//메소드를 활용하여 반환값 객체화

get_title : function (){//접근자
return title;
},

set_title : function(_title){//설정자
title = _title
}
}
}

ghost = factory_movie('Ghost in the shell');
matrix = factory_movie('Matrix');

alert(ghost.get_title());
alert(matrix.get_title());

ghost.set_title('공각기동대');//설정자 호출

alert(ghost.get_title());
alert(matrix.get_title());
~~~ 
**클로져 에러**
~~~ 
var arr = []
for(var i = 0; i < 5; i++){
arr[i] = function(){
return i;
}
}
for(var index in arr) {
console.log(arr[index]());
}
~~~ 

- 위 코드에서 루프가 다 돌고 난후 `i++`이 실행되어 최종적으로 i값은 5이다
- 첫번재 반복문에서 arr[index]에 담긴 것은 특정한 값이 아니라 함수이다.
- console.log(arr[index]());를 호출했을 때, 외부의 컨텍스트에 접근할 수 있을 것으로 기대하였다.
- 하지만 for문의 i는 외부함수의 변수가 아니었다. 훼이크!
- 따라서 단순히 arr[index]에 담긴 함수가 5회 실행되어 현재의 i값인 5를 출력하였다.

**argument**
+ 배열이나 함수의 전달 인자를 담는 객체의 인스턴스
~~~ 
function sum(){
var i, _sum = 0; 
for(i = 0; i < arguments.length; i++){
document.write(i+' : '+arguments[i]+'<br />');
_sum += arguments[i];
} 
return _sum;
}
document.write('result : ' + sum(1,2,3,4));
~~~ 
**예시** 
~~~ 
function zero(){
console.log(
'zero.length', zero.length,
'arguments', arguments.length
);
}
function one(arg1){
console.log(
'one.length', one.length,
'arguments', arguments.length
);
}
function two(arg1, arg2){
console.log(
'two.length', two.length,
'arguments', arguments.length
);
}
zero(); // zero.length 0 arguments 0 
one('val1', 'val2'); // one.length 1 arguments 2 //이름.length argument.lenth의 차이
two('val1'); // two.length 2 arguments 1//선언인자 2개 받은인자 1개
~~~ 

## 마무리 함수의 호출법
~~~
//오리지널 호출법
function func(){
..}
func();

//apply 호출법 저장된 객체를 활용할 때 사용하면 용이하다. 불러오기 가능

function sum(arg1, arg2){
return arg1+arg2;
}
alert(sum.apply(null, [1,2]))



//apply활용법(name.apply(null))

o1 = {val1:1, val2:2, val3:3}
o2 = {v1:10, v2:50, v3:100, v4:25}

function sum(){

var _sum = 0;
for(name in this){
_sum += this[name];
}
return _sum;

}

alert(sum.apply(o1)) // 6
alert(sum.apply(o2)) // 185
~~~ 

# 3 
# 객체지향(자바스크립트ver)
**선언**
+ c++ class와 같은 형식
~~~  
//내부정의
var person = {
'name' : 'egoing',
'introduce' : function(){
return 'My name is '+this.name;
}
}
document.write(person.introduce());

//외부정의
var person = {}
person.name = 'egoing';
person.introduce = function(){
return 'My name is '+this.name;
}
document.write(person.introduce());

~~~  
**생성자**
~~~ 
function Person(name){//함수 정의
this.name = name;
this.introduce = function(){
return 'My name is '+this.name; 
} 

}

var p1 = new Person('egoing');//동적할당+생성자1
document.write(p1.introduce()+"<br />");

var p2 = new Person('leezche');//동적할댱+생성자2
document.write(p2.introduce());

~~~ 

**생성자와 this의 관계**

+ 그 메소드가 소속된 객체를 의미한다. 함수일땐 전역객체windows 생성객체에 소속되었을땐 그 객채

~~~ 
var funcThis = null; 
function Func(){
funcThis = this;
}

var o1 = Func();
if(funcThis === window){//생성자 선언x(객체 미 생성)
document.write('window <br />');//window출력
}

var o2 = new Func();//생성자로 선언(빈 객체 생성)
if(funcThis === o2){
document.write('o2 <br />');//o2출력
}
생성자는 빈 객체를 만들기 때문에 this가 객체인 o2를 가리키게 된다.
~~~ 

**생성자 없이 this 제어**

~~~
var o = {}
var p = {}
function func(){
switch(this){
case o:
document.write('o<br />');
break;
case p:
document.write('p<br />');
break;
case window:
document.write('window<br />');
break; 
}
}
func();//window생성
func.apply(o);//o생성
func.apply(p);//p생성
~~~ 

## 상속

+ c++ class 상속과 비슷한 맥락 하지만 자녀class를 만들기본단 prototype이라는 명령어를 이용한다.

~~~
function Person(name){
this.name = name;
}

Person.prototype.name=null;
Person.prototype.introduce = function(){
return 'My name is '+this.name; 
}

var p1 = new Person('egoing');//생성자로 빈객체 생성
document.write(p1.introduce()+"<br />");//prototype의 함수 사용가능(상속)
~~~

**두함수의 상속 관계**

~~~
function Person(name){
this.name = name;
}
Person.prototype.name=null;
Person.prototype.introduce = function(){
return 'My name is '+this.name; 
}

function Programmer(name){//생성자
this.name = name;
}

Programmer.prototype = new Person();//peron을 programer이 상속하게 한다

var p1 = new Programmer('egoing');//생성자 빈객체 생성
document.write(p1.introduce()+"<br />");//introduce  사용가능 상속했기 때문에
~~~ 
**예제 2**

~~~
function Person(name){
this.name = name;
}
Person.prototype.name=null;
Person.prototype.introduce = function(){
return 'My name is '+this.name; 
}
function Programmer(name){
this.name = name;
}
Programmer.prototype = new Person();
Programmer.prototype.coding = function(){
return "hello world";
}
var p1 = new Programmer('egoing');
document.write(p1.introduce()+"<br />");
document.write(p1.coding()+"<br />");
~~~

 


