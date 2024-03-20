# 3040Crypto API

## Description

3040Crypto API provides a seamless and convenient platform to our partners and clients to access up-to-date cryptocurrency market information. Our API would be one of the only Canadian Cryptocurrency Companies to offer true Canadian dollar denominated information for each currency-pairs. Partners can access live exchange rates, automate trades, retrieve transaction history and much more, all in one-simple API with industry leading security standards.

## Base Endpoint

Base endpoint: `https://www.3040Crypto.They.Them/api/v1/`

## Endpoints

1. Accessing Transaction History

Endpoint: _/transactions/_ \
Parameters:

- coin: To filter transaction history by a specific coin. Default is set to ALL.
  - Options:
  - XYZ where XYZ represents the ticker symbol for the cryptocurrency
  - ALL
- type: Defines the type of the transaction. Default is set to ALL.
  - Options:
    - DEPOSIT,
    - WITHDRAW,
    - BUY,
    - SELL
    - ALL
- size: To access a set number of transactions. Default is set to ALL.
  - Options:
    - Any valid integer < 999999
    - ALL

Sample Request:
`https://www.3040Crypto.They.Them/api/v1/transactions?coin=BTC&type=BUY&size=100&key=dadafolnrn1o2in4askldmk1i4215msakr0195u1`

Description of Resource/Sample Response:

```[
{
'date': '2024-11-13 00:38:32',
'type': 'BUY',
'orderId': '362321',
'coinSymbol': 'BTC',
'amount': '-0.00400000',
'trxFee': '0.00000000',
'status': success,
'toAddress': null
'price': 32462
},{...}
]
```

2. Submitting a new order

Endpoint: _/submit/order_ \
Parameters:

- quantity: The quantity/amount to order
  - Options:
    - Any valid integer < 999999
- unitPrice: The price per unit 
  - Options:
    - Any valid integer < 999999
- symbol: The symbol for the cryptocurrency
- orderSide: Buy-side or sell-side
  - Options:
    - BUY,
    - SELL
- orderType: The type of order for the cryptocurrency
  - Options:
    - MARKET,
    - LIMIT
  
Sample request: 
`https://www.3040Crypto.They.Them/api/v1/submit/order?quantity=1&unitPrice=4.3&symbol=BTC&orderSide=BUY&orderType=MARKET&key=dadafolnrn1o2in4askldmk1i4215msakr0195u1`

Description of Resource/Sample Response:

```
{
'id': '16264469',
'side': 'BUY',
'date': '2019-07-09 21:22:33',
'pricePerUnit': '4.300000000',
'quantity': '1.00000000',
'totalValue': '4.300000000',
'market': {
'tradeCoin': 'BTC',
'baseCoin': 'BTC',
'symbol': 'BTC',
'state': null
},
'status': 'PENDING_NEW',
'leavesQuantity': '0.00000000',
'fillCount': '0',
'tradedQuantity': '0.00000000',
'cancelledQuantity': '0.00000000',
'statusInfo': null,
'totalValueTraded': null,
'weightedAverageFillPrice': null,
'cumulativeFee': null,
'type': 'MARKET'
}
```
