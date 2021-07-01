//this => context(맥락에 따라 달라진다.)
function func (){
    if (window === this){
    document.write("windows == this")
    }
}

--> windouw == this

var o = {
    func : function (){
        if(o === this){
            document.write("o === this");
        }
    }
}
o.func();
--> o == this
//어떠한 객체 안의 메소드에서 메소드가 소속되어 있는 객체를 this로 접급 할 수 있다.
//o는 사실 window가 앞에 생략되어 있다는 사실을 명심하기.

var funcThis = null;

function Func(){ //생성자로 사용될 경우에는 생성될 객체를 가르킴, 함수로 호출될 경우 윈도우를 가르킴.
    funcThis = this;
}

var o1 = Func(); // 함수로 호출 함
if(funcThis === window){
    document.write('window <br />');
}

var o2 = new.Func(); / 생상자로 호출 함
if(funcThis === o2){
    document.write('o2 <br />');
}

function sum (x, y){return x + y}; 
//함수리터럴, Literal var 0 = {} 객체 리터럴, var a =[1,2,3]; 배열 Literal
sum(1,2); //3

var sum2 = new Function('x', 'y', 'return x + y'); // 마지막에 등장하는 인자가 본문의 함수에 해당한다.
sum2(1,2); //3


//apply와 call
var o = {}
var p = {}
function func(){
    switch(this){
        case o:
            document.write('o<br />');
            break;
        case p;
            document.write('p<br />');
            break;
        case window:
            document.write('window<br />);
            break;
    }
}
func();
func.apply(o);
func.apply(p);


//메소드라 하는 것은 객체에 포함되어 있음.
//보통은 객체는 주인이고 메소드는 주인에 종속되어있는 노예의 상태. -> master - slave

//window <- 함수
//o <- 함수
//p <- 함수 
//함수

// 함수는 심지어 객체이기 때문에 대등한 관걔를 가진다. 

//상속 (inheritance) -> 객체의 로직을 그대로 물려 받는 또 다른 객체를 만들 수 있는 기능.
//오리지널의 로직을 수정 변경하여 새로운 객체를 만들 수 있다. 

function Person (name){
    this.name = name;
    this.introduce = function(){
    return 'My name is' + this.name;
    }
}
var p1 = new Person('egoing');
document.wirte(p1.introduce() +"<br />");
--> My name is egoing


function Person (name){
    this.name = name;
}

Person.prototype.name = null;
Person.prototype.introduce = function(){
    return 'My name is ' + this.name;
}
var p1 = new Person('egoing');
document.wirte(p1.introduce() +"<br />");


//prototype에 대하여 
function Person (name){
    this.name = name;
}

Person.prototype.name = null;     // 상속을 하고 싶다면 prototype을 써서 상속을 시키면 된다. 
Person.prototype.introduce = function(){
    return 'My name is ' + this.name;
}

function Programmer (name){
    this.name = name;
}
programmer.prototype = new Person();

var p1 = new programmer('egoing');
document.write(p1.introduce() + "<br / >");

//prototype 분모를 건들지 않고 분자의 기능들만 확장하는 방법
function Person (name){
    this.name = name;
}
Person.prototype.name = null;     
Person.prototype.introduce = function(){
    return 'My nickname is ' + this.name;
}

function Programmer (name){
    this.name = name;
}
programmer.prototype = new Person();
programmer.prototype.coding = function (){
    return "hello world";
}

function Designer (name){
    this.name = name;
}
Designer.prototype = new Person();
Designer.prototype.design = function (){
    return "beautiful";
}

var p1 = new Programmer('egoing');
document.write(p1.introduce() + "<br / >");
document.write(p1.coding()+"<br />);

var p2 = new Designer('leechze');
document.write(p2.introduce() + "<br / >");
document.write(p2.design()+"<br />);

//Person이라는 공통의 분모(자기소개)가 있고
//Designer Programmer이라는 각각의 메소드를 통해 오리지널을 확장


//What is prototype(한국어로는 원형) -->  prototype chain 
function Ultra(){}
ULtra.prototype.ultraProp = true;

function Super(){}
Super.prototype = new Ultra();

function Sub(){}
Sub.prototype = new Super();

var o = new Sub();
console.log(o.ultraProp);

o.ultraprop = 1;
console.log(o.ultraProp); --> 1이 된다

//함수는 생성자가 되어 새로운 객체를 만들어서 로직을 함유하는 객체를 o으로 리턴한다. 

//생활 코딩님의 설명이 잘되어 있어 퍼온다. 
prototype chain
1. 객체 o에서 ultraPop를 찾는다.
2. 없다면 Sub.prototype.ultraProp를 찾는다.
3. 없다면 Super.prototype.ultraProp를 찾는다. 
4. 없다면 Ultra.prototype.ultraProp를 찾는다.











