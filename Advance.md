# JS Workshop 2 ⚙

> Make your painting interactable

Estimated completion time: 1.5 - 2 hours

<br>
<br>

## Table of content <a name="table"></a>

1. [Recap](#recap)
2. [Callback function](#callback)
3. [List](#list)
4. [Object](#object)
5. [DOM](#dom)
6. [Project](#project)
7. [Conclusion](#conclusion)

## Recap <a name="recap"></a>

Let's recap what we had learned in the last session!

- Data Types

  - We covered 4 kinds of data types in JavaScript (there are more! Do explore them when you have time)
  - String - words
  - Number - numbers
  - Boolean - true / false, useful in conditional statement
  - Undefined - a data type that specifies this variable has no value inside.

- Conditional Statement

```javascript
if (condition) {
    execute these code if true
} else if (another condition){
    execute these code if true
} else {
    only execute this if all the above are false
}
```

- Loop

```javascript
for (initialize; condition; process after execution){
    execute these code only when the condition is true
}
```

- Function

```javascript
function sumUpTheNumbers(num1, num2){
    execute these code
}

sumUpTheNumbers(num1, num2);
```

We will cover what the` return` keyword will do when it comes to function, later

---

<br>
<br>

## Callback function <a name="callback"></a>

> Call me back later, I am cooking now.

Let's consider this question:

```
Create a function, to sum up, the 2 numbers input, then, print out the numbers with "Your total is: <the total>"
```

We can use the keyword `return` (I am going to talk about it later), but, we can use a `callback` function to solve this question!

In JavaScript, and many other languages, we can treat function just like a variable:

```javascript
function greeting(name) {
  console.log("Hello " + name);
}

greeting("Rain");

let anyVariable = greeting; // assigning "function" into variable "anyVariable", notice we do not call the function

anyVariable("Rain");
```

In this case, we are treating function just like any of our other data types (words, numbers, etc).

With that in mind, we can move on to the callback function!

A callback function look something like this:

```javascript
function greeting(name, theFunctionPassedIn) {
  console.log("Hello " + name);
  theFunctionPassedIn(); // call the function
}

function print_weather() {
  console.log("Today weather is:");
  console.log("A rainny day!");
}

greeting("Rain", print_weather); // treat print_weather like variable here;
```

In a real-world example, the concept of the callback is extensively used when it comes to network requests (getting data from the server). Like "After gotten the data from the server, call this function to update user profile for this page".

So to solve the question mentioned, what we can do is:

```javascript
function sumUpTwoNumbers(num1, num2, callback) {
  let total = num1 + num2;

  callback(total); // pass in the total as parameter of the callback
}

function print_total(total) {
  console.log("Your total is:");
  console.log(total);
}

let first_number = 1;
let second_number = 2;

sumUpTwoNumbers(second_number, first_number, print_total);
```

The beauty of the callback function is, it doesn't care what's gotta happen, it will just call it dynamically!

For say:

```javascript
function sumUpTwoNumbers(num1, num2, callback) {
  let total = num1 + num2;

  callback(total); // pass in the total as parameter of the callback
}

function print_total(total) {
  console.log("Your total is:");
  console.log(total);
}

function multiply_two(total) {
  total = total * 2;
  console.log("After multiply 2: " + total);
}

let first_number = 1;
let second_number = 2;

sumUpTwoNumbers(second_number, first_number, print_total);
sumUpTwoNumbers(second_number, first_number, multiply_two);
```

See? Same `sumUpTwoNumbers` but have different final output!

Other than the callback function, I mentioned there is a keyword called `return` that I want to introduce to you:

### keyword "return"

```javascript
function sumUpTwoNumbers(num1, num2) {
  let total = num1 + num2;
  return total; // return the value of total
}

let first_number = 1;
let second_number = 2;

let theSum = sumUpTwoNumbers(second_number, first_number); // whatever this function return, store the value in this variable
console.log("Your total is");
console.log(theSum);
```

---

<br>
<br>

## List <a name="list"></a>

Let's recall our previous session:

> Data can be in any form: Number, word, a paragraph of words, a grocery list (a list of words), etc. We typically call these **data types** (type of the data, a number, word, etc) and **data structures** (collection of the data, a list, a set, etc).

List in JavaScript is not a data type, but rather **data structure**, a data structure is a structure that holds many data inside.

To create a list of your grocery list, you can write as such:

```javascript
let grocery_list = ["Milk", "Coca-cola", "Apple cider"];
```

We use `[ ]` to specify it's a list, we then use `,` to separate out each item in the list.

To access our first item in the list, we can write as such:

```javascript
let grocery_list = [
  "Milk", // no 1.
  "Coca-cola", // no 2.
  "Apple cider", // no 3.
];
console.log(grocery_list[0]);
```

Remember, in programming, the number always starts with 0.

But if I want to print out all my items in the grocery list, it will be tedious every time to write out with the index! We can reuse what we learned in session 1: **for loop** to work in our favor

```javascript
let grocery_list = ["Milk", "Coca-cola", "Apple cider"];
console.log(grocery_list.length);
for (let i = 0; i < grocery_list.length; i++) {
  console.log(grocery_list[i]);
}
```

`.length` will get the length of the list!

---

<br>
<br>

## Object <a name="object"></a>

We had been using object since the very beginning, the object is a **data structure** (like list too!) that help you to hold all your variables!

Imagine a situation like this:

```
Rain has 2 eyes, both of them are black. He has 2 hands too and so do legs!
```

To express this idea in JavaScript, we can utilize `Object` (if you are familiar with Python, this is the dictionary or map in Java)

To make it easier to visualize here is a diagram

![rain](https://raw.githubusercontent.com/pupubird/WebLaunchJS-2021/master/assets/rain.png)

To express such logic in JavaScript, the syntax is as below:

```javascript
let rain = {
  eye_colour: "black",
  eye_amount: 2,
  leg_amount: 2,
  hand_amount: 2,
};
console.log(rain);
console.log(rain.eye_colour);
```

We use `,` to separate each item and use `.` to access the item

If you couldn't wrap your head around, just imagine Object is like List, but you give it a name (Proper term is **key**) to all your item (Proper term is **value**) instead of a number.

We had been using `console.log` since the beginning, now after learning Object, let's look a bit closer

```javascript
console.log(console);
```

To visualize it out:

![console](https://raw.githubusercontent.com/pupubird/WebLaunchJS-2021/master/assets/log.png)

Thou there is a more advanced data structure like `Class`, but we are not going to cover it in this session.

You might be wondering, where exactly does `console` come from?

**It's actually a variable that the browser help you to declare by default every time you open a new page**

Wanna try to disable it? :P you can't

Here is an exercise to practice our understanding of what we had covered so far:

Create an Object with a variable name called `person`, give it few keys as below:

- eye_colour - a string with the person eyes' color
- walk - a function that accepts `steps` ( A number ) as a parameter, the print out `"I walk <steps> amount of steps"`;
- age - a number of the age of the person
- friends - a list of all his friends' name

You may refer to the answer below, but you may clear it off and write it from scratch again if you want to practice.

```javascript
function walk(steps) {
  console.log("I walk " + steps + " amount of steps");
}
let person = {
  walk: walk,
  age: 21,
  eye_colour: "brown",
  friends: ["Rain", "Frankey", "Nick"],
};
person.walk(2);
console.log(person);
```

---

<br>
<br>

## DOM <a name="dom"></a>

> Now, finally with the doom has come

DOM, or Document Object Model, is a variable that you can access directly from the browser, very much like `console`, it's a built-in variable that the browser declared every time you open a new page.

to access to DOM:

```javascript
console.log(document);
```

Just like what `console` does, which helps you access the console tab of your browser, `document` helps you access your `HTML` (Remember `Doctype`?)!

Let's initialize our HTML as such:

```html
<html>
    <head>
        <style>
            .description {
                color: red;
            }
            .title {
                color: blue;
            }
            #magic {
                background-color: blue;
                color: white;
            }
            body > p {
                font-size: 25px;
            }
        </style>
    </head>
    <body>
        <h1 class="title">My hello world page!</h1>
        <p class="description">Hehe</a>
        <p class="description">My first one yoo</a>
        <a href="https://www.linkedin.com/in/rain-chai-48370318a/" id="linkedin" class="description">My linkedin here</a>
        <button id="magic">Click me to see magic</button>
    </body>
</html>
```

Some terms recap on CSS

- selector: A special way of writing to select your HTML tags
- class: an attribute that groups your tags together
- id: an attribute that gives your tag a special name

In `document`, to select our HTML elements, we have function called `querySelector` in the `document` object!

![document](https://raw.githubusercontent.com/pupubird/WebLaunchJS-2021/master/assets/document.png)

`query selector accepts a string parameter, which, is our selector in CSS!

```javascript
let title = document.querySelector(".title"); // pass in your CSS selector here
console.log(title);
```

This opens up a lot of possibilities, we can change the color of the title now!

```javascript
let title = document.querySelector(".title"); // pass in your CSS selector here
console.log(title);
title.style.color = "green";
```

What `querySelector` will return you is, an Object of the HTML element that is found!

![title](https://raw.githubusercontent.com/pupubird/WebLaunchJS-2021/master/assets/title.png)

Currently, `querySelector` will only return you the first element that it found, so for example:

```javascript
let descriptions = document,querySelector(".description");
console.log(descriptions);
```

it will return you the first element with class `.description`

Let's go a bit more advance, I want to select all my tags with class `description`, then make them green too!

In this case, we can utilize a function in `document` called `querySelectorAll`

```javascript
let descriptions = document.querySelectorAll(".description");
console.log(descriptions);
```

It returns you a list of all your elements!

Now you can loop them with `for loop`!

```javascript
let descriptions = document.querySelectorAll(".description");
console.log(descriptions);
for (let i = 0; i < descriptions.length; i++) {
  console.log(descriptions[i]);
}
```

To change their color, simply do it in the loop

```javascript
let descriptions = document.querySelectorAll(".description");
console.log(descriptions);
for (let i = 0; i < descriptions.length; i++) {
  descriptions[i].style.color = "green";
  console.log(descriptions[i]);
}
```

### Everything together

Let's solve this question

```
Change all your tags with class name "description" to green when the button is clicked!
```

To do so, let's start by selecting our button:

```javascript
let button = document.querySelector("#magic");
console.log(button);
console.log(button.onclick);
```

`button` is also an Object (arguably), there is a key called "onclick" that we can utilize!

![button](https://raw.githubusercontent.com/pupubird/WebLaunchJS-2021/master/assets/button.png)

It's currently "null" ( another data type in JavaScript, which basically means empty, or void ), awaiting us to do something!

To understand the logic behind it, whenever the user clicks on the button, the browser will look for the button's `onclick` key and call the **callback function** that is inside the button!

Remember the callback function? This is when it becomes useful

Let's go with simple first, we let the browser print "it works!" every time when the user clicks on the button

```javascript
let button = document.querySelector("#magic");
console.log(button);
function callback() {
  console.log("it works!");
}

button.onclick = callback; // notice we won't call the function here
console.log(button.onclick);
```

Now, the diagram looks like this

![button](https://raw.githubusercontent.com/pupubird/WebLaunchJS-2021/master/assets/button_callback.png)

We finally obtained all the necessary skills to solve the question! Remember, you don't need to learn everything in order to do programming.

We can simply merge all the logic we built before together

```javascript
let button = document.querySelector("#magic");
function callback() {
  console.log("it works!");
  let descriptions = document.querySelectorAll(".description");
  console.log(descriptions);
  for (let i = 0; i < descriptions.length; i++) {
    descriptions[i].style.color = "green";
    console.log(descriptions[i]);
  }
}

button.onclick = callback; // notice we won't call the function here
console.log(button.onclick);
```

With these 12 lines of code, it's basically almost all that you need to become a front-end developer! Celebrate for yourself! 🥳

---

<br>
<br>

## Project <a name="project"></a>

Let's add a dark mode toggle button!

Well, to do so, it's actually quite simple:

We need to add 2 classes in our CSS

```css
.black-background {
  background-color: black;
}
.dark-mode {
  filter: invert(100%);
}
```

**invert** will invert all the color of any element that has this class

We will assign `black-background` class to our `body` whenever the user click the toggle button!

We can do so by using `toggle` function in the `classList` key of our HTML element

```javascript
function toggleDarkMode() {
  let body = document.querySelector("body");
  body.classList.toggle("black-background");
  // select all elements in body, except image, as we wouldn't want to invert our image color
  let contents = document.querySelectorAll("body > *:not(img)");
  for (let i = 0; i < contents.length; i++) {
    contents[i].classList.toggle("dark-mode");
  }
}
document.querySelector("#magic").onclick = toggleDarkMode;
```

That's it!
