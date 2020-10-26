# 정규 표현식  
문자열을 처리하는 방법 중 하나로, 정규식(Regular Expression, Regex, Regexp)이라고도 불린다.  
문자열에 나타나는 특정 문자 조합과 대응시키기 위해 사용되는 패턴으로, 자바스크립트에서는 정규표현식 또한 객체이다.  
  
현재 많은 프로그래밍 언어, 텍스트 처리 프로그램, 고급 텍스트 편집기 등이 정규 표현식 기능을 제공한다.  
일부는 펄, 자바스크립트, 루비, Tcl처럼 문법에 내장되어 있기도 하지만 자바, 파이썬, C, C++ (C++ 11 이후) 등에서는 표준 라이브러리를 통해 제공한다.  
이 글에서는 javascript의 정규 표현식 사용법에 대해 기록한다.  

## 함께 쓰이는 메소드  
- __exec__ : 대응되는 문자열을 찾는 RegExp 메소드로, 정보를 가지고 있는 배열을 반환  
대응되는 문자열을 찾지 못하면 null을 반환
- __match__ : 대응되는 문자열을 찾는 RegExp 메소드로, 정보를 가지고 있는 뱅열을 반환  
대응되는 문자열을 찾지 못하면 null을 반환  
- __test__ : 대응되는 문자열이 있는지 검사하는 RegExp 메소드로, true나 false를 반환  
- __search__ : 대응되는 문자열이 있는지 검사하는 String 메소드로, 대응된 부분의 인덱스를 반환  
대응되는 문자열을 찾지 못하면 -1을 반환  
- __replace__ : 대응되는 문자열을 찾아 다른 문자열로 치환하는 String 메소드  
- __split__ : 정규식 혹은 문자열로 대상 문자열을 나누어 배열로 반환하는 String 메소드  
  
문자열 내부에 패턴에 대응되는 부분이 있는지 알고 싶다면, test나 search 메소드 사용  
실행은 더 느리지만 좀 더 많은 정보가 필요할 때는 exec나 match 메소드 사용  
만약 exec나 match 메소드 사용했는데 대응되는 부분이 있다면 배열을 반환하고 정규식 객체의 속성을 업데이트하고, 대응되는 부분이 없다면 exec 메소드는 null을 반환(= false와 같은 의미로 사용될 수 있음)  

## 예시  
```javascript  
let data = ['    ++- ---+    '];

for (const s of data) {
	console.log(s.replace(/ /g, ''));
}
```
결과 : `++----+`  
/g가 없으면 가장 앞의 공백만 삭제된다. /g는 global로 전체를 검색해줌.  

## Test Site  
https://regex101.com/  

## Reference Site  
[MDN web docs 정규 표현식](https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/%EC%A0%95%EA%B7%9C%EC%8B%9D)

