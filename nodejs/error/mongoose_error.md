# MongooseError

## The 'uri' parameter to 'openUri()' must be a string, got "undefined".
```
MongooseError: The `uri` parameter to `openUri()` must be a string, got "undefined". Make sure the first parameter to `mongoose.connect()` or `mongoose.createConnection()` is a
string.
    at NativeConnection.Connection.openUri (C:\Users\MINJI\til\JavaScript\youtube_clone_coding\node_modules\mongoose\lib\connection.js:651:11)
    at Mongoose.connect (C:\Users\MINJI\til\JavaScript\youtube_clone_coding\node_modules\mongoose\lib\index.js:339:15)
    at Object.<anonymous> (C:\Users\MINJI\til\JavaScript\youtube_clone_coding\src\/db.js:5:10)
    at Module._compile (internal/modules/cjs/loader.js:1137:30)
    at Module._compile (C:\Users\MINJI\TIL\JavaScript\youtube_clone_coding\node_modules\pirates\lib\index.js:99:24)
    at Module._extensions..js (internal/modules/cjs/loader.js:1157:10)
    at Object.newLoader [as .js] (C:\Users\MINJI\TIL\JavaScript\youtube_clone_coding\node_modules\pirates\lib\index.js:104:7)
    at Module.load (internal/modules/cjs/loader.js:985:32)
    at Function.Module._load (internal/modules/cjs/loader.js:878:14)
    at Module.require (internal/modules/cjs/loader.js:1025:19)
    at require (internal/modules/cjs/helpers.js:72:18)
    at Object.<anonymous> (C:\Users\MINJI\til\JavaScript\youtube_clone_coding\src\/init.js:3:1)
    at Module._compile (internal/modules/cjs/loader.js:1137:30)
    at Module._compile (C:\Users\MINJI\TIL\JavaScript\youtube_clone_coding\node_modules\pirates\lib\index.js:99:24)
    at Module._extensions..js (internal/modules/cjs/loader.js:1157:10)
    at Object.newLoader [as .js] (C:\Users\MINJI\TIL\JavaScript\youtube_clone_coding\node_modules\pirates\lib\index.js:104:7)
```

### 상황
유튜브 클론코딩(#11.5 Building for Producetion) 실습 중 `npm run dev:server` 실행했더니 해당 오류가 발생했다.  
직전에 root 위치에 src 폴더를 만들고 build, node_modules 폴더와 package-lock.json, package.json을 제외한 파일을 모두 src 폴더로 넣는 작업을 했다. 이 때 숨김 파일도 제외하고 옮겼어야 했는데 다 src 폴더 안으로 옮겼다.  
.env 파일이 root여야 한다고 해서 .env만 옮겼더니 동일한 에러가 반복되었고, 숨김 파일들을 모두 root로 꺼내니 해결되었다.  

### 해결
1. .env 파일명 확인
2. <b>.env 파일 위치 확인 (project의 root여야 함)</b>

