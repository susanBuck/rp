# Lab 6: JavaScript Conditionals

## Goals
Practice...
+ More JS input/output
+ Conditionals
+ Error checking




## Set up
From the CS110 `Downloads` folder, download the `lab06` folder and open it in your code editor.




## Warmup
+ calculateLifeStatus
+ numberRounder




## Where to put your JS code

In this lab, and this week's homework, we're giving you a HTML file with some buttons that are programmed to trigger some functions in the JS file:

```html
<button type="button" onClick="sayHello()">Say hello...</button>
````

We're using **inline** JavaScript here to call the function `sayHello()`. Inline JS is not something you'll want to use regularly, but it gets the job done easily for these simple examples. We'll cover better ways of connecting buttons to functions later in the semester.

<br>
Fill out the `sayHello()` function in `lab06.js` so that it displays an alert with this text:

```txt
Welcome to the Coffee Consumption Calculator. We're here to help you gauge your coffee habit.
```

<Br>
Then test (i.e. click) the *Say Hello* button and make sure it displays that alert.

<img src='http://cs110.wellesley.edu/labs/lab06/images/say-hello-alert@2x.png' style='width:488px'>

<br>
The functions we set up for you in this lab (and in this week's homework) are **custom functions**, i.e. functions you create, not functions already built into JavaScript (like `parseInt()`). We'll discuss custom functions more later in the semester, but for now all you need know is that the code for a button goes in its corresponding function.


## Summary
Your goal in this lab is to ask the user how much they spend on coffee and how many cups of coffee they purchase per week. Given this information, you will calculate how much money they spend on coffee per week and per month.

*A working demo will be shown during lab.*

## Execute

### Get data
When the user clicks the **Calculate...** button, they should be prompted for two values:

Value 1:
> On average, how much does your favorite cup of coffee cost?

Value 2:
> On average, how many cups of coffee do you purchase per week?

### Run calculation
Using the data you collect from these prompts, calculate:

+ How much the user spends on coffee **per week**.
+ How much the user spends on coffee **per month** (assume 4 weeks per month).

### Output the results to the Console
Output both results to the Console, so it looks exactly like this, assuming the user entered a **cost of 2.50** and **4 cups per week**:

<img src='http://cs110.wellesley.edu/labs/lab06/images/first-output-to-console@2x.png' style='width:493px'>

### Format the results
If your user enters an excessive amount of decimal points, for example `2.9999` for cost and `1.9999` for cups per week, your results will also include excessive decimal points:

```txt
Total per week: $5.999500009999999
Total per month: $23.998000039999997
```

<br>
To fix this, you can use JavaScript's [`.toFixed()` method](http://www.w3schools.com/jsref/jsref_tofixed.asp) to restrict how many decimal points are used.

This method takes a single parameter to indicate *how many* decimal points you want.

Example:
```js
total = 4.99999;
total = total.toFixed(2);
console.log(total); // Outputs "5.00"
```

<br>
Once utilizing `.toFixed(2)` in your code, if you enter `2.9999` for cost, and `1.9999`, the output should now look like this:

<img src='http://cs110.wellesley.edu/labs/lab06/images/output-to-console-after-fixing-decimals@2x.png' style='width:493px'>


### Pick an appropriate message

Based on how much the user spends on coffee **per week**, include a message to your user as part of your results. The message should correspond to the volume of their coffee consumption:

+ Less than $10 a week:
    + `That seems like a reasonable amount; enjoy!`
+ $10 or more, but less than $30:
    + `Ok, that's a little pricey, but still not too bad.`
+ $30 or more, but less than $50:
    + `Do you have any money leftover for food?`
+ $50 or more:
    + `You'd better quit the habit before you go broke.`

Hint: You'll need a **cascading if statement**. Here's an example of a cascading if statement taken from lecture:

```js
if (grade >= 90) {
  letterGrade = "A";
} else if (grade >= 80) {
  letterGrade = "B";
} else if (grade >= 70) {
  letterGrade = "C";
} else if (grade >= 60) {
  letterGrade = "D";
} else {
  letterGrade = "F";
}
```

Here's what it should look like after you implement the above if you drink 100 cups of coffee a week at 2.75 per cup:

<img src='http://cs110.wellesley.edu/labs/lab06/images/output-to-console-after-adding-message@2x.png' style='width:493px'>


## Bonus - Write results to the page

If you look at the HTML file, you'll see there's an empty div where you can write results:

```html
<div id='coffee_results'></div>
```

*In addition to* outputting your results to the console, also output your results to this div.

Here's an example of how you'd write the word `Hello` to that div:

```js
document.querySelector('#coffee_results').innerHTML = 'Hello';
```

If you wanted to add multiple lines to the div, you could use the `+=` operator to *append* new content to any existing content:

```js
document.querySelector('#coffee_results').innerHTML = 'Hello<br>';
document.querySelector('#coffee_results').innerHTML += 'World,<br>';
document.querySelector('#coffee_results').innerHTML += 'It is nice to meet you.';
```




## Bonus - Error checking

In an ideal world, users would always enter the kind of data we're expecting.

For example, if we ask *How many cups of coffee do you drink?* you'd expect a simple, positive number right?

Well, you'd be amazed by the kind of wacky things users will enter when filling in data on your web applications.

Here are a list ways a user might throw off your simple prompt with unexpected answers:

+ `1 cups` They include text
+ `1.9999` They include extra decimals
+ `$1.00` They include a number sign
+ `-5` They enter a negative number
+ `asdjfka` They enter jibberish
+ ` ` They don't enter anything at all

<Br>
To accommodate these edge cases, you need to follow a practice called **Error checking** in which you check the data the user is entering to make sure it's something your application can work with, and if it's not, handle accordingly...

Error checking is often done with conditionals. Here's a &ldquo;pseudo-code&rdquo; example of what the conditional might look like:

```txt
if(the data is not what we need) {
    return some error message....
}
```

<br>
When expecting simple positive number (like in the case of cost) you can use the following If condition:

```
var cost = prompt('On average, how much does your favorite cup of coffee cost?',2.75);
if(cost == '' || cost <= 0 || isNaN(cost)) {
    alert('Please enter a valid positive number for cost.');
    return; // This return statement will prevent any other code from executing after this point
}
```

In plain English, this is what the above If expression is testing for:

> &ldquo;If cost is blank, **or** cost is negative **or** cost is &lsquo;not a number&rsquo;&rdquo;

If *any* of those conditions are met, the user will see an alert with a error message, and any subsequent code in the function will not execute (because of the `return` statement).

There are two new concepts we used here to make this work:

1. The JavaScript [isNaN](http://www.w3schools.com/jsref/jsref_isnan.asp) function.
2. The `return` statement.

Update your code so that after both prompts, you have an if condition like the one used above.

Then, test your calculator by entering letters, negative numbers, nothing at all, etc.
