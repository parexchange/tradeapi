
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
- `apikey : Parex API Key`
- `secretkey : Parex Secret Key`
- `token : Parex Token (getToken)`
```
- `id : Asset ID` 
- `shortname : Asset Short Name`
- `assets : Asset Name`


```
"https://apiv1.parex.exchange/getMarkets"
- `apikey : Parex API Key`
- `secretkey : Parex Secret Key`
- `token : Parex Token (getToken)`
```
- `id : Market ID` 
- `marketname : Market Name`
- `paircoin : PairCoin ID`
- `maincoin : MainCoin ID`
- `pairinfo : PairCoin Name`
- `maininfo : MainCoin Name`


```
"https://apiv1.parex.exchange/getWalletBalances"
- `apikey : Parex API Key`
- `secretkey : Parex Secret Key`
- `token : Parex Token (getToken)`
```
- `id : line number` 
- `address : Wallet Address`
- `shortname : Asset Short Name`
- `balance : Balance`


```
"https://apiv1.parex.exchange/getMyOrders"
- `apikey : Parex API Key`
- `secretkey : Parex Secret Key`
- `marketid : Parex Market ID`
- `token : Parex Token (getToken)`
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
