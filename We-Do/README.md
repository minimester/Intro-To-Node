# We Do Exercise

## Problem
Oh no! Your personal bank's atm software has gone down all of a sudden! The app has gone down! The branches are closed! It's up to us to build a backup ATM application that can work while everything gets back up!

## What we need to do
We need to build a script that can `deposit`, `withdraw` money as well as let us check our balances in our accounts. You have two bank accounts: a `checkings` account and `savings` account with an initial amount of money. You should be able to:

- `deposit` money into either my checkings account or savings account
- `withdraw` money from either my checkings account or savings account
- `checkBalances` the amount of money I have from either my checkings or savings account

## Requirements
In order to do this, we should include the following:

- A function `deposit` that returns the sum of the account with the deposited amount. This function takes in two arguments:
    - A number `account` - the account balance you want to deposit into
    - A number `amount` - the amount of money we wish to deposit

    NOTE:
    - Check if the value of `amount` is a number. If not, display an error message: `amount is not a number`.

<details>
<summary>See deposit guide</summary>

```js
function deposit(account, amount) {
    /*
        Check if `amount` is a valid number:
            
        IF `amount` is NOT a valid number:
            Display message: `amount is not a number`

        IF `amount` is a valid number:
            return sum of `account` + `amount`
    */
}
```
</details>

<details>
<summary>See deposit implementation</summary>

```js
function deposit(account, amount) {
    //Check if `amount` is a valid number:

    //If amount is NOT a valid number
    if (Number.isNaN(Number(amount))) {
        console.log('amount is not a number') //Display error message if invalid number
    } else {
        //Return money in account after depositing
        return account += amount;
    }
}
```
</details>

- A function `withdraw` that withdraws money from a selected account. This function takes in two arguments:

    - A number `account` - the account balance you want to withdraw money from
    - A number `amount` - the amount of money we wish to withdraw

    NOTE: 
    - This function should check if we have enough money in our account to withdraw. If not, then display a `You don't enough have money in your account` message and do NOT withdraw money.
    - Check if the value of `amount` is a number. If not, display an error message: `amount is not a number`.


<details>
<summary>See withdraw guide</summary>
        
```js
function withdraw(account, amount) {
    /*  
        Check if `amount` is NOT a valid number

        IF `amount` is NOT a valid number:
            Display message: `amount is not a number`
            Exit out of the function

        Check if `account` has the amount of money we want to withdraw
        
        IF YES:
            Subtract `amount` from `account`
        IF NO
            Display message: `You don't have enough money in your account`
    */
}
```
</details>

<details>
<summary>See withdraw implementation</summary>

```js
function withdraw(account, amount) {
    //Check if `amount` is NOT a valid number

    //If `amount` is NOT a valid number, display error message and exit out of function
    if (Number.isNaN(Number(amount))) {
        console.log('amount is not a number')
        return;
    }

    //Check if account has the amount of money we want to withdraw
    if ((account - amount) >= 0) {
        return account -= amount; //subtract `amount` from account
    } else {
        //If not enough amount of money in account
        console.log("You don't have enough money in your account"); //Display error message
    }
}
```
</details>


- A function `checkBalances` that displays the amount of money there is within your checkings and savings account. This function doesn't take any arguments. 

<details>
<summary>See checkBalances guide</summary>
     
```js
function checkBalances() {
    /*
        Display amount of money in savings account
        Display amount of money in checkings account
    */
}
```
</details>

<details>
<summary>See checkBalances implementation</summary>

```js
function checkBalances() {
    //Display amount of money in savings account
    console.log(`You have $${savings} in your savings account.`);
    //Display amount of money in checkings account
    console.log(`You have $${checkings} in your checkings account.`);
}

```

</details>

## Testing

Make sure to test our solution after we are done building it.

### Scenario
Frank needs to do a variety of transactions on the ATM. He has the same bank as you! Frank has a total of `$500` in his `checkings` account and `$1,500` in his `savings` account. Using your script, help Frank with the following (in the exact order):

- Deposit `$300` into his `checkings` account
- Withdraw `$200` from his `savings` account
- After doing all the above, check how much money he currently has in his bank accounts

<details>
<summary>See solution</summary>

```js
let checkings = 500;
let savings = 1500;

function deposit(account, amount) {
    //If amount is NOT a valid number
    if (Number.isNaN(Number(amount))) {
        console.log('amount is not a number') //Display error message if invalid number
    } else {
        //Return money in account after depositing
        return account += amount;
    }
}

function withdraw(account, amount) {
    //Check if `amount` is NOT a valid number

    //If `amount` is NOT a valid number, display error message and exit out of function
    if (Number.isNaN(Number(amount))) {
        console.log('amount is not a number')
        return;
    }

    //Check if account has the amount of money we want to withdraw
    if ((account - amount) >= 0) {
        //Return money in account after withdraw
        return account -= amount;
    } else {
        //If not enough amount of money in account
        console.log("You don't have enough money in your account"); //Display error message
    }
}

function checkBalances() {
    //Display amount of money in savings account
    console.log(`You have $${savings} in your savings account.`);
    //Display amount of money in checkings account
    console.log(`You have $${checkings} in your checkings account.`);
}

checkings = deposit(checkings, 300); //Deposit $300 into checkings account
savings = withdraw(savings, 200); //Withdraw $200 from savings account
checkBalances(); //Display balance of both checkings and savings account
```

</details>

Your saving's account `6%` interest is not applying! Your bank needs a fix for that! Write a function `interest` that returns your savingss account balance with 6% interest applied. This function takes in one argument:
    
- A number `savings` - your savings account balance
- A constant variable `interest` that holds 6% as a decimal

<details>
<summary>See interest solution</summary>

```js
function interest(savings) {
    const interest = 0.06; //constant variable for interest
    let earn = savings * interest; //find earn of savings with interest
    //Return savings account balance with 6% interest
    return savings + earn;
}

```

</details>


Frank thanks you for helping him out! A week later and all the original bank's ATMs, branches, and mobile app are all back up and running. Frank has his banking app on his mobile device. Frank is lazy and doesn't want to go his local branch. He wants to make use of the check deposit feature on the bank's mobile app. Frank has 6 `$100` checks he wishes to deposit into his `savings` account

Using your implementation, `deposit` Frank's 6 `$100` checks into his `savings` account. Do this in a `loop`. Afterwards, display how much money he has in his `savings` account after depositing his checks.

<details>
<summary>See solution</summary>

```js
//Deposit $100 into savings account 6 times
for (let i = 0; i < 6; i++) {
    savings = deposit(savings, 100);
}
checkBalances(); //Display balance of both checkings and savings account
```

</details>