+ Reference :- https://www.youtube.com/watch?v=coQ5dg8wM2o

+ Setup:
- install NodeJs
- install ganache :-  personal Ethereum blockchain which you can use to run tests
- truffle framework npm install -g truffle@5.0.2 :- develope/deploy/test smart contracts
- metamask extension for google chrome :- connecting to the etherium block chain network

+ Project Structure
- mkdir eth-todo-list
- cd eth-todo-list
- truffle init :- this will create contracts, migrations and test folders, plus truffle-config.js
- echo > package.json :- create package json for pulling in some dependencies
- use the code from https://github.com/dappuniversity/eth-todo-list/blob/master/package.json
- npm install :- install the dependencies
- echo > TodoList.sol :- create the smart contract file that will be used to build the to-do list, inside "contracts" folder. note there exisit a migration contract that comes bundled with truffle. This new file acts like a DB schema update; a new table with some data.
- copy the code from GitHub
- truffle compile :- this will create the build folder
- update truffle-config.js :- setup to connect to localHost ganache
- echo 2_deploy_contracts.js :- create a migration file to put your smart contract (SC) on the blockchain (BC). consider the BC as a DB. so when you are putting a new SC on there, you are updating the state. Therefore we use migratiosn and each file is numbered to make sure things are running in the expected order by truffle.
- truffle migrate :- run the migration and deploy the SC to BC. Deploying SCs costs Ether/gas, therfore truffle uses the first wallet on ganache to pay for it. if you have already migrated something before you can use: "truffle migrate --reset" command.
- you can open truffle console and check the deployed SC:
	- truffle console
		- await TodoList.deployed() :- retrieve SC from BC
		- TodoList address :- get the SC address on BC
- add .gitignore to test folder and ignore node_modules/
- push to github
- create the client side app
	- mkdir src
	- echo > index.html
	- echo > app.js
	- under the main dir, create bs-config.json :- browser source config file will tell "lite-server" that we use in dependecies for running the client side where the build, src and node modules are.
	- npm run dev