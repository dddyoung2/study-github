# ch04. reset & checkout
> 복원을 하기위한 reset, checkout에 대해 공부한다.

## 커밋 가리키기
- `git log --oneline --graph --all`을 하면 모든 브랜치 역사에 대해 그래프 형태로 한줄씩 요약하여 출력됨
- `git show` 명령어를 활용하는데, 이때 HEAD포인터를 이용하거나 체크섬을 활용해 무슨 내용인지 추적할 수 있음
    - `git show` opt
        - `^`: HEAD 포인터나 체크섬에 ^를 붙이면 개수만큼 부모를 거슬러 올라가 가리킴
        - `^0`: ^ 뒤에 숫자를 붙이면 브랜치의 경우 가리키는 대상을 조절할 수 있음
            - 빠른 숫자가 상위(merge 된 브랜치)이고, 이후 숫자는 하위(merge 한 대상) 브랜치임
        - `~`: 끝에 ~과 숫자를 붙이면 숫자만큼 거슬러 올라가는데, 하위 브랜치를 무시하고 상위들만 바라봄, ~ == ~1

## 명령어
- `git reset`: HEAD를 이동시키거나, Index를 업데이트시키거나, 워킹 디렉터리를 업데이트 시킴
    - `--soft {checksum|HEAD-pointer}`: HEAD 이동  
    지정한 지점으로 HEAD 포인터를 이동시켜 즉, 그 당시로 돌아감. 다만, 돌아가면서 업데이트된 최신기록들은 staged 상태가 되어 사라지지 않음  
    commit message를 잘못 적었거나 등에 사용, `git commit --amend`와 동일함. 분할해서 할 뿐.
    - `--mixed {checksum|HEAD-pointer}`: HEAD 이동  
    지정한 지점으로 HEAD 포인터를 이동시켜 즉, 그 당시로 돌아감. 다만, 돌아가면서 업데이트된 최신기록들은 unstaged 상태가 되어 사라지지 않음  
    대대적 수정이 필요하거나, `git add .`을 실수로 사용하여 과하게 staged 시켰을 때 사용
    - `--hard {checksum|HEAD-pointer}`: HEAD 이동  
    지정한 지점으로 HEAD 포인터를 이동시켜 즉, 그 당시로 돌아감. 다만, 돌아가면서 업데이트된 **물리적 기록들도 같이 돌아가 사라짐.**
    - `{file-name}`: staged 상태인 대상 파일을 unstaged 상태로 끌어내림
    - `{checksum|HEAD-pointer} {file-name}`: 

- `git checkout`: 