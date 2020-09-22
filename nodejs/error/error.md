# Erro황r  
## Cannot find module '파일'  
```
internal/modules/cjs/loader.js:968
  throw err;
  ^

Error: Cannot find module '../routers/globalRouter'
Require stack:
- C:\Users\MINJI\youtube_challenge\Day_5\src\index.js
    at Function.Module._resolveFilename (internal/modules/cjs/loader.js:965:15)
    at Function.Module._load (internal/modules/cjs/loader.js:841:27)
    at Module.require (internal/modules/cjs/loader.js:1025:19)
    at require (internal/modules/cjs/helpers.js:72:18)
    at Object.<anonymous> (C:\Users\MINJI\youtube_challenge\Day_5\src\/index.js:2:1)
    at Module._compile (internal/modules/cjs/loader.js:1137:30)
    at Module._compile (C:\Users\MINJI\youtube_challenge\Day_5\node_modules\pirates\lib\index.js:99:24)
    at Module._extensions..js (internal/modules/cjs/loader.js:1157:10)
    at Object.newLoader [as .js] (C:\Users\MINJI\youtube_challenge\Day_5\node_modules\pirates\lib\index.js:104:7)
    at Module.load (internal/modules/cjs/loader.js:985:32) {
  code: 'MODULE_NOT_FOUND',
  requireStack: [ 'C:\\Users\\MINJI\\youtube_challenge\\Day_5\\src\\index.js' ]
}
```

### 상황  
src 폴더 바깥에 있던 controllers 폴더와 routers 폴더를 src 폴더 안쪽으로 이동했더니 해당 오류가 발생했다.  

### 해결  
controllers, routers 폴더가 포함된 __경로 수정__
