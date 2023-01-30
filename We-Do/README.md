# We Do Exercise

## Problem
Oh no! Your personal bank's atm software has gone down all of a sudden! The app has gone down! The branches are closed! It's up to us to build a backup ATM application that can work while everything gets back up!

## What we need to do
We need to build a script that can `deposit`, `withdraw`, `display`, and `transfer` money. I have two bank accounts: a `checkings` account and `savings` account with an initial amount of money. I should be able to:

- `deposit` money into either my checkings account or savings account
- `withdraw` money from either my checkings account or savings account
- `transfer` money from one bank account to the other
- `display` the amount of money I have from either my checkings or savings account

## Requirements
In order to do this, we should include the following:

- A function `deposit` that deposits money into a selected account. This function takes in two arguments:
    - A string `account` - indicates which account (checkings or savings) you want to deposit money into
    - A number `amount` - the amount of money we wish to deposit

    NOTE:
    - Check if the value of `amount` is a number. If not, display an error message: `amount is not a number`.
    - Check if `account` is a valid account. If not, display an error message: `account is not a valid account. Try again`

<details>
<summary>See deposit guide</summary>

```js
function deposit(account, amount) {
    /*
        Check if `amount` is a valid number:
        IF `amount` is a valid number:
            Check which account we're depositing to
            IF checkings: 
                add `amount` to checkings account
            IF savings: 
                add `amount` to savings account
            IF neither checkings or savings:
                Display message: `account is not a valid account. Try again`
            
        IF `amount` is NOT a valid number:
            Display message: `amount is not a number`
    */
}
```
</details>

<details>
<summary>See deposit implementation</summary>

```js
function deposit(account, amount) {
    //Check if `amount` is a valid number

    //If amount is NOT a valid number
    if (Number.isNaN(Number(amount))) {
        console.log('amount is not a number') //Display error message if invalid number
    } else {
        //Check which account we're depositing to
        if (account === 'checkings') { //Checkings
            checkings += amount; //add `amount` to checkings account
        } else if (account === 'savings') { //Savings
            savings += amount //add `amount` to savings account
        } else { //Invalid account
            console.log('account is not a valid account. Try again') //Display error message
        }
    }
}
```
</details>

- A function `withdraw` that withdraws money from a selected account. This function takes in two arguments:

    - A string `account` - indicates which account (checkings or savings) you want to withdraw money from
    - A number `amount` - the amount of money we wish to withdraw

    NOTE: 
    - This function should check if we have enough money in our account to withdraw. If not, then display a `You don't enough have money in your [account] account` message and do NOT withdraw money.
    - Check if the value of `amount` is a number. If not, display an error message: `amount is not a number`.
    - Check if `account` is a valid account. If not, display an error message: `account is not a valid account. Try again`

    

    **Brainstorm**: Try to think of a way where we don't have to use a lot of nested if statements

<details>
<summary>See withdraw guide</summary>
        
```js
function withdraw(account, amount) {
    /*  
        Check if `amount` is NOT a valid number

        IF `amount` is NOT a valid number:
            Display message: `amount is not a number`
            Exit out of the function

        Check which account we're withdrawing from

        If checkings:
            Check if the checkings account has the amount of money we want to withdraw
            IF YES: subtract amount from checkings account
            IF NO: display 'You don't have enough money in your checkings account'

        IF savings:
            Check if the savings account has the amount of money we want to withdraw
            IF YES: subtract amount from savings account
            IF NO: display 'You don't have enough money in your savings account'

        IF neither checkings or savings:
            Display message: `account is not a valid account. Try again`
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

    //Check which account we're withdrawing from
    if (account === 'checkings') {
        //Check if the checkings account has the maount of money we want to withdraw
        if ((checkings - amount) >= 0) {
            checkings -= amount; //subtract `amount` from checkings account
        } else {
            //If not enough amount of money account
            console.log("You don't have enough money in your checkings account"); //Display error message
        }

    } else if (account === 'savings') {
        //Check if the savings account has the maount of money we want to withdraw
        if ((savings - amount) >= 0) {
            savings -= amount; //subtract `amount` from savings account
        } else {
            //If not enough amount of money in account
            console.log("You don't have enough money in your savings account"); //Display error message
        }

    } else {
        //Invalid account error message
        console.log("account is not a valid account. Try again");
    }
}
```
</details>


- A function `transfer` that transfers money from one account to another. This function should remove money from one account and add the money to the other. This function takes in three arguments:

    - A string `fromAccount` - indicates which account we are transferring money from
    - A string `toAccount` - indicates which account we are transferring the money to
    - A number `amount` - the amount of money we wish to transfer

    NOTE: 
    
    - Check if we have enough money in our `fromAccount` account to remove and add it to our `toAccount` account. 
    - If the `fromAccount` account does not have enough `amount` of money, then display a `You don't have enough money in your [fromAccount] account` message and do NOT transfer money.
    - Both `fromAccount` and `toAccount` should be valid accounts. If not, display a `[fromAccount/toAccount] is invalid. Please check.` and do NOT transfer money
    - If the `fromAccount` account and `toAccount` account are the same, display a `You cannot transfer to the same account` message and do NOT transfer money.
    - Check if the value of `amount` is a number. If not, display an error message: `amount is not a number`.

    **Brainstorm**: Try to think of a way where we don't have to use a lot of nested if statements

<details>
<summary>See transfer guide</summary>
     
```js
function transfer(fromAccount, toAccount, amount) {
    /*
        Check if `amount` is NOT a valid number

        IF `amount` is NOT a valid number:
            Display message "amount is not a number"
            Exit out of the function

        Check if `fromAccount` and `toAccount` are NOT valid accounts (checkings/savings)

        IF `fromAccount` is NOT a valid account
            Display message "fromAccount is invalid. Please check"
            Exit out of the function

        IF `toAccount` is NOT a valid account
            Display message "toAccount is invalid. Please check"
            Exit out of the function

        Check if `fromAccount` and `toAccount` are NOT the same account

        IF `fromAccount` and `toAccount` are the same account:
            Display message "You cannot transfer to the same account"
            Exit out of the function

        Check which account `fromAccount` is

        IF `fromAccount` is checkings:
            Check if `checkings` has `amount` of money
            IF YES:
                Remove `amount` from checkings
                Add `amount` to savings
                
            IF NO:
                Display message: `You don't have enough money in your checkings account`

        IF `fromAccount` is savings:
            Check if `savings` has `amount` of money
            IF YES:
                Remove `amount` from savings
                Add `amount` to checkings
                
            IF NO:
                Display message: `You don't have enough money in your savings account`
    */
}
```
</details>

<details>
<summary>See transfer implementation</summary>

```js
function transfer(fromAccount, toAccount, amount) {
    //Check `amount` is NOT a valid number

    //If `amount` is NOT a valid number, display error message and exit out of function
    if (Number.isNaN(Number(amount))) {
        console.log('amount is not a number')
        return;
    }

    //Check `fromAccount` or `toAccount` are NOT valid accounts

    //If `fromAccount` and `toAccount` are NOT valid accounts, display error message and exit out of function
    if (fromAccount !== 'checkings' && fromAccount !== 'savings')  {
        console.log("fromAccount is invalid. Please check");
        return;
    }

    if (toAccount !== 'checkings' && toAccount !== 'savings')  {
        console.log("toAccount is invalid. Please check");
        return;
    }

    //Check that `fromAccount` and `toAccount` are NOT the same account

    //If `fromAccount` and `toAccount` are the same account, display error message and exit out of function
    if (fromAccount === toAccount) {
        console.log('You cannot transfer to the same account');
        return;
    }

    //Check which account we're transferring money from

    if (fromAccount === 'checkings') { //Transferring from checkings account
        //Check if checkings has enough money to tranfer
        if ((checkings - amount) >= 0) {
            checkings -= amount; //Subtract from checkings
            savings += amount; //Add to savings
        } else {
            //Insufficient amount of money in checkings error message
            console.log("You don't have enough money in your checkings account");
        }
    }

    else if (fromAccount === 'savings') { //Transferring from savings account
        //Check if savings has enough money to tranfer
        if ((savings - amount) >= 0) {
            savings -= amount; //Subtract from savings
            checkings += amount; //Add to checkings
        } else {
            //Insufficient amount of money in savings error message
            console.log("You don't have enough money in your savings account");
        }
    }
}
```
</details>


- A function `display` that displays the amount of money there is within the account. This function takes in one argument: 
    - A string `account` - indicates which account (checkings or savings) you want to display money from

    NOTE:
    - Check if `account` is a valid account. If not, display an error message: `account is not a valid account. Try again`

<details>
<summary>See display guide</summary>
     
```js
function display(account) {
    /*
        Check which account we're trying to display money from

        IF `account` is checkings:
            Display message: `You have $[money] in your checkings account`

        IF `account` is savings:
            Display message: `You have $[money] in your savings account`

        IF `account` is neither checkings or savings:
            Display message: `account is not a valid account. Try again`
    */
}
```
</details>

<details>
<summary>See display implementation</summary>

```js
function display(account) {
    //Check which account we're display money from

    if (account === 'checkings') {
        //Display money in checkings account
        console.log(`You have $${checkings} in your checkings account`)
    } else if (account === 'savings') {
        //Display money in savings account
        console.log(`You have $${savings} in your savings account`)
    } else {
        //Invalid account error message
        console.log("account is not a valid account. Try again")
    }
}

```

</details>

- For `amount`, check if the value is a number. If not, display an error message: `amount is not a number`.
- For `account`, check if the value is a valid account. If not, display an error message: `account is not a valid account. Try again`

## Testing

Make sure to test our solution after we are done building it.

### Scenario
Frank needs to do a variety of transactions on the ATM. He has the same bank as you! Frank has a total of `$500` in his `checkings` account and `$1,500` in his `savings` account. Using your script, help Frank with the following (in the exact order):

- Deposit `$300` into his `checkings` account
- Withdraw `$200` from his `savings` account
- Transfer `$600` from his `checkings` account to his `savings` account
- After doing all the above, display how much money he currently has in his `savings` account

<details>
<summary>See solution</summary>

```js
let checkings = 500;
let savings = 1500;

function deposit(account, amount) {
    //Check if `amount` is a valid number

    //If amount is NOT a valid number
    if (Number.isNaN(Number(amount))) {
        console.log('amount is not a number') //Display error message if invalid number
    } else {
        //Check which account we're depositing to
        if (account === 'checkings') { //Checkings
            checkings += amount; //add `amount` to checkings account
        } else if (account === 'savings') { //Savings
            savings += amount //add `amount` to savings account
        } else { //Invalid account
            console.log('account is not a valid account. Try again') //Display error message
        }
    }
}

function withdraw(account, amount) {
    //Check if `amount` is NOT a valid number

    //If `amount` is NOT a valid number, display error message and exit out of function
    if (Number.isNaN(Number(amount))) {
        console.log('amount is not a number')
        return;
    }

    //Check which account we're withdrawing from
    if (account === 'checkings') {
        //Check if the checkings account has the maount of money we want to withdraw
        if ((checkings - amount) >= 0) {
            checkings -= amount; //subtract `amount` from checkings account
        } else {
            //If not enough amount of money account
            console.log("You don't have enough money in your checkings account"); //Display error message
        }

    } else if (account === 'savings') {
        //Check if the savings account has the maount of money we want to withdraw
        if ((savings - amount) >= 0) {
            savings -= amount; //subtract `amount` from savings account
        } else {
            //If not enough amount of money in account
            console.log("You don't have enough money in your savings account"); //Display error message
        }

    } else {
        //Invalid account error message
        console.log("account is not a valid account. Try again");
    }
}

function transfer(fromAccount, toAccount, amount) {
    //Check `amount` is NOT a valid number

    //If `amount` is NOT a valid number, display error message and exit out of function
    if (Number.isNaN(Number(amount))) {
        console.log('amount is not a number')
        return;
    }

    //Check `fromAccount` or `toAccount` are NOT valid accounts

    //If `fromAccount` and `toAccount` are NOT valid accounts, display error message and exit out of function
    if (fromAccount !== 'checkings' && fromAccount !== 'savings')  {
        console.log("fromAccount is invalid. Please check");
        return;
    }

    if (toAccount !== 'checkings' && toAccount !== 'savings')  {
        console.log("toAccount is invalid. Please check");
        return;
    }

    //Check that `fromAccount` and `toAccount` are NOT the same account

    //If `fromAccount` and `toAccount` are the same account, display error message and exit out of function
    if (fromAccount === toAccount) {
        console.log('You cannot transfer to the same account');
        return;
    }

    //Check which account we're transferring money from

    if (fromAccount === 'checkings') { //Transferring from checkings account
        //Check if checkings has enough money to tranfer
        if ((checkings - amount) >= 0) {
            checkings -= amount; //Subtract from checkings
            savings += amount; //Add to savings
        } else {
            //Insufficient amount of money in checkings error message
            console.log("You don't have enough money in your checkings account");
        }
    }

    else if (fromAccount === 'savings') { //Transferring from savings account
        //Check if savings has enough money to tranfer
        if ((savings - amount) >= 0) {
            savings -= amount; //Subtract from savings
            checkings += amount; //Add to checkings
        } else {
            //Insufficient amount of money in savings error message
            console.log("You don't have enough money in your savings account");
        }
    }
}

function display(account) {
    //Check which account we're display money from

    if (account === 'checkings') {
        //Display money in checkings account
        console.log(`You have $${checkings} in your checkings account`)
    } else if (account === 'savings') {
        //Display money in savings account
        console.log(`You have $${savings} in your savings account`)
    } else {
        //Invalid account error message
        console.log("account is not a valid account. Try again")
    }
}

deposit("checkings", 300); //Deposit $300 into checkings account
withdraw("savings", 200); //Withdraw $200 from savings account
transfer("checkings", "savings", 600); //Transfer $600 from checkings to savings
display("savings"); //Display amount of money in savings account
```

</details>

Frank thanks you for helping him out! A week later and all the original bank's ATMs, branches, and mobile app are all back up and running. Frank has his banking app on his mobile device. Frank is lazy and doesn't want to go his local branch. He wants to make use of the check deposit feature on the bank's mobile app. Frank has 6 `$100` checks he wishes to deposit into his `savings` account

Using your implementation, `deposit` Frank's 6 `$100` checks into his `savings` account. Do this in a `loop`. Afterwards, display how much money he has in his `savings` account after depositing his checks.

<details>
<summary>See solution</summary>

```js
//Deposit $100 into savings account 6 times
for (let i = 0; i < 6; i++) {
    deposit("savings", 100);
}
display("savings"); //Display amount of money in savings account
```

</details>