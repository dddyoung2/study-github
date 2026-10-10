# ch03. branch
> 깃에서 쓰이는 브랜치에 대해서 공부했습니다.

## 브랜치 관련 개념
- 브랜치 활용 방식
    - 협업하는 기반이 됨
    - 각 담당자가 새로운 브랜치를 생성, 분리되어 별도 공간에서 개발함. 즉, 공통된 정보를 소유하고 있는 main에서 시작하여 각자가 담당한 새로운 기능들을 별도 공간에서 개발!
    - 완성이후, 브랜치를 병합하여 전체를 통합
- 브랜치 유의 사항
    - 한 브랜치를 오래 갖고 있으면 main과의 차이가 심해 merge 하는 도중 충돌 확률이 매우 높아짐
    - 기능별 잘 나누어 한 브랜치를 갖고 있는 시간을 최소화하고, 완료하면 바로 main 병합 준비를 해야함
    - 별도 공간을 바라보고 있지만 협업의 과정에서 겹치는 부분을 건드리게 되면 병합에 있어 충돌이 발생하므로 브랜치를 작게작게 갖고 있어야 함
- main 브랜치: git이 기본적으로 생성하는 브랜치. 즉, 시작점이므로 보통 병합을 하면 이 브랜치에 합침. 예전에는 master 브랜치라고 불렀다고 함.
- HEAD Pointer: 현재 작업 중인 로컬 브랜치를 가리킴.
    - `main`에서 작업 중이면 HEAD -> `main`
    - `feat/user-admin` 브랜치에서 작업 중이면 HEAD -> `feat/user-admin`

## 명령어
- `git branch`: 존재하는 branch 확인 명령어
- `git branch {branch-name}`: branch를 생성하는 명령어
    - opt
        - `--merged`
        - `--no-merged`
        - `-d`
        - `-D`: **브랜치 삭제 강제 옵션**
- `git checkout {branch-name}`: HEAD를 지정한 브랜치로 이동시키는 명령어.
    - opt
        - `-b`: `git branch {branch-name}` + `git checkout {branch-name}`을 할 수 있음
- `git remote`
    - opt
        - `add`
        - `-v`
        - `show`
- `git fetch`

## 협업 과정