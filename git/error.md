# Error  
## Committing is not possible because you have unmerged files.  
```
error: Committing is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
U       Day_17_18_19/src/movieController.js
U       Day_17_18_19/src/movieRouter.js
U       Day_17_18_19/src/views/edit.pug
```

## 상황  
Day_23 디렉토리에 템플릿을 추가하고 커밋을 하려고 했더니 해당 오류가 발생했다.  

## 해결  
U 체크된 파일들에서 충돌이 난 것이므로 해당 파일을 열어서 충돌 난 부분을 삭제하거나 수정한다.  
```
<<<< HEAD
pull 받은 코드
=========
기존 코드
>>>>
```
