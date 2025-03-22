Приложения для отслеживания валютных пар, работает со следующеми биржами:
- Binance
- Bybit
- Bitget
- Kucoin
  
  По требованиям реализовано через Rest:
```csharp
public interface IRestExchangeClient
{
    Task<decimal> GetPriceAsync(string firstCoin, string secondCoin);
    ExchangeType GetExchangeType();
}
```
И WebSocket интерфейсы:
```csharp
public interface ISocketExchangeClient
{
    public event Action<decimal>? NewTrade;
    Task SubscribeTrades(string firstCoin, string secondCoin);
    Task UnsubscribeTrades(string firstCoin, string secondCoin);
    ExchangeType GetExchangeType();
}
```

Пример работы:
![ezgif-49d4ab8bd3cce4](https://github.com/user-attachments/assets/5fa837d2-c297-4083-a44f-f5ba01a71e7c)
