## Register Order Report
If you want to catch order or match report, one can define a function and register

### Stock
```python
def OrderReportHandler(result, msg):
        order_result = {'result'    : result.ResultType,
                        'status'    : result.StatusCode,
                        'desc'      : result.CodeDesc,
                        'order_guid'    : result.OrderGuid,
                        'net_no'    : result.ClOrdID
                        }

        if result.ResultType=='1':
            report = result.ExcReport
            exe_report = {'order_id'  : report.OrderID,
                        'orig_net_no'   : report.OrigClOrdID,
                        'execute_status'    : report.ExecType,
                        'account_no'    : report.Account,
                        'symbol'    : report.Symbol,
                        'side'      : report.Side,
                        'quantity'  : report.OrderQty,
                        'price'     : report.Price,
                        'strike_quantity'   : report.LastQty,
                        'strike_price'   : report.LastPx,
                        'transaction_time'  : report.TransactTime}

agent.OrderReportEvent += OrderReportHandler
```

### Futures
```python
def OrderReportHandler(code, msg):
    dict_msg = dict((agent.msg_tag[k], v) for k,v in [tag.split('=') for tag in msg.split('|')])
    print(dict_msg)

agent.OnFOrderReport += OrderReportHandler
```
<br/>
<p style="text-align:left;">
    [🏠 Back to main page](../index.md)
    <span style="float:right;">
        <a href="#top"><font size="5">⮉</font><font size="3">Back to top</font></a>
    </span>
</p>