# Day 16

## Web crawler

pip3 install ==request==  ==lxml==

pre： Website URL 

``` mermaid
graph TB
Right --> Network --> F5 --> Request_URL
```

web =‘http://www.jkl.com.cn/shop.aspx’

UA ={’User-Agent‘: ‘Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.82 Safari/537.36’}

```python
import requests
from lxml import etree

web = 'http://www.jkl.com.cn/shop.aspx'
UA ={'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.82 Safari/537.36'}

#1.grab website from different part
data = requests.get(url=web,headers=UA).text
analyst = etree.HTML(data)
part = analyst.xpath( '//div[@class="infoLis"]//@href')
for place in part:
    web2 = 'http://www.jkl.com.cn/' + place
    data2 = requests.get(url=web2, headers=UA).text
    analyst1 = etree.HTML(data2)
    name = analyst1.xpath('//span[@class="con01"]/text()')
    address = analyst1.xpath('//span[@class="con02"]/text()')
    Tel = analyst1.xpath('//span[@class="con03"]/text()')
    Time = analyst1.xpath('//span[@class="con04"]/text()')
    print(address)
#combine into excel
```