# ch01. 준비
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

`git clone {repo-URL}`

## 복제 확인하기
``` bash
ls
cd {repo-name}
ls -a
git remote -v
```
- 상위 디렉터리에서 복제한 레포 이름이 잘 출력되는지 확인
- 복제한 레포로 이동한 후, 해당 레포 내 파일 정보를 a 옵션을 활용해 .git이 있는지 확인
- 이후 `git remote -v` 로 잘 연결되었는지 확인.

## 관련 명령어 정리
``` bash
git config --global {key.value}
git clone {repo-URL}
git remote -v

ls -a
cd {repo-name}
```