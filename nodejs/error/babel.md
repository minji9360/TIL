# babel  
## Requires Babel "버전", but was loaded with "버전"  
```
[BABEL] src/app.js: Requires Babel "^7.0.0-beta.41", but was loaded with "7.0.0-beta.3". You'll need to update your @babel/core version.   
(While processing: "/tmp/build_c5371708/node_modules/@babel/preset-env/lib/index.js")  
remote:     at throwVersionError (/tmp/build_c5371708/node_modules/@babel/helper-plugin-utils/lib/index.js:63:11)
remote:     at Object.assertVersion (/tmp/build_c5371708/node_modules/@babel/helper-plugin-utils/lib/index.js:13:11)
remote:     at /tmp/build_c5371708/node_modules/@babel/preset-env/lib/index.js:219:7
remote:     at /tmp/build_c5371708/node_modules/@babel/helper-plugin-utils/lib/index.js:19:12
remote:     at /tmp/build_c5371708/node_modules/babel-cli/node_modules/babel-core/lib/config/option-manager.js:238:14
remote:     at cachedFunction (/tmp/build_c5371708/node_modules/babel-cli/node_modules/babel-core/lib/config/caching.js:48:17)
remote:     at loadPresetDescriptor (/tmp/build_c5371708/node_modules/babel-cli/node_modules/babel-core/lib/config/option-manager.js:321:28)
remote:     at /tmp/build_c5371708/node_modules/babel-cli/node_modules/babel-core/lib/config/option-manager.js:59:14
remote:     at Array.map (<anonymous>)
remote:     at OptionManager.mergeOptions (/tmp/build_c5371708/node_modules/babel-cli/node_modules/babel-core/lib/config/option-manager.js:58:34)
remote:     at OptionManager.init (/tmp/build_c5371708/node_modules/babel-cli/node_modules/babel-core/lib/config/option-manager.js:114:14)
remote:     at manageOptions (/tmp/build_c5371708/node_modules/babel-cli/node_modules/babel-core/lib/config/option-manager.js:40:30)
remote:     at loadConfig (/tmp/build_c5371708/node_modules/babel-cli/node_modules/babel-core/lib/config/index.js:17:37)
remote:     at Object.transformFileSync (/tmp/build_c5371708/node_modules/babel-cli/node_modules/babel-core/lib/transform-file-sync.js:20:36)
remote:     at Object.compile (/tmp/build_c5371708/node_modules/babel-cli/lib/babel/util.js:71:18)
remote:     at write (/tmp/build_c5371708/node_modules/babel-cli/lib/babel/dir.js:30:21)
remote:     at handleFile (/tmp/build_c5371708/node_modules/babel-cli/lib/babel/dir.js:54:20)
remote:     at /tmp/build_c5371708/node_modules/babel-cli/lib/babel/dir.js:78:9
remote:     at Array.forEach (<anonymous>)
remote:     at handle (/tmp/build_c5371708/node_modules/babel-cli/lib/babel/dir.js:75:56)
remote:     at Array.forEach (<anonymous>)
remote:     at _default (/tmp/build_c5371708/node_modules/babel-cli/lib/babel/dir.js:86:15)
remote:     at Object.<anonymous> (/tmp/build_c5371708/node_modules/babel-cli/lib/babel/index.js:185:1)
remote:     at Module._compile (internal/modules/cjs/loader.js:1137:30)
remote:     at Object.Module._extensions..js (internal/modules/cjs/loader.js:1157:10) {
remote:   code: 'BABEL_VERSION_UNSUPPORTED',
remote:   version: '7.0.0-beta.3', ●
remote:   range: '^7.0.0-0' ●
remote: }
remote: npm ERR! code ELIFECYCLE
remote: npm ERR! errno 1
remote: npm ERR! youtube_clone_coding@1.0.0 build:server: `babel src --out-dir build --ignore 'src/assets','src/static','src/webpack.config.js'`
remote: npm ERR! Exit status 1
remote: npm ERR!
remote: npm ERR! Failed at the youtube_clone_coding@1.0.0 build:server script.
remote: npm ERR! This is probably not a problem with npm. There is likely additional logging output above.
remote:
remote: npm ERR! A complete log of this run can be found in:
remote: npm ERR!     /tmp/npmcache.3TgfV/_logs/2020-09-15T11_52_24_597Z-debug.log
remote: npm ERR! code ELIFECYCLE
remote: npm ERR! errno 1
remote: npm ERR! youtube_clone_coding@1.0.0 build: `npm run build:server && npm run build:assets && npm run copyAll`
remote: npm ERR! Exit status 1
remote: npm ERR!
remote: npm ERR! Failed at the youtube_clone_coding@1.0.0 build script.
remote: npm ERR! This is probably not a problem with npm. There is likely additional logging output above.
remote:
remote: npm ERR! A complete log of this run can be found in:
remote: npm ERR!     /tmp/npmcache.3TgfV/_logs/2020-09-15T11_52_24_616Z-debug.log
remote:
remote: -----> Build failed
remote:
remote:        We're sorry this build is failing! You can troubleshoot common issues here:
remote:        https://devcenter.heroku.com/articles/troubleshooting-node-deploys
remote:
remote:        Some possible problems:
remote:
remote:        - Node version not specified in package.json
remote:          https://devcenter.heroku.com/articles/nodejs-support#specifying-a-node-js-version
remote:
remote:        Love,
remote:        Heroku
remote:
remote:  !     Push rejected, failed to compile Node.js app.
remote:
remote:  !     Push failed
remote: Verifying deploy...
remote:
remote: !       Push rejected to still-sierra-36389.
remote:
To https://git.heroku.com/still-sierra-36389.git
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'https://git.heroku.com/still-sierra-36389.git'
```

### 상황  
유튜브 클론코딩(#11.6 Deploying to Heroku part One) 실습 중 heroku 배포를 위해 주소를 git remote에 추가한 후 `git push heroku master` 실행했더니 해당 오류가 발생했다.  
마지막 에러 메시지(remote rejected)를 보고 다른 프로젝트를 진행할 때 동일한 오류를 봤어서 같은 문제라고 생각해서 다음과 같은 시도를 했다.  
1. __git pull__ 혹은 __git clone__으로 local의 파일과 github에 있는 파일을 맞춰준다.  
2. <b>git push -f 원격_저장소_이름 브랜치_이름</b>으로 강제 push (파일 손실 위험성)  
3. __git commit__  
4. __heroku login__  

위의 시도 후 해결이 되지 않아서 가장 위의 에러를 살펴봤다.  
push가 실패하는 것은 결과고, 가장 위에서부터 내려오면서 에러를 해결해야겠다는 생각을 했기 때문이다.  
다시 찬찬히 보니 @babel/core의 버전과 관련된 에러라는 사실을 깨달았고 관련 시도들로 해결했다.  

### 해결  
1. package.json에서 devDependencies에 있는 babel 관련 내용 dependencies로 이동
--production 빌드 시 devDependencies에 있는 plugin들은 포함되지 않는다.  
(devDependencies에는 개발자만 사용할 것들만 있어야 함. eslint나 nodemon, prettier 등)  
2. __npm i @babel/core @babel/preset-env__  
3. __npm i babel-loader@next__  
4. babel 삭제 후 재설치, npm 재설치  
5. .babelrc 수정  
※ 시도 후에는 꼭 commit 후 push ※  

```javascript
/* .babelrc before */
{
	"presets": ["@babel/preset-env"]
}

/* .babelrc after */
{
	"presets": [
		["@babel/preset-env", 
			{
				"modules": false
		    }
		]
	],
	"env": {
		"test": {
			"presets": [["@babel/preset-env"]]
		}
	}
}
```
계속 버전을 특정하거나 @next로 최근 버전으로 업데이트를 했는데 `npm babel -v`로 버전을 확인해도 6.14.6으로 나와서 `npm -v`로 npm 버전을 확인했더니 동일한 6.14.6이 나왔다.  
npm 버전을 바꿔야 하나 싶어 전부 지우고 새로 설치해도 에러 메시지는 그대로이고 버전도 바뀌지 않았다.  
(아직 npm 버전이 바뀌지 않는 문제는 해결하지 못했지만 에러의 원인은 아니었기 때문에 일단 그냥 넘어갔다.)  
<br/>
그래서 에러 메시지를 다시 봤더니 ● 부분에서 이상함을 느꼈다.  
npm과 babel의 버전은 6.xx으로 나오는데, 왜 7.0.0-0이 문제라고 하지? 싶어서 package.json을 다시 살펴봤더니 devDependencies에 버전 "7.0.0-0"의 babel-cli가 있었다. 문제가 되는 부분인 것 같아 삭제했더니 오류가 해결되었다.  
<br/>
heroku 오류인 줄 알았는데 역시 오류는 처음부터 끝까지 잘 살펴보고 가장 위에서부터 내려오면서 해결해야 한다.  
위에서 난 오류의 결과로 뒤의 오류들이 발생할 수 있다.  
<br/>

## 'babel-node'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는 배치 파일이 아닙니다.  

### 상황  
챌린지용 디렉토리를 생성하고 day 5 챌린지 완료 후 테스트를 위해 npm start를 실행했더니 해당 오류가 발생했다. (start script는 `nodemone --exec babel-node src/index.js`)
1. __npm i babel-node__  
2. __npm i @babel/node__  
3. __npm i babel-node -g__

### 해결  
1. __npm i @babel/core__  
2. __npm i @babel/node__  
3. __npm i @babel/preset-env__  

