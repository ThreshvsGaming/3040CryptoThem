# 3040Crypto API

## Description

Our 3040Crypto API will provide a seamless and convenient platform to our partners and clients to access up-to-date cryptocurrency market information. This API will be one of the only Canadian Cryptocurrency Companies to offer true Canadian dollar denominated information for each currency-pairs and partners can access live exchange rates, automate trades, retrieve transaction history and much more, all in one-simple API with industry leading security standards.

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
    - BUY,
    - SELL
    - ALL
- size: To access a set number of transactions. Default is set to ALL.
  - Options:
    - Any valid integer < 999999
    - ALL

Sample Request:
`https://www.3040Crypto.They.Them/api/v1/transactions?coin=BTC&type=BUY&size=100`

Description of Resource/Sample Response:
```
[
{
'date': '2024-11-13 00:38:32',
'type': 'BUY',
'orderId': '362321',
'coinSymbol': 'BTC',
'amount': '-0.00400000',
'status': success,
'price': 32462
},{...}
]
```

2. Submitting a new order

Endpoint: _/submit/order_ \
Parameters:

- amount: The amount to order
  - Options:
    - Any valid float < 999999
- price: The price per unit 
  - Options:
    - Any valid integer < 999999
- coinSymbol: The symbol for the cryptocurrency
- type: Buy or sell
  - Options:
    - BUY,
    - SELL
  
Sample request: 
`https://www.3040Crypto.They.Them/api/v1/submit/order?amount=0.5&price=40000&coinSymbol=BTC&type=BUY`

Description of Resource/Sample Response:
```
[
{
'date': '2024-11-10 00:12:31',
'amount': '0.5',
'price': 39999.5
'status': success,
}
]
```


3. Canceling an order

Endpoint: _/cancel_ \
Parameters:
  - orderId: The ID of the order you wish to cancel

Sample request: 
`https://www.3040Crypto.They.Them/api/v1/cancel?orderId=362321`

Description of Resource/Sample Response:

```
{
'status': success
}
```