# Pug  
## expected "indent", but got "outdent"  
```
Error: /sandbox/src/views/detail.pug:8:1
    6|   ul

    7|     each genre in movieById.genres

  > 8|   a(href=`/edit`) Edit

-------^
    9| 

expected "indent", but got "outdent"
    at makeError (/sandbox/node_modules/pug-error/index.js:32:13)
    at Parser.error (/sandbox/node_modules/pug-parser/index.js:53:15)
    at Parser.expect (/sandbox/node_modules/pug-parser/index.js:137:12)
    at Parser.block (/sandbox/node_modules/pug-parser/index.js:988:20)
    at Parser.parseEach (/sandbox/node_modules/pug-parser/index.js:752:19)
    at Parser.parseExpr (/sandbox/node_modules/pug-parser/index.js:236:21)
    at Parser.block (/sandbox/node_modules/pug-parser/index.js:996:25)
    at Parser.tag (/sandbox/node_modules/pug-parser/index.js:1157:24)
    at Parser.parseTag (/sandbox/node_modules/pug-parser/index.js:1049:17)
    at Parser.parseExpr (/sandbox/node_modules/pug-parser/index.js:208:21)
    at Parser.block (/sandbox/node_modules/pug-parser/index.js:996:25)
    at Parser.parseBlock (/sandbox/node_modules/pug-parser/index.js:793:52)
    at Parser.parseExpr (/sandbox/node_modules/pug-parser/index.js:212:21)
    at Parser.parse (/sandbox/node_modules/pug-parser/index.js:112:25)
    at parse (/sandbox/node_modules/pug-parser/index.js:12:20)
    at Object.parse (/sandbox/node_modules/pug/lib/index.js:125:22)
```  

### 상황  
detail 페이지 pug와 controller 생성 후, detail 페이지로 이동했더니 해당 오류가 발생했다.  

### 해결  
ul 아래 __li 추가__
