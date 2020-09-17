# ngrok  
## cannot execute binary file: Exec format error  
```
/c/Users/MINJI/AppData/Roaming/npm/ngrok: line 8: C:\Users\MINJI\AppData\Roaming\npm/node_modules/ngrok/bin/ngrok: cannot execute binary file: Exec format error
```
### 상황  
외부에서 로컬 서버에 접속할 수 있도록 ngrok을 설치하고 `ngrok http 8080`을 실행했더니 해당 오류가 발생했다.  

### 해결
1. __ngrok.exe 파일이 있는 위치에서 명령어 실행__  
2. __터미널에 ngrok이 들어가야 할 위치에 ngrok.exe 파일을 끌어다 놓고 ` http 4000`을 붙여서 명령어 실행__  

