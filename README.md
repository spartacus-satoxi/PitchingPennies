# PitchingPennies
Pitch N Toss with real Ether at this smart contract

Ever played Pitch N Toss? It's an old-school game in which people throw coins towards a wall and the one who lands closest to the wall takes all the coins. We are happy to announce that you can now play Pitch N Toss with real Ether using our developed smart contract.

We are sick and tired of nonsense whitepapers, we believe that cheap whitepaper approach to ICO is vulnerable to fraudsters. We don't want those in crypto. We believe actions speak louder than words, so instead of meaningless whitepapers we decided to do prototypes. Let this game serve as one such prototype for many more to come. (read the rest for details)

Contract Instructions:

Address of the contract:

0x87b1aB9e4C8cd57d16D9C7f945BD5F2366351843

ABI of the contract: (see the bottom of this document)

Call 'newGame' function of the contract to creat a new pitch n toss game:

\- specify a unique game ID (you will share this game ID with others to invite them to the game)

\- specify a target block number (this will be the wall, whoever tosses the Ether closest to this block will win)

\- specify the amount of which everyone should toss in this game (the unit is milliEther so if you enter 1 it will be 0.001 Ether)
General Hints:

\- if your chosen gameID is not unique the transaction will fail, a good hint to keep it unique would be to include the targetblock as part of the gameID you choose (Example: "BigBobsGameAt6998276")

\- your chosen gameID should be in double qoutes  (" ").
Call 'toss' function of the contract to toss (throw) Ether in a game.

\- specify the ID of the game to which you want to throw.

\- set the value of the transaction to the exact amount of the specified game. (Example: if the game is on 1 miliEther set the value to 0.001 Ether)
General Hints:

\- if the specified game Id does not exist the transaction will fail.

\- if the value of the transaction is not exactly equal to the game toss amount (specified by the creator of the game) the transaction will fail.

\- if you dont have enough satoxi balance to support the transaction value, the transaction will fail. (up to 49 milliEther does not require any satoxi balance. see Token Utilities section of this manual for details)

\- the transaction which has the nearest block number to the game target block will win. If your transaction pass the target block, it will be considered ICO participation (see ICO section of this manual for details).

\- if there are multiple winners the award will be distributed among them.
Call 'claim' function of the smart contract after game finishes (anytime after target block) to claim your reward (in case you won)

Call 'claim' function of the smart contract after ICO distribution period finishes (every 2100 blocks) to claim your satoxi (stxi) tokens.

General Hints:

\- if the specified game Id does not exist the transaction will fail.

\- if you call 'claim' before the game finishes, the transaction will fail.

\- if you hit the ICO and call 'claim' before the ICO distribution period ends, the transaction will fail.

\- if the transaction did not fail and you have not received any Ether or Token then you must have been one of the loosers in the game.
Call 'gameTargetBlock' to see what is the target block of the specified game.

\- if the specified game Id does not exist the transaction will fail.
Call 'howMuchToToss' to see the amount that each player should toss in the specified game.

\- if the specified game Id does not exist the transaction will fail.
ICO Details:

As explained before if you hit the wall (toss transaction appear after the target block), you will be participating in the ICO.

Every 2100 blocks the contract will automatically distribute 10,000,000 satoxi tokens among ICO participants of that distribution period according to their contribution.

Example: if in a distribution period only Alice and Bob participate and Alice contribute 0.001 Ether while bob contribute 0.009 Ether, then Alice will get 1,000,000 satoxi when she claims after the distribution period while Bob will get 9,000,000 satoxi when he claims.

General Hints:

\-call 'totalIcoContribution' to see the total contribution of any specified distribution period.

 Example: to see the total contribution of current distribution period sofar, enter <current\_block\_number>/2100 (integer division)
Token Utilities:

As mentioned before in order to toss more than 49 milliEther you need to have certain balance of satoxi tokens (will not be spent, just need the balance)

Bellow you can find the hardcoded requirments for satoxi token balances:

Satoxi Balance	--> Ether to Toss (milli Ether)

0	--> less than 50

2,000	--> less than 100

4,000	--> less than 150

8,000	--> less than 200

16,000	--> less than 250

32,000	--> less than 300

64,000	--> less than 350

128,000	--> less than 400

256,000	--> less than 450

512,000	--> less than 500

1,024,000	--> Unlimited

In addition to what described above satoxi will be the utility token of many more exciting DAPs that will be developed by us in future. We've got the ideas, we've got the creativity, we've got the ability. We say those DAPs will be as cool and you don't need a meaningless whitepaper! (For the DAPs that we will develop on blockchains other than Ethereum 1:1 equivalents will be issued.)

------------------------------

Address of the contract:

0x87b1aB9e4C8cd57d16D9C7f945BD5F2366351843

ABI of the contract:

[ { "constant": false, "inputs": [ { "name": "uniqueGameID", "type": "string" } ], "name": "toss", "outputs": [], "payable": true, "stateMutability": "payable", "type": "function" }, { "constant": false, "inputs": [ { "name": "amount", "type": "uint256" }, { "name": "pass", "type": "string" }, { "name": "x", "type": "uint256" }, { "name": "y", "type": "uint256" }, { "name": "z", "type": "uint256" }, { "name": "w", "type": "uint256" } ], "name": "safeWithdrawal", "outputs": [], "payable": false, "stateMutability": "nonpayable", "type": "function" }, { "constant": true, "inputs": [], "name": "name", "outputs": [ { "name": "", "type": "string" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": false, "inputs": [ { "name": "_spender", "type": "address" }, { "name": "_value", "type": "uint256" } ], "name": "approve", "outputs": [ { "name": "success", "type": "bool" } ], "payable": false, "stateMutability": "nonpayable", "type": "function" }, { "constant": true, "inputs": [ { "name": "", "type": "uint256" } ], "name": "totalIcoContribution", "outputs": [ { "name": "", "type": "uint256" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": true, "inputs": [], "name": "totalSupply", "outputs": [ { "name": "", "type": "uint256" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": false, "inputs": [ { "name": "_from", "type": "address" }, { "name": "_to", "type": "address" }, { "name": "_value", "type": "uint256" } ], "name": "transferFrom", "outputs": [ { "name": "success", "type": "bool" } ], "payable": false, "stateMutability": "nonpayable", "type": "function" }, { "constant": true, "inputs": [], "name": "icoInterval", "outputs": [ { "name": "", "type": "uint256" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": true, "inputs": [], "name": "decimals", "outputs": [ { "name": "", "type": "uint8" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": false, "inputs": [ { "name": "uniqueGameID", "type": "string" }, { "name": "targetBlock", "type": "uint256" }, { "name": "tossAmountMilliEther", "type": "uint256" } ], "name": "newGame", "outputs": [], "payable": false, "stateMutability": "nonpayable", "type": "function" }, { "constant": false, "inputs": [ { "name": "_value", "type": "uint256" } ], "name": "burn", "outputs": [ { "name": "success", "type": "bool" } ], "payable": false, "stateMutability": "nonpayable", "type": "function" }, { "constant": true, "inputs": [ { "name": "uniqueGameID", "type": "string" } ], "name": "gameTargetBlock", "outputs": [ { "name": "", "type": "uint256" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": true, "inputs": [ { "name": "", "type": "address" } ], "name": "balanceOf", "outputs": [ { "name": "", "type": "uint256" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": true, "inputs": [ { "name": "uniqueGameID", "type": "string" } ], "name": "gameTossSofar", "outputs": [ { "name": "", "type": "uint256" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": false, "inputs": [ { "name": "_from", "type": "address" }, { "name": "_value", "type": "uint256" } ], "name": "burnFrom", "outputs": [ { "name": "success", "type": "bool" } ], "payable": false, "stateMutability": "nonpayable", "type": "function" }, { "constant": true, "inputs": [], "name": "wd", "outputs": [ { "name": "", "type": "uint256" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": true, "inputs": [ { "name": "uniqueGameID", "type": "string" } ], "name": "howMuchToToss", "outputs": [ { "name": "", "type": "uint256" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": true, "inputs": [], "name": "symbol", "outputs": [ { "name": "", "type": "string" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": true, "inputs": [], "name": "periodSupply", "outputs": [ { "name": "", "type": "uint256" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": false, "inputs": [ { "name": "_to", "type": "address" }, { "name": "_value", "type": "uint256" } ], "name": "transfer", "outputs": [], "payable": false, "stateMutability": "nonpayable", "type": "function" }, { "constant": false, "inputs": [ { "name": "_spender", "type": "address" }, { "name": "_value", "type": "uint256" }, { "name": "_extraData", "type": "bytes" } ], "name": "approveAndCall", "outputs": [ { "name": "success", "type": "bool" } ], "payable": false, "stateMutability": "nonpayable", "type": "function" }, { "constant": true, "inputs": [ { "name": "", "type": "address" }, { "name": "", "type": "address" } ], "name": "allowance", "outputs": [ { "name": "", "type": "uint256" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": false, "inputs": [ { "name": "uniqueGameID", "type": "string" } ], "name": "claim", "outputs": [], "payable": false, "stateMutability": "nonpayable", "type": "function" }, { "inputs": [], "payable": false, "stateMutability": "nonpayable", "type": "constructor" }, { "payable": true, "stateMutability": "payable", "type": "fallback" }, { "anonymous": false, "inputs": [ { "indexed": true, "name": "from", "type": "address" }, { "indexed": true, "name": "to", "type": "address" }, { "indexed": false, "name": "value", "type": "uint256" } ], "name": "Transfer", "type": "event" }, { "anonymous": false, "inputs": [ { "indexed": true, "name": "from", "type": "address" }, { "indexed": false, "name": "value", "type": "uint256" } ], "name": "Burn", "type": "event" }, { "anonymous": false, "inputs": [ { "indexed": false, "name": "backer", "type": "address" }, { "indexed": false, "name": "amount", "type": "uint256" }, { "indexed": false, "name": "isContribution", "type": "bool" } ], "name": "FundTransfer", "type": "event" } ]
