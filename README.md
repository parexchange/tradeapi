
## API Reference

```
"https://apiv1.parex.exchange/echo"
```

- Fetch system status.

```
"https://apiv1.parex.exchange/ping"
```
- Test connectivity to the Rest API.


"apikey and secretkey"
These variables are completely specific to your user.
Please get it from the parex app


```
"https://apiv1.parex.exchange/getToken"

```
Method : POST 

- The 'GetToken' call returns a token that is used in all subsequent API calls. Since a token is short-lived, it will be necessary to repeat this process to obtain a new token when the previous token expires.

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | Parex Secret Key |



` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| result | String | Yes | Parex Token  |



```
"https://apiv1.parex.exchange/getAssets"
```
Method : POST 

- Get information of coins (available for deposit and withdraw) for user.

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | Parex Secret Key |
| token | String | Yes | Parex Token |



` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| id | Integer | Yes | Asset ID  |
| shortname | String | Yes | Asset Short Name  |
| assets | String | Yes | Asset Name  |



```
"https://apiv1.parex.exchange/getMarkets"
```
Method : POST 


- Get information of available market

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | Parex Secret Key |
| token | String | Yes | Parex Token |



` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| id | Integer | Yes | Market ID  |
| marketname | String | Yes | Market Name  |
| paircoin | String | Yes | PairCoin ID  |
| maincoin | String | Yes | MainCoin ID  |
| pairinfo | String | Yes | PairCoin Name  |
| maininfo | String | Yes | PairCoin Name  |




```
"https://apiv1.parex.exchange/getWalletBalances"
```
Method : POST 


- Get your wallet balances

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | Parex Secret Key |
| token | String | Yes | Parex Token |


` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| id | Integer | Yes | line number  |
| address | String | Yes | Wallet Address  |
| shortname | String | Yes | Asset Short Name |
| balance | String | Yes | Balance  |




```
"https://apiv1.parex.exchange/getMyOrders"
```
Method : POST 


- Get your orders

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | Parex Secret Key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |


` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| orderid | Integer | Yes | orderID |
| type | String | Yes | Buy/Sell  |
| date | Datetime | Yes | Order Date |
| amount | String | Yes | Amount  |
| price | String | Yes | Price  |
| total | String | Yes | Total  |
| marketid | String | Yes | Parex MarketID  |
| pairinfo | String | Yes | PairCoin Name  |
| maininfo | String | Yes | MainCoin Name  |


```
"https://apiv1.parex.exchange/getMyOrdersByID"
```
Method : POST 


- Get your orders by ID

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | Parex Secret Key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |
| orderid | String | Yes | Parex Market Order ID |


` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| orderid | Integer | Yes | orderID |
| type | String | Yes | Buy/Sell  |
| date | Datetime | Yes | Order Date |
| amount | String | Yes | Amount  |
| price | String | Yes | Price  |
| total | String | Yes | Total  |
| marketid | String | Yes | Parex MarketID  |
| pairinfo | String | Yes | PairCoin Name  |
| maininfo | String | Yes | MainCoin Name  |




```
"https://apiv1.parex.exchange/cancelMyOrdersByID"
```
Method : POST 


- Cancel your Order By ID

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | Parex Secret Key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |
| orderid | String | Yes | Parex Market Order ID |



` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| orderid | Integer | Yes | orderID |
| marketid | String | Yes | Parex Market ID |
| marketname | String | Yes | Parex Market Name |


```
"https://apiv1.parex.exchange/getMyHistory"
```
Method : POST 


- Get your historical orders


` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | Parex Secret Key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |

` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| orderid | Integer | Yes | orderID |
| type | String | Yes | Buy/Sell  |
| date | Datetime | Yes | Order Date |
| amount | String | Yes | Amount  |
| price | String | Yes | Price  |
| total | String | Yes | Total  |
| marketid | String | Yes | Parex MarketID  |
| pairinfo | String | Yes | PairCoin Name  |
| maininfo | String | Yes | MainCoin Name  |


```
"https://apiv1.parex.exchange/getBuyOrders"
```
Method : POST 


- Get your Active Buy orders

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | Parex Secret Key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |

` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| orderid | Integer | Yes | orderID |
| type | String | Yes | Buy/Sell  |
| date | Datetime | Yes | Order Date |
| amount | String | Yes | Amount  |
| price | String | Yes | Price  |
| total | String | Yes | Total  |
| marketid | String | Yes | Parex MarketID  |
| pairinfo | String | Yes | PairCoin Name  |
| maininfo | String | Yes | MainCoin Name  |


```
"https://apiv1.parex.exchange/getSellOrders"
```
Method : POST 

- Get your Active Sell orders



` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | Parex Secret Key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |

` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| orderid | Integer | Yes | orderID |
| type | String | Yes | Buy/Sell  |
| date | Datetime | Yes | Order Date |
| amount | String | Yes | Amount  |
| price | String | Yes | Price  |
| total | String | Yes | Total  |
| marketid | String | Yes | Parex MarketID  |
| pairinfo | String | Yes | PairCoin Name  |
| maininfo | String | Yes | MainCoin Name  |


```
"https://apiv1.parex.exchange/setSellOrder"
```
Method : POST 


- Set new Sell Order

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | Parex Secret Key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |
| amount | String | Yes | Amount  |
| price | String | Yes | Price  |
| total | String | Yes | Total  |

` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| orderid | Integer | Yes | orderID |
| marketid | String | Yes | Parex Market ID |
| marketname | String | Yes | Parex Market Name |


```
"https://apiv1.parex.exchange/setBuyOrder"
```
Method : POST 


- Set new Buy Order

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | Parex Secret Key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |
| amount | String | Yes | Amount  |
| price | String | Yes | Price  |
| total | String | Yes | Total  |

` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| orderid | Integer | Yes | orderID |
| marketid | String | Yes | Parex Market ID |
| marketname | String | Yes | Parex Market Name |
