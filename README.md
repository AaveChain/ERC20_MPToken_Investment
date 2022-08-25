# ERC20-MindPay-Token-Investment

Below funcionality is covered :
-	Create ERC20 token “MINDPAY”
-	Contracts for accepting Investment through Ether with following  functionalities,
-	1 Ether = 1000 Mindpay
-	>1 & <5 Ether investment will have 10% bonus tokens
-	>5 Ether investment will have 20% bonus tokens 
-	90% of the investment (ether) should be locked in a reserve contract along with 100% tokens he/she is going to get. Ideally it should be locked 365 days but for testing we can put 15 Minutes
-	10% of the investment should go to a liquidity contract.
-	At the end of 15 minutes investor can take following functions (Any of the action)
-	Cancel investment - in this case 90% of investment will return to investors from reserve contract 100% tokens will be burned automatically.
-	Stake Investment - Stake the investment. 90% of the funds will go to liquidity contract and 100% MindPay tokens goes to Staking Contract 

Work Flow:-

Import the project into your system from gitHub and go to Project folder
    1. Start truffle development server in your terminal –  

    truffle develop

Go to server.js file and set first account address as the MindPayOwner and private key
(set the value since this is used once only for ERC20 token contract deployment (MindPay))

   2. In another terminal, compile and migrate the scripts

    truffle compile 
    and truffle migrate

Start server.js – node – npm start server.js and you will see below screen.

Go to your browser and open localhost:3000 and make sure metamask is connected with localhost 8545 and is MindPay owner account is connected.

You will notice that that the ETH is less than 100 because gas was used for deployment of MIndPay Token contract. You can also see the supply value by clicking button.

Choose another account(client) Enter the ETH you want to invest in the input box and click Convert.

Now click on Invest into MindPay to deploy the Investment Contract which will then transfer the assets to Reserve and Liquid contracts respectively

You will now notice that if you click on the Supply button that the token Supply has decreased indicating the tokens have been transferred to Reserve contract.

90% of the Ether has been transferred to a Reserve contract which can be checked by clicking Check Reserve Balance button.

10% of the Ether has been transferred to a Liquidity contract which can be checked by clicking Check Liquid Balance button.

You can cancel / stake the investment after 15 min
If you try to cancel from a different account or before 15 min you get and error in the console. You can check the reason there.

If cancellation /stake is successful you will get the transaction hash and the 90% Ether will refunded and token is burnt.