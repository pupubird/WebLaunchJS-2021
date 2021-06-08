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
6. [Function](#function)
7. [Project](#project)
8. [Conclusion](#conclusion)

## JavaScript in browser <a name="intro"></a>

> JavaScript was created by Brendan Eich in 1995 during his time at Netscape Communications. It was inspired by Java, Scheme and Self. Netscape, for a time, made the best browser in the world and enjoyed market dominance.

--- [A brief history of JavaScript by Ben Aston](https://medium.com/@_benaston/lesson-1a-the-history-of-javascript-8c1ce3bffb17#:~:text=JavaScript%20was%20created%20by%20Brendan,by%20Java%2C%20Scheme%20and%20Self.&text=Netscape%2C%20for%20a%20time%2C%20made,world%20and%20enjoyed%20market%20dominance.)

JavaScript wasn't a general-purpose programming language --- it is a scripting language for browser only.

What it means is essentially it was never meant to go out from the browser, the only purpose was only for you to add a behavior layer on your browser, like getting data from the server periodically

Using JavaScript, you are able to get your HTML element, and manipulate the styling, attributes of the element.

Although there are some alternative to manipulate your element with other languages (like Java Applet, etc), but the only officially marketed language is JavaScript.

Fun fact: JavaScript has nothing to do with Java, other than the name itself is similiar, nothing is 🤣.

<br>
<br>

## Hello World! <a name="hello-world"></a>

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
      let text = "World";
      console.log(text);
    </script>
  </body>
</html>
```

Open up your browser, look for inspection tool, right click on the browser, you should be seeing something like this:

<br>
<br>

## A short walkthrough for programming <a name="programming"></a>

Programming, or rather, Computer Science, it's all about data.

Data can be in any form: Number, word, a paragraph of words, etc.

## Data types <a name="datatypes"></a>

Let's recall this sentence again:

> Programming is all about how you process the data.

-- by me 🤣

Look around yourself, you are living in a world with full of data (not matrix haha).

My laptop battery level is a data, my bottle's water level is also a data.

There are a lot of different type of data, be it a number (water level like litres, etc), a word (your name), etc.

In JavaScript specifically, we have:

1. **String** - a series of words like "Rain Chai".
2. **Number** - Integer or decimal number like 1, 1.1, 2.2
3. **Boolean** - it can only be `true` or `false`, useful for cases like `let isLoggedIn = true;`
4. **Undefined** - it's a state for a variable, it stands for "this variable is not defined, does not have any data.", you can think of it like void, it's empty. You will only use this in a more advance case, don't worry if you don't understand it now.

You may refer to [w3schools JavaScript documentation](https://www.w3schools.com/js/js_datatypes.asp) for more information.

#### Variable

It's better to name our data, in our last example, we called it `apples`, it can be any other names that you think is most suited for your cases.

We called these names `variable`, it's just like `x`, `y` in mathematic, nothing fancy, I can call it `IamNotX` or `IamNotY`, doesn't matters.

For us to assign a data into a variable we can use the keywords `let`:

```javascript
let apples = 5;
```

Notice the syntax is:

\<keywords\> \<variable name\> = \<data\> ;

This is used for the creation of the variable the **Create** part of the CRUD operations.

There are some names you can't use for variable, because the browser reserved some names (or keywords) for the browser to understand what operation you want to do.

In our case, `let` is a keyword, it tells browser that whenever you see this keyword, it means I am creating a new variable.

We can't do something like:

```javascript
let let = 1;
```

but we can do:

```javascript
let letThisBecomeVariable = "Yay";
```

Do note that you **cannot** have spaces in between for your variables, below are a few examples that is **invalid** for naming the variable:

1. Spaces

   `let this is the apple = 5;`

2. Number as the first character

   `let 5apples = 5;`

3. Symbols other than `_` and `$` as the first character

   `let @thisIsVariable = 5;`

[Here are a list of keywords in JavaScript](https://www.w3schools.com/js/js_reserved.asp), if you have some free time, do take a look into each of them.

#### Operators

Just like in math, we can have `+`, `-`, `×`, and `÷`, we have it in programming as well:

- `+` is `+` in JavaScript
- `-` is `-` in JavaScript
- `*` is `×` in JavaScript
- `/` is `÷` in JavaScript

`=` in JavaScript stands for assignment, not the equal in mathematic, `let x = 1;` in this case is assigning `1` into `x`

We had wrote an example of Update in CRUD in our last example:

```javascript
apples = apples - 1;
```

In programming, we always have \<variable\> = \<value\>, so whatever on the right side will always get assign into the left side variable.

A more detail breakdown is as below:

1. Current state of `apples` is 5
2. Right side: `apples - 1` is like saying `5 - 1`, hence it is 4 on the right side
3. Left side: `apples`, so the value (4) on the right side will get assign into variable `apples` again
4. Now, `apples` become 4

There are few more operators in JavaScript:

- `**` is exponentiation in JavaScript, like `2**3` will return you `8` ( 2 to the power of 3 )
- `++` a shorthand for increment, like `apples++` will have the same effect as `apples = apples + 1`
- `--` a shorthand for decrement, like `apples--` will have the same effect as `apples = apples - 1`

Using all the shorthand, we can achieve the same effect with lesser code:

```html
<html>
    <head>
        <title>My first website with JavaScript!</title>
    </head>
    <body>
        <script>
            // create
            let apples = 5;

            // update, decrement 1
            apples --;

            // read, print it out in our inspect tool
            console.log(apples);
        </script>
    <body>
</html>
```

Do feel free to play around with other operators! [Here is a list of operators](https://www.w3schools.com/js/js_operators.asp)

<br>
<br>

## Conditional statement <a name="conditional"></a>

Say we set up a scenario:

```text
Nick has 5 apples, he wanted to give one of them to his friend,
but his friend can choose to accept it or not, if he accepted,
then Nick's apples amount will decrease 1,
else, Nick's apples amount remain the same.
```

We can implement the above logic by using another keywords: `if-else`

```javascript
let apples = 5;
let friendAccept = true;

if (friendAccept == true) {
  apples--;
} else {
  // do nothing
}
console.log(apples);
```

Output:

`4`

Now let's try to let the friend refuse to accept the apple:

```javascript
let apples = 5;
let friendAccept = false;

if (friendAccept == true) {
  apples--;
} else {
  // do nothing
}
console.log(apples);
```

Output:

`5`

### Breakdown

1. We have a variable called `friendAccept`, which is a boolean variable ( can only stored true or false).

   `if` statement's syntax is as follow

   `if(<condition>) { <operation> }`

   if whatever inside the bracket, the (\<condition\>) is true, then execute whatever operation is in the curly braces.

2. We then write out a `if` statement that, if `friendAccept` is equal to `true`, then execute the operation.

   the `==` is a logical operator, different with `=`, `==` stands for **equal**, `=` is assignment.

   There are a few other logical operators, like:

   - `!=` is **not equal**: `apples != 1` will return true, because apples is **not equal** to 1, but is equal to 5
   - `&&` is **and**: `apples == 5 && friendAccept` this is saying "if apples is equal to 5 and friendAccept is true, then return true"
   - `||` is **or**: `apples == 5 || friendAccept` this is saying "if apples is equal to 5 or friendAccept is equal to true, then return true"

   you may check it out [here](https://www.w3schools.com/js/js_comparisons.asp) for more kinds of operators

   If you don't understand the use cases yet, don't be worried, we will be using those a lot in the future and you will get yourself be more familiar with it.

3. The `friendAccept` is `true`, hence the if block is executed, it output `4`

4. We then change the `friendAccept` into `false`, we refresh the page again and in this case it output `5`, because `friendAccept` is **not equal** to `true`.

I do strongly suggest you to head on [w3schools exercises](https://www.w3schools.com/js/js_if_else.asp) to practice a few times on how to use this `if-else` statement, as it's one of the building blocks for all kind of programs.

<br>
<br>

## Function <a name="function"></a>

Function is very simple, given 1 input, give out 1 output,

In all the examples above, we keep writing out `apples -= 1`, this operation is saying "decrease apple's amount by 1", we can write out a function to replace the operation:

Let's try to declare a function.

```javascript
let apples = 5;

function minusOne(x) {
  let output = x - 1;
  return output;
}

console.log(minusOne(apples)); // -> output: 4
```

Something to note here:

return: the keyword for "output this data"

We can have more fancy stuff in function, say if I want to `console.log` everytime when the apple amount decreased, we can do so:

```javascript
let apples = 5;

function minusOne(x) {
  console.log("Apples decrease by 1!");
  let output = x - 1;
  return output;
}
```

Doing so, we can inject additional logic in the function.

Let's try to use what we had learned earlier: while loop together

```javascript
let apples = 5;

while (apples >= 0) {
  apples = minusOne(apples);
}

function minusOne(x) {
  console.log("Apples decrease by 1!");
  let output = x - 1;
  return output;
}
```

In the example above, the output of `minusOne` will get assign to apples again.

1. when apples = 5

   while loop condition is `true` (5 is more or equal to 0), hence, execute the logic.

   pass in the variable apples (which is 5) to `minusOne` function, the `minusOne` function will process the data, and output another data (which is simply, minus 1)

   We store the output data of `minusOne` back to `apples` again.

   Now, apples = 4

   Continue to check if while loop is true

2. when apples = 4

   while loop condition is `true` (4 is more or equal to 0), hence, execute the logic.

   pass in the variable apples (which is 4) to `minusOne` function, the `minusOne` function will process the data, and output another data (which is simply, minus 1)

   We store the output data of `minusOne` back to `apples` again.

   Continue to check if while loop is true

3. ...

4. when apples = -1

   while loop no longer `true` (-1 is not more or equal to 0)

   Loop finish, function no longer get called.

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

Source: [https://www.hackerrank.com/challenges/staircase/problem](https://www.hackerrank.com/challenges/staircase/problem)

<br>
<br>

## Conclusion <a name="conclusion"></a>

You had completed a simple JavaScript walkthrough, there are tons of stuff that I didn't include.

[https://www.freecodecamp.org/](https://www.freecodecamp.org/) offers a great hands-on and practice for you to learn more.

[> Redirect to DOM Workshop](/dom)

[> Go to top](/js)
