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