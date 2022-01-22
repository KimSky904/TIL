## IP와 도메인

## 💡 IP
    IP란?    
        Internet Protocol, 인터넷 통신   

    IP주소?
        인터넷 통신을 주고받기 위해 가지고 있는 특정 주소


* 우리가 사용하고 있는 컴퓨터, 스마트폰 모두 특정 IP주소를 가지고 있다.   
* 서버와 웹사이트도 마찬가지로 특정 IP주소를 가지고 있다.

<br>

👉 *컴퓨터와 서버 모두* **고유한 IP주소값을 가지고 있기 때문에**   
 *컴퓨터가 서버의 IP주소에 접속하여 원하는 홈페이지를 요청할 수도 있고, 서버는 나의 IP주소에 접속하여 요청에 답하면서 통신이 일어난다.*

<br>


* 웹사이트에 접속할 수 있는 방법은 두 가지로 나뉜다.
    + 도메인 네임(Domain Name)
    + IP주소 

<br>

컴퓨터가 원하는 웹사이트에 접속하려면 github.com이라는 도메인 네임을 입력하여 접속할 수 있고,   
12.34.56.78(임의의 주소값)을 입력하여 접속할 수 있다.

<br>

하지만 실제로 우리는 **IP주소를 입력하여 웹서비스에 접속하지는 않는다.**   
수많은 IP주소들을 외울 수 없기 때문이고, 외울 필요도 없기 떄문이다.


우리가 IP주소를 외우지 않고도 쉽게 github.com 등의 이름으로 웹서비스에 접속할 수 있는 것은
DNS이 존재하기 때문이다.

<br><br><br>




## 💡 DNS
    앞서 말했던 웹사이트에 접속할 수 있는 방법 중 첫번째가 도메인 네임이라는 것을 떠올려보자.

* 우리는 웹서비스(웹사이트)의 '이름(github.com)'을 알고 있기 떄문에 좀 더 쉽고 빠르게 외우거나 검색하여 접속할 수 있다.


* 이때 github.com, google.com, naver.com 등 우리가 입력하는 **웹서비스(웹사이트)의 이름이 도메인 네임이다.**

* 도메인 네임은 사실 IP주소와 동일한 값을 가지고 있다.

<br>


👉 ***그렇다면 컴퓨터는 실제 서버에 접속할 때 'github.com'을 바로 12.34.56.78로 번역하여 이동하는 것일까?***

**따지자면 아니다.**

<br>

컴퓨터는 실제로 서버에 접속할 때에는 도메인 네임이 아닌 IP주소를 사용함으로써 접속한다.  
즉, 도메인 네임은 식별자가 될 수 없다.  
그렇다면 어떻게 도메인 네임을 입력했는데 IP주소로 서버에 접속할 수 있을까?

<br>


이를 가능하게 하는 것이 **DNS**이다.   

    DNS란?
        Domain Name System
        Domain Name이 동작하는 시스템

* Domain Name은 IP의 이름과 같다고 위에서 언급했다.
    + DNS는 IP와 Domain Name(IP의 이름)을 연결하는 시스템으로 이해하면 쉽다.

<br>

❗ DNS의 동작과정을 통해 이해해보자.          

    노트북에서 github.com에 접속한다고 가정해보자.

    사용자는 주소창에 github.com 즉 도메인 네임(IP의 이름)을 입력한다.

<img src="https://github.com/KimSky904/TIL/blob/master/AWS/img/search-github.PNG?raw=true"  >


    노트북은 github.com의 IP주소를 모른다.
    때문에 노트북은 Name Server에 'github.com'이라는 도메인 네임(IP의 이름)을 가진 웹서비스의 IP주소를 요청한다. 

<img src="https://github.com/KimSky904/TIL/blob/master/AWS/img/name-server1.PNG?raw=true" style="width: 480px">


    
    Name Server는 모든 도메인 네임(IP의 이름)과 IP의 관계를 알고 있는 서버이다. 즉 IP의 이름과 내용을 연결시켜주는 역할을 한다.

<img src="https://github.com/KimSky904/TIL/blob/master/AWS/img/name-server2.PNG?raw=true"  target="_blank"  style="width: 250px"><img src="https://github.com/KimSky904/TIL/blob/master/AWS/img/name-server3.PNG?raw=true" style="width: 480px" >


    Name Server가 github.com에 대한 IP주소를 응답하면, 노트북은 이제 원하는 사이트의 IP주소를 알기 때문에 해당 IP에 해당하는 컴퓨터(웹)에 접속할 수 있다.

<img src="https://github.com/KimSky904/TIL/blob/master/AWS/img/name-server4.PNG?raw=true" style="width: 480px">












