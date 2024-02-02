# Server Docs
## 스크립트 제작 우선도

### 높음

- NPC 시스템

- Quest 시스템

- UI

- LoadingScreen

- 휴대폰

- 옷장 시스템

- Interaction 시스템

### 중간

- 로그인 시스템

- Shop 시스템

- Trade 시스템

- 시세 조정 시스템

- 공장 시스템

- NPC 자동 운영 시스템

### 낮음

- 경찰 시스템

- 구역 시스템

- 직업 시스템

- 조직 시스템

- 정부 관리 시스템

- 공지 시스템

- 물건 시스템

## 스크립트 제작 가이드

### 스크립트 이름 작성법
**작성자의 이니셜 - 스크립트의 주요 기능이나 그를 포괄하는 이름**

ex) 작성자 - podo, 스크립트의 주요 기능 loadingscreen

=> pd-loadingscreen


### 스크립트 업로드 관련

- 스크립트 제작후에 github를 사용하여 공유한다.

- 자신이 만든 스크립트를 깃허브에 Pull Request를 통해 요청할시 상위 권한자를 통해 처리된다.
  - 요청시 자신이 뭘 수정하였고, 추가하였는지 작성할 것 ex) NPC 스크립트를 추가하고, 권한을 받아오기 위해 groups.lua에 npcpermission 추가

- 스크립트를 깃허브에 Merge하기 전 테스트를 반드시 진행한다.

### 스크립트 관련

- lua, C, typescript 중 무엇을 사용해도 상관없다.

- 새로운 함수 또는 이벤트를 만들었을 시에는 주석을 통해 꼭 설명한다.

```
  예시 코드 (Lua)

//text를 요소로 넣으면 채팅창에 출력해주는 함수
function addChat(text)
    TriggerEvent('chat:addMessage', {
        args = { text }
    })
end
```


- 스크립트 제작 중 전역에 선언하는 Event, Command, Data 등은 .md 파일을 통하여 문서화 한다.

```
[CarSpawn]

RegisterCommand('SpawnCar', function(source, args)
  
  ...

end)

Docs

Name : SpawnCar
Type : Command
Description : 차량 id를 입력하면 해당 유저를 차에 태운 상태로 차량을 스폰하는 명령어
```

### UI 관련

- UI는 상황에 맞게 사용한다. ex) 컴퓨터를 누르면 UI가 나온다

  - 다만 UI 사용이 불가피한 상황에서는 사용하도록 한다. ex) NPC와의 대화

- 스크립트에 UI가 들어갈 경우 HUD의 색 테마와 디자인에 통일한다.

- UI는 Vue + Vite를 사용한다.

### DataBase 관련

- 여러번 불러올 필요가 없는 정적 데이터 ( ex) 고유번호, 아이디, 닉네임 ) 는 Main Framework 에 추가해 불러온다.

- 데이터 흐름이 많은 스크립트(동시 데이터 처리량이 100개 이상으로 예상되는 경우)는 데이터 처리 최적화 작업 또는 Redis 등을 사용하여 관리한다.

### 인게임 시스템 관련

- RP와 관련있는 입/출금 내역 또는 팩션의 알림 문자와 같은 것은 휴대폰의 메시지 또는 앱 알림으로 보낸다.

- RP와 관련없는 서버 공지 또는 리붓 알림과 같은 것은 UI 또는 GTA의 Notification을 사용해도 괜찮다.
