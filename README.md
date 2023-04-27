# Web-Dev-Hands-On

## Printing Hello world
```javascript
console.log("hello world");
```

## Data Types
```javascript
let num = 10;
console.log(num, typeof num);
let name = "Kaniskaa"
console.log(name.length)
name = name.trim();// the trimmed name should be stored somewhere
console.log(name.length)
name = name.slice(2,6);//2 will be included and index 6 will not be included
console.log(name);
```
### convert string to number and vice- versa
```javascript
let age = 90+"";
console.log(typeof age)
age = +age;
console.log(typeof age);
```
### convert string to number and vice- versa
```javascript
let age = 12;
age = String(age);
console.log(typeof age);
let name = "45";
name = Number(name);
console.log(typeof name);
```
### Concatenate Strings
```javascript
let string1= "Kaniskaa";
let string2 = "Behera";
let newString = string1 + " " + string2;
console.log(newString);
```

### Concatenate Numbers
```javascript
let string1 = "67";
let string2= "2";
let newString = +string1 + +string2;
console.log(newString);
```
### Tempelate String
```javascript
let firstName = "Kaniskaa";
let age = 21;
let newString = `My name is ${firstName} and my age is ${age}`;
console.log(newString);
```
### a big BUG
```javascript
console.log(typeof null);
```
### Big Int
```javascript
let number = 123;
console.log(Number.MAX_SAFE_INTEGER);
number = BigInt(number);
console.log(number);
let newNumber = 12n;
console.log(number + newNumber);//addition of only bigint with bigint is possible
```
### Falsy statement
```javascript
let number = "";
if(number){
    console.log(" what ?");
}
else{
    console.log("Example of falsy statement");
}
```
### Ternary Operator
```javascript
let num1 = 10;
let num2= 16;
let statement = (num2>num1)?"Number2 is greater":"Number 1 is greater";
console.log(statement);
```
Guessing Game
```javascript
let number = +prompt("Enter your number!!");
let winningNumber = 13;
if(winningNumber===number){
    console.log("You won !!");
}
else{
    if(number>winningNumber){
        console.log("Number is too high");
    }
    if(number<winningNumber){
        console.log("Number is too low");45
    }
}
```
### Arrays
```javascript
let fruits = ["Apple", "Orange","Banana"];
fruits.push("Pineapple");
console.log(fruits, typeof fruits);
console.log(Array.isArray(fruits));// determine whether the given object is an array or not
console.log(fruits.pop());
console.log(fruits);
nshift or shift adds or removes from the beginning
fruits.unshift("Pineapple");
console.log(fruits);
console.log(fruits.shift());
console.log(fruits);
```
### primitive v/s reference DataTypes
```javascript
var num1 = 90;
var num2= num1;
console.log(num1);
console.log(num2);
num1++;
console.log(num1);
console.log(num2);
```
Data stored in stack and values are directly assigned

### But in reference DataTypes
```javascript
let string1 = ["item1","item2","item3"];
let string2 = string1;
console.log(string1);
console.log(string2);
string1[3]="item4";
console.log(string1);
console.log(string2);
Data stored in heap and pointers are assigned
```
### Different ways to copy a string
```javascript
let string1 = ["item1","item2","item3"];
let string2 = string1.slice(0);
let string2 = [...string1];  //spread operator
let string2 = [].concat(string1);
console.log(string2);
```
### Copy and add strings at the same time
```javascript
let string1 = ["item1","item2","item3"];
let string2 = [].concat[string1 , "item4","item5"];
let oneMoreArray =["item4","item5"];
let string2 = [...string1,...oneMoreArray];
console.log(string2);
let string1 = ["item1","item2","item3"];
for(each of string1){
    console.log(each);
}//----------> will print all items
for(each in string1){
    console.log(string1[each]);
}//-------->each will give the index
---->Array Destructuring
let myArray = ["item1", "item2", "item3"];
let [array1, array2] = myArray;
console.log(array1 + " and " + array2);
let [one, , three] = myArray;
console.log(one + " and " + three);
OBJECTS
let person = {
  name: "kaniskaa",
  age: 21,
  eligibility: true,
  "new day": "Monday",
};
console.log(typeof person.name, typeof person);
console.log(person["name"]);
console.log(person["new day"]);
console.log(person.age);
let key = "email";
person[key] = "kaniskaa@gmail.com";
console.log(person);
// for (let key in person) {
  console.log(`${key}:${person[key]}`);
}
-->data will be represented as array
console.log(Object.keys(person));
let dataType = Array.isArray(Object.keys(person));
console.log(dataType);
```

### Object destructuring

```javascript
let objSet = {
  name: "kaniskaa",
  age: 12,
  legal: true,
};
let { name: firstName, legal: condition } = objSet;
console.log(firstName);
console.log(condition);
let songs = {
  genre: "hiphop",
  hits: "multiple",
  popStar: "weekend",
};
let { genre: funk, ...restprop } = songs;
console.log(funk, restprop);
console.log(typeof restprop);
console.log(Array.isArray(restprop));
```
### Objects in Arrays
```javascript
const users=[{
    userId:1,
    name:"kaniskaa",
    female: true
},
{
    userId:2,
    name:"kapil",
    female: false
},
{
    userId:3,
    name:"harshit",
    female: false
}]
for(let user of users){
    console.log(user.userId);
}
const [user1,user2,user3]=users;
console.log(user1);
const[{name:firstName},,{female}]=users;
console.log(firstName,female);
```
### Functions
function Declaration
```javascript
function singHappyBirthday(){
    console.log('Jappy Birthday to you ...........');
}
function addTwoNumber(num1,num2){
    return num1+num2;
}
```
arrow Function
```javascript
const multiply =(num1,num2)=>num1*num2;
singHappyBirthday();
console.log(addTwoNumber(9,7));
console.log(multiply(8,7));
unction Expression
const isEven = function(num){
if(num%2===0)
return true;
else
return false;
}
console.log(isEven(7));
```
arrow Function
```javascript
const isEven = num => num%2===0;
console.log(isEven(7));
```
Hoisting
```javascript
console.log(hello);
var hello ="hello";//change var to let and const
console.log(hello);
function app(){
    const singHappyBirthday=()=>{
        console.log("happy birthday feeeerrrrrrr");
    }
    const addTwoNumber = function(num1,num2){
        return num1+num2;
    }
    console.log('inside app function')
    console.log(addTwoNumber(9,7));
}
app();
```
Lexical Scope
```javascript
let number = 10;
{
    number =9;
    console.log(number);
}
```
Default Parameters
```javascript
const add=(num1,num2=3)=>{
    return num1+num2;
}
console.log(add(9));
```
est Parameters
```javascript
function myFunc(a,b,...c){
    console.log(a,b , " and ",c );
    console.log(Array.isArray(c))//lexical scope
}
myFunc(1,2,3,4,5,6,7);
 function sumOfAll(...a){
    let sum =0;
    for(let num of a){
        sum = sum+num
    }
    return sum;
 }
 console.log(sumOfAll(9,8,7,6,5,4));
 ```
parameter Destructuring
```javascript
 const myFunc1=(name)=>{
    console.log(`your name is ${name}`);
    console.log("I'm a callback !!");
 }
 const myFunc2=(callback)=>{
     callback('kaniskaa');
    console.log('inside func2');
 }
 myFunc2(myFunc1);
const users =[
    {firstNane : "kaniskaa", age : 12},
    {firstNane : "karan", age : 19},
    {firstNane : "harshit", age : 21},
    {firstNane : "garima", age : 20}
]
users.forEach(element => {
    console.log(element.firstNane);
});
```
Function returning function
```javascript
const myFunc=()=>{
    const myFunc2=()=>"hello world";
    return myFunc2;
}
const ans = myFunc();
console.log(ans());//here ans acts like a function
```
ForEach method
```javascript
const array = [2,8,1,6];
array.forEach((number,index)=>console.log(`the index is ${index} aand number is ${number*2}`))
const users =[
        {firstNane : "kaniskaa", age : 12},
        {firstNane : "karan", age : 19},
        {firstNane : "harshit", age : 21},
        {firstNane : "garima", age : 20}
    ]
users.forEach((user)=>console.log(user.age));
```
### Map method

similar to using a callback function where the data will be store din a string aswell
```javascript
const array = [3,9,7,4];
const square = number => number*number;
const squaredNumbers = array.map(square);
console.log(squaredNumbers);
const numbers = [7,8,3,4];
const multiplier =(number)=>{
    return number *6;
}
const updated = numbers.map(multiplier);
console.log(updated);
const users =[
            {firstNane : "kaniskaa", age : 12},
            {firstNane : "karan", age : 19},
            {firstNane : "harshit", age : 21},
            {firstNane : "garima", age : 20}
        ]
const array = users.map(user=>user.firstNane);
console.log(array);
```
### Filter function
```javascript
const array=[2,4,6,7,20];
const isEven =number =>number%2===0;
const even = array.filter(isEven);//This will filter only the even numbers
console.log(even);
```
### Reduce Function
```javascript
const userCart=[
    {productId : 1, productName: "Laptop", price: 20000},
    {productId : 2, productName: "Phone", price: 10000},
    {productId : 3, productName: "AC", price: 50000}
]
const sum = userCart.reduce((totalPrice, user)=>{
    return    totalPrice+user.price},0);
    console.log(sum);
```
### Sort in Ascending Order
```javascript
const array1 = [3,89,27,93,12,9];
array1.sort((a,b)=>a-b);
console.log(array1);
```
### Sort in Descending Order
```javascript
array1.sort((a,b)=>b-a);
console.log(array1);
```
### Sort in case of Objects
```javascript
const userCart=[
        {productId : 1, productName: "Laptop", price: 20000},
        {productId : 2, productName: "Phone", price: 10000},
        {productId : 3, productName: "AC", price: 50000}
    ]
const lowToHigh = userCart.slice(0).sort((a,b)=>a.price-b.price);
console.log(lowToHigh);
const highToLow = userCart.slice(0).sort((a,b)=>b.price-a.price);
console.log(highToLow);
```
### Find method
```javascript
const array = ["hello","kyat","dog","elephant"];
const lengthIs3 = (string)=>string.length===3;
const data = array.find(lengthIs3);
console.log(data);
const userCart=[
            {productId : 1, productName: "Laptop", price: 20000},
            {productId : 2, productName: "Phone", price: 10000},
            {productId : 3, productName: "AC", price: 50000}
        ]
const data = userCart.find(user=>user.productId===2);
console.log(data);
```
### Every Method
```javascript
const number = [3,6,27,81]
const isDivBy3= number => number%3===0;
console.log(number.every(isDivBy3));
```
### Some Method
```javascript
const number = [3,6,27,81]
const isDivBy3= number => number%3===0;
console.log(number.some(isDivBy3));
```
### Fill Method
```javascript
const myArray = new Array(10).fill(-1);
console.log(myArray);
const newArray = [3,8,9,2,3];
newArray.fill(0,3,5);
console.log(newArray);
```
### Splice Method
```javascript
const myArray =['item1','item2','item3','item4'];
myArray.splice(0,3,"hello world");
console.log(myArray);
```
### Set method
```javascript
const numbers = new Set();
numbers.add(1);
numbers.add(2);
numbers.add(3);
numbers.add(4);
numbers.add(5);
console.log(numbers);
console.log(numbers.length);
const randomArray = [1,28,7,6,6,6,3];
const uniqueArray = new Set(randomArray);
console.log(uniqueArray);
console.log(Array.isArray(uniqueArray));
let i =0;
for(let number of numbers){
    console.log(number);
    i++;
}
console.log(`length is ${i}`);
```
### MAP FUNCTION--> stores objects just like set holds arrays
```javascript
const person = new Map();
person.set('firstName','Harshit');
person.set('age',21);
person.set(1,'one');
person.set([2,4,6],'twoFourSix');
for(let key of person.keys()){
    console.log(typeof key)
}
console.log(person.get('age'));
console.log(person.get([2,4,6]));
for (let key of person){
    console.log(key, typeof key);//this makes map function iterable as objects are not iterable
    console.log(Array.isArray(key));
}
const person1 = {
    id:1,
    name :"kaniskaa"
}
const personNew = new Map();
personNew.set(person1,{age:8,gender: "male"});//here we are storing an object
console.log(person1.id);
console.log(personNew.get(person1).gender);
console.log(personNew);
```
### Clone with object.assign

either use spread operator or reference is passed
```javascript
const person1= {
    id:1,
    name:"kaniskaa",
    female: true,
}
// const person2 = person1;
// const person2 = {...person1};
const person2 = Object.assign({}, person1)
person1.movie="Daylight";//use dot operator only to assign
console.log(person1);
console.log(person2);
```
### Optional Chaining
```javascript
const user = {
name : "kaniskaa",
address:{homeLocation: "sector1"}
}
console.log(user)
console.log(user.name);
console.log(user?.address?.homeLocation)// this will give undefined instead of an error
```
### Create  your own methods
```javascript
const individual = {
    id: 5,
    name:"kaniskaa",
    about: function(){
        console.log(`Name is ${this.name} and Id is ${this.id}`)
    }
}
individual.about();
const individual2 = {
    id: 10,
    name:"harshit"
}
individual.about.call(individual2);
function print(){
    console.log(`name is ${this.name} and id is ${this.id}`);
}
const info1 ={
    id:'B221029',
    name:"kaniskaa",
    age:21,
    about: print
}
const info3 ={
    id:'B221026',
    name:"harsh",
    age:20,
    about: print
}
info1.about();
info2.about();
info3.about();
```
all apply and bind
```javascript
function about(musician, dates){
        console.log(`name is ${this.name} and id is ${this.id} with ${musician} and ${dates}`);
    }
const info1 ={
        id:'B221029',
        name:"kaniskaa",
        age:21}
    const info3 ={
            id:'B221026',
            name:"harsh",
            age:20,
        }
about.call(info1,"drake","available");
about.apply(info1,["drake","available"])
const func = about.bind(info3,"bacgh","busy");//bind will make func a function which can be called
console.log(func());
```
### Create your own methods
```javascript
const person = {
    firstName :"harshit",
    age : 8,
    about : function(){
        console.log(`person name is ${this.firstName}, and age is ${this.age}`)
    }
}
person.about();
function personInfo(musician, dancer){
    console.log(`person name is ${this.firstName} and age is ${this.age}`);
    console.log(`favourite musician is ${musician} and dancer is ${dancer}`)
}
const person1={
    firstName:"kaniskaa",
    age:21,
    about: personInfo
}
const person2 = {
    firstName: "harshit",
    agge : 22,
}
person1.about.call(person2,"drake","mj");
person1.about.apply(person2,["drake","mj"]);
```
### Short syntax
```javascript
const person = {
        firstName :"harshit",
        age : 8,
        about(){
            console.log(`person name is ${this.firstName}, and age is ${this.age}`)
        }
    }
    person.about();
``` 
### Proto, Prototype and classes
```javascript
const userMethod={
    about: function(){
        return `name is ${this.firstName} ${this.lastName} and age is ${this.age}`
    },
    is18: function(){
        return this.age>=18
    }
}
function createUser(firstName, lastName, email, age, address){
    const user={};
    user.firstName= firstName;
    user.lastName=  lastName;
    user.email= email;
    user.age=age;
    user.address=address;
    user.about=userMethod.about,
    user.is18=userMethod.is18
    // user.about = function(){
    return `name is ${this.firstName} ${this.lastName} and age is ${this.age}`
}
user.is18 = function(){
    return age>=18;
}
}
const user1 = createUser("kaniskaa","behera","kaniskaab33@gmail.com",21,"sector1");
const data = user1.about();
const obj1= {
    key1: "value1",
    key2:"value2"
}
const obj2 = Object.create(obj1);
obj2.key3="value3";
obj2.key2="unique"
console.log(obj2.key1);
console.log(obj2);
console.log(obj2.__proto__)//this stores the values of obj1 as optional values
```
### Prototype
```javascript
function hello(){
    console.log("hello World");
}
console.log(hello);
console.log(hello.prototype);
hello.prototype = {
    name:"kaniskaa",
    age : 21
}
console.log(hello.prototype);
hello.prototype = ["kaniskaa","21","true"];
console.log(hello.prototype);
hello.prototype.abc="abc";
hello.prototype.xyz="xyz";
hello.prototype.sing= function(){
    return "lalala";
}
console.log(hello.prototype);
console.log(hello.prototype.sing());
function createUser(firstName, lastName, email, age, address){
    const user= Object.create(createUser.prototype);
    user.firstName= firstName;
    user.lastName=  lastName;
    user.email= email;
    user.age=age;
    user.address=address;
user.about=userMethod.about,
user.is18=userMethod.is18
user.about = function(){
    return `name is ${this.firstName} ${this.lastName} and age is ${this.age}`
}
user.is18 = function(){
    return age>=18;
}
createUser.prototype.about = function(){
    return `name is ${this.firstName} ${this.lastName} and age is ${this.age}`
}
createUser.prototype.is18 = function(){
    return this.age>=18;
}
createUser.prototype.sing= function(){
    return "lalala";
}
const user1 = createUser("kaniskaa","behera",21);
console.log(user1);
function createUser (firstName,age){
    this.firstName= firstName;
    this.age = age;
}
createUser.prototype.about = function(){
    return `name is ${this.firstName} and age is ${this.age}`;
}
const user1 = new createUser("kaniskaa",21);
console.log(user1.about());
function createId(id,info){
    this.id= id;
    this.address= info;
}
createId.prototype.about= function(){
    return `id is ${this.id} and address is ${this.address} `
}
const userx = new createId("B221029","sector1");
console.log(userx.about());
console.log(userx);
-------------
function UserInfo(name, id){
    this.name = name;
    this.id = id;
}
UserInfo.prototype.about = function(){
    return `Name is ${this.name} and id is ${this.id}`;
}
const user1 = new UserInfo("kaniskaa","B221029");
console.log(user1.about());
for (let key in user1){
    console.log(key);
}
let number = new Array(1,2,3);
console.log(number);
// console.log(Array.prototype);
console.log(Object.getPrototypeOf(number));
console.log(UserInfo.prototype);
UserInfo.prototype=[];
UserInfo.prototype.push("Alekhya");
console.log(UserInfo.prototype);// here prototype is being used as an array
----------->Class Keyword
class Animal{
    constructor(name,age){
        this.name = name;
        this.age = age;
    }
    eat(){
        return `${this.name} is eating`;
    }
    isSuperCute(){
        return this.age<=1;
    }
    isCute(){
        return this.age<=2;
    }
}
const Animal1 = new Animal("tom",2);
console.log(Animal1);
console.log(Animal1.eat());
console.log(Animal1.isCute());
class Dog extends Animal{
    constructor(name,age,speed){
        super(name,age);
        this.speed = speed;
    }
    run(){
        return `${this.name} is running at the speed of ${this.speed}mph`
    }
}
const newDog = new Dog("Rocky",1,23);
console.log(newDog.run());
class Cat extends Animal{
    constructor(name,age,hours){
        super(name,age);
        this.hours=hours;
    }
    sleep(){
        return `${this.name} sleeps for ${this.hours}hours`;
    }
}
const Cat1 = new Cat("kimmin",1,10);
console.log(Cat1.sleep());
class Person{
    constructor(firstName,lastName,age){
        this.firstName=firstName;
        this.lastName=lastName;
        this.age=age;
    }
    get fullName(){
        return `${this.firstName} ${this.lastName}`;
    }
    // setname(firstName,lastName){
    //     this.firstName=firstName;
    //     this.lastName=lastName;
    // }
    static is18(){
        return this.age>=18;
    }
    static data = "Hello world";
set setName(fullName){
    const[firstName,lastName]=fullName.split(" ");
    this.firstName=firstName;
    this.lastName=lastName;
}
}
const Person1 = new Person("Kaniskaa","Behera",20);
console.log(Person1.fullName);
Person1.setName = "kabir singh"
console.log(Person1.fullName);
console.log(Person.is18());
console.log(Person.data
```