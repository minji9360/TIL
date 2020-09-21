# TypeError
## Cannot read property 'length' of undefined at pathtoRegexp  
```
Browserslist: caniuse-lite is outdated. Please run next command `yarn upgrade`
/sandbox/node_modules/path-to-regexp/index.js:63
  path = ('^' + path + (strict ? '' : path[path.length - 1] === '/' ? '?' : '/?'))
                                                ^

TypeError: Cannot read property 'length' of undefined
    at pathtoRegexp (/sandbox/node_modules/path-to-regexp/index.js:63:49)
    at new Layer (/sandbox/node_modules/express/lib/router/layer.js:45:17)
    at Function.route (/sandbox/node_modules/express/lib/router/index.js:494:15)
    at Function.proto.(anonymous function) [as get] (/sandbox/node_modules/express/lib/router/index.js:509:22)
    at Object.get (/sandbox/routers/coursesRouter.js:12:15)
    at Module._compile (internal/modules/cjs/loader.js:778:30)
    at Module._compile (/sandbox/node_modules/pirates/lib/index.js:99:24)
    at Module._extensions..js (internal/modules/cjs/loader.js:789:10)
    at Object.newLoader [as .js] (/sandbox/node_modules/pirates/lib/index.js:104:7)
    at Module.load (internal/modules/cjs/loader.js:653:32)
```

### 상황  
router 생성해서 특정 링크 접속 시 원하는 페이지를 보여주도록 설정했더니 해당 오류가 발생했다.  

### 해결  
routes.js에서 routes 내 __오타 수정__  


## Router.use() requires a middleware function but got a undefined at Function.use
```
TypeError: Router.use() requires a middleware function but got a undefined
    at Function.use (/sandbox/node_modules/express/lib/router/index.js:458:13)
    at Function.<anonymous> (/sandbox/node_modules/express/lib/application.js:220:21)
    at Array.forEach (<anonymous>)
    at Function.use (/sandbox/node_modules/express/lib/application.js:217:7)
    at Object.use (/sandbox/src/index.js:16:5)
    at Module._compile (internal/modules/cjs/loader.js:778:30)
    at Module._compile (/sandbox/node_modules/pirates/lib/index.js:99:24)
    at Module._extensions..js (internal/modules/cjs/loader.js:789:10)
    at Object.newLoader [as .js] (/sandbox/node_modules/pirates/lib/index.js:104:7)
    at Module.load (internal/modules/cjs/loader.js:653:32)
```

### 상황  
생성한 Router를 index.js에 app.use로 추가하고 서버를 구동했더니 해당 오류 발생  

### 해결  
export를 default로 한 것은 import 할 때 {}로 받으면 안된다. __{} 삭제__
