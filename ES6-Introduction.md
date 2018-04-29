# Contents

* [Topics](#topics)
----------------------------------------------------------------------------------------------------------------------
* [Transipiller](#transpiller)
* [Hands on](#hands-on)
* [Strict mode](#strict-mode)
* [Hoisting](#hoisting)
* [Variable](#variable)
* [Object](#object)
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







