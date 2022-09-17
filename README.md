# memo
git branch 전략

git flow를 권장합니다. (필수는 아닙니다.)

git flow 참고: 우린 Git-flow를 사용하고 있어요 | 우아한형제들 기술블로그 

Git-flow에는 5가지 종류의 브랜치가 존재합니다. 항상 유지되는 메인 브랜치들(master, develop)과 일정 기간 동안만 유지되는 보조 브랜치들(feature, release, hotfix)이 있습니다.

master : 제품으로 출시될 수 있는 브랜치

develop : 다음 출시 버전을 개발하는 브랜치

feature : 기능을 개발하는 브랜치

release : 이번 출시 버전을 준비하는 브랜치

hotfix : 출시 버전에서 발생한 버그를 수정 하는 브랜치

bugfix : Jira bug issue를 수정 하는 브랜치




[upload]

git status

git add

git status

git commit -m "update doc/tmplog.txt"

git push -u origin master

[pull]  (note: before pull, you need to check to commit)

git status

git add

git status

git commit -m "log.txt"

[pull2]

git clean -xdf

git checkout -f

git pull

[conflict - binary]

git checkout FETCH_HEAD <file name> // 서버것을 적용할떄

git checkout HEAD <file name> //로컬것 적용

git commit -a //컨플릭 작업 완료시 명령어를 친다
  
[conflict - code]
  
1. vi 창을 띄운다

git mergetool -t vimdiff
 
2. vi 창에서 / 입력해서 search를 한다. <<<<< conflict 시작부분 >>>>> conflict 끝나는 부분 =====
  
3. vi 창에서 conflict난 부분을 지우거나 수정한다. (참고 라인 삭제: d키)
  
4. vi 창 작업이 끝나면 :를 입력 후 wqa! 입력 (저장하고 모두 닫기)

5. cmd 창에서 git status를 쳐보면 불필요한 파일들이 생성되어있을 것이다 .orig 등 이것들을 아래 명령어로 날

git clean -xdf
  
6. 그 이후 git commit -a 를 입력하여 머지 커밋 작성을 완료 한다.
  
 
[patch 생성 방법.
  
git diff --binary <before commit id> <after commit id> <file name>

ex) git diff --binary abcdefghi qwertyui > ~/1.diff
  
[patch 적용 방법.
  
  
  
  
  
//참고 우아한형제들 git flow, https://sourcetreeapp.com/
  
  
  
  


