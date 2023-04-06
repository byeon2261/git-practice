# git repository 생성

<https://www.daleseo.com/git-init/>
디렉토리를 삭제하면 .git 파일도 삭제되어 git 이력이 사라진다.

1. git init
   1-1. git branch -m main
2. git add .
3. git commit -m "[comment]"
4. github 에서 repository 생성
5. git remote add origin [연결할 주소]
6. git push origin

git에 커밋한 목록을 확인할 수 있다.

    $ git log

(HEAD -> master) : 데스크탑에서 서버로 적용. push

커밋된 내역을 master에 보내준다.

    $ git pust origin master

일부 파일만 stage영역에 추가해준다.

    $ git add story2.txt

현재 딕셔너리에 모든 파일을 stage영역에 추가해준다.

    $ git add .

커밋을 하며 커밋을 할때 message를 추가해줘야하며 -m옵션을 부여한다.

    $ git commit -m "New Chapter!"
    ❯ git commit -m "New Chapter!"
    dquote> ?
    dquote> main
    dquote> master
    dquote> byeon2261
    dquote> "
    [master 4c11089] New Chapter ? main master byeon2261
    1 file changed, 1 insertion(+)
    create mode 100644 story2.txt

최상단 명령어를 입력하였으나 'dquote>'가 뜨면서 계속 입력을 받았으며 message내용에 적용되었다.
...분명 쌍따옴표를 붙여서 끝냈는데 해당 상황이 발생

> 확인해본결과 '!'는 적영되지 않았다. !를 넣어주면서 'dquote>'이 발생된 것으로 확인.

특정 snapshot으로 되돌아 갈 수 있다. 명칭은 log에 있는 별명을 사용한다.

    $ git checkout 4c110897bab422505735906b462643e04c8cef2d

Head를 삭제할 수 도 있다. push된 내용이 지워진다.'--hard' = Delete. 'HEAD^' = HEAD에서 얼마나 갈것이냐 정의.
'^'개수만큼 이전의 커밋으로 돌아간다.

    $ git reset --hard HEAD^

원격저장소인 origin에도 삭제한 내용을 적용한다. 커밋내역은 전부 삭제되게 된다.

    $ git push origin master --force

reset에는 옵션에는 hard, soft, 복합이 있다.
하드리셋은 파일 변경사항을 전부 삭제.
복합리셋은 커밋만 삭제. 파일은 그대로 두며 unstaged영역에 둔다.
소프트리셋은 커밋만 삭제 후 변경된 파일을 stage 영역에 둔다. 되돌린 파일들을 unstaged영역에 두고싶지 않을때 ㅏ

git 전체 내용을 삭제할 수 있다.

    $ rm -rf .git

git을 연결할 수 있다.

    $ git remote add origin [연결시킬 주소]

git 히스토리에서 삭제. <https://velog.io/@yoogail/GitHub%EC%97%90-%EC%9D%B4%EB%AF%B8-%EC%98%AC%EB%A6%B0-%ED%8C%8C%EC%9D%BC-history%EC%97%90%EC%84%9C-%EC%82%AD%EC%A0%9C%ED%95%98%EA%B8%B0>

1. .gitignore에 추가하기

추가 후 커밋, 푸쉬 해준다. 푸쉬하고도 리스트에 해당 파일이 계속 존재한다.
캐시가 남아있어서 나오는 것이므로 캐시를 삭제해야한다.

2. 캐시 삭제하기

   $ git rm -r --cached .

위

2.
