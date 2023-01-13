# API Reference



## Table of Contents

1. [System Status](#system-status)
2. [Apikey](#apikey-and-secretkey)
3. [Generate Secure Private Key](#generate-secure-private-key)
4. [Generate HashCode](#generate-hashCode)
5. [Get Token](#gettoken)
6. [Get Assets](#get-assets)
7. [Get Markets](#get-markets)
8. [Get Spot Wallet Balances](#get-spot-wallet-balances)
9. [Get My Active Orders](#get-my-active-orders)
10. [Get My Orders By ID](#get-my-orders-by-id)
11. [Cancel My Orders By ID](#cancel-my-orders-by-id)
12. [Get My Historycal Data](#get-my-historycal-data)
13. [Get Active Orders](#get-active-orders)
14. [Get Active Buy Orders](#get-active-buy-orders)
15. [Get Active Sell Orders](#get-active-sell-orders)
16. [Send a New Sell Order](#send-a-new-sell-order)
17. [Send a New Buy Order](#send-a-new-buy-order)






## System Status
```
"https://apiv1.parex.exchange/echo"
```

 Fetch system status.

```
"https://apiv1.parex.exchange/ping"
```
- Test connectivity to the Rest API.


## Generate Secure Private Key

```
$plaintext = "78cd69434Q00Yc4e11ec2354e8iGdfU6i5UWad5402ca01Mix"; ///apikey
$cipher = "aes-128-gcm"; 
if (in_array($cipher, openssl_get_cipher_methods()))
{
    $ivlen = openssl_cipher_iv_length($cipher);

    $iv = "Uixp8sInuZvBBIY78huLlladrbptBjtf0sNQ71k5";   ///secretkey

    $ciphertext = openssl_encrypt($plaintext, $cipher, $key, $options=0, $iv, $tag);

    echo $ciphertext."\n";  //secure_private_key
}
```


## Generate HashCode
```
$secretkey = "Uixp8sInuZvBBIY78huLlladrbptBjtf0sNQ71k5";   ///secretkey

$newtimestamp = time();
$hash = hash_hmac("sha256",$timestamp,$secretkey);

```



## apikey and secretkey
These variables are completely specific to your user.
Please get it from the parex app


## GetToken
```
"https://apiv1.parex.exchange/getToken"

```
Method : POST 

- The 'GetToken' call returns a token that is used in all subsequent API calls. Since a token is short-lived, it will be necessary to repeat this process to obtain a new token when the previous token expires.

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | secure_private_key |
| hash | String | Yes | [Generate HashCode](#generate-hashCode) |
| timestamp | String | Yes | timestamp |




` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| result | String | Yes | Parex Token  |


## Get Assets
```
"https://apiv1.parex.exchange/getAssets"
```
Method : POST 

- Get information of coins (available for deposit and withdraw) for user.

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | secure_private_key |
| token | String | Yes | Parex Token |
| hash | String | Yes | HashCode |
| timestamp | String | Yes | timestamp |



` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| id | Integer | Yes | Asset ID  |
| shortname | String | Yes | Asset Short Name  |
| assets | String | Yes | Asset Name  |


## Get Markets
```
"https://apiv1.parex.exchange/getMarkets"
```
Method : POST 


- Get information of available market

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | secure_private_key |
| token | String | Yes | Parex Token |
| hash | String | Yes | HashCode |
| timestamp | String | Yes | timestamp |



` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| id | Integer | Yes | Market ID  |
| marketname | String | Yes | Market Name  |
| paircoin | String | Yes | PairCoin ID  |
| maincoin | String | Yes | MainCoin ID  |
| pairinfo | String | Yes | PairCoin Name  |
| maininfo | String | Yes | PairCoin Name  |



## Get Spot Wallet Balances

```
"https://apiv1.parex.exchange/getWalletBalances"
```
Method : POST 


- Get your wallet balances

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | secure_private_key |
| token | String | Yes | Parex Token |
| hash | String | Yes | HashCode |
| timestamp | String | Yes | timestamp |


` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| id | Integer | Yes | line number  |
| address | String | Yes | Wallet Address  |
| shortname | String | Yes | Asset Short Name |
| balance | String | Yes | Balance  |



## Get My Active Orders

```
"https://apiv1.parex.exchange/getMyOrders"
```
Method : POST 


- Get your orders

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | secure_private_key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |
| hash | String | Yes | HashCode |
| timestamp | String | Yes | timestamp |


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


## Get My Orders By ID
```
"https://apiv1.parex.exchange/getMyOrdersByID"
```
Method : POST 


- Get your orders by ID

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | secure_private_key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |
| orderid | String | Yes | Parex Market Order ID |
| hash | String | Yes | HashCode |
| timestamp | String | Yes | timestamp |


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



## Cancel My Orders By ID

```
"https://apiv1.parex.exchange/cancelMyOrdersByID"
```
Method : POST 


- Cancel your Order By ID

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | secure_private_key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |
| orderid | String | Yes | Parex Market Order ID |
| hash | String | Yes | HashCode |
| timestamp | String | Yes | timestamp |



` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| orderid | Integer | Yes | orderID |
| marketid | String | Yes | Parex Market ID |
| marketname | String | Yes | Parex Market Name |


## Get My Historycal Data

```
"https://apiv1.parex.exchange/getMyHistory"
```
Method : POST 


- Get your historical orders
Get trades for a specific account and symbol,Only the transaction records in the past 1 month can be queried. If you want to view more transaction records, please use the export function on the web side, which supports exporting transaction records of the past 3 years at most.


` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | secure_private_key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |
| hash | String | Yes | HashCode |
| timestamp | String | Yes | timestamp |



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



## Get Active Orders

```
"https://apiv1.parex.exchange/getOrders"
```
Method : POST 


- Get all open buy orders on a symbol. Careful when accessing this with no symbol.

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | secure_private_key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |
| depth | String | No | Limit |
| hash | String | Yes | HashCode |
| timestamp | String | Yes | timestamp |



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



## Get Active Buy Orders

```
"https://apiv1.parex.exchange/getBuyOrders"
```
Method : POST 


- Get all open buy orders on a symbol. Careful when accessing this with no symbol.

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | secure_private_key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |
| depth | String | No | Limit |
| hash | String | Yes | HashCode |
| timestamp | String | Yes | timestamp |



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



## Get Active Sell Orders

```
"https://apiv1.parex.exchange/getSellOrders"
```
Method : POST 

- Get all open sell orders on a symbol. Careful when accessing this with no symbol.



` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | secure_private_key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |
| depth | String | No | Limit |
| hash | String | Yes | HashCode |
| timestamp | String | Yes | timestamp |


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


## Send a New Sell Order

```
"https://apiv1.parex.exchange/setSellOrder"
```
Method : POST 


- Set new Sell Order

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | secure_private_key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |
| amount | String | Yes | Amount  |
| price | String | Yes | Price  |
| total | String | Yes | Total  |
| hash | String | Yes | HashCode |
| timestamp | String | Yes | timestamp |


` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| orderid | Integer | Yes | orderID |
| marketid | String | Yes | Parex Market ID |
| marketname | String | Yes | Parex Market Name |


## Send a New Buy Order

```
"https://apiv1.parex.exchange/setBuyOrder"
```
Method : POST 


- Set new Buy Order

` --- INPUT  --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| apikey | String | Yes | Parex API Key |
| secretkey | String | Yes | secure_private_key |
| marketid | String | Yes | Parex Market ID |
| token | String | Yes | Parex Token |
| amount | String | Yes | Amount  |
| price | String | Yes | Price  |
| total | String | Yes | Total  |
| hash | String | Yes | HashCode |
| timestamp | String | Yes | timestamp |


` --- OUTPUT --- `
| Name | Type         | Mandatory| Description |
| :--: | :---------- | :------ | :--------- |
| orderid | Integer | Yes | orderID |
| marketid | String | Yes | Parex Market ID |
| marketname | String | Yes | Parex Market Name |


- MARKET orders using the quantity field specifies the amount of the base asset the user wants to sell at the market price
For example, sending a MARKET order on BTCUSDT will specify how much BTC the user is selling.
- MARKET orders using quoteOrderQty specifies the amount the user wants to spend (when buying) the quote asset; the correct quantity will be determined based on the market liquidity
- Using BTCUSDT as an example:
On the BUY side, the order will buy as many BTC as quoteOrderQty USDT can.
On the SELL side, the order will sell the quantity of BTC.


