# study-github
> github 공부

## 목적
오픈소스기반기초설계 퀴즈 대비겸 깃허브 및 깃 공부 복습 루틴 설계

## 공부
### 0. 배경 및 특징
  
### 1. 준비
#### Git 사용자 정보 설정
``` bash
git config --global user.name "{user.name}"
git config --global user.email "{user.email}"
git config --global init.defaultBranch main
git config --global core.editor vim
```

#### Git 사용자 정보 확인
`git config --list`

#### 깃허브  프로젝트를 로컬로 복제하기
먼저, 복제할 깃허브 프로젝트의 URL을 복사한다.
`git clone {repo-URL}`

#### 복제 확인하기
``` bash
ls
cd {repo-name}
ls -a
git remote -v
```
