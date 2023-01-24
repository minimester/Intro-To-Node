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