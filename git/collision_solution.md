# 충돌 해결  
## failed to push some refs to '저장소주소'  
```
git push 저장소_이름 브랜치_이름
```
위 명령어 사용 시, 해당 에러가 나올 때가 있다.  
```
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to '저장소_주소'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
이 때, push 명령어에 -f를 붙여 강제 push하지 말고 pull로 해결하도록 하자.  
(강제 push로 돌이킬 수 없는 강을 건넌 경험담은 구글에서 적지 않게 볼 수 있다.)  

```
git pull 저장소_이름 브랜치_이름
``` 
명령어가 먹히지 않을 때는, 원격 저장소를 다시 추가`git remote add 저장소_주소` 후 시도해보자.  

<br/>
## refusing to merge unrelated histories
pull 명령어 사용 시, 해당 에러가 발생할 때가 있다.  
```
fatal: refusing to merge unrelated histories
```
원격 저장소와 로컬 저장소의 변경 내역이 다르기 때문에 발생하는 경고이다.  
원격 저장소의 주소가 올바른지 확인 후, pull 명령어를 사용할 주소가 맞다면 아래 옵션을 추가하면 된다.  
(원격 저장소의 주소를 잘못 가져온 줄 모르고 pull을 하는 실수를 저질렀다.)  
```
git pull --allow-unrelated-histories
```

