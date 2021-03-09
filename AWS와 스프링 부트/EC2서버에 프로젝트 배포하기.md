EC2서버에 프로젝트 배포하기
===

먼저 git 을 설치해준다.

```
$ sudo yum install git
```

완료 후 설치 상태를 확인한다.

```
git --version
```

git clone 할 디렉토리를 생성해준다.

```
$ mkdir ~/app && mkdir ~/app/step1
```

생성된 디렉토리로 이동한다.

```
$ cd ~/app/step1
```

git clone를 진행한다
```
$ git clone 주소
```

메이븐 빌드를 하기위해 mvnw 권한을 주고 빌드를 한다
```
chmod +x mvnw
```
```
./mvnw clean package
```

