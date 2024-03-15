# W2

English: ***The Elements of Style***

#### 书写具备一致风格、通俗易懂 JavaScript 的原则:

https://github.com/rwaldron/idiomatic.js/tree/master/translations/zh_CN

### Differences between ECMAScript and JavaScript
ECMAScript 被标记为“规范”，而 JavaScript 被标记为“编程语言”。
ECMAScript 是 JavaScript 所基于的标准。JavaScript 是开发人员使用的实际编程语言，它遵循 ECMAScript 规范。还有其他语言也实现了 ECMAScript 标准，但 JavaScript 是最突出且使用最广泛的。

### Differences between Java and JavaScript
Java：
- 是一种静态类型、基于类的面向对象编程语言。
- 它需要将源代码编译成字节码，在Java虚拟机（JVM）上运行。
- 它用于广泛的应用程序，从企业软件到     Android 应用程序。

JavaScript：
- 是一种动态类型、基于原型的脚本语言，主要用于向网页添加交互行为。
- 它是一种解释性语言，这意味着它在运行时逐行执行。
- JavaScript 是 Web     的脚本语言，无需编译即可在任何浏览器中运行。

这两种语言有不同的用途，并且不能互换。Java 通常用于后端和移动开发，而 JavaScript 对于前端 Web 开发至关重要，也可以在 Node.js 等环境中用于服务器端。

### HTML vs CSS vs JavaScript
• HTML is the markup language that we use to structure and give meaning to our web content, for example defining paragraphs, headings, and data tables, or embedding images and videos in the page.
• CSS is a language of style rules that we use to apply styling to our HTML content, for example setting background colors and fonts, and laying out our content in multiple columns.
JavaScript is a scripting language that enables you to create dynamically updating content, control multimedia, animate images, and pretty much everything else. (Okay, not everything, but it is amazing what you can achieve with a few lines of JavaScript code.)

DOM API 代表文档对象模型应用程序编程接口。它是 Web 文档的编程接口，允许程序动态访问和更新文档的内容、结构和样式。React, Angular, and Vue 是JavaScript的库和框架。这些框架和库提供了抽象、有效的方法来操作 DOM 并构建动态、响应式 Web 应用程序。它们处理直接 DOM 操作的许多复杂性，并提供创建 Web 应用程序的结构化方法。

# 1. Comments

same as in Java and C#

(1) multiline comments 

```javascript
/*
everything in between is a comment.
*/
```

(2) single line comments

```javascript
// This is a comment
```

# 2. Variables

1. the var , let or const

建议开发中默认使用`const`，这样可以确保变量值不被意外改变。

仅当你知道变量的值需要更改时才使用`let`。

避免使用`var`，因为它可能会导致由于函数作用域和变量提升所引起的预期之外的行为。

2. case sensitive: myVariable != myvariable

3. Variables' data types:

   string, number, boolean, array, object

   For the same variable, its datatype can be changed.

   ```javascript
   var myVariable = 'Bob';
   myVariable = 10;
   ```

| 特性/关键字            | var                          | let              | const            |
| ---------------------- | ---------------------------- | ---------------- | ---------------- |
| 作用域（Scope）        | 否（函数作用域或全局作用域） | 是（块级作用域） | 是（块级作用域） |
| 可重声明（Redeclare）  | 是                           | 否               | 否               |
| 可重新赋值（Reassign） | 是                           | 是               | 否               |
| 提升（Hoisted）        | 是                           | 否               | 否               |
| 绑定this（Binds this） | 是                           | 否               | 否               |

**Function name is like const variable**: can't change the variable 

## Redeclaring

`var` is allowed anywhere. 

```javascript
var x = 2;
// Now x is 2

var x = 3;
// Now x is 3
```

`let` and `const`  is not allowed in the same block, but is allowed in another block

```javascript
var x = 2;   // Allowed
let x = 3;   // Not allowed

{
let x = 2;   // Allowed
let x = 3;   // Not allowed
}

{
let x = 2;   // Allowed
var x = 3;   // Not allowed
}

// another block
let x = 2;   // Allowed

{
let x = 3;   // Allowed
}

{
let x = 4;    // Allowed
}
```

## Constant Objects and Arrays

 `const` does not define a constant value. It defines a constant reference to a value.

It can NOT:

- Reassign a constant value
- Reassign a constant array
- Reassign a constant object

But it CAN:

- Change the elements of constant array
- Change the properties of constant object

```javascript
//array:
const cars = ["Saab", "Volvo", "BMW"];

// You can change an element:
cars[0] = "Toyota";
// You can add an element:
cars.push("Audi");

//can NOT reassign the array
cars = ["Toyota", "Volvo", "Audi"];    // ERROR
```

```javascript
//objects
const car = {type:"Fiat", model:"500", color:"white"};

// You can change a property:
car.color = "red";
// You can add a property:
car.owner = "Johnson";

//can NOT reassign the object
car = {type:"Volvo", model:"EX60", color:"red"};    // ERROR
```

## Logical Operators

















# 3. Operators

- Arithmetic Operators

- Assignment Operators

- Comparison Operators

- String Operators

- Logical Operators

- Bitwise Operators

- Ternary Operators

- Type Operators

  ## 1. Arithmetic Operators

  | Operator | Description                  | Example          | Example Result      |
  | -------- | ---------------------------- | ---------------- | ------------------- |
  | +        | Addition                     | `5 + 3`          | 8                   |
  | -        | Subtraction                  | `5 - 3`          | 2                   |
  | *        | Multiplication               | `5 * 3`          | 15                  |
  | **       | Exponentiation (ES2016)      | `5 ** 3`         | 125                 |
  | /        | Division                     | `5 / 3`          | 1.666...            |
  | %        | Modulus (Division Remainder) | `5 % 3`          | 2                   |
  | ++       | Increment                    | `let a = 5; a++` | 6 (after increment) |
  | --       | Decrement                    | `let a = 5; a--` | 4 (after decrement) |
  | +=       |                              |                  |                     |
  | -=       |                              |                  |                     |
  | *=       |                              |                  |                     |
  | /=       |                              |                  |                     |
  
  increment（递增）和decrement（递减）操作，以及它们的前置（pre-）和后置（post-）版本的不同之处: 
  
  | 类型           | 符号  | 描述                                | 示例                  | 示例中变量的变化              | 返回值 |
  | -------------- | ----- | ----------------------------------- | --------------------- | ----------------------------- | ------ |
  | Post-increment | `a++` | 先返回变量的当前值，然后变量的值加1 | `let a = 5; b = a++;` | `a`变为6，`b`为赋值前的`a`值5 | 5      |
  | Pre-increment  | `++a` | 先将变量的值加1，然后返回新值       | `let a = 5; b = ++a;` | `a`和`b`都变为6               | 6      |
  | Post-decrement | `a--` | 先返回变量的当前值，然后变量的值减1 | `let a = 5; b = a--;` | `a`变为4，`b`为赋值前的`a`值5 | 5      |
  | Pre-decrement  | `--a` | 先将变量的值减1，然后返回新值       | `let a = 5; b = --a;` | `a`和`b`都变为4               | 4      |

## Assignment Operators

| Operator | Example | Same As    |
| :------- | :------ | :--------- |
| =        | x = y   | x = y      |
| +=       | x += y  | x = x + y  |
| -=       | x -= y  | x = x - y  |
| *=       | x *= y  | x = x * y  |
| /=       | x /= y  | x = x / y  |
| %=       | x %= y  | x = x % y  |
| **=      | x **= y | x = x ** y |

## Comparison Operators

| Operator | Description                       |
| :------- | :-------------------------------- |
| ==       | equal to                          |
| ===      | equal value and equal type        |
| !=       | not equal                         |
| !==      | not equal value or not equal type |
| >        | greater than                      |
| <        | less than                         |
| >=       | greater than or equal to          |
| <=       | less than or equal to             |
| ?        | ternary operator                  |







## 	JavaScript has 8 Datatypes:
|string|number|bigint|bollean|undefined|null|symbol|ogject|

### The object datatype
- an object
- an array 
- a date
## String
可以使用反引号 ( ) 声明字符串。像这样声明的字符串称为模板文字，并且具有一些特殊属性。特别是，您可以在其中嵌入其他变量甚至表达式：

```javascript
const name = 'mahalia';
const greeting = 'hello ${name}';
```

Note: When adding a number and a string, JavaScript will treat the number as a string.

```javascript
let x = 16 + 'vovo' //16vovo
let x = 'vovo'+ 16 + 4 //vovo164
let x = 16 + 4 + 'vovo' //20vovo
```

JavaScript Types are Dynamic: the same variable can be used to hold different data types.

### String functions

| 函数名                                   | 解释                                                         | 示例                                                         |
| ---------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `charAt(index)`                          | 返回指定位置的字符。                                         | `var str = "hello"; console.log(str.charAt(1)); // "e"`      |
| `concat(string2, string3, ..., stringN)` | 连接两个或多个字符串，并返回新的字符串。                     | `var str = "Hello"; console.log(str.concat(" ", "World!")); // "Hello World!"` |
| `includes(searchString, position)`       | 检查字符串中是否包含指定的子字符串，并返回布尔值。           | `var str = "Hello world"; console.log(str.includes("world")); // true` |
| `indexOf(searchValue, fromIndex)`        | 返回字符串中指定值首次出现的索引，如果未找到则返回-1。       | `var str = "Hello world"; console.log(str.indexOf("world")); // 6` |
| `lastIndexOf(searchValue, fromIndex)`    | 返回字符串中指定值最后一次出现的索引，如果未找到则返回-1。   | `var str = "Hello world, hello"; console.log(str.lastIndexOf("hello")); // 13` |
| `replace(searchFor, replaceWith)`        | 使用一个替换值替换字符串中的另一个值或符合正则表达式的子串。 | `var str = "Hello world"; console.log(str.replace("world", "everyone")); // "Hello everyone"` |
| `slice(startIndex, endIndex)`            | 提取字符串的一部分，并返回新的字符串。                       | `var str = "Hello world"; console.log(str.slice(0, 5)); // "Hello"` |
| `split(separator, limit)`                | 将字符串分割成子字符串数组。                                 | `var str = "Hello world"; console.log(str.split(" ")); // ["Hello", "world"]` |
| `substring(startIndex, endIndex)`        | 返回字符串的指定部分。                                       | `var str = "Hello world"; console.log(str.substring(1, 4)); // "ell"` |
| `toLowerCase()`                          | 将字符串转换为小写。                                         | `var str = "Hello World"; console.log(str.toLowerCase()); // "hello world"` |
| `toUpperCase()`                          | 将字符串转换为大写。                                         | `var str = "Hello World"; console.log(str.toUpperCase()); // "HELLO WORLD"` |
| `trim()`                                 | 从字符串的两端删除空白字符。                                 | `var str = " Hello world "; console.log(str.trim()); // "Hello world"` |
| `length`                                 | 属性，返回字符串的长度。                                     | `var str = "Hello"; console.log(str.length); // 5`           |

## Numbers

Javascript numbers are always the double (64-bit floating point) type. 

## BigInt

JavaScript BigInt is a new datatype ([ES2020](https://www.w3schools.com/js/js_2020.asp)) that can be used to store integer values that are too big to be represented by a normal JavaScript Number.

```javascript
let x = BigInt('1223465786786')
```

## Array

```javascript
const cars = ["Saab", "Volvo", "BMW"];
```

### Array functions

| 函数名                                                       | 解释                                                         | 示例                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `push(element1, ..., elementN)`                              | **末尾**向数组的末尾添加一个或多个元素，并返回新的长度。     | `var arr = [1, 2]; arr.push(3); // arr is now [1, 2, 3]`     |
| `pop()`                                                      | 移除数组的最后一个元素并返回该元素。                         | `var arr = [1, 2, 3]; var last = arr.pop(); // last is 3`    |
| `shift()`                                                    | 移除数组的第一个元素并返回该元素，数组中的其他元素向前移动一位。 | `var arr = [1, 2, 3]; var first = arr.shift(); // first is 1` |
| `unshift(element1, ..., elementN)`                           | 向数组的开头添加一个或多个元素，并返回新的长度。             | `var arr = [2, 3]; arr.unshift(1); // arr is now [1, 2, 3]`  |
| `slice(start, end)`                                          | 返回数组的一个浅拷贝，从start到end（不包括end）。start和end都是索引值。 | `var arr = [1, 2, 3]; var newArr = arr.slice(1, 2); // newArr is [2]` |
| `splice(start, deleteCount, item1, ..., itemN)`              | 从数组中添加/删除元素，然后返回被删除的元素。                | `var arr = [1, 2, 3]; arr.splice(1, 0, 'a'); // arr is now [1, 'a', 2, 3]` |
| `concat(array2, ..., arrayN)`                                | 合并两个或多个数组，并返回一个新数组。                       | `var arr1 = [1, 2]; var arr2 = [3, 4]; var newArr = arr1.concat(arr2); // newArr is [1, 2, 3, 4]` |
| `join(separator)`                                            | 将数组中的所有元素连接成一个字符串并返回。                   | `var arr = [1, 2, 3]; var str = arr.join("-"); // str is "1-2-3"` |
| `indexOf(searchElement, fromIndex)`                          | 返回数组中找到的第一个元素的索引，如果不存在，则返回-1。     | `var arr = [1, 2, 3]; var index = arr.indexOf(2); // index is 1` |
| `lastIndexOf(searchElement, fromIndex)`                      | 返回数组中找到的最后一个元素的索引，如果不存在，则返回-1。   | `var arr = [1, 2, 3, 2]; var index = arr.lastIndexOf(2); // index is 3` |
| `forEach(callback(element, index, array), thisArg)`          | 数组每个元素执行一次提供的函数。                             | `var arr = [1, 2, 3]; arr.forEach(item => console.log(item)); // logs 1, 2, 3` |
| `map(callback(element, index, array), thisArg)`              | 创建一个新数组，其结果是该数组中的每个元素都调用一个提供的函数后的返回值。 | `var arr = [1, 2, 3]; var newArr = arr.map(item => item * 2); // newArr is [2, 4, 6]` |
| `filter(callback(element, index, array), thisArg)`           | 创建一个新数组，包含通过所提供函数实现的测试的所有元素。     | `var arr = [1, 2, 3, 4]; var newArr = arr.filter(item => item > 2); // newArr is [3, 4]` |
| `reduce(callback(accumulator, currentValue, currentIndex, array), initialValue)` | 对累加器和数组中的每个元素（从左到右）应用一个函数，将其减少为单个值。 | `var arr = [1, 2, 3, 4]; var sum = arr.reduce((acc, curr) => acc + curr, 0); // sum is 10` |
| `find(callback(element, index, array), thisArg)`             | 返回数组中满足提供的测试函数的第一个元素的值，否则返回 undefined。 | `var arr = [1, 2, 3, 4]; var found = arr.find(item => item > 2); // found is 3` |
| `findIndex(callback(element, index, array), thisArg)`        | 返回数组中满足提供的测试函数的第一个元素的索引，否则返回-1。 | `var arr = [1, 2, 3, 4]; var index = arr.findIndex(item => item > 2); // index is 2` |
| `includes(searchElement, fromIndex)`                         | 判断数组是否包含指定的值，根据情况返回 true 或 false。       | `var arr = [1, 2, 3]; var includes = arr.includes(2); // includes is true` |
| `sort(compareFunction)`                                      | 对数组的元素进行排序，并返回数组。默认排序顺序是在将元素转换为字符串，然后比较它们的UTF-16代码单元值序列时构建的。 | `var arr = [3, 1, 2]; arr.sort(); // arr is now [1, 2, 3]`   |
| `reverse()`                                                  | 颠倒数组中元素的位置，第一个元素成为最后一个元素，最后一个元素成为第一个元素。 | `var arr = [1, 2, 3]; arr.reverse(); // arr is now [3, 2, 1]` |
| toString()                                                   | `toString()` 可以比 `join()` 更简单，因为它不需要一个参数，但更有限制。使用 `join()` 可以指定不同的分隔符 |                                                              |

## Object

Object name={value pairs}, separated by commas.

```javascript
const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```

## Undefined

A variable without a value,----type: undefined and value: undefined

```javascript
let car;    // Value is undefined, type is undefined
car = undefined;    // Value is undefined, type is undefined
```

## Empty Values

An empty string has both a legal value and a type.

```javascript
let car = "";    // The value is "", the typeof is "string"
```





use the JavaScript typeof operator to find the type of a JavaScript variable.

```javascript
typeof "John"             // Returns "string"

```







## JavaScript Keywords

| Keyword  | Description                                                  |
| :------- | :----------------------------------------------------------- |
| var      | Declares a variable                                          |
| let      | Declares a block variable                                    |
| const    | Declares a block constant                                    |
| if       | Marks a block of statements to be executed on a condition    |
| switch   | Marks a block of statements to be executed in different cases |
| for      | Marks a block of statements to be executed in a loop         |
| function | Declares a function                                          |
| return   | Exits a function                                             |
| try      | Implements error handling to a block of statements           |

# JavaScript Where To

## The <script> Tag

In HTML, JavaScript code is inserted between `<script>` and `</script>` tags.

## a. Internal JS

Scripts can be placed in the `<body>`, or in the `<head>` section of an HTML page, or in both.

```html
<script>
document.getElementById("demo").innerHTML = "My First JavaScript";
</script>
```

## b. Extrnal JS

JavaScript files have the file extension **.js**.

Put the name of the script file in the `src` (source) attribute of a `<script>` tag

at the end of <body> part

```html
<script src="myScript.js"></script>
```

#### Advantages:

Placing scripts in external files has some advantages:

- It separates HTML and code
- It makes HTML and JavaScript easier to read and maintain
- Cached JavaScript files can speed up page loads

###  🌟 External References

An external script can be referenced in 3 different ways:

- With a full URL (a full web address)

  ```html
  <script src="https://www.w3schools.com/js/myScript.js"></script>
  ```

- With a file path (like /js/)

  ```html
  <script src="/js/myScript.js"></script>
  ```

- Without any path

  ```html
  <script src="myScript.js"></script>
  ```

  

# Output: Display Possibilities

JavaScript can "display" data in different ways:

- Writing into an HTML element, using `innerHTML`.

- Writing into the HTML output using `document.write()`.

- Writing into an alert box, using `window.alert()`.

- Writing into the browser console, using `console.log()`.

- | 方法               | 联系                                  | 区别                                                         | 何时使用                                                     |
  | ------------------ | ------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
  | `innerHTML`        | 所有方法都是在不同的地方显示数据。    | 通过改变HTML元素的`innerHTML`属性来显示数据，通常用于动态更新网页的一部分。 | 当需要将数据插入到页面的特定元素中时。适用于**单页应用程序**，或需要**不刷新页面即可更新页面内容**的情况。 |
  | `document.write()` | 与`innerHTML`相似，也是直接写入HTML。 | `document.write()`用于直接向HTML输出流写内容，如果在文档加载完成后执行，会**重写整个页面**。 | 主要用于测试或者在页面加载过程中输出HTML。**不推荐在生产环境中使用**，因为它会覆盖页面内容。 |
  | `window.alert()`   | 与其他方法不同，它不修改HTML。        | `window.alert()`会**弹出一个警告框显示数据**，中断用户操作。 | 用于需要用户立即注意的情况，如表单验证反馈或提示信息。不适用于常规的信息显示，因为它会打断用户的操作流程。 |
  | `console.log()`    | 用于调试目的，不会更改用户界面。      | `console.log()`将信息输出到**浏览器的控制台**，主要用于调试目的。 | **for debugging purposes**主要用于开发过程中调试，帮助开发者了解和检查代码执行过程中的状态或变量值。不用于生产环境中向用户展示数据。 |

| 方法                                | 解释                                                        | 应用示例                                                     |
| ----------------------------------- | ----------------------------------------------------------- | ------------------------------------------------------------ |
| `document.getElementById()`         | 选择具有指定 ID 的元素。                                    | `var elem = document.getElementById('myId'); elem.style.color = 'red';` |
| `document.getElementsByClassName()` | 选择具有指定类名的所有元素。                                | `var items = document.getElementsByClassName('myClass'); for (var i = 0; i < items.length; i++) { items[i].style.backgroundColor = 'yellow'; }` |
| `document.getElementsByTagName()`   | 选择具有指定标签名的所有元素。                              | `var paragraphs = document.getElementsByTagName('p'); for (var i = 0; i < paragraphs.length; i++) { paragraphs[i].style.fontSize = '18px'; }` |
| `document.querySelectorAll()`       | 返回一个 NodeList，包含文档中所有与指定选择器组匹配的元素。 | `var items = document.querySelectorAll('.container .item'); items.forEach(function(item) { item.style.border = '1px solid blue'; });` |
| `addEventListener()`                | 向指定元素添加事件监听器。                                  | `var btn = document.querySelector('button'); btn.addEventListener('click', function() { alert('Button clicked!'); });` |
| `removeEventListener()`             | 从指定元素移除事件监听器。                                  | `function handleClick() { alert('Button clicked!'); } var btn = document.querySelector('button'); btn.removeEventListener('click', handleClick);` |
| `setAttribute()`                    | 设置元素的属性值。                                          | `var link = document.querySelector('a'); link.setAttribute('href', 'https://www.example.com');` |
| `getAttribute()`                    | 获取元素的属性值。                                          | `var link = document.querySelector('a'); var hrefValue = link.getAttribute('href'); console.log(hrefValue);` |
| `createElement()`                   | 创建一个新的元素节点。                                      | `var newDiv = document.createElement('div'); newDiv.textContent = 'Hello, world!'; document.body.appendChild(newDiv);` |
| `appendChild()`                     | 将一个节点添加到指定父节点的子节点列表的末尾。              | `var newParagraph = document.createElement('p'); newParagraph.textContent = 'This is a new paragraph.'; document.body.appendChild(newParagraph);` |





#### 1. Using innerHTML

a. Access an HTML element:  `document.getElementById(id)` 

b. The `innerHTML` property defines the HTML content:

**Syntax:  `document.getElementById(id).innerHTML = ` **

```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My First Paragraph</p>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = 5 + 6;
</script>

</body>
</html>
<!--output: 
My First Web Page
My First Paragraph.
11
-->
```

#### 2. Using document.write()

For **testing purposes**, it is convenient to use `document.write()`:

```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<script>
document.write(5 + 6);
</script>

</body>
</html>
```

#### 3. window.alert()

```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<script>
window.alert(5 + 6);
</script>

</body>
</html>
```

#### 4. console.log()

```html
<!DOCTYPE html>
<html>
<body>

<script>
console.log(5 + 6);
</script>

</body>
</html>
```



# 条件语句

#### if .. else..

```javascript
if (condition) {
  /* 条件为真时运行的代码 */
} else {
  /* 否则，运行其他的代码 */
}
```

举例：

```html
<label for="weather">选择今天的天气：</label>
<select id="weather">
  <option value="">--作出选择--</option>
  <option value="sunny">晴天</option>
  <option value="rainy">雨天</option>
  <option value="snowing">雪天</option>
  <option value="overcast">阴天</option>
</select>

<p></p>

```

```javascript
const select = document.querySelector("select");
const para = document.querySelector("p");

select.addEventListener("change", setWeather);

function setWeather() {
  const choice = select.value;

  if (choice === "sunny") {
    para.textContent = "阳光明媚。穿上短裤吧！去海滩，或公园，吃个冰淇淋。";
  } else if (choice === "rainy") {
    para.textContent = "外面下着雨；带上雨衣和雨伞，不要在外面呆太久。";
  } else if (choice === "snowing") {
    para.textContent =
      "大雪纷飞，天寒地冻！最好呆在家里喝杯热巧克力，或者去堆个雪人。";
  } else if (choice === "overcast") {
    para.textContent =
      "虽然没有下雨，但天空灰蒙蒙的，随时都可能变天，所以要带一件雨衣以防万一。";
  } else {
    para.textContent = "";
  }
}
```

<img src="/Users/akira/Library/Application Support/typora-user-images/截屏2024-02-26 18.18.58.png" alt="截屏2024-02-26 18.18.58" style="zoom:50%;" />

### [逻辑运算符：与、或、非]

`&&`--- and 

`||`--- or

`!`--- not 

```javascript
if (x === 5 || x === 7 || x === 10 || x === 20) {
  // 执行代码
}
```

#### switch 

以单个表达式/值作为输入，然后查看多个选项，直到找到与该值相匹配的选项

```javascript
switch (表达式/值) {
  case 选择1:
    运行这段代码
    break;

  case 选择2:
    否则，运行这段代码
    break;

  // 包含尽可能多的情况

  default: //如果之前没有选项匹配，则运行此
    实际上，仅仅运行这段代码
}

```

**备注：** `default` 部分不是必须的——如果表达式不可能存在未知值，则可以安全地省略它。然而，如果有这样的机会，你需要包括它来处理未知的情况。

```javascript
const select = document.querySelector("select");
const para = document.querySelector("p");

select.addEventListener("change", setWeather);

function setWeather() {
  const choice = select.value;

  switch (choice) {
    case "sunny":
      para.textContent = "阳光明媚。穿上短裤吧！去海滩，或公园，吃个冰淇淋。";
      break;
    case "rainy":
      para.textContent = "外面下着雨；带上雨衣和雨伞，不要在外面呆太久。";
      break;
    case "snowing":
      para.textContent =
        "大雪纷飞，天寒地冻！最好呆在家里喝杯热巧克力，或者去堆个雪人。";
      break;
    case "overcast":
      para.textContent =
        "虽然没有下雨，但天空灰蒙蒙的，随时都可能变天，所以要带一件雨衣以防万一。";
      break;
    default:
      para.textContent = "";
  }
}
```

# 循环

伪代码

```javascript
loop(food = 0; foodNeeded = 10) {
  if (food = foodNeeded) {
    exit loop;
    // 我们有足够的食物了，回家吧。
  } else {
    food += 2; // 花一个小时多收集两个食物。
    // 循环将会继续执行。
  }
}
```

##### for loop

```javascript
for (initializer; exit-condition; final-expression) {
  // code to run
}
```

1. 在括号内，我们有三个项目，以分号分隔：
   1. 一个**初始化器** - 这通常是一个设置为一个数字的变量，它被递增来计算循环运行的次数。它也有时被称为**计数变量**。
   2. 一个**退出条件** - 如前面提到的，这个定义循环何时停止循环。这通常是一个表现为比较运算符的表达式，用于查看退出条件是否已满足的测试。
   3. 一个**最终条件** - 这总是被判断（或运行），每个循环已经通过一个完整的迭代消失时间。它通常用于增加（或在某些情况下递减）计数器变量，使其更接近退出条件值。

```javascript
var cats = ["Bill", "Jeff", "Pete", "Biggles", "Jasmin"];
var info = "My cats are called ";
var para = document.querySelector("p");

for (var i = 0; i < cats.length; i++) {
  if (i === cats.length - 1) {
    info += "and " + cats[i] + ".";
  } else {
    info += cats[i] + ", ";
  }
}

para.textContent = info;
```



















```javascript
alert("");
prompt("");
var yourName = prompt("what is your name?")
alert ("My name is" + yourName + "!")
word.length()
```

```javascript
var name = 'aaaaa'
word.length(name)  //5

name.slice(x,y) //allow to slice/dice the strings to separate them into individual characters
name.slice(0,1) // 'a'
name.slice(0,3) //'aaa'

word.toUpperCase()
word.toLowerCase()
```

```javascript
var para = prompt('Input your contents:')
var output = para.slice(0,140)
alert(output)
// alert(prompt('Input your contents:').slice(0,140))

```

```javascript
function getMilk (bottles) {
  var cost = bottles * 1.5
  return cost * 2
}
```

alert: sth. that users can see

console.log: only developer can see

```html
<button>按这里</button>
<div id="greeting"></div>

```

```javascript
const button = document.querySelector("button");

function greet() {
  const name = prompt("你叫什么名字？");
  const greeting = document.querySelector("#greeting");
  greeting.textContent = `你好呀，${name}！很高兴见到你！`;
}

button.addEventListener("click", greet);
```

