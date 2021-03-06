EC2 서버에 접속하기
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

### ppk 파일 생성 및 접속
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




