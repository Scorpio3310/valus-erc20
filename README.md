# VALUS Smart contract for crowdsale (Crowdsale and ERC20)

## Step 1

Fistly deploy "crowdsale.sol" in [Remix Solidity](https://remix.ethereum.org). 

Select compiler 0.4.17+commit and click "Start to compile" then in Run tab in dropdown select ValusCrowdsale and enter following parameters like "1541592227","0x5dcaa1d8d8132e1bf9cf12deccfc0cecf26a780d". 1541592227 is Unix Timestamp when contract starts and 0x5dcaa1d8d8132e1bf9cf12deccfc0cecf26a780d is multisign address. Wait for contract deployed.

## Step 2

Second deploy is "token.sol". Select the same compiler as for fist contract and in Run tab in dropdown select ValusToken. You need to add contract address of crowdsale which was deployed.

## Step 3

Go back to Remix and in tab Run on bottom "Deployed Contracts" and find first deployed contract. In field "setTokenContract" add contract address from second deployed contract to connect this two contracts.



# Parameters in "Crowdsale.sol"

In function "ValusCrowdsale" you can change folowing parameters:

```shell
  endDay = startDay + 29 days;   // Duration of crowdsale is 29 days 
  minEthToRaise = 3030 * 10**18;  // Min ethereum for raise            
  maxEthToRaise = 30303 * 10**18;   // Max ethereum for raise 
  
```


 and in function "getValusTokenIssuance" ypu can change price and duration of bonuses
 
 ```shell
  if (_now >= startDay && _now < startDay + 2 days) return _ethSent * 1400; // In first 48h price for 1 VLS is 0.085 USD
  if (_now >= startDay + 2 days && _now < startDay + 7 days) return _ethSent * 1300; // From day 2 to day 7 price for 1 VLS is 0.09 USD
  if (_now >= startDay + 7 days && _now < startDay + 14 days) return _ethSent * 1200; //From day 7 to day 14 price for 1 VLS is 0.094 USD
  if (_now >= startDay + 14 days && _now < startDay + 21 days) return _ethSent * 1100; //From day 14 to day 21 price for 1 VLS is 0.097 USD
  if (_now >= startDay + 21  days) return _ethSent * 1000; //From day 21 to day 29 price for 1 VLS is 0.10 USD
  
```
