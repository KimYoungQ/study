EC2 서버에 접속 및 리룩스 서버 설정
===

윈도우 운영체제에서만 접속하는 법만 다룹니다.

윈도우에서는 ssh 접속하기엔 불편한 점이 많아 별도의 클라이언트 putty를 사용하여 진행한다.

putty사이트(http://www.putty.ory)에서 실행파일을 다운받는다.

실행파일은 2가지다

> * putty.exe
> * puttygen.exe

puttygen.exe 파일을 실행한다.

putty는 pem 키로 사용이 안되며 pem 키를 ppk 파일로 변활을 해야만 한다. puttygen은 이 과정을 진행해 주는 클라이언트이다.

<br/>

ppk 파일 생성 및 접속
---

![puttygen](https://user-images.githubusercontent.com/45932388/110197051-31259580-7e8c-11eb-8e0b-1a3cf138584d.png)

![ppk파일생성_LI](https://user-images.githubusercontent.com/45932388/110197065-47335600-7e8c-11eb-96ee-0a88f3aba1cf.jpg)

<br/>

ppk 파일이 생성되었다면 putty.exe 파일을 실행해 주자.

<br/>

![putty설정(1)](https://user-images.githubusercontent.com/45932388/110197210-68e10d00-7e8d-11eb-83b7-624ceaf8a1a2.PNG)

<br/>

> * HostName : username@public_lp 를 등록한다. 우리가 생성한 Amazon Linux는 ec2-user가 username이라서 ec2-user@탄력적 IP 주소를 등록하면 된다.
> * port : 접속 포트인 22를 등록한다.
> * Connection type : SSH를 선택한다.

<br/>

![putty설정(2)](https://user-images.githubusercontent.com/45932388/110197217-6e3e5780-7e8d-11eb-8310-454d4273c120.PNG)

<br/>

왼쪽 메뉴에 있는 Connection -> SSH -> Auth에 들어가 Browse...버튼을 클릭해 좀 전에 생성한 ppk 파일을 선택해서 불러온다.

<br/>

![putty설정(3)_LI](https://user-images.githubusercontent.com/45932388/110197222-74343880-7e8d-11eb-85c9-fe5598915b79.jpg)

<br/>

Saved Sessions에 저장을 한뒤 open을 클릭하고 SSH 접속 알림이 등장하면 [예]를 클릭한다.

<br/>

![ec2접속성공](https://user-images.githubusercontent.com/45932388/110197226-7a2a1980-7e8d-11eb-8cb5-a838271938df.PNG)

<br/>

SSH 접속이 성공한 것을 확인할 수 있다.

<br/>

아마존 리눅스 2서버 설정
---

자바 기반의 웹 애플리캐이션이 작동해야하는 서버에서 필수로 해야하는 설정들

> * *알맞은 java 버전 설치*  : 프로젝트에 맞는 java 버전 설지
> * *타임존 변경*  : 기본 서버의 시간은 미국 시간대이다. 한국 시간대가 되어야만 우리가 사용하는 시간이 모두 한국 시간으로 등록되고 사용된다.
> * *호스트네임 변경*  : 현재 접속한 서버의 별명을 등록한다. 실무에서는 한대의 서버가 아닌 수십 대의 서버가 작동 되는데, 
>                      IP만으로 어떤 서버가  어떤 역할을 하는지 알 수 없다. 이를 구분하기 위해 보통 호스트 네임을 필수로 등록한다.

<br/>

### 알맞은 java 버전 설치

EC2와 연동할 프로젝트가 java 11이므로 버전에 맞게 설치를 한다. 
```
sudo amazon-linux-extras install java-openjdk11
```
명령어를 입력해준다.

<br/>

### 타임존 변경


EC2 서버의 기본 타임존은 UTC이다. 세계 표준 시간으로 한국과 9시간 차이가 발생한다. 그러므로 한국시간(KST)로 수정해주어야 한다.

```
sudo rm /etc/localtime
sudo ln -s /usr/share/zoneinfo/Asia/Seoul /etc/localtime
```



---
[ 출처 ] : [스프링 부트와 AWS로 혼자 구현하는 웹서비스](http://www.yes24.com/Product/Goods/83849117?OzSrank=1)   


