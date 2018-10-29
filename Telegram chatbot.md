## Telegram chatbot

- Bot init

```tex
@Botfather 검색
start 버튼클릭
/newbot 입력
이름생성=>중복가능
username=>
token,url
url 클릭하여 봇 활성화
```

- Send message to chat bot

```python
import requests
token='Telegram chatbot token'
method_name='getUpdates'
url='https://api.telegram.org/bot{}/{}'.format(token,method_name)
update=requests.get(url).json()
user_id=update['result'][0]['message']['from']['id']
method_name='sendmessage'
msg='Hi~!'
msg_url='https://api.telegram.org/bot{}/{}?chat_id={}&text={}'.format(token,method_name,user_id,msg)

```

- Practice:Get Kospi and Send to Chat bot 

```python
import requests
from bs4 import BeautifulSoup
token='My chatbot token'
method_name='getUpdates'
url='https://api.telegram.org/bot{}/{}'.format(token,method_name)
update=requests.get(url).json()

#################
kospi_url='https://finance.naver.com/sise/'
html=requests.get(kospi_url).text
soup=BeautifulSoup(html,'html.parser')
select=soup.select_one('#KOSPI_now').text
#print(update['result'][0]['message']['from']['id'])
#################
user_id=update['result'][0]['message']['from']['id']
method_name='sendmessage'
msg=select
msg_url='https://api.telegram.org/bot{}/{}?chat_id={}&text={}'.format(token,method_name,user_id,msg)
print(requests.get(msg_url))
```

