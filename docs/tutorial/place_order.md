## Place Order
After login to the API **{==successfully==}**, can start to use the **{==order==}** function to place the order.

!!! note
    Parameters can be convert to correctly string for API by constant function.<br>
    ex:<br>
    To convert LotType's ROUND_LOT to correctly string for API.<br>
    → constant.LotType.ROUND_LOT.value

### Stock
If you want to place a **new** order of **stcok**, stock symbol as **6016** and price in **10.0** with other settings like lot type
as **RoundLot**, order type as **Ordinary**, price flag as **FIX**, day trade flag as **DayTradeFlag** ,and time force as ROD.
Based on this situation, we will pass these parameters into **{==order==}** function.
```python
from conrich.Stock import constant

result = agent.order(action = constant.Action.NEW_ORDER.value,
                     branch_no = '8450',
                     account_no = "YOUR_ACCOUNT",
                     lot_type = constant.LotType.ROUND_LOT.value,
                     order_type = constant.OrderType.ORDINARY.value,
                     side = constant.Side.BUY.value,
                     day_trade_flag = constant.DayTradeFlag.N.value,
                     symbol = '6016',
                     quantity = 1,
                     price = 10.0,
                     price_flag = constant.PriceFlag.FIX.value,
                     time_in_force = constant.TimeInForce.ROD.value)
```
### Futures
If you want to place a **new** order of **futures**, stock symbol as **TXFI0** and price in **12000.00** with other settings like
compound type as **Single**, time force as **ROD**, write off as **AUTO** ,and order type as **LIMIT**.
Based on this situation, we will pass these parameters into **{==order==}** function.
```python
from conrich.Futures import constant

result = agent.order(action = constant.Action.NEW_ORDER.value,
                     branch_no = 'F029000',
                     account_no = "YOUR_ACCOUNT",
                     market_type = constant.Market.FUTURES.value,
                     compound_type = constant.CompoundType.FUTURES_SINGLE.value,
                     commodity = 'TXFI0',
                     time_in_force = constant.TimeInForce.ROD.value,
                     writeoff = constant.WriteOff.AUTO.value,
                     order_type = constant.OrderType.LIMIT.value,
                     side = constant.Side.BUY.value,
                     quantity = 1,
                     price = 12000.00)
```
### Foreign Futures
If you want to place a **new** order of **foreign futures** in **NYM**, stock symbol as **QM**, contract time on **2020/10** and stop price in **42.95**
with other settings like put_call as **None**, write off as **OPEN** ,and foreign order type as **LIMIT**.
Based on this situation, we will pass these parameters into **{==order==}** function.
```python
agent.order(action=constant.Action.NEW_ORDER.value,
            branch_no = 'F029000',
            account_no = "YOUR_ACCOUNT",
            exchange = 'NYM',
            side1 = constant.Side.BUY.value,
            market_type1 = constant.Market.FUTURES.value,
            commodity1 = 'QM',
            commodity_month1 = '202010',
            strike_price1 = 0,
            put_call1 = constant.PutCall.NONE.value,
            side2 = '',
            market_type2 = '',
            commodity2 = '',
            commodity_month2 = '',
            strike_price2 = 0,
            put_call2 = constant.PutCall.NONE.value,
            order_type = constant.ForeignOrderType.LIMIT.value,
            price = 0,
            price_numerator = 0,
            price_denominator = 0,
            stop_price = 42.95,
            stop_price_numerator = 0,
            stop_price_denominator = 0,
            quantity = 1,
            writeoff = constant.Writeoff.OPEN.value)
```
<br>
<p style="text-align:left;">
    [🏠 Back to main page](../index.md)
    <span style="float:right;">
        <a href="#top"><font size="5">⮉</font><font size="3">Back to top</font></a>
    </span>
</p>