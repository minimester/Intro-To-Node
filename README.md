# I DO

## Intro to Node

We'll be using **[Node.js](https://nodejs.dev/en/)**  for the full length of Minimester to write and execute our JavaScript code.

First, we need to know how we will run our JavaScript files.

1. Open up a terminal/command prompt on your computer.

    - If you're using VSCode, you can open a new terminal using your menu options at the top of your left screen. At the top left menu bar, select `Terminal` then `New Terminal` in the dropdown. This will open a command prompt/terminal in the same folder where we are at now.
    - If NOT using VSCode, we can open a terminal/command prompt using our folders.
        - macOS: Go to your folder where you downloaded the repository to. Right click on the repository folder. A menu will popup. Select `New Terminal at Folder`
        - Windows: Go to your folder where you downloaded the repository to. Right click on the repository folder. A menu will popup. Select `Open in Terminal`


2. Now our terminal/command prompt is pointing to the folder of our repository! What we want to do from here is create a new JavaScript file.

    - Using our terminal/command prompt, we can create a new file using commands that are appropriate for your machine:
        - macOS: In your terminal, write `touch app.js` and press Enter.
        - Windows: In your command prompt, write `echo > app.js` and press Enter.

3. We now created a JavaScript file called `app.js`. We can now see this in our browser explorer in our file editor (ex: VSCode). Open the `app.js` file by clicking on it in your browser explorer

4. We can now start writing our JavaScript code!. In your editor, write the following:

    `console.log("Hello World")`

5. Great! Now we have something to execute! We can now use Node to run our JavaScript code we just wrote! Going back to your terminal/command prompt, write the following command and press Enter:

    ```js
    node app.js
    ```

We should now see an output in your terminal/command prompt that says `Hello World`. If you do then congratulations!

You are ready to rock and roll with me! Let's get started!

## Data Types

### Primitive DataTypes

Since JavaScript is largely about storing data and manipulating it, we'll be spending time going over the different primitive DataTypes that exist in JavaScript and a few things that we can do with them. The term primitive DataTypes refers to data that is immutable and therefore cannot be changed. There are also non-primitive DataTypes that we will be covering tomorrow.

In JavaScript, the primitive DataTypes include:

- **Number**: A space in memory that stores any number, integer or floating point (decimals)
  - _Values_: `4`, `16.25`, `-3`, `NaN`, etc.
- **String**: A space in memory that stores any text, always surrounded by quotes
  - _Values_: `"Amanda"`, `'Cow'`, `"I'm a full sentence. In fact I'm two!"`, etc.
- **Undefined**: A space in memory that has nothing in it _yet_
  - _Only Value_: `undefined`
- **Null**: A space in memory that has been _explicitly_ set to be empty
  - _Only Value_: `null`
- **Boolean**: whether something is True or False
  - _Only Values_: `true`, `false`

We'll be covering these DataTypes and exploring some of the things we can do with them. Let's begin with Numbers!

## Numbers

All numbers, integers or floating-point decimals are encompassed under JavaScript's **[Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** datatype. When we have a number, JavaScript has provided us a useful method of checking whether or not it is an integer. Type each of the following lines into the console and look at the responses:

```js
Number.isInteger(6);
// Should be true
Number.isInteger(2.167);
// Should be false
```

Before we continue with our numbers, I want to talk about **comments**.

### Comments

Let's also take a look at the lines that start with `//`. Notice that those lines are a dark-green color. These are called **Comments**. A comment is a line of code that we want to be ignored at run time. It's not code that needs to execute; it's a comment for a developer to see.

```js
Number.isInteger(6);
// Should be true
```

In JavaScript, we have two ways to write comments:

```js
// This 'comments out' all text on the remainder of this line

2 + 2; // This comment can also come at the end of a line of executing code
```

## Arithmetic Operators

Returning to the topic of Numbers, we can perform all of our basic Arithmetic Operations in JavaScript. Addition, Subtraction, Multiplication, and Division all work as expected, including Parentheses! Order of operations follows traditional **PEMDAS**.

The only thing that sometimes trips people up is that `*` is the symbol for multiplication.

```js
12 + 97;
// 109

54 - 16;
// 38

212 * 57;
// 12084

461 / 4;
// 115.25

(1 + (17 / 2) * 3 - 18 / 4) / (15 + 2 * 4);
// 0.9565217391304348
```

### Modulo

JavaScript also has a version of an operation called **Modulo**, which will return the remainder of a division. For example, `9/4`, 4 goes into 9 twice. The remainder is 1. We can do that with Modulo:

```js
9 % 4;
// 1
```

## Variables

One of the most important features of JavaScript is the ability to save values to **variables** in memory and access them later. Let's say, for example, that we want to track the number of times a user has clicked on our page, because after the 1,000th click, they'll get a prize! Let's create a variable called `numOfClicks` and establish that it equals `1`. 

**NOTE**: variables are not specific to just Numbers

Write the following in your console:

```js
let numOfClicks = 1;
```

The `let` and `const` keywords are going to be our keywords of choice for creating variables. You will also commonly see `var` being used, as it was originally the only variable keyword, but `let` and `const` are widely considered the superior choice for a variety of relatively advanced reasons.

Now, let's reassign our variable `numOfClicks` to be 2:

```js
numOfClicks = 2;
```

Notice that I don't need the `let` keyword here. Because we've already instantiated our variable, I don't need `let` to reinstantiate it. I can just set it equal to another value! Now let's say that they've clicked 8 more times and we need to add that. Instead of manually setting our variable to be 10, we can set it to increase by 8:

```js
numOfClicks = numOfClicks + 8;
```

Alright, so the new value of `numOfClicks` is the current value + 8. That makes sense! But this [syntax](https://www.techopedia.com/definition/3959/syntax) feels kind of wordy. Fortunately, there's a shorthand for this, which is:

```js
numOfClicks += 8;
// Identical in function to numOfClicks = numOfClicks + 8;
```

## NaN

There is one last possible value for the Number datatype that we have to discuss: **`NaN`**, or Not a Number.

JavaScript is able to convert data points of one datatype into another datatype. For example, 6 and "6" are not the same datatype.

6 is the number 6.

"6", on the other hand, is a String of alphanumeric characters, where the only character happens to be the character we use to represent the number 6.

If needed, JavaScript can convert "6" into the number 6 because that's pretty intuitive. On the other hand, if we ask it to convert "cat" into a number, it will give us **`NaN`** because there's not a clear way it should numericize the word "cat".

Generally, but not always, getting `NaN` is because of some error. JavaScript was trying to give you a number, but couldn't figure out how. The datatype of `NaN` is still **Number** because that's the type JavaScript was trying to convert the value into.

Importantly, any number modified by `NaN` will ultimately become `NaN` as well:

```js
2 + NaN;
// NaN;

12 / NaN;
// NaN;
```

## Strings

We have another DataType called **[Strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)**, which are sequences of alphanumeric characters. Broadly speaking, we're talking about words and sentences, although they can also be sequences of seemingly incoherent characters strung together like "wa5pl7r". Note that strings are always surrounded by quotes to differentiate them from variable names:

Note that Strings can be written using several different types of quotes:

- 'Single Quotes'
- "Double Quotes"
- \`Backticks`

## String Concatenation

One of the common things that we will do with strings is called **Concatenation**, which is where we combine multiple strings into one string:

```js
'Say hello to ' + 'Davy Jones!';
// Say hello to Davy Jones!"
```

Commonly, we'll do this with strings saved to variables:

```js
let firstName = 'Barbara';
let lastName = 'Streisand';
let fullName = firstName + lastName;

fullName;
// "BarbaraStreisand"
```

Uh oh. That `fullName` looks slightly off. What do we need to do to fix it?

<details>
  <summary>Solution</summary>

> ```js
> fullName = firstName + ' ' + lastName;
> // "Barbara Streisand"
> ```

</details>

## Type Conversion

You may have noticed that the `+` sign is doing some pretty heavy lifting right now. With the `Number` datatype, it adds numbers together. With the `String` datatype, it concatenates strings. But what happens with a `String` + a `Number`?

```js
ageOfLuke;
// 15

fullName;
// "Barbara Streisand"

fullName + ageOfLuke;
// "Barbara Streisand15"

ageOfLuke + fullName;
// "15Barbara Streisand"
```

When an operation is run on 2 different data types, JavaScript converts the type of one data point into the type of the other. In this case, our `Number` is turned into a `String` (because all JS has to do is slap quotes around the `Number`). Thus we end up with 2 Strings being concatenated.

We can also force conversion from one type to another, though. For example, we can convert a `String` into a `Number` with either of the following 2 syntaxes:

```js
Number('12');
// 12

//OR

+'12';
// 12
```

## `undefined` and `null`

Let's take a look at two of our other Primitive DataTypes, which are fairly similar but have a critical difference.

**[Undefined](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Undefined)** and **[Null](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Null)** are both data types that represent emptiness or the lack of a value. The key difference is in how that emptiness came about.

Take the following code snippet for example:

```js
let meaningOfLife;

meaningOfLife;
// undefined
```

`meaningOfLife` is `undefined` because we never actually assigned a value to that variable. It is currently `undefined`, but once we assigned a value to it, it will be a different datatype:

```js
meaningOfLife = 42;
// 42
```

Many operations in JavaScript do not have **implicit return**, which means they don't have an output unless we specify one. Whenever one of those operations occurs, `undefined` will be output.

**Null**, on the other hand, is intended to be used for values that have had a value at some point and have been intentionally stripped of any value:

```js
let accountBalance = 1000;
accountBalance = null;
```

When manually setting a value to be empty, best practice is to set it to `null`, not to `undefined`. Leave `undefined` for when JavaScript automatically assigns it.

## Typeof

There's a useful method of JavaScript called `typeof` that allows us to check the type of a variable. Let's test it out on the following:

```js
let someNumber = 3;
let someString = 'cow';
let someUndefined;

typeof someNumber;
// "number"
typeof someString;
// "string"
typeof someUndefined;
// "undefined"
```

## Boolean

Our last Primitive DataType that we're going to cover today is called **Boolean**, which is a set of two values that describe a status of `true` or `false`. Some situations where these show up include when we manually set a `Boolean` value to a variable or when a `Boolean` is outputted as the result of an expression:

```js
let isLoggedIn = true;

5 > 15;
// false
```

### Truthiness and Falsiness

Every value in JavaScript is considered either **Truthy** or **Falsy**, which describes whether it becomes `true` or `false` when converted to a `Boolean`. It's important that you learn what is truthy and what is falsy, but fortunately you only have to memorize a small amount of information. This is because **there are only 6 falsy values**:

1. `false`
2. `0`
3. `''`, `""`, ` `` ` (empty strings)
4. `null`
5. `undefined`
6. `NaN`

**All other values are considered truthy** and therefore evaluate to `true`.

One common area where you'll see truthiness and falsiness come into play is in something called a **Conditional Statement**. We'll learn more about Conditionals in a dedicated lesson later in the course, but the general idea (in pseudocode) is:

```
if (isLoggedIn evaluates to true){
  log "you're logged in" to the console
}
```

## Equals Comparisons

A common mistake that early Software Engineers make is misusing the `=` sign when trying to compare values. Take a look at the following:

```js
24 = 25;
// Uncaught SyntaxError: Invalid left-hand side in assignment
```

A single `=` sign is used for assigning a value to a variable, _not_ for comparing if they are equal to each other. If we want to compare values to see if they are equal, we'll use `===`, or three equals signs:

```js
3 === 4;
// false

4 === 4;
// true

let leavesOnClover = 3;
leavesOnClover === 4;
// false

leavesOnClover === 3;
// true
```

### Strict Comparison vs Abstract Comparison

Let's take a look at the following snippets:

```js
27 === 27;
// true

27 === '27';
// false
```

Our first example is `true` because the `Number` `27` is equal to the `Number` `27`. Our second example, however, is `false` because the `Number` `27` **does not** equal the String `'27'`. This is known as a **Strict Comparison**. It compares both data type and value

We can also perform an **Abstract Comparison** by using two equals signs, `==`. Take a look at the following:

```js
27 == '27';
// true

27 == '29';
// false

27 == 'twenty-seven';
// false
```

Despite the fact that one of these values is a `Number` and the other is a `String`, our first Abstract Comparison returns `true` because they are "abstractly" the same. If the `String` on the left is converted into a `Number`, they would be equal! The next two comparisons, however, are categorically `false`. Even if we convert `'29'` to `29`, it still won't equal `27`.

Under the hood, what happens here is actually **Type Conversion**, where one or more value is converted until the two are of the same type. Then a Strict Comparison is run:

```js
27 == '27';

// actually runs...
27 === Number('27');
```

At first it might seem much easier to use the `==` operator instead of the `===` operator. However, the `==` operator in JavaScript can be tricky and often produces some unexpected results. Because of this, it is almost universally preferred to using `===` instead of `==`.

### Going Out with a Bang

In JavaScript, the `!` symbol is called **Bang**! In context of Truthiness, Bang will reverse (or negate) the truthiness of a given value. In other words, `!` is the logical "not" operator. For example:

```js
!true;
// false

!0;
// true

!!!!true;
// true
```

We can also combine Bang with Strict and Abstraction Comparisons. It just takes the place of the first `=` sign. For a Strict example:

```js
3 !== 4;
// true
```

`3` does not strictly equal `4`, so this is `true`! For an Abstract example:

```js
3 != '3';
// false
```

This asserts that `3` does not abstractly equal `'3'`, but that assertion is actually `false`.

## Conditionals

### Comparators
The following logic gates are helpful when working with conditionals and creating boolean expressions.

### AND

With the `&&` logical operator, if at least one condition is `false` out of all the conditions connected by and(s), everything connected is treated as a `false` return. If all of those conditions are `true` that use the and(s), everything connected is treated as a `true` return.

For example, `true && false` would evaluate to `false`.

### OR

With the `||` logical operator, if at least one condition is `true` within all the conditions connected by or(s), everything connected is treated as a `true` return. If none of those conditions are `true` that use or(s), everything connected is treated as a `false` return.

For example, `true || false` would evaluate to `true`

### NOT

The `!` by itself is referred to as the not operator or "bang operator". It can be used as a shorthand way of checking what a value is NOT in your coding logic.

For example, `!true` would evaluate to `false`

### More Logic Gate Info

For more info on common logic gates and the truth tables associated with them, check out this [tutorial](https://www.electronics-tutorials.ws/boolean/bool_7.html)

## Conditionals

**Conditionals** can be used to determine if code should execute or not based on certain... well, conditions. We can also use these to provide multiple possibilities for what should happen!

### The `if` Statement

Let's start with a simple **`if`** statement! We'll begin with some pseudocode:

```text
if your final exam grade is 80 or above
    you pass the class
```

If we wanted to turn this into an `if` statement, it would look like this:

```js
let examGrade = 90;

if (examGrade >= 80) {
    console.log("You passed the class!");
}
```

We're giving the exam grade of a user. We then use the `if` keyword and provide a condition in parentheses. Here, if the `grade` is `80` or over, that condition evaluates to truthy and we tell the user that they passed the class.

However, what happens if you put in a value below 80? Well, currently nothing. Sometimes that's completely fine. Often, however, we'll want another block that executes if the condition is `false`. For example, if the student did not get a grade of 80 or above, then we want to give them a different message saying they did not pass the class unfortunately. This is where we include an **`else`** statement.

### The `else` statement

```js
let examGrade = 90;

if (examGrade >= 80) {
    console.log("You passed the class!");
} else {
    console.log("You did not pass the class")
}
```

In this case, we've created two possible outcomes. If the condition evaluates to `true`, we run our `if` block. If it evaluates to `false`, we run our `else` block.

But what if there are more than two possible outcomes? Well, in addition to `if` and `else`, we also have `else if`:

### The `else if` statement

```js
let examGrade = 90;
let classGrade = 80;

if (examGrade >= 80) {
    console.log("You passed the class!");
} else if (classGrade === 100) {
    console.log("You finished off the year with a perfect class grade. You passed the class!")
} else {
    console.log("You did not pass the class")
}
```

Now, we have three possible circumstances and outcomes. But here's a question for you: what happens if a user received a final exam grade of 90 **and** a class grade of 100?

Because our conditions are evaluated in order, if a user received a final exam grade of 90 and a class grade of 100, they'll get the response from the first block. That's because `examGrade >= 80` evaluates to `true` and the conditional statement stops evaluating the conditions that come after.

There's one last thing we want to discuss with `if`, `else if`, `else` statements. You can only have **one** `if` and **one** `else` in a given conditional, but you can have **multiple** `else if` statements. For example:

```js
let examGrade = 90;
let classGrade = 80;
let extraCredit = 'yes';

if (examGrade >= 80) {
    console.log("You passed the class!");
} else if (classGrade === 100) {
    console.log("You finished off the year with a perfect class grade. You passed the class!")
} else if (extraCredit === 'yes') {
    console.log("You passed the class by doing some extra credit.")
} else {
    console.log("You did not pass the class")
}
```

Again, the order of your `else if` statements matters here.

### The `switch` Statement

A `switch` statement is another way to write conditionals. that can provide multiple different outcomes. Switch statement syntax is a little different from `if` `else` statements. Because of the nature of `switch` statements, they have a few more limitations than `if` statements, but they're very popular when applicable due to their readability.

The way that a `switch` statement works is that you provide a variable or expression and then provide a variety of different possible values that the above condition could possibly be equal to. You'll also provide a `default` statement, in case the  condition doesn't equal to any of the provided possibilities described above. It looks roughly like this:

```js
switch (expression) {
    case possibility1:
        outcome
    case possibility2:
        outcome
    default:
        generic outcome
}
```

Let's look at an example wherein a user is deciding what to eat for lunch:

```js
let lunch = "sandwich";
switch (lunch) {
    case "salad":
        console.log("Look at you! You're so healthy");
        break;
    case "cheeseburger":
        console.log("You deserve this! You've been working so hard!");
        break;
    case "sandwich":
        console.log("You're being so frugal! Financial responsibility is important at this age!");
        break;
    default:
        console.log("Look at you, you rebel! No one tells you what to eat for lunch!");
        break;
}
```

One thing that's important to note here is that each *`case`* **must** end with the keyword `break` or the cases below will all execute until it reaches a `break`! 
<br/>

Switch statements are very useful if you want to evaluate a single variable or expression, however, if there are multiple values you want to consider (such as before when we cared about exam grade, class grade, and extra credit) a Switch statement will not be able to accomplish this. These cases are for a **single** value and not a range of values.

### Ternary Operators

There is one last type of conditional that we want to mention. This is something called a **Ternary Operator**. It consists of three parts: a condition, an affirmative option, and a negative option.

Ternary operators are very popular for boolean conditionals that can execute exactly two options: one if a condition is `true` and one if the condition is `false`. One reason for their tremendous popularity is that they are a conditional that exists on a single line! They are particularly popular for assigning a value to a variable conditionally.

In pseudocode, a ternary operator looks like this:

```text
variable = (condition) ? affirmative option : negative option;
```

We provide a condition, then put a question mark `(?)`, then put a value for if the condition is `true`, a colon `(:)`, then a value for if the condition is `false`, and we end it with semicolon `(;)`.

Let's look at an example:

```js
let age = 75;
let sentence = (age > 65) ? "You are eligible for the senior citizens discount!" : "Well, at least you're young!";
console.log(sentence);
```

If `age` is greater than `65`, the value of the `sentence` variable is set to `"You are eligible for the senior citizens discount!"`. If `age` is not greater than `65`, the value of the `sentence` variable is set to `"Well, at least you're young!"`.

## Loops

An iteration or loop is the repetition of a process. You can think of your current minimester summit as being an iteration of minimester. There have been iterations prior to your summit and there will continue to be iterations afterward. So if an iteration is a single repetition of something, an iterator is something that causes multiple iterations or repetitions.

For example, if you were ever a child, you probably repeated a wonderful phrase a multitude of times: "Are we there yet?".

### `while` Loop

A `while` loop is an iterator that will execute a block of code repeatedly as long as given condition is `true`.

```js
while (condition) {
  statement;
}
```

Let's look at some **pseudocode**, or simple english logic of what we will eventually code:
<br/>

```js
set counter to 1
while (counter is less than 6) {
    display the counter
    increment counter by 1
}
```

From the pseudocode, we defined our counter, gave our condition and included any logic we'd like to repeat in those curly braces. Specifically for the logic, we'll display the counter and increase our counter by 1 (increment).

```js
let counter = 1;
while (counter < 6) {
    console.log(counter);
    counter++;
}
console.log("Done counting!");
```

Let's compare this with the following, slightly different code. We're not incrementing `counter`. **DO NOT** paste this into your console. What's going to happen here?

```js
let counter = 1;
while (counter < 10) {
    console.log(counter);
}
```

<details>
<summary>Click here to reveal the answer</summary>

This code would cause an *infinite loop*. We're never changing the value of `number`, so that conditional will always be met and we'll continue our iterations infinitely. Every developer sometimes creates these by accident while working on something, but they're obviously bad for actual applications.

</details>

### `do...while` Loop

Another version of a `while` loop is a `do...while` loop.

```js
do {
    statement
} while (condition);
```

So what is the difference you ask?

A `do...while` loop will also execute a block of code repeatedly as long as given condition is `true`. However the main difference is `do...while` loop checks the condition after executing the block of code, resulting in the block of code within curly braces `{...}` executing at least once. Guaranteed.

Let's see this in a quick example;

```js
let count = 1;
do {
    console.log("Count is: ", count);
    count++;
} while (count > 10);  // Condition already evaluates to false.
```

Above example will run at least once, resulting in `Count is: 1` output.

### `for` Loop

While there are better suited application when we need to use a `while` loop, for counting we'd probably be better of with a **`for` loop**!

This syntax for `for` loop can be a little bit trickier than it is for `while` loop, so let's take a look at how our loop is structured in some pseudocode:

```txt
for (initialization; condition; final-expression) {
   statement(s);
}
```

For example:

```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

<details><summary>T-diagram</summary>
<table>
    <tr>
        <th>Iteration</th>
        <th>i</th>
        <th>i < 5</th>
        <th>Loop runs?</th>
    </tr>
    <tr>
        <td>1</td>
        <td>0</td>
        <td>true</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>2</td>
        <td>1</td>
        <td>true</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>3</td>
        <td>2</td>
        <td>true</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>4</td>
        <td>3</td>
        <td>true</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>5</td>
        <td>4</td>
        <td>true</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>6</td>
        <td>5</td>
        <td>false</td>
        <td>No</td>
    </tr>
</table>
</details>

<details><summary>What does it log in the console?</summary>
0 <br/>
1 <br/>
2 <br/>
3 <br/>
4 <br/>
</details>
<br/>

This is going to accomplish the same goal as our `while` loop that counted to 10, so let's start by looking at our `while` loop from before:

```js
let number = 1;
    
while (number < 10) {
    console.log(number);
    number++;
}
```

And we'll recreate this with a for loop:

```js
for (let number = 1; number < 10; number++) {
    console.log(number);
}
```

#### Nested `for` Loops

In addition to using `for` loops like we discussed above, it's possible to nest `for` loops inside of each other! Let's build some code that iterates two variables from 0 to 10 in sequantial order:

```js
for (let i = 0; i < 10; i++) {
    for (let j = 0; j < 10; j++) {
        console.log("i is:", i, "j is", j);
    }
}
```

We have one loop nested inside of another one. What happens here is that we start by looping through the outer loop where `i` is the iterator. The initial value for `i` is `0`. 

Then, the inner loop begins to execute. `j` begins at `0` and iterates up to its condition as we would expect. Meanwhile, `i` remains at `0` since the outer loop did not yet finish one iteration, so `i` has not incremented yet.

Once ALL the code within the inner loop finishes, then `i` can increment. In this case, the code within the outer loop is another loop. Therefore, the inner loop, or the `j` loop, must fully complete before `i` can increment.

With this style of nested loop, we are able to see ALL the possible pairings of `i` and `j`. This will come in handy when working with variables that represent grid like coordinates or matrices.


**For Loops vs While Loops**

<details><summary>Where would you use a 'for' loop versus a 'while' loop?</summary>

If you know exactly how many times you want a loop to run, use a `for` loop. Otherwise, use a `while` loop. A `while` loop sort of says "while X is true, execute this code repeatedly." A `for` loop, on the other hand, says "for X number of times, execute this code." So a `while` loop is good for more abstract conditions and a `for` loop is good if there's some way to calculate a predictable number of times to execute something.
</details>

## `break` and `continue`

You can further control your code flow within your loops with ***`break`*** and ***`continue`*** statements:

`break` jumps out of your current loop lifecycle and continues your code from outside of the current loop.

`continue` jumps out of your current loop *iteration* (just one time) and continues the loop at the *next iteration*.

***Break Example:***

``` js
for (i = 0; i < 10; i++) {
    if (i === 2) {
        break;  // when i is 2, this for loop is exited
    }
    
    console.log(i);  // we will only ever log 0 and 1
}
```

***Continue Example:***

``` js
for (i = 0; i < 10; i++) {
    if (i === 1) {
        continue;  // when i is 1, iteration is exited and next one begins, never logging 1
    }
  
    console.log(i);  // we will only ever log 0,2,3...9
}
```

## Functions

A function is a block of code that performs a specific and concise functionality. Functions are usually intended to be reused later in code after they are declared. In JavaScript you will typically see a *camelCase* naming convention with a leading verb for function names (**i.e** `addItems()` or `stopServer()`)

### Do's and Don'ts of Functions

- DO clearly name your functions
- DO have your functions achieve one thing with efficiency
- DON'T set out to have your functions do every thing in the world
- DON'T have your function do something that can be achieved in a line or two of code

### Named Functions

```js
firstFunction();  // Named functions can be invoked before declaration because of hoisting

function firstFunction() {  // function declaration
    console.log("Hello World");  // Functions don't have to return a value and if no `return` is specified it will be return undefined.
}
```

### Parameters and Arguments

You can setup *parameters* associated with your functions by enclosing them in `()` after function declaration. When you invoke/call a function you supply it with arguments that correspond with the parameters. The difference between parameters and arguments is largely semantic.

```js
function ourFunction(name) {  // function declaration with 1 parameter, name
    console.log(`Hi, ${name}!`);
}

ourFunction("Jane");  // function invocation with 1 argument passed in, "Jane"
```

More about how arguments are handled in JavaScript:

```js
function getFullName(firstName, lastName) {
    return `${firstName} ${lastName}`;
}

getFullName("Don", "Joe");  // return "Don Joe"
getFullName("Don", "Joe", "Shmoe");  // JS doesn't require right number or ANY parameters -- returns Don Joe
getFullName(1);  // js isn't typed -- returns 1 undefined
```

### Function Expressions

You are able to create functions as expressions as well:

```js
let sum = function addNumbers(num1, num2) {
    return num1 + num2;
}

sum(1, 2);
```

Function expressions can be anonymous by omitting the function name:

```js
let sum = function(num1, num2) {
    return num1 + num2;
}

sum(1, 2);
```

### `console.log()` vs. `return`

So far we have seen functions use both `console.log()` and `return` within them. What is the difference?

`console.log()` is a method that takes any number of arguments and then prints the values of the arguments in the console.

`return` is a statement you define within a function to *give back* a value and cease execution.

```js
function addTwoNumbers(num1, num2) {
    console.log("doing math.....");  // just log message, NOT what is being returned by function
    return num1 + num2;  // return value is sum of two arguments
}

const answer = addTwoNumbers(3, 4);  // set variable sum to return value of function. Value is 7
console.log(`Answer: ${answer}`); //outputs 'Answer: 7'
```

### Arrow Functions

ES6 introduced arrow function syntax as yet another way to declare functions. Arrow functions are slightly more concise and succinct than the previous ways shown.

When used on one line, everything after the `=>` is the return statement:

```js
let getFullName = (firstName, lastName) => `${firstName} ${lastName}`;
```

You can use statement blocks as well with arrow functions for multiple lines:

```js
let getFullName = (firstName, lastName) => {
    console.log("log me first");
    return `${firstName} ${lastName}`;  // explicitly returning a value here
};
```

# We Do
## Problem
Oh no! Your personal bank's atm software has gone down all of a sudden! The app has gone down! The branches are closed! It's up to us to build a backup ATM application that can work while everything gets back up!

## What we need to do
We need to build a script that can `deposit`, `withdraw`, `display`, and `transfer` money. I have two bank accounts: a `checkings` account and `savings` account. I should be able to:

- `deposit` money into either my checkings account or savings account
- `withdraw` money from either my checkings account or savings account
- `transfer` money from one bank account to the other
- `display` the amount of money I have from either my checkings or savings account

## Requirements
In order to do this, we should include the following:

- A function `deposit` that deposits money from a selected account. takes in two arguments:
    - A string `account` - indicates which account (checkings or savings) you want to deposit money into
    - A number `amount` - the amount of money we wish to deposit

- A function `withdraw` that withdraws money from a selected account. This function takes in two arguments:
    - A string `account` - indicates which account (checkings or savings) you want to withdraw money from
    - A number `amount` - the amount of money we wish to withdraw

- A function `transfer` that transfers money from one account to another. This function should remove money from one account and add money to the other. This function takes in three arguments:
    - A string `from` - indicates which account we are transferring money from
    - A string `to` - indicates which account we are transferring the money to
    - A number `amount` - the amount of money we wish to transfer

- A function `display` that displays the amount of money there is within the account. This function takes in one argument: 
    - A string `account` - indicates which account (checkings or savings) you want to display money from

- For `amount`, check if the value is a number. If not, display an error message: `amount is not a number`.
- For `account`, check if the value is a valid account. If not, display an error message: `account is not a valid account. Try again`

## Testing

Make sure to test our implementation after we are done with it.

### Scenario
Frank needs to do a variety of transactions on the ATM. He has the same bank as you! Frank has a total of `$500` in his `checkings` account and `$1,500` in his `savings` account. Using your script, help Frank with the following (in the exact order):

- Deposit `$300` into his `checkings` account
- Withdraw `$200` from his `savings` account
- Transfer `$600` from his `checkings` account to his `savings` account
- After doing all the above, display how much money he currently has in his `savings` account

Frank thanks you for helping him out. A week later and all the original bank's ATMs, branches, and mobile app are all back up and running. Frank has his banking app on his mobile device. Frank is lazy and doesn't want to go his local branch. He wants to make use of the check deposit feature on the mobile app. Frank has 6 `$100` checks he wishes to deposit into his `savings` account

Using your implementation, `deposit` Frank's 6 `$100` checks into his `savings` account. Do this in a `loop`. Afterwards, display how much money he has in his `savings` account after depositing his checks.

# You Do

# You Do

## Exercises

<details>
<summary>Exercise 1</summary>

It's SUMMERRRRR! You booked a flight to France for your vacation! You get to France and you try communicating with the sweet French folk. One small issue! You're in a neighborhood that uses military time (24 hour clock). Everyone gives you the time in military time. You're not used to it. You just have to have your time in AM/PM.

Write a function `convertTime` that takes a number `military` and returns the correct time in AM/PM. For this problem, assume no minutes are given. Just the hours. Your implementation should include the following:

- If `military` is a value NOT between 0 and 24, display an error: `Not a valid time`
- If `military` is NOT a number value, display an error: `Not a valid time`
- The function should include both `0` and `24`
- The converted time should be in the format showing `am/pm`. Ex: `2pm`, `10am`
- `console.log` the converted time

REMINDER: `0` and `24` represent the same time (midnight)

### Examples

| Input | Output | Explanation |
| -------- | ----- |  ----- | 
| `convertTime(1)` | `1am` | 1:00 is the same as 1am|
| `convertTime(18)` | `6pm` | 18:00 is the same as 6pm|
| `convertTime(24)` | `12am` | 0:00 and 24:00 both represent midnight |
| `convertTime(27)` | `Not a valid time` | Military time uses the 24 hour clock. Anything past 24 is not a valid time |
| `convertTime("five o'clock")` | `Not a valid time` | The given time is not a number|
</details>

<details>
<summary>Exercise 2</summary>

Write a function `oddsAndEvens` that takes a number variable `start` and finds the number of odd and even numbers from that number to 100. `start` should be a number from 1 and 100 (not including 1 or 100). Include the number `start` in your count. 
- If the given number is greater than 100, display an error message: `start is greater than 100`.
- If the given number is less than 1, display an error message: `start is less than 1`.
- If the given number is not a number, display an error message: `start is not a number`.
- `console.log` the number of even numbers from `start` to 100.
- `console.log` the number of odd numbers from `start` to 100.

### Examples

| Input | Output | Explanation |
| -------- | ----- |  ----- | 
| `oddsAndEvens(95)` | `evens = 2, odds = 3` | Starting from 95 there are 2 even numbers before reaching 100 (96, 98). There are 3 odd numbers (95, 97, 99)|
| `oddsAndEvens(0)` | `start is less than 1` | Start is not an acceptable value that falls between 1 and 100|
| `oddsAndEvens(112)` | `start is greater than 100` | Start is not an acceptable value that falls between 1 and 100|
| `oddsAndEvens("cat")` | `start is not a number` | Starting is not an acceptable value. It is not a number|
</details>

<details>
<summary>Exercise 3</summary>

You are a credit card holder of your bank's student rewards program. One of your favorite perks about this card is that you earn `3%` cash back on dining. You just found out that you are now part of Minimester and treat yourself to an unforgettable culinary experience at an award-winning restaurant! You enjoy your fancy meal and your bill comes to a total of `$42.35`. At such a great restaurant, you should be expecting to leave a tip for great service! We will not be including tax in this situation.

Write a script that calculates out how much cash back you earned after paying the bill with tip included.
Your script should include:

- A number variable called `bill` that holds original $42.35.
- A function called `calculateTip` that takes in a number as a parameter. The number represents a given tip percentage as a whole number. This function returns a number `tip`.
     - If the given tip is not a number, then display the error message: `tip was not a number` and stop the application
- Calculation finding the total (bill + tip) and finding the amount of cash back (3%) earned from the total.
- A `console.log` that displays the cash back amount your earned in dollar format. `Ex: $3.25` Don't worry about rounding

REMINDER: `3%` = `0.03`. Percentage as decimal = Whole number / 100;

| Input | Output | Final | Explanation |
| -------- | ----- | ----- | ----- | 
| `calculateTip(18)` | `7.623` | `Your cash back is $1.49919` | 18% of 42.35 is 7.623. (42.35 + 7.623) * 0.03 = 1.49919. (bill + tip) * (cash back percentage) = cash back |
| `calculateTip("car")` | `tip was not a number` | N/A | car is not a number value |

</details>