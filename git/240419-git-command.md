## 현재 내 git 설정을 보고 싶다?
```bash
git config --list
```


## 내 git 설정을 파일수정 형식으로 수정하고 싶다?
```bash
vi ~/.gitconfig
```


## 초기 username, password 등 최초 설정
```bash
git config --global user.name "my name"

git config --global user.password "my password" -> 요즘은 password 안 쓰고 토큰만 쓰도록 바뀌었다는데..흠 

git config --global credential.helper store   -> 토큰 한번 저장하면 그 다음부터는 안 묻도록
```

이 두 줄은 필요한건지 모르겠다. 강의시간에는 안 나온것같은데 내가 안돼서 구글링하며 찾은거라..
```bash
git config --global credential.https://github.com.username <username>
git config --global credential.https://github.com.token <token>
```


## 스테이징
git add filename



## 커밋
git commit

-> commit message를 입력하는 vi파일이 나오는데, 입력 후 :wq



## 푸시
git push origin branchname -> 최초에 푸시를 하면 토큰을 입력하라고 나온다.



## 꿀팁
git config --global alias.lg "log --graph --pretty=tformat:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --decorate=full"

-> 로그(git status 등)를 깔끔하c게 볼 수 있다!




## Conventional Commits!
1. 제목: 구나 절의 형태로. 구구절절 문장x

2. Importance of Capitalization(O). importanceofcapitalization(X)

3. Prefix

- feat: 기능 개발

- build: 빌드 작업

- fix: 버그패치, 오류 개선

- ci: Continuous Integration

- docs: 문서작업

- chore: 패키지 매니저, 스크립트 등

- test: 테스트 관련

- style: 코드 포매팅

- conf: 환경설정 관련




## .gitignore 파일 작성
https://gitignore.io 들어가서 팀원들이 사용하는 툴, os, 언어 다 넣어서 생성 -> .gitignore에 복붙
