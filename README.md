# JointSavings

## Background
A fintech startup company has recently hired you. This company is disrupting the finance industry with its own cross-border, Ethereum-compatible blockchain that connects financial institutions. Currently, the team is building smart contracts to automate many of the institutions’ financial processes and features, such as hosting joint savings accounts.

To automate the creation of joint savings accounts, you’ll create a Solidity smart contract that accepts two user addresses. These addresses will be able to control a joint savings account. Your smart contract will use ether management functions to implement a financial institution’s requirements for providing the features of the joint savings account. These features will consist of the ability to deposit and withdraw funds from the account.

## What You're Creating
- The completed JointSavings Solidity smart contract.

- A folder named Execution_Results that contains at least eight images. These images should confirm that the deposit and withdrawal transactions, which are designed to test the JointSavings functionality in the JavaScript VM, worked as expected.

## Step 1: Create a Joint Savings Account Contract in Solidity
1) From the provided starter code, open the Solidity file named `joint_savings.sol` in the Remix IDE.

2) Define a new contract named `JointSavings`.

3) Define the following variables in the new contract:

- Two variables of type `address payable` named `accountOne` and `accountTwo`

- A variable of type `address public` named `lastToWithdraw`

- Two variables of type `uint public` named `lastWithdrawAmount` and `contractBalance`

4) Define a function named `withdraw` that accepts two arguments: `amount` of type `uint` and `recipient` of type `payable address`. In this function, create code as follows:

- Define a `require` statement that checks if `recipient` is equal to either `accountOne` or `accountTwo`. If it isn’t, the `require` statement will return the “You don't own this account!” text.

- Define a `require` statement that checks if `balance` is sufficient for accomplishing the withdrawal operation. If insufficient funds exist, it will return the “Insufficient funds!” text.

- Add an `if` statement to check if `lastToWithdraw` is not equal to (`!=`) `recipient`. If it isn’t equal, set it to the current value of `recipient`.

- Call the `transfer` function of the `recipient`, and pass it the `amount` to transfer as an argument.

- Set `lastWithdrawAmount` equal to `amount`.

- Set the `contractBalance` variable equal to the balance of the contract by using `address(this).balance` to reflect the new balance of the contract.

5) Define a `public payable` function named `deposit`. In this function, create code as follows:

- Set the contractBalance variable equal to the balance of the contract by using address(this).balance.

6) Define a `public` function named `setAccounts` that takes two `address payable` arguments, named `account1` and `account2`. In the body of the function, set the values of `accountOne` and `accountTwo` to `account1` and `account2`, respectively.

7) Add a fallback function so that your contract can store ether that’s sent from outside the deposit function.

## Step 2: Compile and Deploy Your Contract in the JavaScript VM
1) Compile your smart contract. If an error occurs, review your code, and make the necessary changes for a successful compilation.   

2) In the Remix IDE, navigate to the “Deploy & Run Transactions” pane, and then make sure that “JavaScript VM” is selected as the environment.

3) Click the Deploy button to deploy your smart contract, and then confirm that it successfully deployed.

## Step 3: Interact with Your Deployed Smart Contract
Now that your contract is deployed, it’s time to test its functionality. After each step, capture a screenshot of the execution, and then save it in a folder named `Execution_Results`. You’ll share this folder with your final submission.

To interact with your deployed smart contract, complete the following steps:

1) Use the setAccounts function to define the authorized Ethereum address that will be able to withdraw funds from your contract.

2) Test the deposit functionality of your smart contract by sending the following amounts of ether. After each transaction, use the contractBalance function to verify that the funds were added to your contract:
 
- Transaction 1: Send 1 ether as wei.
<img width="1470" alt="Screenshot 2024-06-02 at 2 39 48 PM" src="https://github.com/gerxxoo/JointSavings/assets/151468004/de9d42fe-9776-4f3a-859a-d39487ec5b84">


- Transaction 2: Send 10 ether as wei.
<img width="1470" alt="Screenshot 2024-06-02 at 2 41 03 PM" src="https://github.com/gerxxoo/JointSavings/assets/151468004/4a131df8-d67c-4319-ba2d-a24358c1e5f0">


- Transaction 3: Send 5 ether.
<img width="1470" alt="Screenshot 2024-06-02 at 2 43 36 PM" src="https://github.com/gerxxoo/JointSavings/assets/151468004/b0604ca7-a2e8-4895-a337-d0059c0aed2b">


3) Once you’ve successfully deposited funds into your contract, test the contract’s withdrawal functionality by withdrawing 5 ether into `accountOne` and 10 ether into `accountTwo`. After each transaction, use the `contractBalance` function to verify that the funds were withdrawn from your contract. Also, use the `lastToWithdraw` and `lastWithdrawAmount` functions to verify that the address and amount were correct.

- 5 ether into `accountOne`
<img width="1470" alt="Screenshot 2024-06-02 at 2 51 17 PM" src="https://github.com/gerxxoo/JointSavings/assets/151468004/47b99698-41f7-4e05-b4c7-1220cbdfc97c">

- 10 ether into `accountTwo`
<img width="1470" alt="Screenshot 2024-06-02 at 2 52 10 PM" src="https://github.com/gerxxoo/JointSavings/assets/151468004/d6064bbe-7680-492c-9d3d-b62b1831c8a7">
