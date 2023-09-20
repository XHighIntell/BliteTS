# bliteTS
bliteTS is an open-source, browser-platform JavaScript runtime. The main target of bliteTS is Edge/Chrome extension. Blite is not compatible with NodeJs runtime.

# Targeted Features
✅ Spot  
❌ Margin  
✅ USD-M Future  
❌ COIN-M Future  

## Namespace Structure
```ts
{} blite
├──⚡ buildQueryString(object, bool): string
├──⚡ HMACSHA256(apiSecret: string, message: string): Promise<string>
├──🔩 environments
│  ├── testnet
│  └── live
├──📦 ApiCredentials(string, string)
│  ├──⚡ sign(object): Promise<object>
│  └──⚡ signQuery(object): Promise<string>
├──{} spot
│  ├──📦 BliteClient
│  │   ├──🔒 market: BliteClientMarket 
│  │   │  ├──⚡ exchangeInfo(string[]?)
│  │   │  └──⚡ getKlines(string, KlineInterval, number, number, number)
│  │   ├──🔒 account: BliteClientAccount 
│  │   │  ├──⚡ startUserStream(ApiCredentials)
│  │   │  ├──⚡ keepAliveUserStream(string, ApiCredentials)
│  │   │  └──⚡ stopUserStreamAsync(string, ApiCredentials)
│  │   ├──🔒 order: BliteClientOrder
│  │   └──🔒 stream: BliteClientStream
├──{} future
│  ├──📦 BliteFutureClient
│  │   ├──🔒 market
│  │   │  ├──⚡ bookTicker
│  │   │  ├──⚡ exchangeInfo
│  │   │  ├──⚡ klines
│  │   │  └──⚡ premiumIndex
│  │   ├──🔒 account
│  │   │  ├──⚡ account
│  │   │  ├──⚡ balance
│  │   │  ├──⚡ getPositionInfo
│  │   │  ├──⚡ startUserStream
│  │   │  ├──⚡ keepAliveUserStream
│  │   │  └──⚡ stopUserStreamAsync
│  │   ├──🔒 order
│  │   │  └──⚡ new
│  │   ├──🔒 stream
│  │   │  ├──⚡ subscribeToBookTicker/unsubscribeToBookTicker
│  │   │  ├──⚡ subscribeToKline/unsubscribeToKline
│  │   │  └──⚡ subscribeToUserData/unsubscribeToUserData
```

## Socket API & Rest API
Blite will use the most latest available feature that is supported by Binance. Spot endpoint will use websocket while margin/future will use rest api.


