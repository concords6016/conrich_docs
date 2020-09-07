## Register realtime Quote
when you wan to initiate a quote server, you should open and connect to 金好康 first.

```python
from conrich import QuoteServer

def test_get_quote(commodity, topic, value):
    print('[{}][{}] {}'.format(commodity, topic, value))

agent = QuoteServer()
agent.OnQuoteUpdate += test_get_quote

agent.register_topic('2330.TW','Bid')
agent.register_topic('2330.TW','Ask')

topic1 = agent.code_convert(commodity='TXO', commodity_type='P', strike_price=12500, expire_date=datetime(2020, 10, 18), after_hour=True)
agent.register_topic(topic1, 'Bid')
topic2 = agent.code_convert(commodity='TX', commodity_type='F', strike_price=0, expire_date=datetime(2020, 10, 18), after_hour=False)
agent.register_topic(topic2, 'Ask')
```