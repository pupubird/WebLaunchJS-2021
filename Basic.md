# JS Workshop ⚙

> Make your painting interactable

Estimated completion time: 1.5 - 2 hours

<br>
<br>

## Table of content <a name="table"></a>

1. [JavaScript in browser](#intro)
2. [Hello World!](#hello-world)
3. [A short walkthrough for programming](#programming)
4. [Data types](#datatypes)
5. [Conditional statement](#conditional)
6. [Loop](#loop)
7. [Function](#function)
8. [Project](#project)
9. [Conclusion](#conclusion)

## JavaScript in browser <a name="intro"></a>

> JavaScript was created by Brendan Eich in 1995 during his time at Netscape Communications. It was inspired by Java, Scheme and Self. Netscape, for a time, made the best browser in the world and enjoyed market dominance.

--- [A brief history of JavaScript by Ben Aston](https://medium.com/@_benaston/lesson-1a-the-history-of-javascript-8c1ce3bffb17#:~:text=JavaScript%20was%20created%20by%20Brendan,by%20Java%2C%20Scheme%20and%20Self.&text=Netscape%2C%20for%20a%20time%2C%20made,world%20and%20enjoyed%20market%20dominance.)

JavaScript wasn't a general-purpose programming language --- it is a scripting language for browser only.

What it means is essentially it was never meant to go out from the browser (thou this is no longer true with **node.js**), the only purpose was only for you to add a behavior layer on your browser, like getting data from the server periodically

Using JavaScript, you are able to get your HTML element, and manipulate the styling, attributes of the element.

Although there are some alternative to manipulate your element with other languages (like Java Applet, etc), but the only officially marketed language is JavaScript.

Fun fact: JavaScript has nothing to do with Java, other than the name itself is similiar, nothing is 🤣.

<br>
<br>

## Hello World! <a name="hello-world"></a>

### Initialize

Let's start by creating our `index.html` as such:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <h1>Hello</h1>
    <script>
      console.log("World");
    </script>
  </body>
</html>
```

Open up your browser, look for inspection tool, right click on the browser, you should be seeing something like this:

![inspect](https://raw.githubusercontent.com/pupubird/WebLaunchJS-2021/master/assets/inspect.png)

Click on `Inspect`, there will be a new tab opening up as such:

![inspect_tab](https://raw.githubusercontent.com/pupubird/WebLaunchJS-2021/master/assets/inspect_tab.png)

_It's totally fine if your layout is different_

Inspect tool on the browser is one of the most used tool when it comes to front-end web development, you can't live without it.

### Console

Notice on your inspection tool, there is a section called `Console`, this is where we will be mainly looking at

![console](https://raw.githubusercontent.com/pupubird/WebLaunchJS-2021/master/assets/console.png)

Look! There is already something showing up in the console!

Console is where we will be printing out text etc, it's usually hidden from users as it's for debug and development purpose only. Don't worry if you do not understand the usage of it now, it will be clearer later.

### Code

Now we are seeing a message `World` being printten on the console, but why?

Let's look at our `index.html`, where we have the `script` tag:

```html
<script>
  console.log("World");
</script>
```

- JavaScript code usually live in a HTML tag that we called `script` tag, just like your typical `h1`, `p` etc, it's a way of telling the browser this is contains JavaScript code

What `console.log` essentially does is that, it tells the browser "Hey, can you help me to print this out in your **console** tab?". We are using JavaScript to access to our browser console tab to print out our first Hello World application!

Let's have some fun by changing some of the code:

```html
<script>
  let myName = "Rain Chai";
  console.log(myName);
</script>
```

Give yourself a try and see what will the output be!

<br>
<br>

## A short walkthrough for programming <a name="programming"></a>

Let's go with some fundamentals.

When it comes to programming, or rather, computer science, it's all about data (and googling), and how we compute the data.

Data can be in any form: Number, word, a paragraph of words, a grocery list (a list of words), etc. We typically call these **data types** (type of the data, a number, word, etc) and **data structures** (collection of the data, a list, a set, etc).

We call the step by step of processing the data (for say, adding up 2 numbers) an **algorithm**, after you write the steps into code, we call it **program**

<br>
<br>

## Data types <a name="datatypes"></a>

> Programming is all about how you process the data.

-- by me 🤣

Look around yourself, you are living in a world with full of data.

My laptop battery level is a data, my bottle's water level is also a data.

There are a lot of different type of data, be it a number (water level like litres, etc), a word (your name), etc.

In JavaScript specifically, we have:

1. **String** - a series of words like `"Rain Chai"`. It has to be wrapped in double or single quotes.
2. **Number** - Integer or decimal number like `1`, `1.1`, `2.2`
3. **Boolean** - it can only be `true` or `false` (literally, without double nor single quotes), useful for cases like `let isLoggedIn = true;`
4. **Undefined** - `undefined`, it's a state for a variable, it stands for "this variable is not defined, does not have any data.", you can think of it like void, it's empty. You will only use this in a more advance case, don't worry if you don't understand it now.

You may refer to [w3schools JavaScript data types documentation](https://www.w3schools.com/js/js_datatypes.asp) for more information.

#### Variable

It's better to name our data, in our last example, we called it `myName`, it can be any other names (like `abcd`, `klasdjlasjkd`) that you think is most descriptive for your variable.

To declare a variable, we use `let`, `let` is a keyword in JavaScript (there are many others too!), it tells browser that whenever you see this keyword, it means I am creating a new variable.

We can't do something like:

```javascript
let let = 1; // let is a keyword, you cannot use keyword as variable name by itself
```

but we can do:

```javascript
let letThisBecomeVariable = "Yay";
```

Do note that you **cannot** have spaces in between for your variables, below are a few examples that is **invalid** for naming the variable:

1. Spaces

   `let this is the apple = 5; //invalid!`

2. Number as the first character

   `let 5apples = 5; //invalid!`

3. Symbols other than `_` and `$` as the first character

   `let @thisIsVariable = 5; //invalid!`

[Here are a list of keywords in JavaScript](https://www.w3schools.com/js/js_reserved.asp), if you have some free time, do take a look into each of them.

#### Arithmetic Operators

Just like in math, we can have `+`, `-`, `×`, and `÷`, we have it in programming as well:

- `+` is plus in JavaScript
- `-` is minus in JavaScript
- `*` is times in JavaScript
- `/` is divide in JavaScript
- `=` in JavaScript stands for assignment, not the equal in mathematic, `let x = 1;` in this case is assigning `1` into `x`

### Example

#### = operator

In programming, we always have \<variable\> = \<value\>, so whatever on the right side will always get assign into the left side variable.

```html
<script>
  let myName = "Rain Chai"; // assigning "Rain Chai" into variable myName
  console.log(myName); // will print Rain Chai in console

  myName = "Hehe"; // Reassign "Hehe" into variable myName
  console.log(myName); // will print Hehe in console

  myName = 1; // Can assign a number too!
  console.log(myName);
</script>
```

#### + operator

Just like how you would expect, `+` will add two values together

```html
<script>
  let myAge = 19 + 1; // 20!
  myAge = myAge + 1; // Get current value of myAge (20), then plus 1. Now it becomes 21!
</script>
```

In JavaScript, words can be easily concatenated together with `+` operator too!

```html
<script>
  let myName = "Rain Chai";
  console.log("Hello" + myName); // Becoming "Hello Rain Chai"!
</script>
```

#### - \* and / operators

```html
<script>
  let myAge = 19;
  myAge = myAge + 1;
  myAge = myAge * 2;
  myAge = myAge / 2;
</script>
```

What if you want to have `myAge` plus 1 then divide 2?

```html
<script>
  let myAge = 20;
  myAge = 1 + 20 / 2;
</script>
```

This will return you myAge = 11!
When the JavaScript engine is parsing this, it will read as such:

```javascript
myAge = 1 + 20 / 2; // it calculate 20 / 2 first
```

This is what we call _operator precedence_ in programming, [here is the relevant information](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence#table)

To calculate what we want, `myAge` plus 1 then divide 2, we have to bracket it as such:

```javascript
myAge = (1 + 20) / 2;
```

Be careful when it comes to operator precedence! It will easily cause you some bugs!

Lastly, do feel free to play around with other operators. [Here is a list of operators](https://www.w3schools.com/js/js_operators.asp)

### Challenge!

Get the user birth year by using `window.prompt` (Accessing to window in browser), then, print out current user age using `console.log`!

Example output:

Assuming this year is 2021

```
> user input: 2000
> console log output: 21
```

```
> user input: 1995
> console log output: 26
```

<br>
<br>

## Conditional statement <a name="conditional"></a>

Let's think of this question:

Get the user birth year by using `window.prompt` (Accessing to window in browser), then, print out current user age using `console.log`, if the person is under or equal 18, print "Below 18", if the person is above 18 and below 30, print "Above 18 and below 30", else, print "Above 30".

With the knowledge that we have right now, it's impossible to implement such logic, hence, we will need the help of **Logical operator**.

### Logical operator

Just like arithmetic operator, logical operators are a bunch of symbols.

To use logical operators, we will need keywords like: `if` and `else`, just like your keyword `let`.

For example:

```javascript
let age = 20;

if (age <= 18) {
  // less than or equal
  console.log("Below 18");
} else if (age > 18 && age <= 30) {
  // more than 18 and less than / equal 30
  console.log("Above 18 and below 30");
} else {
  console.log("Above 30");
}
```

Do notice we have `{ }` in between of each if-else statements, all your code logic will be executed here if the `if-else` statement is `true` (Remember boolean?)

There are a few other logical operators in JavaScript too!

#### OR operator

```javascript
let age = 20;

if (age > 20 || age < 10) {
  // "Or" operator
  console.log("Age is more than 20 or less than 10");
}
```

#### NOT operator

```javascript
let age = 20;

if (age != 20) {
  console.log("Age is not 20!");
}
```

Just like arithmetic operator, logical operators have precedence too! If you want any of them has the highest priority, you can wrap them with `( )`

```javascript
let age = 20;

if ((age >= 20 && age <= 30) || age != 25) {
  console.log("Between 20 to 30 or not 25");
}
```

<br>
<br>

## Loop <a name="loop"></a>

Here is a problem to solve:

Print your name 1000 times.

We can't be possibly copy-pasting `console.log` 1000 times, in programming, when we want to do things iteratively, we use **loop**:

```javascript
let myName = "Rain";
for (let index = 0; index < 1000; index++) {
  console.log(myName + " printing at " + index);
}
```

We are going to cover only **for loop** for now, but I will let you try to discover on **while loop**

### For loop

`for` is another keyword in JavaScript, as what we cover in `if-else`, the `{ }` here acting as the container that contains the code that will run in loops.

for loop has a specific syntax as such:

```javascript
for (/*<declaring the index starting>*/ ,/*<a condition that if true, this loop will run again>*/, /*<what happen after this loop finished>*/ ){
  //...
}
```

<br>
<br>

## Function <a name="function"></a>

<br>
<br>

## Project <a name="project"></a>

### Challenge 1

Source: [Hackerrank](https://www.hackerrank.com/challenges/solve-me-first/problem)

Complete the function solveMeFirst to compute the sum of two integers.

Function prototype:

```javascript
solveMeFirst(number1, number2);
```

where,

```text
number1 is the first number input.
number2 is the second number input
```

Sample Input:

number1 = 2

number2 = 3

Sample Output:

5

Explanation

The sum of the two integers number1 and number2 is computed as: 2 + 3 = 5.

### Challenge 2

Source: [https://www.hackerrank.com/challenges/fizzbuzz/problem](https://www.hackerrank.com/challenges/fizzbuzz/problem)

<br>
<br>

## Conclusion <a name="conclusion"></a>

You had completed a simple JavaScript walkthrough, there are tons of stuff that I didn't include.

[https://www.freecodecamp.org/](https://www.freecodecamp.org/) offers a great hands-on and practice for you to learn more.

[> Redirect to Advance JS Workshop](./Advance.md)

[> Go to top](./)
