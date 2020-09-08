## Login API
Before using functions in conrich, we need to initiate the trade API object and login to it with your ID and passwords.

!!! danger highlight blink "Requirement"
    - Check is your account is **activated** for API trading.
        - If not, please contact us.
    - Check is the **certificate** expired.
        - If certificate is expired, reapply from here [Certuficate Enrollment System](https://raweb.concords.com.tw/RAWEB/CertSearch.jsp).

### Stock
```python
from conrich import StockAPI

agent = StockAPI()
agent.login("YOUR_PERSON_ID", "YOUR_PASSWORD")
```
### Futures
```python
from conrich import FuturesAPI

agent = FuturesAPI()
agent.login("YOUR_PERSON_ID", "YOUR_PASSWORD")
```
### Foreign Futures 
```python
from conrich import ForeignFuturesAPI

agent = ForeignFuturesAPI()
agent.login("YOUR_PERSON_ID", "YOUR_PASSWORD")
```



<br/>
<p style="text-align:left;">
    [🏠 Back to main page](../index.md)
    <span style="float:right;">
        <a href="#top"><font size="5">⮉</font><font size="3">Back to top</font></a>
    </span>
</p>