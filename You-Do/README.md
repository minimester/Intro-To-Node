# You Do

## Exercises

<details>
<summary>Exercise 1</summary>

It's SUMMERRRRR! You booked a flight to France for your vacation! You get to France and you try communicating with the sweet French folk. One small issue! You're in a neighborhood that uses military time (24 hour clock). Everyone gives you the time in military time. You're not used to it. You just have to have your time in AM/PM.

Write a function called `convertMilitary` that takes a number variable `military` and returns the correct time in AM/PM. For this problem, assume no minutes are given. Just the hours. Your implementation should include the following:

- If `military` is a value NOT between 0 and 24, display an error: `Not a valid time`
- If `military` is NOT a number value, display an error: `Not a valid time`
- Include both `0` and `24` as valid input values
- The converted time should be in the format showing `am/pm`. Ex: `2pm`, `10am`
- `console.log` the converted time

REMINDER: `0` and `24` represent the same time (midnight)

<details>
<summary>Stretch Goal</summary>

Rewrite `convertMilitary` so that it takes a string variable `military` and returns the correct time in AM/PM. This time both hours and minutes are included in the format `HH:MM`. E.g: `15:35`.
Your implementation should include the following:

- A way to split up the hour and minute from the string. Try to take a look at **[split](https://www.geeksforgeeks.org/javascript-string-prototype-split-function/)**
- Convert the `military` hour and minute from a string to a number
- If `military` hour is a value NOT between 0 and 24, display an error: `Not a valid time`
- If `military` minute is a value NOT between 00 and 60, display an error: `Not a valid time`
- If `military` hour or minute is NOT a number value, display an error: `Not a valid time`
- Include both `0` and `24` for the hour as valid values
- Include `00` for the minute as valid values
- The converted time should be in the format showing `am/pm`. Ex: `2:15pm`, `10:00am`
- `console.log` the converted time

You may use your previous `convertMilitary` solution to do this.

### Examples

| Input | Output | Explanation |
| -------- | ----- |  ----- | 
| `convertMilitary("1:00")` | `1:00am` | 1:00 is the same as 1:00am|
| `convertMilitary("18:00")` | `6:00pm` | 18:00 is the same as 6:00pm|
| `convertMilitary("15:32")` | `3:32pm` | 15:32 is the same as 3:32pm|
| `convertMilitary("24:00")` | `12:00am` | 0:00 and 24:00 both represent midnight |
| `convertMilitary("0:00")` | `12:00am` | 0:00 and 24:00 both represent midnight |
| `convertMilitary("0:41")` | `12:41am` | 0:41 is the same as 12:41am |
| `convertMilitary("27:12")` | `Not a valid time` | Military time uses the 24 hour clock. Anything past the 24th hour is not a valid time |
| `convertMilitary("21:78")` | `Not a valid time` | Anything past the 60th minute is not a valid time |
| `convertMilitary("five o'clock")` | `Not a valid time` | The given time is not a number|

</details>


### Examples

| Input | Output | Explanation |
| -------- | ----- |  ----- | 
| `convertMilitary(1)` | `1am` | 1:00 is the same as 1am|
| `convertMilitary(18)` | `6pm` | 18:00 is the same as 6pm|
| `convertMilitary(24)` | `12am` | 0:00 and 24:00 both represent midnight |
| `convertMilitary(0)` | `12am` | 0:00 and 24:00 both represent midnight |
| `convertMilitary(27)` | `Not a valid time` | Military time uses the 24 hour clock. Anything past 24 is not a valid time |
| `convertMilitary("five o'clock")` | `Not a valid time` | The given time is not a number|
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

You are a credit card holder of your bank's student rewards program. One of your favorite perks about this card is that you earn `3%` cash back on dining. There's a new dine in restaurant in town that you want to try! One evening you go to the restaurant, you enjoy your meal and then you receive your bill. You should be expecting to leave a tip for the great service! We will not be including tax in this situation.

Write a function called `calculateCashback()` that calculates out how much cash back you earned after paying the bill with tip included. This function takes in two arguments:

- A number `bill` - your restaurant bill
- A number `tip` - the tip percentage (as a whole number) you want to give


Your function should include:

- Calculation finding the total (`bill` + `tip`) and finding the amount of cash back (3%) earned from the total.
- A `console.log` that displays the cash back amount your earned in dollar format. `Ex: $3.25` Don't worry about rounding

NOTE:
- If the given `bill` is NOT a number, then display the error message: `bill was not a number`
- If the given `tip` is NOT a number, then display the error message: `tip was not a number`

<details>
<summary>Stretch Goal</summary>

Try rounding the **cash back** to 2 decimal places for cents. Take a look at **[toFixed()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed)** to see how you can do this.
</details>

| Input | Output | Explanation |
| -------- | ----- | ----- | 
| `calculateCashback(42.35, 18)` | `Your cash back is $1.49919` | 18% of 42.35 is 7.623. (42.35 + 7.623) * 0.03 = 1.49919. (bill + tip) * (cash back percentage) = cash back |
| `calculateCashback(39.41, "car")` | `tip was not a number` | car is not a number value |
| `calculateCashback("dog", 20)` | `bill was not a number` | dog is not a number value |

</details>