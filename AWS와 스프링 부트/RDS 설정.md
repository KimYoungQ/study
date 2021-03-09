RDS 설정하기
===

RDS를 처음 설정하면 다음 3가지를 필수로 해야한다.

> * 타임존
> * Character Set
> * Max Connection

왼쪽 카테고리에서 파라미터 그룹을 선택한뒤 아래그림의 파라미터 그룹생성을 클릭한다.
![파라미터 그룹 생성](https://user-images.githubusercontent.com/45932388/110460285-524ae800-8111-11eb-89c9-429ee45d778c.PNG)

적용될 DB패밀리에 앞의 생성한 DB와 버전이 같아햐한다.
![파라미터 편집](https://user-images.githubusercontent.com/45932388/110460449-8b835800-8111-11eb-9374-b6e048dec1ab.PNG)

생성된 파라미터 그룹이 보이면 클릭하고 파라미터 편집을 누른다.

먼저 `time_zone`를 검색하여 `Asia/Seoul`을 선택한다.

![타임존](https://user-images.githubusercontent.com/45932388/110460598-bf5e7d80-8111-11eb-932e-a36532aafef1.PNG)

다음 `Character Set`을 변경한다

아래 항목 8가지중 character 항목들은 모두 utf8mb4로, collation 항목들은 utf8mb4_general_ci로 변경한다.

utf8mb4부터 이모지를 저장할 수 있으므로 보편적으로 utf8mb4를 많이 사용한다.

> * character_set_client
> * character_set_connection
> * character_set_database
> * character_set_filesystem
> * character_set_results
> * character_set_server
> * collation_connecetion
> * collation_server

![characterset](https://user-images.githubusercontent.com/45932388/110461127-62af9280-8112-11eb-8088-c825f3bf08ee.PNG)

마지막으론 `Max Connecion`을 수정한다.

![maxconnection](https://user-images.githubusercontent.com/45932388/110461720-24ff3980-8113-11eb-852b-f83dbec66e00.PNG)

이제 생성된 파라미터 그룹을 데이터 베이스에 연결해보자.

데이터베이스 항목에서 수정을 클릭한뒤 DB 파라미터 그룹을 방금 생성한 신규 파라미터로 변경한다.

![데이터베이스연결설정](https://user-images.githubusercontent.com/45932388/110461949-727ba680-8113-11eb-9d70-02e2911a5cea.PNG)

### 내 PC에서 RDS 접속하기

EC2페이지의 보안 그룹 항목에서 *EC2에 사용된 보안 그룹의 ID* 를 복사한다.

그 후 복사한 그룹 ID와 본인의 IP를 RDS 보안 그룹의 인바운드로 추가한다.

![인바운드규칙추가](https://user-images.githubusercontent.com/45932388/110463667-8de7b100-8115-11eb-810e-5bbcbc7644b8.PNG)

인텔리제이의 database 탭의 연결을 추가해준다.

Host에는 RDS 정보페이지에서 엔드포인트 값을 복사해서 넣어준다.

![엔드포인트](https://user-images.githubusercontent.com/45932388/110467312-3566e280-811a-11eb-81ef-a01931f752e2.PNG)

![인텔리제이DB연결](https://user-images.githubusercontent.com/45932388/110467208-11a39c80-811a-11eb-8c7e-ce363cac31ad.PNG)

생성된 콘솔 창에 다음과 같이 입력한다.
```
use 앞서 만든 데이터베이스명
```

그리고 현재의 character_set, collation 설정을 확인한다.
```
show variables like 'c%'
```

결과를 조회하면 다른 필드는 utf8mb4로 잘 적용되었는데 character_set_database, collation_connection 2가지항목이 latin1로 되어있다.

이 2개의 항목은 RDS 파라미터 그룹으로는 변경이 안된다. 그래서 직접 수정해주자.

```
ALTER DATABASE 데이터베이스명
CHARACTER SET = `utf8mb4`
COLLATE = 'utf8mb4_general_ci
```

수정 후 다시 확인해준다.

![직접쿼리수정](https://user-images.githubusercontent.com/45932388/110467899-ea010400-811a-11eb-8563-02db766d028f.PNG)

```
select @@time_zone, now();
```

타임존 확인도 해준다.
