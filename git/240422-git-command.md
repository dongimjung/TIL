## 1, 브랜치 조회, 생성, 변경, 삭제

### branch 확인 (로컬, 리모트, 전체)

```
$ git branch
```

```
$ git branch -r
```

```
$ git branch -a
```

### 브랜치 생성

```
$ git branch {branch name}
```

### 브랜치 변경

```
$ git switch {branch name}
```

```
$ git checkout {branch name}
```

\-  git switch는 브랜치 관리에 더 특화되어 있고 브랜치 전환에 초점을 맞추어 설계되었으며, git checkout은 브랜치 전환뿐만 아니라 다양한 작업(파일 복구, 새 브랜치 생성, 특정 커밋 또는 태그로 이동)을 수행할 수 있는 보다 범용적인 명령어이다. Git 2.23 이상을 사용한다면 git switch를 사용하는 것이 좋다.

### 브랜치 삭제

```
$ git branch -D {branch name}
```

## 2\. Trouble Shooting

### 파일이름 혹은 위치 수정(rename)

```
$ mv a.py to. b.py
```

### 변경사항 취소(undo)

```
$ git restore {file name}
$ git restore .  -> 모든 변경사항 취소
```

### 스테이징 취소(unstaging)

```
$ git reset HEAD {filename}
```

※ HEAD는 현재 작업 중인 브랜치의 가장 최근 커밋을 가리키는 포인터

### 직전 커밋메세지 수정(amend)

```
$ git commit --amend
```

\- 만약 더 이전의 커밋메세지를 수정하고 싶다면?  

\-> 과거는 잊어버려라.

### 커밋을 없던 일로 만들기(reset)

```
$ git reset --hard HEAD~{number of commit}
$ git push -f origin {branch name}
```

\- 최근 n개 커밋을 삭제 후 강제 푸시

\- 웬만하면 권장하지 않는다.

\- 협업시에 나의 Local과 clone한 remote repo에서 지워졌다고 해도, 다른 곳에 남아있던 이력으로 인해 살아나거나, 충돌이 발생함.

### 잘못을 인정하고 특정시점으로 되돌리기(revert)

```
$ git revert --no-commit HEAD~{number of commit}..
$ git commit
$ git push origin {branch name}
```

\- 잘못하기 직전 시점으로 되돌리고, 해당 되돌림의 이력을 팀원들에게 전달하여 어떤 문제가 있었고, 어떻게 수행되는지에 대한 뚜렷한 설명 가능
