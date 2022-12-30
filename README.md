
## API Reference

```
"https://apiv1.parex.exchange/echo"
```

```
"https://apiv1.parex.exchange/ping"
```


```
"https://apiv1.parex.exchange/getToken"

```

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
- `apikey : Parex API Key`
- `secretkey : Parex Secret Key`
- `marketid : Parex Market ID`
- `token : Parex Token (getToken)`
- `orderid : Parex Market Order ID`
```
- `orderid : orderID `
- `type : Buy/Sell `
- `date : Datetime `
- `amount : Amount`
- `price : Price`
- `total : Total`
- `marketid : Parex MarketID`
- `pairinfo : PairCoin Name`
- `maininfo : MainCoin Name`


```
"https://apiv1.parex.exchange/cancelMyOrdersByID"
- `apikey : Parex API Key`
- `secretkey : Parex Secret Key`
- `marketid : Parex Market ID`
- `token : Parex Token (getToken)`
- `orderid : Parex Market Order ID`
```
- `orderid : orderID `
- `type : Buy/Sell `



```
"https://apiv1.parex.exchange/getMyHistory"
- `apikey : Parex API Key`
- `secretkey : Parex Secret Key`
- `marketid : Parex Market ID`
- `token : Parex Token (getToken)`
```
- `type : Buy/Sell `
- `date : Datetime `
- `amount : Amount`
- `price : Price`
- `total : Total`
- `marketid : Parex MarketID`
- `pairinfo : PairCoin Name`
- `maininfo : MainCoin Name`


```
"https://apiv1.parex.exchange/getBuyOrders"
- `apikey : Parex API Key`
- `secretkey : Parex Secret Key`
- `marketid : Parex Market ID`
- `token : Parex Token (getToken)`
```
- `id : line number `
- `type : Buy/Sell `
- `price : Price`
- `remaining : Remaining`


```
"https://apiv1.parex.exchange/getSellOrders"
- `apikey : Parex API Key`
- `secretkey : Parex Secret Key`
- `marketid : Parex Market ID`
- `token : Parex Token (getToken)`
```
- `id : line number `
- `type : Buy/Sell `
- `price : Price`
- `remaining : Remaining`


```
"https://apiv1.parex.exchange/setSellOrder"
- `apikey : Parex API Key`
- `secretkey : Parex Secret Key`
- `marketid : Parex Market ID`
- `token : Parex Token (getToken)`
- `price : Price`
- `amount : Amount`
```


```
"https://apiv1.parex.exchange/setBuyOrder"
- `apikey : Parex API Key`
- `secretkey : Parex Secret Key`
- `marketid : Parex Market ID`
- `token : Parex Token (getToken)`
- `price : Price`
- `amount : Amount`
```
