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
