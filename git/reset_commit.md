# 변경 내용 되돌리기

깃을 사용하다보면 로컬에서 변경 또는 commit, push한 내용을 되돌리고 싶을 때가 있다.  
그때 사용할 수 있는 명령어들을 정리해보았다.

### 작업 내역 조회
git에서 가장 최근에 수행한 작업부터 순서대로 History 조회  
commit 뿐만 아니라 reset과 같은 모든 작업들을 조회할 수 있다.
```
git reflog
```

### work tree에 수정된 파일
work tree에서 파일을 수정한 뒤, 수정한 내용을 HEAD 상태(가장 최근 버전)로 되돌리고 싶을 때 사용  

- repository 내 전체 파일
```
git checkout .
```
- 특정 폴더 내 전체 파일
```
git checkout 해당_폴더명
```
- 특정 파일
```
git checkout 해당_파일명
```

### add
stage에 올라간 파일을 되돌리고 싶을 때 사용

- repository 내 전체 파일
```
git reset 
```
- 특정 파일
```
git reset HEAD 해당_파일명
```

### commit
이미 수행한 commit을 삭제하는 명령어는 reset

- commit 취소 후, 해당 파일을 staged 상태로 보존
```
git reset --soft HEAD^
```
- commit 취소 후, 해당 파일을 unstaged 상태로 삭제
```
git reset --hard HEAD^
```
- commit messgae 변경  
가장 최근 commit만 변경할 수 있다.
```
git commit --amend
```

### push
push 명령어로 원격 저장소에 올라간 commit을 되돌리는 명령어는 reset과 revert

- <b>로컬에서 commit 취소 후, 강제 push</b>  
	commit history에 잘못된 commit의 기록을 아예 없애줘서 commit log를 깔끔하게 유지할 수 있다.  
	하지만 이 방법은 굉장히 위험한 방법이므로 추천하지 않는다.  

	여차하면 해당 repository의 commit history가 죄다 날아갈 수 있는데 복구할 수 없다.  
	(구글링을 해보면 피해자들의 간절한 후기를 찾아볼 수 있다.)  

	특히, 팀원들과 작업을 하게 된다면 내가 commit을 되돌리기 전, 팀원이 pull 한다면 내가 commit을 삭제하더라도 해당 팀원에게는 commit이 남아 있게 된다. 팀원이 본인 작업 후 push하게 되면 없앴던 코드가 부활하여 혼란을 야기한다.
```
git reset --hard HEAD~개수
git push -f origin master
```

- <b>혼란을 방지하는 방법</b>  
아예 commit을 삭제하는 것이 아니라 commit을 제거한다는 또 다른 commit을 생성한다.  
원하는 버전으로 돌아가되 모든 commit의 이력이 그대로 보존된다.  

	- 특정 commit으로 돌아감  
	```
	git revert 되돌리고_싶은_commit의_hash
	```
	- HEAD로부터 범위를 지정하여 돌아감  
	해당 방법은 revert 된 개수대로 commit이 남는다.  
	보기 싫다면 revert 뒤에 --no -commit 옵션을 붙여주면 revert commit이 자동 생성되지 않고 work tree와 staging area에만 변경사항이 적용된다.
	```
	git revert HEAD~개수
	```

