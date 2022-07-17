# Solidity-


## Tips for less gas consumption:
1. If you're sure that the value of an u/int not is going to meet the maxium value use unchecked before it





## Transfer/Withdraw funds from contract
You can send Ether to other contracts by

* transfer (2300 gas, throws error)
* send (2300 gas, returns bool)
* call (forward all gas or set gas, returns bool)

Transfer: will automatically revert if it fails
```Solidity
payable(msg.sender).transfer(address(this).balance);
```
Send: will only revert if we use the require statement
```Solidity
bool sendSuccess = payable(msg.sender).send(address(this).balance);
require(sendSuccess, "Send failed");
```
Call: Similar to send. Call is the recomended way to send ETH or other tokens
```Solidity
(bool callSuccess, ) = payable(msg.sender).call{value: address(this).value}("");
require(callSuccsess, "Call Failed");
```





## Usefull links
- Solidity Documentation - https://docs.soliditylang.org/en/v0.8.6/index.html
- Etherscan mainNetwork - https://etherscan.io/
- TestNetworks - https://docs.chain.link/docs/link-token-contracts/#rinkeby
- ETH Converter - https://eth-converter.com/
- Chainlink Oracle Data - https://data.chain.link/
- Solidity by example - https://solidity-by-example.org/
