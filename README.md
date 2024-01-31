# Server Docs
## 스크립트 이름 작성법
**작성자의 이니셜 - 스크립트의 주요 기능이나 그를 포괄하는 이름**

ex) 작성자 - podo, 스크립트의 주요 기능 loadingscreen

=> pd-loadingscreen

## 스크립트 제작하는 방법
### github 권한이 있을때
1. github에서 파일을 자신의 컴퓨터로 내려받는다.
    
      1-1. github 명령어를 통해 내려받는다.
            
          1. git을 내려받기 및 설치한다 ( https://git-scm.com/downloads )
          2. git을 처음 내려받는 것이라면 계정을 연동해준다.
            ex) git config --global user.name "당신의 유저 이름"
                git config --global user.email "당신의 이메일"
          3. 자신의 저장소에 git을 연동해준다.
                git init
                git remote add origin 레퍼지토리 링크(ex: https://github.com/podo24/ServerDocs.git)
                git pull origin 다운받을 branch(ex: main 또는 master)
    
2. github branch를 만든다 ex) loadingscreen

        branch 만들기
          git branch 브랜치 이름(ex: loadingscreen)
       
        branch 지우기
          git branch -D 브랜치 이름
    
      2-1. vscode를 사용할시 github branch를 변경 해준다 ex) github branch loadingscreen
3. server-data에 스크립트 폴더에 자신의 스크립트를 분류에 맞게 배치한다.
4. 개발이 완료되었을시 테스트를 진행 후 회의를 통해 업로드 후 main branch에 병합을 한다.

---

### github 권한이 없을때
1. 
