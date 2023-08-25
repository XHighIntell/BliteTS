## Rest API vs Socket API

```
Market Data Endpoints
☀ GET /api/v3/exchangeInfo             exchangeInfo ✔
   GET /api/v3/depth                    depth
   GET /api/v3/trades
   GET /api/v3/historicalTrades
   GET /api/v3/aggTrades
☀ GET /api/v3/klines                   klines  
   GET /api/v3/avgPrice
   GET /api/v3/ticker/24hr
   GET /api/v3/ticker/price
   GET /api/v3/ticker/bookTicker
   GET /api/v3/ticker
```

```
Account Trade Endpoints
☀ POST /api/v3/order/test              order.test
☀ GET /api/v3/order                    order.status            Query Order (USER_DATA)
☀ POST /api/v3/order                   order.place
☀ DELETE /api/v3/order                 order.cancel
   POST /api/v3/order/cancelReplace     order.cancelReplace     Cancel an Existing Order and Send a New Order
   GET /api/v3/allOrders                allOrders
   GET /api/v3/openOrders               openOrders.status
   DELETE /api/v3/openOrders            openOrders.cancelAll    Cancel all Open Orders on a Symbol
   POST /api/v3/order/oco

```

```
User Data Streams
☀ POST /api/v3/userDataStream
☀ PUT /api/v3/userDataStream
☀ DELETE /api/v3/userDataStream
```

## Namespace Structure
```ts
{} blite
├──🔩 environments
│  ├── testnet
│  └── live
├──📦 ApiCredentials(string, string)
├──{} spot
│  ├──📦 Account
│  ├──📦 BliteClient
│  │   ├──🔒 market: BliteClientMarket 
│  │   └──🔒 order: BliteClientOrder
```

Environment  
  ↓  
BliteClient  
  ↓  
Account  

```
├──🌟 Environment
│  ├──🌟 BliteClient
│  │  ├──🌟 Account
         ├──⚡
```

