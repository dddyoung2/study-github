# ch01. 준비
> 깃과 깃허브 기본 세팅에 대해 기록했습니다.

## Git 사용자 정보 설정
``` bash
git config --global user.name "{user.name}"
git config --global user.email "{user.email}"
git config --global init.defaultBranch main
git config --global core.editor vim
```
- `--global` 옵션은 전체 프로젝트에 대해 적용하겠다는 뜻.

## 깃허브  프로젝트를 로컬로 복제하기
먼저, 복제할 깃허브 프로젝트의 URL을 복사한다.
![캡처1](https://github.com/user-attachments/assets/3d1740ee-73c3-43ce-9fd1-66240eb29924)
  
`git clone {repo-URL}`을 수행한다.
- opt `-o`: 리모트 저장소 이름을 지정 가능함 

## 복제 확인하기
```bash
ls
cd {repo-name}
ls -a
git remote -v
```
- 상위 디렉터리에서 복제한 레포 이름이 잘 출력되는지 확인
- 복제한 레포로 이동한 후, 해당 레포 내 파일 정보를 a 옵션을 활용해 .git이 있는지 확인
- 이후 `git remote -v` 로 잘 연결되었는지 확인.

## 복제 없이 깃 추적 활성화
- 추적 활성화할 대상 디렉터리에 가서 `git init`
- 깃 추적이 활성화 되었는지 복제와 마찬가지로 `ls -a`를 통해 `.git`을 확인하면 됨

## git 추적 무시 관리 (.gitignore)
- .gitignore 파일을 통해 별도 지정한 파일들을 추적을 무시할 수 있음
```plaintext 
# [abc] 문자 집합 중 하나
file[abc].txt == filea.txt fileb.txt filec.txt 전부 무시

# [0-9] 범위 지정
file[0-9].txt == file0.txt ~ file9.txt까지 무시

# 확장자 무시
.a
.o
...

# 중요파일 무시
.env

# 무시 제외
!system.a

# 현재 디렉터리 기준 직속 하위파일명만 예외. 즉, 하위폴더 내 같은 이름 파일이어도 그것은 무시안함.
/TODO (./TODO만 무시, ./fake/TODO 는 무시안함)

# 해당 디렉터리의 지정 파일만 무시
doc/*.txt 

# 디렉터리 이하 전부 무시
fake/

# 해당 디렉터리의 이하 모든 대상 파일 무시
a/**/*.txt (a 디렉터리 밑의 모든 txt파일은 어디이 위치하든 상관없이 전부 무시.)
```
## 관련 명령어 정리
```bash
git config --global {key.value}
git clone {repo-URL}
git remote -v
git init

ls -a
cd {repo-name}
```