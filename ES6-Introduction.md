# Contents

* [Topics](#topics)
----------------------------------------------------------------------------------------------------------------------
* [Transipiller](#transpiller)
* [Hands on](#hands-on)
* [Strict mode](#strict-mode)
* [Hoisting](#hoisting)
* [Variable](#variable)
* [Objects](#objects)
* [Class](#class)
* [Arrow Function](#arrow-function)
* [Destructuring](#destructuring)
* [Spread Operator](#spread-operator)

## Transpiller
> What will be the problem if we use ES6? `All browsers are not updated to ES6. They are still using ES5.`

> What is the purpose of transpiller? `A Transpiller takes ES6 code and generates ES5 source code that can be run on any browser.`

> There are two alternatives to transpile the ES6 code.
  * Traceur :  It is the google project. [Traceur](https://github.com/google/traceur-compiler/wiki/Getting-Started)
  * BabelJs : A Project started by young developer, Sebastian McKenzie (He was 17 Years old that time) [Babeljs](https://babeljs.io/)

## Hands on
> write below code in any of the text editor [ATOM, Visual Studio Code, Bracket, Sublime or Notepad ++ etc.]

```
var message = "hello world";
console.log(message);
```
follow below steps
1. save the file with test.js name
2. goto folder location where you saved this
3. open the folder in command prompt
4. run below command
```
node test.js
```

> Note :  node and npm need to be installed on your system. `node -v` command is used for checking node version and `npm -v` is used for checking npm version.

Make a small change in your app, remove var, save everything and rerun your app.

## Strict Mode
> The fifth edition of ECMAScript specification introduces the Strict Mode.

> make below changes in your test.js file and rerun your app.
```
"use strict"
message = "hello world";
console.log(message);
```
save the changes and rerun your test.js file useing `node test.js` command on command prompt.
> you'll get ouput as 
message = "hello world";
        ^
ReferenceError: message is not defined

`you can also use the strict mode inside scope, like function or if block etc.it will make impose the strict mode inside the block.`

## Hoisting

The JavaScript engine, by default, moves declarations to the top. This feature is termed as hoisting. This feature applies to variables and functions. Hoisting allows JavaScript to use a component before it has been declared. However, the concept of hoisting does not apply to scripts that are run in the Strict Mode.

## Variable

Variable is a “named space in memory.” It works as a container to hold values in program. 
```
//ES5 syntax for declaring a variable
var variable_name;
```
ES6 introduces following variable declaration syntax
- Using let
- Using const

## Variable – JavaScript and Dynamic Typeing
JavaScript is an un-typed language. This means that a JavaScript variable can hold a value of any data type. Unlike many other languages, you don't have to tell JavaScript during variable declaration what type of value the variable will hold. The value type of a variable can change during the execution of a program and JavaScript takes care of it automatically. This feature is termed as dynamic typing.

```
var message="Hello World";
message=10;
console.log(message);
```
While executing this code it will not show any error, rather it will assign new value type in message and message will be displayed.

## Variable – JavaScript variable scope
JavaScript defines only two scopes.
- Global Scope: a variable with global scope can be accessed from any part of the JS code
- Local Scope:  a variable with local scope can be accessed within a function where it is declared.

```
var num=10;
function test(){
var num=100;
console.log("value of num in test()"+num);
}
console.log("value of num outside test()"+num);
test()
```
> What will be the output of above code

## Variable – JavaScript variable scope
```
var a=10;
var a=20;
console.log(a);
```
> What will be the output of above code

## Variable – JavaScript const
```
const a=10;
a=20;
console.log(a);
```
> What will be the output of above code

Rules about constant:
- Constant cannot be reassigned a value
- Constant cannot be declared
- A Constant requires initialization
- A value assigned to constant value is mutable

## Variable – JavaScript Hoisting
> Is it possible to access a variable outside its scope?
```
function main(){
for(var i=1;i<=5;i++){
console.log(i);
}
console.log("value of i = "+i);
}
main();
```
> What will be the output of above code
> i is declared inside the for() but still available outside the for(), this is variable hoisting

## Objects
An object is an instance which contains a set of key value pairs. Unlike primitive data types, objects can represent multiple or complex values and can change over their life time. The values can be scalar values or functions or even array of other objects.

> Object Declaration Syntax

```
var identifier = { 
Key1:value, 
Key2: function () { 
//functions }, 

Key3: [“content1”,” content2”] 
} 
```
> Write the below code in text editor, and execute it

```
var employee={
name: "pankaj sharma",
salary: 175000,
showDetail: function(){
console.log("Name : "+this.name);
console.log("Salary : "+this.salary);
}
}
employee.showDetail();
```

Here employee is an object having name, salary and showDetail as properties. 

## Objects-constructor
JavaScript provides a special constructor function called Object() to build the object. The new operator is used to create an instance of an object. To create an object, the new operator is followed by the constructor method.

> What will be the output of below code?

```
var testObj=new Object();
console.log(testObj);
```
> Output :  {}

Now if you want to add some property along with value to be associated. Then we use the below methods. 

```
testObj.property=value;
Or
testObj[“key”]=value
```
> Check for  below code:

```
var car=new Object();
car.make="Maruti";
car.model="Maruti Alto LX";
car.year=2008;
console.log(car);
```
One more way of creating object: using function

```
function Car(){
this.make="Maruti"
this.model="Maruti Alto LX"
this.year=2008
}
var car=new Car();
console.log(car);
```
```
function Car(){
this.make="Maruti"
}
var car=new Car();
car.model="Maruti Alto Lx";
console.log(car);
```

## Objects (Creating Object using Object.create() method)

Objects can also be created using the Object.create() method. It allows you to create the prototype for the object you want, without having to define a constructor function.

```
var roles={
type:"Admin", // default role
showType: function(){
// show the type of role
console.log(this.type);
}
}
//create new super_role
var super_role=Object.create(roles);
super_role.showType();
```
Make changes to above code to create new roles as “Manager”

Solution:
```
var roles={
type:"Admin", // default role
showType: function(){
// show the type of role
console.log(this.type);
}
}
//create new super_role
var super_role=Object.create(roles);
super_role.showType();
//Create new manager_role
var manager_role=Object.create(roles);
manager_role.type="Manager";
manager_role.showType();
```

## Objects (Object.assign() function)
The Object.assign() method is used to copy the values of all enumerable own properties from one or more source objects to a target object. It will return the target object.

Syntax
Object.assign(target,…sources);

Object cloning
```
var employee=new Object();
employee.name="Pankaj";
employee.salary=90000;
var employeeCopy=Object.assign({},employee);
console.log("employee: ",employee);
console.log("employeeCopy: ",employeeCopy);
employeeCopy.id=1004482;
console.log("employeeCopy: ",employeeCopy);
console.log("employee: ",employee);
```

## Class
```
class Employee{
constructor(name,salary){
this.name=name;
this.salary=salary;
}
showEmployeeDetail(){
console.log('name : ',this.name);
console.log('salary : ',this.salary);
}
}
var employee=new Employee('pankaj',90000);
employee.showEmployeeDetail();

```









