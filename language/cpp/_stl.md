# 표준 템플릿 라이브러리  
c++의 템플릿을 사용해 표준으로 정리되어 편리하게 사용할 수 있도록 제공되는 도구라고 할 수 있다.    
보통 STL(Standard Template Library)이라고 하는데, STL이라고 할 때는 많은 종류의 라이브러리 중 보통 컨테이너, 반복자, 알고리즘을 말한다.  

## 컨테이너 (container)  
같은 타입의 여러 객체를 담아 다루기 위한 집합으로, 크게 세 종류로 나뉜다.  

### 시퀀스 컨테이너 (sequence container)  
특별한 제약이나 규칙이 없는 가장 일반적인 컨테이너로, 데이터를 선형으로 저장하여 삽입된 요소의 순서가 유지된다.  

- 요구사항  
1. 모든 요소가 직선 순서로 배치되어 있어야 한다.  

2. 반복자가 최소한 순방향 반복자(forward iterator) 이상이어야 한다.  

3. 명확한 순서를 가지기때문에 특정 위치를 참조하는 연산이 가능해야 한다.  

#### vector
##### 개념
동적 배열구조 클래스로, 임의 접근을 제공하는 가장 간단한 시퀀스 컨테이너이다.  
모든 자료형에 대해 배열처럼 저장 가능하지만, 한 번에 한 타입만 저장할 수 있다.  
요소가 추가되거나 삭제될 때 자동으로 메모리를 재할당이 발생하여 상당한 비용을 지불하게 된다.  

##### 문법
- 헤더파일 : vector

- 문법
```
vector<템플릿_인수> 객체_이름(생성자_인수);
```  
템플릿 인수 : vector 컨테이너에 저장될 요소의 타입  
생성자 인수 : vector 컨테이너의 초기 크기. 생략 시 요소를 가지지 않는 빈 벡터 생성  

1. 생성자  
- __vector__ : v는 빈 컨테이너이다.  
- __vector v(n)__ : ve는 기본값으로 초기화된 n개의 원소를 갖는다.  
- __vector v(n, x)__ : v는 x값으로 초기화된 n개의 원소를 갖는다.  
- __vector v(v2)__ : v는 v2컨테이너의 복사본이다. (복사 생성자 호출)  
- __vector v(b, e)__ : v는 반복자구간 (b, e)로 초기화된 원소를 갖는다.  

2. 멤버 함수  
- __v.assign(n, x)__ : v에 x값으로 n개의 원소를 할당한다.  
- __v.assign(b, x)__ : v를 반복자 구간 (b,e)로 할당한다.

##### 예제  
```c
vector<int> vc = {10, 20, 30}; // vector 객체의 선언 및 초기화
cout << "현재 벡터의 크기 : " << vc.size() << endl;

vc.push_back(40);	// vector 요소 추가  
cout << "현재 벡터의 크기 : " << vc.size() << endl;
cout << "현재 벡터의 네 번째 요소 : " << vc[3] << endl;

cout << "현재 벡터의 모든 요소" << endl;
copy(vc.begin(), vc.end(), ostream_iterator<int>(cout, " "));
```  

사용된 STL 함수  
1. size() : 컨테이너에 저장된 요소의 개수 반환  
2. push_back() : 컨테이너의 마지막 요소로 해당 데이터 추가  
3. begin() : 컨테이너의 첫 번째 요소를 가리키는 반복자  
4. end() : 컨테이너의 마지막 요소 바로 다음(past the end)를 가리키는 반복자  

#### deque  
##### 개념  
양쪽에 끝이 있는 큐(queue)로, double-ended queue를 의미한다.  
컨테이너 양 끝에서 요소를 빠르게 삽입/삭제할 수 있다.  
vector 객체와 마찬가지로 임의 접근과 동적 크기의 장점을 가지며, vector로 할 수 없는 전방 삽입/삭제도 빠르게 수행할 수 있다.  

##### 문법
- 헤더 파일 : deque  

- 문법
```
deque<템플릿_인수> 객체_이름(생성자_인수);
```

##### 예제  
```c
deque<int> dq = {20};	// deque 객체의 선언 및 초기화
dq.push_back(30);		// 요소의 후방 삽입
dq.push_front(10);		// 요소의 전방 삽입

cout << "현재 데큐의 모든 요소 : " << endl;
copy(dq.begin(), dq.end(), ostream_iterator<int>(cout, " "));
cout << endl << "현재 첫 번째 요소 : " << dq.front() << endl;

dq.pop_front();
cout << "현재 데큐의 모든 요소 : " << endl;
copy(dq.begin(), dq.end(), ostream_iterator<int>(cout, " "));
```
  
사용된 STL 함수  
1. push_front() : 컨테이너의 첫 번째 요소로 해당 데이터를 추가  
2. front() : 컨테이너의 첫 번째 요소를 반환  
3. pop_front() : 컨테이너의 첫 번째 요소를 삭제


#### list  
##### 개념  
이중 연결 리스트(double linked list)의 클래스 템플릿 표현이라고 할 수 있다.  
모든 요소에서 양방향 접근과 빠른 삽입/삭제가 가능하나, 임의 접근은 불가능하다.  
구성하는 링크(link)는 포인터이기 때문에 특정 함수로 링크를 재배치하는 것으로 아주 빠르게 수행할 수 있다.
장점 : 요소들의 빠른 삽입과 삭제  

##### 문법  
- 헤더 파일 : list

- 문법  
```
list<템플릿_인수> 객체_이름(생성자_인수);
```

- 함수  
swap() : 두 요소의 위치를 서로 바꿈  
reverse() : 리스트 전체 요소의 위치를 역순으로 변경  
sort() : 리스트 전체 요소를 정렬  
unique() : 같은 값이 인접해 있을 경우, 그 값들을 하나로 단일화  
merge() : 두 정렬된 리스트를 합병  
splice() : 두 리스트를 연결하거나, 한 쪽 리스트로 이동  

##### 예제  
```c
list<int> ls = {1, 2, 3, 4, 3, 5, 5};	// list 객체의 선언 및 초기화  
// ls.sort();	// 1, 2, 3, 4, 5  
ls.unique();	// 1, 2, 3, 4, 3, 5  
cout << "현재 리스트의 모든 요소 : " << endl;  
copy(ls.begin(), ls.end(), ostream_iterator<int>(cout, " "));
```

unique 사용 전에 sort()를 사용해 정렬하면, 리스트 내의 모든 중복값을 제거할 수 있다.  

#### forward_list
##### 개념  
단방향 연결 리스트(singly linked list)의 클래스 템플릿 표현이라고 할 수 있다.  
C++11부터 추가되었으며, 모든 요소에서 순방향으로 접근할 수는 있으나 역방향으로 접근할 수는 없다.  
따라서 순방향 리스트 컨테이너에는 순방향 반복자(forward iterator)만 사용한다.  

리스트 객체와 비교시, 더 적은 메모리로 간편하게 사용할 수 있다는 장점이 있다.  

##### 문법  
```
forward_list<템플릿_인수> 객체_이름(생성자_인수_;
```  

##### 예제  
```
forward_list<int> fls01 = {10, 20, 400, 30};	// forward_list 객체의 선언 및 초기화
forward_list<int> fls02 = {40, 50};
forward_list<int>::iterator itr;

fls01.remove(400);		 // 값이 400인 모든 요소 삭제
cout << "현재 순방향 리스트의 모든 요소" << endl;
copy(fls01.begin(), fls01.end(), ostream_iterator<int>(cout, " "));
cout << endl;

itr = fls01.begin();		// fls01의 첫 번째 요소를 가리키도록 반복자를 초기화
fls01.splice_after(itr, fls02);	//fls02의 모든 요소를 fls01의 첫 번째 요소 다음에 삽입
cout << "fls01: " ;
copy(fls01.begin(), fls01.end(), ostream_iterator<int>(cout, " "));
cout << endl << "fls02 : ";
copy(fls02.begin(), fls02.end(), ostream_iterator<int>(cout, " "));
```
사용된 stl 함수  
1. remove() : 전달된 값과 같은 값을 가지는 요소를 컨테이너에서 모두 삭제  
2. splice_after() : 해당 요소를 원본 순방향 리스트에서 삭제하고, 대상 순방향 리스트의 지정된 위치에 삽입  

위의 예제에서 splice_after() 호출 후, 순방향 리스트 fls02에는 어떤 요소도 저장되어 있지 않게 된다.  


### 연관 컨테이너 (associative container)  
데이터를 일정 규칙에 따라 조직화하여 저장하고 관리하는 컨테이너로, 키를 바탕으로 대응되는 값을 찾아준다.

## 반복자 (iterator)  
컨테이너에서 보유하는 내부 데이터를 순회할 수 있는 객체로, 컨테이너의 특정 위치를 나타낸다.  
요즘 객체지향 언어에서는 간편하게 자료구조가 제공되지만, C++ 에서는 아직 자료를 포인터 단위로 관리하기 때문에 해당 자료의 위치에서 데이터에 접근하고 사용하려면 그 위치에 저장된 자료구조를 읽을 때 읽기 전용 '도구'가 필요하다.  

## 알고리즘 (algorithm)  
자료구조에 관련된 알고리즘을 컨테이너가 메소드로 제공  



