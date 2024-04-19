## 현재 내 git 설정을 보고 싶다

git config --list

## 초기 username, password 등 최초 설정
git config --global user.name "my name"
git config --global user.password "my password" -> 요즘은 password 안 쓰고 토큰만 쓰도록 바뀌었다는데..흠 
git config --global credential.helper store   -> 토큰 한번 저장하면 그 다음부터는 안 묻도록

이 두 줄은 필요한건지 모르겠다. 강의시간에는 안 나온것같은데 내가 안돼서 구글링하며 찾은거라..
git config --global credential.https://github.com.username <username>
git config --global credential.https://github.com.token <token>

## 스테이징
git add filename

## 커밋
git commit
-> commit message를 입력하는 vi파일이 나오는데, 입력 후 :wq

## 푸시
git push origin branchname -> 최초에 푸시를 하면 토큰을 입력하라고 나온다.

## 꿀팁
git config --global alias.lg "log --graph --pretty=tformat:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --decorate=full"
로그(git status 등)를 깔끔하게 볼 수 있다!
