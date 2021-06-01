## 파이썬 주식 투자 자동화 강의 코드
### 증권사 API를 활용하여 대신증권 프로그램에서 주식이나 펀드를 자동매매를 하는 코드입니다.
### 파일 구성
-  1.txt : commit 확인을 위한 test파일
-  AutoConnect.py : creon 프로그램에 id 와 pw 를 입력하여 자동으로 로그인 해주는 파일
-  Manual.txt : 실행 방법을 알려주는 파일
-  autoTrade.py 실행 파이썬 파일
-  test.py : 실행이 잘 되는지 확인 하기 위한 파일
-  강의 보러가기: https://www.youtube.com/watch?v=s24dxIp-Cp0


# Installation
~~~
$ pip install slacker
~~~
# Examples
~~~
from slacker import Slacker

slack = Slacker('<your-slack-api-token-goes-here>')

# Send a message to #general channel
slack.chat.post_message('#general', 'Hello fellow slackers!')

# Get users list
response = slack.users.list()
users = response.body['members']

# Upload a file
slack.files.upload('hello.txt')

# If you need to proxy the requests
proxy_endpoint = 'http://myproxy:3128'
slack = Slacker('<your-slack-api-token-goes-here>',
                http_proxy=proxy_endpoint,
                https_proxy=proxy_endpoint)

# Advanced: Use `request.Session` for connection pooling (reuse)
from requests.sessions import Session
with Session() as session:
    slack = Slacker(token, session=session)
    slack.chat.post_message('#general', 'All these requests')
    slack.chat.post_message('#general', 'go through')
    slack.chat.post_message('#general', 'a single https connection')
    ~~~



### by 유튜브 조코딩 채널
