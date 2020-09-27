# 입력 함수  
여러 종류의 데이터를 다양한 서식에 맞춰 입력받을 수 있도록 하는 함수를 말한다.  

## 개념  
### scanf()  
f는 formatted의 약자로, 서식화된 입력을 받는다는 의미이다.  
- C언어 표준 입력 함수에서 가장 많이 사용됨  
- 입력받은 데이터를 어떤 서식으로 변환할지 서식 지정자(format specifier)를 통해 직접 지정 가능  
- 비주얼 스튜디오에서 scanf() 대신 scanf_s()로 쓰기도 함  


### gets()  
- scanf() 함수와 비슷하지만, 문자형을 위해 새롭게 개발된 함수이다.  
- 띄어쓰기가 포함된 문자를 입력받을 수 있다.  
- 현업에서는 오류가 많아 사용이 금지되었으나 시험 문제로 한 번쯤 나올 수 있기 때문에 정리  


### getchar()
- 엔터로 입력을 종료할 때 \n를 키보드 버퍼에 저장하는데, getchar()는 이 값을 없애줌  


## 사용법  
- scanf(), getchar(), gets() 함수가 포함된 헤더파일을 include  
```
#include <stdio.h>
```

	* scanf() 함수  
- scanf("", );  

※ 변수가 int인 경우, &(주소 연산자)를 선언  
& : 입력받은 데이터를 뒤에 나오는 변수에 저장하라는 의미. 변수를 사용할 때는 & 안붙여도 됨


	* getchar(), gets() 함수  
- getchar();  
- gets();  
 

## 예시
```c
#include<stdio.h>
int main(){
	myscanf();
}

myscanf(){
    char name[30], addr[100];
    int age;
    
    printf("이름 : ");
    scanf("%s", name);
    printf("\n나이 : ");
    scanf("%d", &age);
    printf("\n주소 : ");
    getchar();
    gets(addr);
    
    printf("\n\n%s에 살고 있는 %s님은 %d세입니다.", addr, name, age);
}
```
