---
layout: article
title: 컴퓨터 개념
permalink: /computer-science/computer-concepts
key: computer-science
tags: cs

aside:
  toc: true
sidebar:
  nav: language-cs
---
<!--more-->
## 10진 코드 (Decimal Code)  
도서관에서 도서 정리를 목적으로 널리 사용되어 다른 말로는 도서 분류식 코드라고 한다.  
- 방법 : 코드화 대상 항목을 0부터 9까지 10진 분할, 다시 그 각각에 대해 10진 분할하는 방법을 필요한 만큼 반복한다.  
- 장점 : 코드 체계가 명확, 추가하기 용이  
- 단점 : 10개 이상 분류일 때 비효율적이고 자릿수가 길어질 수 있음  

## 3 초과 코드 (Excess-3 Code)  
BCD 코드에 3(10)(= 0011₂)을 더해 만든 코드
대표적인 자기 보수 코드, 비가중치 코드  

### 자기 보수 코드  
2진수로 된 코드의 1을 0으로, 0을 1로 모두 바꿔 해당 코드의 10진수 값에 대해 9의 보수를 얻는 코드  

### 비가중치 코드  
2진수 각 자리가 고유한 값을 갖는 코드  

## 가변 비트레이트 (VBR; Bariable BitRate)  
오디오/비디오 인코딩 형식 중 하나로, 인코딩 시 상황에 따라 압축률을 다르게 하는 압축 방법  
- 고정 비트레이트(CBR)과 차이점 : 단위 시간당 출력하는 데이터의 양이 변함  
- MP3, WMA, Vorbis, AAC 오디오에서 선택적으로 가변 비트레이트로 인코딩할 수 있고, 비디오는 MPEG-2 형식에서 사용 가능  
- 장점 : 단위 비트 당 할당하는 용량을 효율적으로 조절할 수 있다. 많은 데이터를 요구하는 곳에 더 많은 비트를 할당, 상대적으로 데이터 요구가 적은 곳에는 비트를 적게 할당하는 체제로 고정 비트레이트의 인코딩 결과물보다 질이 좋다.  

## 가상 메모리 (Virtual Memory)  
가상 메모리(논리적 메모리)는 컴퓨터와 운영체제에 의해 구현되는 개념으로, 프로그래머가 대용량의 메모리나 데이터를 사용할 수 있게 해주는 것  
컴퓨팅 시스템은 프로그래머가 사용하는 가상의 저장 공간 주소를 하드웨어 저장 공간(보통 HDD)으로 매핑하는 일을 처리해 주므로, 프로그래머는 데이터 저장 공간의 가용성에 관한 두려움으로부터 자유로워 질 수 있다.  
컴퓨터는 가상 저장 공간에 대한 주소를 실제 저장 공간으로 매핑하는 것 외에도 가상 메모리 구현, 램과 하드 디스크 또는 다른 대규모 저장장치들 사이에 이루어지는 데이터 스와핑을 관리  
- 장점 : 실제 소요되는 물리적인 저장 공간의 크기를 절약, 전체적인 시스템 처리 속도도 빨라진다.  

## 결합도 (Coupling)  
모듈간에 상호 의존하는 정도를 의미  
독립적인 모듈 : 각 모듈간 결합도 약하고 의존하는 모듈이 적어야 함  
- 종류 : 자료 결합도, 스탬프 결합도, 제어 결합도, 외부 결합도, 공통 결합도 등  

### 모듈  
소프트웨어 구조를 이루는 기본 단위  
하나 또는 그 이상의 논리적 기능들을 수행하는 컴퓨터 지시어들의 집합  

## 고성능 영상 코딩 (HVC; High Performance Video Coding)  
ISO/IEC JTC1 MPEG에서 AVC(Advanced Video Coding) 이후 표준으로 추진 중인 차세대 비디오 부호화 표준  
HD 이상의 해상도를 주 대상으로, 고성능의 압축 효율과 이동성을 보장  
화질은 QVGA에서 8K x 4K를 지원, 컬러 스페이스(Color Space)도 YUV가 4:4:4, 픽셀 당 비트 수가 14Bit, 프레임 레이트는 172fps까지 구현 가능  
이동 방송을 고려한 SVC와 이동망에서의 에러 강인성을 제공  

### YUV  
색을 나타내는 형식  
휘도 신호(Y), 휘도 신호와 청색 성분의 차(U), 휘도 신호와 적색 성분의 차(V)  


### SVC (Scalable Video Coding)  
하나의 소스로 TV는 물론 개인용 컴퓨터(PC)나 휴대 전화에서도 사용 가능한 차세대 색 일치용 비디오 코덱  

## 구분 코드 (Block Code)  
코드화 대상 항목 중 공통성이 있는 것끼리 블록으로 구분, 각 블록 내에서 일련 번호를 부여하는 방법  
자릿수가 비교적 짧고 블록 별 식별과 분류가 쉬우며 블록마다 여유 코드를 두어 코드를 쉽게 추가할 수 있지만, 여유 코드는 코드 낭비의 요인이 되기도 한다.  

## 그레이 코드 (Gray Code)  
BCD 코드의 인정하는 비트를 X-OR 연산하여 만든 코드  
입출력 장치, D/A 변환기, 주변장치 등에서 숫차 표현 시 사용  
1비트만 변화시켜 다음 수치로 증가시키기 때문에 하드웨어적인 오류가 적음  

### X-OR  
입력되는 것이 모두 같으면 0, 하나라도 다르면 1을 출력하는 논리 게이트  

## 그룹 분류식 코드 (Group Classification Code)  
코드화 대상 항목을 일정 기준에 따라 대분류, 중분류, 소분류 등으로 구분하고, 각 그룹 안에서 일련 번호를 부여하는데 각 자리가 특정한 의미를 가진다.  
- 장점 : 분류 기준이 명확한 경우 이용도가 높고, 기계 처리에 가장 적합하며 구분별 분류와 집계 기능이 좋다.  

## 그리드 컴퓨팅 (Grid Computing)  
분산 설치되어 있는 컴퓨터의 처리 능력을 한 곳으로 모아 가장 중요한 업무에 집중적으로 사용할 수 있게 해주는 기술  
세계적으로 연구 진행 중인 차세대 인터넷 망으로, 현재 인터넷 방식(월드 와이드 웹)과 달리 처리 능력을 한 곳으로 집중시킬 수 있는 인터넷 망  

## 그린 IT 지수 (Green IT Index)  
기관 또는 기업의 그린 IT 활용을 평가하는 지수  
IT 제품과 기술의 그린화를 넘어 IT 기술을 녹색전략에 어느 정도, 얼마나 잘 활용하는지 체계적으로 측정해 그린 IT로 인한 생산성 향상을 평가할 수 있는 지표  

## 그린 에너지 기술지수 (GETI; Green Energy Technology Index)  
그린에너지 부문에서 국가 및 기업의 경쟁력 측정과 기술 동향 파악을 위해 개발한 새로운 기술 평가 지표  
정부가 발표한 그린에너지 15대 유망 분야 가운데 산업적으로 의미있고 기술 특허의 비중이 높은 5개 분야(태양광, 연료전지, 2차전지, 발광다이오드, 청정연료)를 선별해 경쟁력을 수량화  
미국 시장의 등록 특허를 기준으로 하고 있어 객관적인 국가 및 기업의 글로벌 경쟁력 비교 가능  
기존 특허 평가지수는 양적인 부문에 치우치는 단점이 있으나 GETI는 가중치를 부여하는 방식으로 특허의 질적인 측면까지 평가해 높은 수준의 객관성 보장  

## 기계어 (Machine Language)  
0과 1, 2진수의 형태로 표현되어 컴퓨터가 직접 이해할 수 있는 언어  
- 장점 : CPU에 내장된 명령을 직접 사용 가능, 수행 시간 빠름  
- 단점 : 프로그램 작성, 이해가 어려움  

## 기본 입출력 시스템 (BIOS; Basic Input Output System)  
컴퓨터의 기본 입출력장치나 메모리 등 하드웨어 작동에 필요한 명령들을 모아놓은 프로그램. ROM에 저장되어 있어 ROM-BIOS라고 함.  
전원이 켜지면 POST(Power On Self Test)를 통해 컴퓨터 점검 후 사용 가능한 장치들을 초기화  
하드 드라이브의 고정된 위치에서 운영체제를 읽어와 RAM으로 RAM으로 적재시키는 것이 주임무  

### POST (Power On Self Test)  
전원이 들어오면 컴퓨터 스스로 이상 유무 검사를 수행하는 과정  

## 나노 기술 (Nanotechnology)  
나노 기술이란 분자와 원자를 다루는 초미세 기술로, 나노미터 정도로 아주 작은 크기의 소자를 만들고 제어한다.
전자와 정보통신은 물론 기계, 화학, 바이오, 에너지 등 거의 모든 산업에 응용할 수 있는 것으로 인류 문명을 혁명적으로 바꿀 수 있는 기술로 부상하고 있다.
이 기술이 발전하면 환경, 의료, 생명공학, 신소재 등에서 상상을 초월한 변화가 예상

### 나노 (Nano)  
10억분의 1을 나타내는 단위  
난쟁이를 뜻하는 고대 그리스어 나노스(Nanos)에서 유래  
1mm(나노미터)는 머리카락 1만분의 1인 초미세의 세계로, 원자 3~4개가 들어갈 정도의 크기  

## 나노 발전기 (Nano Generator)  
사용자 발전(UCP) 기술을 이용한 초소형 발전기  
얇고 잘 휘어지는 폴리머 기판에 산화아연 소재의 나노 와이어를 붙인 구조  
나노 발전기를 부착한 생물체가 움직일 때마다 와이어가 구부러지면서 전류가 흐른다.  
- ex) 입는 컴퓨터, 휴대기기, 특히 산화 아연 소재를 사용하는 나노 발전기는 몸속에 들어가서 활동하는 초소형 장비에 활용  

## 나선형 모형 (Spiral Model, 점진적 모형)  
보헴(Boehm)이 제안한 소프트웨어 생명 주기 모형  
폭포수 모형 장점 + 프로토타입 모형 장점 + 위험 분석 기능  
나선을 따라 돌듯이 여러 번의 과정을 거쳐 점진적으로(프로토타입을 지속적으로 발전) 완벽한 최종 소프트웨어를 개발  
- 목적 : 소프트웨어를 개발하며 발생할 수 있는 위험을 관리하고 최소화하는 것
- 개발 순서 : 업무 영역(Task Region)이라는 여러 개의 작업 단위로 나뉨  
각 작업 단위는 다음과 같은 순서로 진행  
![나선형-모형](https://i.pinimg.com/originals/29/eb/ae/29ebae0c66e97906fd8f0e7f6ab5494c.png)  

## 네트워크 컴퓨터 (Network Computer)  
인터넷/인트라넷 접속 전용 컴퓨터 또는 네트워크 단말기  
일반적인 개인용 컴퓨터의 기능과 규격을 축소해 가격은 저렴하게 낮추고 망 접속 기능은 대폭 개선한 새로운 개념의 PC  
네트워크 컴퓨터를 방대한 양의 정보와 응용 프로그램을 저장하고 있는 서버에 연결해, 이 서버로부터 필요한 정보다 소프트웨어를 가져와 모든 정보의 저장과 검색 등의 작업을 처리  
PC 기능의 축소와 그에 따른 가격 인하가 가능해 미국의 오라클 사가 제안  
1966년 5월, 네트워크 컴퓨터 표준규격안(NC Reference Profile)을 IBM, 애플 컴퓨터, 선 마이크로시스템스, 넷스케이프 커뮤니케이션스 사 등이 지원  
판매 가격의 목표를 500달러로 책정해서 500달러 PC라고도, 네트워크 접속 전용 PC라는 의미로 넷 PC라고도 한다.  

### 서버 (Server)  
네트워크에서 다른 프로그램 또는 사용자에게 서비스를 제공하는 컴퓨터 시스템  

## 녹색 성장 (Green Growth)  
환경과 성장 두 가치를 포괄하는 개념  
기존 경제성장 패러다임을 환경 친화적으로 전환하는 과정 중 파생되는 에너지, 환경관련 기술 산업에서 미래유망 품목과 신기술을 발굴해 내고 기존 산업과 상호융합을 시도해 신성장동력과 일자리 창출  
- 새로운 유망 산업 : 풍력, 태양광, LED 녹색 산업 등  

## 다중 처리 시스템 (Multiprocessing System)  
2개 이상의 프로세서(처리장치)를 사용해 같은 프로그램에서 2개 이상의 서로 다른 부분을 동시에 처리하는 방식  
다중 처리는 보통 둘 이상의 마이크로프로세서를 사용해 이뤄지는데, 각 마이크로프로세서는 하나의 작은 칩 위에 집적된 중앙처리장치(CPU; Central Processing Unit)  
메인 프레임 컴퓨터는 명령을 해석하고 실행하기 위해 그런 마이크로프로세서를 수백 개 내지 수천 개나 결합해서 사용  
- 장점 : 처리 속도가 빠르고 훨씬 많은 양의 정보를 처리할 수 있음  

## 다중모드 인터페이스 (MMI; MultiModal Interface)  
인간과 컴퓨터, 또는 단말기기 사이의 인터페이스를 음성뿐 아니라 키보드, 펜, 그래픽 등 다양한 수단을 활용하는 것  
사용자가 음성, 키보드, 펜 등으로 정보를 입력하고 음성, 그래픽, 음악 및 멀티미디어나 3차원 영상 등을 통해 출력을 받게 하는 인터페이스  
W3C의 멀티모달 인터랙션 워킹 그룹에서 멀티모달 인터랙션 프레임워크(Multimodal Interaction Framework), EMMA(Extensible Multimodal Annotation) 및 잉크 마크업 언어(Ink Markup Language) 등의 표준화를 진행하고 있음  

## 다형성  
메시지에 의해 객체(클래스)가 연산을 수행하게 될 때 하나의 메시지에 대해 각 객체(클래스)가 가지고 있는 고유한 방법으로 응답할 수 있는 능력  
응용 프로그램 상 하나의 함수나 연산자가 2개 이상의 서로 다른 클래스의 인스턴스들을 같은 클래스에 속한 인스턴스처럼 수행할 수 있도록 하는 것  

### 메시지 (Message)  
객체들 간 상호작용을 하는 데 사용되는 수단  
객체의 메소드(동작, 연산)를 일으키는 외부의 요구 사항  

## 데이터 파일 (Data File)  
처리를 위해 수집하거나 만들어 낸 데이터를 저장하는 파일  
- 원시 파일 (Source File) : 입력 데이터를 알맞은 매체에 변환하여 만든 파일  
- 마스터 파일 (Master File) : 전표 처리에서의 원장 또는 대장에 해당하는 파일. 자료 관리의 중추적 역할을 담당하며 기본이 되는 파일  
- 트랜잭션 파일 (Transaction File) : 거래 내역이나 변동 내용 등 일시적 성격을 지닌 정보를 기록하는 파일. 마스터 파일 갱신/조회할 때 사용  
- 요약 파일 (Summary File) : 다른 파일의 중요 내용이나 합계를 요약해 놓은 파일. 집계용으로 많이 사용  
- 히스토리 파일 (History File) : 후일 통계 처리에 사용할 자료나 사고 발생 시 마스터 파일 등을 원상 복구 시키기 위한 자료를 보존한 파일  
- 백업 파일 (Backup File) : 만일의 사고에 대비해 마스터 파일을 백업해 놓은 파일  
- 트레일러 파일 (Trailer File) : 마스터 파일을 목적에 따라 여러 개의 파일로 나눴을 때 가장 끝부분의 파일  

## 데이터베이스 (Database)  
특정 조직의 기능을 수행하는 데 필요한 상호 관련된 데이터 파일들의 모임  
여러 사람에 의해 공동으로 사용될 데이터의 중복을 최소화하여 통합  
쉽게 접근하고 처리할 수 있도록 저장장치에 저장하여 항상 사용할 수 있도록 운영하는 운영 데이터  

### 파일 (File)  
사용자가 작성한 서로 관련 있는 레코드의 집합체로, 프로그램 구성의 기본 단위  
각 파일마다 위치, 크기, 작성 시기 등의 여러 속성을 가짐  

## 데크 (Deque)  
삽입과 삭제가 리스트 양쪽 끝에서 모두 발생할 수 있는 자료 구조  
Stack과 Queue의 장점만 따서 구성한 것  
입력 제한 : 입력이 한쪽에서만 발생하고 출력은 양쪽에서 일어날 수 있음  
출력 제한 : 입력이 양쪽에서 발생하고 출력이 한쪽에서만 일어날 수 있음  

## 도플러 레이더 (Doppler Radar)  
도플러 효과를 이용해 이동하는 물체의 방향과 속도를 측정하는 레이더  
- 펄스형 : 하나의 안테나로 송수신 겸용할 수 있어 항공기나 미사일에 많이 사용  
- 연속파(CW)형  

## 듀얼 코어 (Dual Core)  
겉으로는 하나의 CPU 형태이나 실질적으로는 2개의 프로세스 코어를 하나의 기판에 집적시킨 형태  
멀티태스킹 환경에서 싱글 코어에 비해 월등히 빠른 속도를 보이지만 하나의 작업만 수행할 경우 싱글 코어와 처리 속도가 비슷  

## 듀얼 프로세서 (Dual Processor)  
한 컴퓨터 시스템 내에 특정 기능이 동시에 수행되는 2개의 중앙처리장치(CPU)가 있는 시스템  
2개의 CPU가 동일한 기억장치를 공유하고 있어 프로그램이나 데이터를 소프트웨어적으로 2개로 분리하여 사용하도록 처리  
- 장점 : 처리 효율을 높이고, 신뢰성 높음 (한쪽 처리기에 장애가 생기면 다른 한쪽 처리기로 자동 전환)  
- 단점 : 자원 경합 등에 대한 문제점이 큼  

## 디코더 (Decoder)  
n Bit의 코드(Code)화된 정보를 그 코드의 각 Bit 조합에 따라 2ⁿ개의 출력으로 번역하는 회로  
명령어 명령부나 번지를 해독할 때 사용  
![디코더](https://i.pinimg.com/564x/51/cc/b6/51ccb69a3847bdc0746227287676bf02.jpg)

## 램버스 DRAM (Rambus DRAM)  
램버스 DRAM은 데이터 처리 속도가 800MHz~1GHz에 달하는 차세대 메모리 반도체 제품  
미국 반도체 설계 회사 램버스 사가 1992년 처음 개발  
- 장점 : 복잡한 신호 전송망을 병렬로 배치해 단순화시킨 버스 방식을 채택하여 속도의 한계 극복  
컴퓨터 주메모리로 사용할 경우, 정보처리 뿐 아니라 그래픽이나 동영상도 효율적으로 처리  
(일반 DRAM이나 SDRAM은 집적도 높아지면 데이터 채널 등의 구조가 복잡해져 잡음 발생, 신호 왜곡 현상을 보여 데이터 처리 속도를 높이는데 한계가 있음)  

## 로더 (Loader)  
컴퓨터 내부로 정보를 들여오거나 로드 모듈을 디스크 등의 보조기억장치로부터 주기억장치에 적재하는 시스템 소프트웨어  
기본적으로 할당(Allocation), 연결(Linking), 재배치(Relocation), 적재(Loading)의 기능을 차례로 수행하지만, 각 기능을 언어 번역 프로그램 또는 링커 등의 시스템 소프트웨어가 수행할 수 있음  

## 링커 (Linker)  
언어 번역 프로그램이 생성한 목적 프로그램들과 라이브러리, 또 다른 실행 프로그램(로드 모듈) 등을 연결하여 실행 가능한 로드 모듈을 만드는 시스템 소프트웨어  
연결 편집기(Linkage Editor)라고도 함  

## 멀티플렉서(Multiplexer)  
조합논리회로로 2ⁿ개의 입력선 중 1개를 선택해 그 선으로부터 입력되는 값을 1개의 출력선으로 출력시키는 회로  
1개의 선을 선택하기 위해 n개의 선택선(Selection Line)을 이용  

## 메인보드 (Motherboard)  
컴퓨터를 구성하는 모든 장치들이 장착되고 연결되는 컴퓨터의 기본 부품
추가적인 보드를 꽂을 수 있는 소켓이 부착  
데스크톱 컴퓨터의 마더보드에는 CPU, 칩셋, PCI 버스 슬롯, 가속 그래픽 슬록, 메모리 소켓과 키보드, 마우스, 디스크 및 프린터를 위한 컨트롤러 서킷 부착  
![메인보드](https://i.pinimg.com/564x/e5/a4/60/e5a4605acb2c332b734b9de2eccf901e.jpg)

## 모니터 (Moniter)  
동기화를 구현하기 위한 특수 프로그램 기법  
특정 공유 자원을 프로세스에게 할당하는 데 필요한 데이터와 이 데이터를 처리하는 프로시저(Procedure)로 구성  
모니터 내 공유 자원을 사용하려면 프로세스는 반드시 모니터의 진입부를 호출해야 함. 한 순간에 하나의 프로세스만 모니터에 진입해 자원을 사용할 수 있음  

### 동기화  
2개 이상의 프로세스 각각에 대한 처리 순서를 결정하는 것  
(한 시점에서 2개 이상의 프로세스를 동시에 처리할 수 X)  

## 모션 캡처 시스템 (MCS; Motion Capture System)  
컴퓨터와 연결된 특수장치를 실제 관절에 연결해 움직임을 입력 받아 그것을 토대로 화면 상에 움직임을 계산  
자연스럽고 생생한 움직임을 만들어 냄  
게임, 영화 제작에 주로 사용  
인간의 관절에 연결되는 특수장치의 종류에 따라 음향식, 기계식, 자기식, 광학식 등으로 구분  

## 미들웨어 (Middleware)  
클라이언트가 서버 측에 어떠한 처리를 요구하고, 서버가 처리한 결과를 클라이언트에게 돌려주는 과정을 효율적으로 수행하도록 도와주는 소프트웨어  
클라이언트와 서버 사이에 존재  
클라이언트와 서버에 각각의 미들웨어가 있어야 정상적으로 수행됨  
- 기능 : 클라이언트와 서버 간 데이터 통로 제공, 작업 처리 서비스 검색, 프로그램 보안 및 감시 등  

## 미디어 벽면광고 (Media Facade)  
건물 외벽의 경관용 디스플레이  
차세대 전광판 광고 방식으로, 건물 벽면 일부 또는 전부를 광고판으로 사용하는 광고 방식  

## 바이트 (Byte)  
문자를 표현하는 최소 단위  
8개의 비트(Bit)가 모여 1바이트를 구성  
1바이트는 256(=2^8)가지의 정보 표현 가능  
일반적으로 영문자나 숫자는 1바이트로 한 글자를 표현하고 한자는 2바이트로 한 글자 표현  

### 비트 (Bit)  
자료(정보) 표현의 최소 단위  
2가지 상태를 표시하는 2진수 한 자리  
하나의 비트는 1과 0, 참과 거짓, "on"과 "off"로 나타냄  
일반적으로 상호 배타적인 2개의 상태를 구별하는데 필요한 정보량을 나타내기도 함  

## 반가산기 (Half Adder)  
조합논리회로의 하나  
1비트(Bit)짜리 2진수 2개를 덧셈한 합과 자리올림 수를 구하는 회로  
![반가산기](https://i.pinimg.com/originals/87/eb/f5/87ebf5dfa6e4e58a14a7f03672bc4258.png)  

### 조합논리회로  
임의의 시간에서의 출력이 이전의 입력에는 관계없이 현재 입력 조합(0 또는 1)으로부터 직접 결정되는 논리 회로  

## 백업 (Backup)  
전산 장비의 고장이나 다른 불의의 사고에 대비해 데이터베이스를 복제해두는 행위  
대형 컴퓨터를 운영하는 대기업은 물론 중소기업 컴퓨터 관리자에게는 필수적이고 일상적인 업무  

## 버스(Bus)  
컴퓨터에서 데이터를 주고받는 통로  
CPU 내부에서 레지스터 간의 데이터 전소에 사용되는 내부 버스와 CPU와 주변장치 간의 데이터 전송에 사용되는 외부 버스 등으로 구분  

## 버퍼 (Buffer)  
입출력 데이터 등의 정보 전송 시 일시적으로 데이터를 저장하는 임시 기억 장소  
각 장치나 프로세서가 상호 간에 정체되지 않고 지속적인 데이터 흐름을 유지하도록 성능을 극대화하고 부하를 최소화할 수 있도록 버퍼 크기를 신중히 결정해야 함  

## 범용 직렬 버스 (USB; Universal Serial Bus)  
윈도우 98의 출시와 더불어 관심을 끌게 된 직렬 포트의 일종  
조이스틱, 키보드, 전화, 스캐너 및 프린터 등과 같은 주변 장치와 컴퓨터 간의 플러그 앤 플레이 인터페이스  
USB는 12Mbps의 데이터 전송 속도를 지원하므로 웬만한 주변기기를 연결해도 충분히 속도를 낼 수 있고, 장치들을 최대 127개까지 사슬처럼 연결 가능  
PC 사용하는 도중에 연결해도 인식 되고 별도의 주변장치용 전원은 필요 없다.  
USB 주변장치 버스 표준은 인텔, 컴팩, IBM, DEC, 마이크로소프트, NEC 등 7개 기업에 의해 개발되었으며, 이 기술은 별도 비용 부담 없이 컴퓨터나 주변기기 개발자들이 사용할 수 있다.  

### 플러그 앤 플레이 (PnP; Plug & Play)  
컴퓨터 시스템에 하드웨어를 설치 했을 때, 해당 하드웨어를 사용하는데 필요한 시스템 환경을 운영 체제가 자동으로 구성해 주는 것  

## 병렬 연결 (Parallel Connection)  
한 번에 하나 이상의 사건이 발생하는 것  
한 번에 오직 한 개의 사건만 발생하는 직렬과 대비하여 데이터를 여러 개의 채널로 동시에 보내는 것을 의미  
데이터 전송에 시간이나 공간을 분할하는 기술이 사용되는데, 여기서 시간 분할이란 개별적인 정보의 비트들이 차례로 보내지는 것  
공간 분할은 여러 개의 회선이나 통로를 통해 여러 개의 비트들이 병렬로 보내지는 것  

## 복수 모듈 기억장치 (Memory Interleaving)  
독자적으로 데이터를 저장할 수 있는 기억장치 모듈을 여러 개 가진 기억장치  
주기억장치와 CPU의 속도 차이를 개선하고, 기억장치의 버스를 시분할하여 사용할 수 있으며 기억 장소의 접근을 보다 빠르게 수행  
![복수-모듈-기억장치](https://i.pinimg.com/564x/a7/17/74/a71774777152f6a63fecedd0fe9dd827.jpg)  

## 분산 시스템 (Distributed System)  
독립적인 처리 능력을 가진 컴퓨터 시스템을 통신망으로 연결한 방식  
서로 다른 장소에 위치한 컴퓨터 시스템에 기능과 자원을 분산시켜 상호 협력 할 수 있는 시스템  

## 사차원 영상 (4 Dimension Picture)  
입체영화인 3D 영화가 진화해 오감 체험을 제공하는 영화  
물, 바람, 진동, 향기까지 동시에 체험할 수 있는 영화로 특수 장치가 구비된 특수 상영관에서만 상영 가능  
오감 체험은 미리 준비된 소품들과 특수 장치가 컴퓨터 프로ㅡㄱ램에 의해 각 장면마다 연출되도록 짜여 있음  

## 상속성 (Inheritance)  
이미 정의된 상위 클래스(부모 클래스)의 모든 속성과 연산을 하위 클래스가 물려받는 것  
상속성을 이용하면 하위 클래스는 상위 클래스의 모든 속성과 연산을 자신의 클래스 내에서 다시 정의하지 않아도 즉시 자신의 속성으로 사용할 수 있음  
상위 클래스의 속성과 연산을 공유할 수 있기 때문에 객체와 클래스의 재사용, 즉 소프트웨어 재사용(Reuse)를 증대시키는 중요한 개념이 됨  

### 소프트웨어 재사용 (Software Reuse)  
이미 개발된 인정받은 소프트웨어의 전체 혹은 일부분을 다른 소프트웨어 개발이나 유지에 사용하는 것  

## 상호 배제 (Mutual Exclusion)  
특정 프로세스가 공유 자원을 사용하고 있을 경우 다른 프로세스가 해당 공유 자원을 사용하지 못하게 제어하는 기법  
여러 프로세스가 동시에 공유 자원을 사용할 때 각 프로세스가 번갈아 가며 공유 자원을 사용하도록 하는 것으로, 임계 구역을 유지하는 방법  

## 세그먼테이션(Segmentation) 기법  
가상기억장치 구현 기법의 하나  
가상기억장치에 보관되어 있는 프로그램을 다양한 크기의 논리적 단위로 나눈 후 주기억장치에 적재시켜 실행시키는 기법  
세그먼테이션 기법을 이용하면 페이징 기법보다 기억 공간을 절약할 수 있음  

## 세마포어 (Semaphore)  
'신호기', '깃발'이라는 의미로, 각 프로세스에 제어 신호를 전달하여 순서대로 작업을 수행하도록 하는 기법  
다익스트라가 제안하였으며, P와 V라는 두 개의 연산에 의해 동기화를 유지시키고 상호 배제의 원리를 보장  

## 셰어웨어 (Shareware)  
기능 혹은 사용 기간에 제한을 두고 배포하는 것  
무료로 사용할 수 있으며 일정 기간 사용해 보고 정식 프로그램을 구입해 사욯알 수 있는 소프트웨어  
제조회사들이 정품 판매를 확대하기 위해 공급하는 일종의 샘플  

## 순서 코드 (Sequence Code)  
자료 발생 순서, 크기 순서 등 일정 기준에 따라 최초의 자료부터 차례로 일련 번호를 부여하는 방법  
항목 수가 적고 변경이 적은 자료에 적합  
일정 순서대로 코드를 할당하기 때문에 기억 공간의 낭비가 없고 자릿수가 가장 짧음  

## 슈퍼 컴퓨터 (Supter Computer)  
최신 기술 동향에서 사용되는 복잡한 계산을 초고속으로 실행하는 고성능의 값비싼 컴퓨터  
원자력·기상·우주 분야에서의 계산, 시뮬레이션의 실현을 위한 방대한 데이터의 계산 등을 수행하는 초고속, 고성능 대형 컴퓨터를 말함  
1초간에 5,000만 회에서 1억 5,000만 회 이상의 명령 실행이 가능하며, 대표적인 것으로 CRAY-1, CDC 등이 있음  

## 스래싱 (Thrashing)  
프로세스의 처리 시간보다 페이지 교체 시간이 더 많아지는 현상  
다중 프로그래밍 시스템이나 가상기억장치를 사용하는 시스템에서 하나의 프로세스 수행 과정 중 자주 페이지 부재가 발생하여 나타나는 현상  
전체 시스템의 성능이 저하  
다중 프로그래밍 정도가 높아짐에 따라 CPU의 이용률은 특정 어느 시점까지는 높아지지만 다중 프로그래밍 정도가 더욱 커지면 스래싱이 나타나고, CPU의 이용률은 급격히 감소하게 됨  

## 스레드 (Thread)  
프로세스 내에서 작업 단위로 시스템의 여러 자원을 할당받아 실행하는 프로그램의 단위  
하나의 프로세스에 하나의 스레드가 존재하면 단일 스레드, 하나 이상의 스레드가 존재하면 다중 스레드  

## 스트리밍 (Streaming) 기술  
웹에서 오디오, 비디오 등의 멀티미디어 데이터를 다운로드하면서 동시에 재생해 주는 기술  
용량이 큰 멀티미디어 데이터 전체를 모두 다운로드하려면 시간이 꽤 걸려서 데이터를 조금씩 전송받는 대로 즉시 재생해 주는 스트리밍 기술이 개발  

## 스풀링 (Spooling)  
저속의 출력장치인 프린터를 고속의 중앙처리장치(CPU)와 병행 처리할 때, 컴퓨터 전체의 처리 효율을 높이기 위해 사용하는 기능  
인쇄할 내용을 먼저 하드디스크에 저장하고 백그라운드 작업으로 CPU의 여유 시간에 틈틈이 인쇄하기 때문에 프린터가 인쇄중이라도 다른 응용 프로그램을 실행하는 포그라운드 작업 가능  

## 시스템 소프트웨어 (System Software)  
시스템 전체를 작동시키는 프로그램  
프로그램을 주기억장치에 적재시키거나 인터럽트 관리, 장치 관리, 언어 번역 등의 기능을 담당  
가장 대포적인 프로그램이 운영체제  

## 시스템 LSI(System Large Scale Intergrated)  
전자제품을 구성하는 다양한 반도체 기능을 하나로 통합한 IC  
메모리 반도체를 비롯한 개별 반도체(Discrete) 등을 제외한 대부분 반도체를 통칭하는 말  
시스템온칩(SoC) 혹은 시스템 반도체 라고도 불림  

## 실감 음향 기술 (Actual Feeling Sound Technology)  
입체영상과 접목되어 음원과의 거리를 실시간으로 예측함으로써 현장감 및 몰입감을 높여주는 기술  
가상현실 기술을 이용한 스테레오 시스템 기술, 가상의 음장을 재현하는 스테레오 기술, 3차원 영상 기술을 보완하여 현장감을 살리는 음향 기술, 음원이 생성되는 공간을 그대로 또는 가공하여 재현하기 위한 HRTF 처리 기술 등이 있음  

## 실감미디어 (Immersive Media)  
현실 세계를 가장 근접하게 재현하고자 하는 차세대 미디어  
현재 사용하는 미디어보다 월등히 나은 표현력과 선명함, 현실감을 제공하여 방송, 영화, 게임 등의 엔터테인먼트 분야 뿐 아니라 컴퓨터 그래픽스, 디스플레이 및 산업 응용 등 다양한 분야에서 활용이 예상  

## 실시간 처리 시스템 (Real Time Processing)  
데이터 발생 즉시, 또는 데이터 처리 요구가 있는 즉시 처리하여 결과를 산출하는 방식  
우주선 운행이나 레이터 추적기, 핵물리학 실험 및 데이터 수집, 전화 교환장치의 제어, 은행의 온라인 업무 등 시간에 제한을 두고 수행되어야 하는 작업에 사용  

## 압전 세라믹 기술 (Piezo Ceramic Technology)  
물리적 압력이 가해지면 전기가 발생하는 모듈을 세라믹 소자로 구성하는 기술  
유동인구가 많은 지하철역이나 백화점, 통행 차량이 많은 교량 등에 설치해 전기를 생산하여 활용하면 전기에너지를 절약할 수 있음  

## 액정 디스플레이 (LCD; Liquid Crystal Display)  
액정 표시기라고도 함  
2장의 얇은 유리판에 액상 결정(Liquid Crystal)을 넣고, 전압을 가해 화면을 보여주는 장치  
CRT보다 두께를 얇게 할 수 있고 빛을 저지하는 원리로 동작하여 LED나 플라즈마 디스플레이(빛을 내뿜는 원리)보다 전력 소모가 적음  
화면의 그리드가 패시브 매트릭스, 액티브매트릭스로 형성  
액티브 매트릭스 : TFT 디스플레이로 알려져 있는 것으로, 픽셀마다 박막 트랜지스터가 연결되어 픽셀 단위로 전압을 조정하여 표시  
패시브 매트릭스 : 가로와 세로의 격자 단위로(픽셀 단위 X) 전압 조정하여 표시  

## 약자식 코드 (Letter Type Code)  
코드화 대상 항목의 약자를 그대로 코드로 사용하는 방법  
일반적으로 많이 사용하는 기호나 문자의 약자를 코드화 하여 코드 식별 용이  

## 양안시차 (Binocular Disparity)  
왼쪽 눈의 영상과 오른쪽 눈의 영상과의 차이  
사람은 양안시차로 입체감을 느낌  
3D TV : 이를 이용해 입체 영상을 구현한 TV 방식  

## 어셈블러 (Assembler)  
어셈블리어로 작성된 원시 프로그램을 기계어로 된 목적 프로그램으로 어셈블(Assemble)하는 언어 번역 프로그램  
과정은 크게 2단계(Pass)로 나누어서 수행되는데, 2개의 Pass를 사용하면 기호를 정의하기 전에 사용할 수 있는 프로그램 작업이 용이  

### 어셈블리어  
= 니모닉(Mnemonic, 상징어)  
기계어와 일대일로 대응되는 기호로 이루어진 언어  

## 엑사바이트 (EB; Exabyte)  
디지털 신호의 처리 속도 또는 용량을 표시하는 단위  
1EB = 2^60 바이트 = 1,024^6 바이트  

## 엠페그 응용 포뱃 (MPEG-A; MPEG-Application)  
MPEG에서 수행해 온 멀티미디어 응용 포맷 표준(ISO/IEC 23000)  
기존 표준들과 달리 시장의 요구에 빠르게 부응할 수 있는 멀티미디어 애플리케이션 혹은 서비스를 개발하는 것을 우선적인 목표로 함  
이를 위해 새로운 기술을 정의하고 개발하기 보다 현존하는 여러 기술을 적절히 조합해 MAF(Multimedia Application Format)라는 새로운 응용 포맷을 정의  
- 예 : Music Player MAF는 MPEG-1, 4, 7, 21 기술, Photo PLayer MAF는 JPEG와 MPEG-4, 7 기술의 일부 이용해 새로운 표준을 정함  

## 연관기억장치 (Associative Memory)  
= CAM(Content Addressable Memory)  
기억장치에서 자료를 찾을 때 주소에 의해 접근하지 않고, 기억된 내용의 일부를 이용해 액세스할 수 있는 기억장치  
캐시 메모리나 가상 메모리 관리 기법에서 사용하는 Mapping Table에 사용됨  
- 장점 : 정보 검색 신속  
- 단점 : 하드웨어 비용 증가 (내용을 비교하기 위한 병렬 판독 논리회로가 있어서)  

### Mapping Table  
대응 관계를 테이블로 표현하여 임의의 정보를 그에 대응하는 정보로 변환하는 것  
## 연산장치 (ALU; Arthmetic & Logical Unit)  
제어장치의 명령에 따라 실제로 연산을 수행하는 장치  
산술연산, 논리연산, 관계연산, 이동(Shift) 등을 수행  
가산기, 누산기(AC; Accumulator), 보수기, 데이터 레지스터, 오버플로 검출기, 시프트 레지스터(Shift Register) 등으로 구성  

## 연상 코드 (Mnemonic Code)  
코드화 대상 항목의 명칭이나 약호와 관계 있는 숫자나 문자, 기호를 이용해 코드를 부여하는 방법  
지명, 물건명, 상호명에 많이 적용  
- 장점 : 코드만 보고 대상 품목을 쉽게 연상할 수 있음  
- 단점 : 자릿수가 길어질 수 있음  

### 약호  
간단하고 알기 쉽게 만든 부호  

## 오류 검사 시스템  
컴퓨터 처리 과정에서 발생할 수 있는 오류를 검사하기 위한 시스템
시스템에 오류가 발생하면 제대로 된 결과를 얻을 수 없어 신뢰성을 잃게 되기 때문에 잘못된 정보의 입력을 막고 오류를 검사해야 함  
- __체크 디지트 검사 (Check Digit Check)__ : 코드 설계 시 본래의 코드에 오류를 검사할 수 있는 한 자리의 숫자를 넣어 컴퓨터에 의해 자동으로 검사  
- __공란 검사 (Blank Check)__ : 공백으로 있어야 할 필드가 확실히 공백으로 되어 있는지 검사  
- __균형 검사 (Balance Check)__ : 차변과 대변의 한계 값을 검사. 대차의 균형이나 가로, 세로의 합계가 일치하는지 검사  
- __형식 검사 (Format Check)__ : 입력되는 데이터의 자릿수, 형식, 행, 열, 페이지 번호 등이 규정대로 되어 있는지 검사  
- __한계 검사 (Limit Check)__ : 입력 데이터의 어떤 항목이 규정된 범위 내에 있는지 검사  
- __일괄 합계 검사 (Batch Total Check, Sum Check)__ : 입력 데이터의 특정 항목 합계값을 미리 계산해서 입력데이터와 함께 입력하고, 컴퓨터 상에서 계산한 결과 값과 수동 계산 결과 값이 같은지 검사  
- __타당성 검사 (Validity Check)__ : 입력된 데이터에 논리적으로 오류가 있는지 검사  
- __숫자 검사 (Numeric Check)__ : 숫자형의 입력 항목에만 적용. 입력된 데이터가 모두 숫자인가 검사  
- __대조 검사 (Matching Check)__ : 입력 데이터와 시스템에 보관된 별도의 코드 표를 대조하여 그것이 일치하는지 검사  

## 오버레이 (Overlay) 기법  
주기억장치보다 큰 사용자 프로그램을 실행하기 위한 기법  
보조기억장치에 저장된 하나의 프로그램을 여러 개의 조각으로 분할한 후, 필요한 조각을 차례로 주기억장치에 적재하여 프로그램 실행  
프로그램이 실행되면서 주기억장치의 공간이 부족하면 주기억장치에 적재된 프로그램의 조각 중 불필요한 조각이 위치한 장소에 새로운 프로그램의 조각을 중첩(Overlay)하여 적재  
프로그램을 여러 개의 조각으로 분할하는 작업은 프로그래머가 수행해야 하므로 프로그래머는 시스템 구조나 프로그램 구조를 알아야 함  
![오버레이-기법](https://i.pinimg.com/564x/2c/43/ac/2c43acd54f7be957d40a547ee1f3e3de.jpg)  

## 외계인 코드 (Alien Code)  
아주 오래 전에 개발되어 유지보수 작업이 매우 어려운 프로그램  
일반적으로 15년 전 혹은 그 전에 개발된 프로그램을 말함  
문서화(Documentation)를 철저하게 하면 외계인 코드를 방지할 수 있음  

## 워드 (Word)  
CPU가 한번에 처리할 수 있는 명령 단위  
바이트의 모임으로, 하프워드(2바이트), 풀워드(4바이트), 더블워드(8바이트)  

## 워크스테이션 (Workstation)  
그래픽, CAD, CAE, 시뮬레이션, 과학 애플리케이션 등에 전형적으로 이용되는 고성능 단일 사용자 컴퓨터  
유닉스나 리눅스 기반으로 동작하는 RISC 기반의 컴퓨터가 대부분  
주로 Sun, HP, IBM, SGI 등의 업체에서 생산  
워크스테이션과 이에 사용되는 응용 프로그램들은 소규모 엔지니어링 회사, 건축가, 그래픽 디자이너, 처리 속도가 빠른 마이크로프로세서와 대용량 메모리 및 고속 그래픽 어댑터와 같은 특수한 기능들을 필요로 하는 기관이나 부서 및 개인이 주로 사용  

### RISC  
기억, 연산, 제어장치가 한 개의 반도체 칩에 내장된 마이크로 프로세서(MPU)의 한 종류  
다른 종류인 CSC에 비해 기능이 우수  

## 워킹 셋 (Working Set)  
프로세스가 일정 시간동안 자주 참조하는 페이지들의 집합  
데닝(Denning)이 제안한 프로그램의 움직임에 대한 모델  
자주 참조되는 워킹 셋을 주기억장치에 상주시켜 페이지 부재 및 페이지 교체 현상을 줄임  

### 페이지 부재 (Page Fault)  
프로세스 실행 시 페이지가 주기억장치에 없는 현상  

## 웹 스피어 (Web Sphere)  
IBM 사에서 개발  
복잡한 사업용 웹 사이트를 제작·관리하기 위한 자바 기반 도구의 모음  
트랜잭션 관리, 보안, 클러스터링, 기능성, 가용성, 연결성, 확장성을 포괄하는 완전한 애플리케이션 서비스 세트를 구비  
기업 전반의 애플리케이션 관리와 통합 기능 제공  
개인 정보 기반으로 고객 취향과 기호에 맞는 상품/서비스를 제공할 수 있는 e-비즈니스 사이트 구축을 지원  

### 트랜잭션  
정보 처리 과정에 있어서 데이터의 변화를 보장하는 일 담당  

### 클러스터링  
가변적인 업무 부하를 처리하거나 여러 대의 컴퓨터 사용 도중 한 대가 고장났을 경우에도 운영 되도록 여러 대의 컴퓨터 시스템을 서로 연결하는 것  

## 위성 생태학 (Satellite Ecology)  
위성 영상자료를 이용해 자원의 이용이 환경 및 생태계에 미치는 영향을 분석하는 학문  
IT와 ET가 융합해 환경 문제를 해결하기 위한 방법으로 고해상도와 3차원으로 고도화된 위성 영상자료를 생태분석체계와 연계시키는 학문  

## 위젯 (Widget)  
컴퓨터에서 운영체제의 응용 프로그램을 동작시키고 결과를 화면에 표시하는 작은 그래픽 사용자 인터페이스(GUI) 도구  
인터넷으로부터 정보를 전달 받아 화면에 표시하는 작은 윈도우  
브라우저에서 제공되던 많은 기능들(메모장, 시계, 달력, 지도, 뉴스 등)이 브라우저를 열지 않고도 제공  
응용 프로그램 작성 시 자주 이용하는 사용자 중심의 그래픽과 데이터 처리 프로그램들을 모은 라이브러리도 위젯  
X윈도우가 윈도우 매니저에 따라 서로 다른 모습을 가지는 것은 위젯 라이브러리가 다르기 때문  
- 현재 가장 많이 사용되는 위젯 라이브러리 : 리눅스 KDE의 QT 라이브러리, GNOME의 GNU의 GTK+ 라이브러리  

## 윈도우(Windows)  
데스크톱 컴퓨터와 랩톱 컴퓨터에서 가장 널리 사용되는 운영체제  
마이크로소프트(Microsoft) 사에서 개발  
기본적으로 x86 기반의 CPU에서 작동 (몇 개의 버전은 인텔의 Itanium CPU에서 작동)  
그래픽 사용자 인터페이스(GUI)와 화면 크기 조절 및 이동 가능한 윈도우 상에 표시되는 데스크톱 이용 환경 제공  

## 윈도우 CE (Windows CE)  
마이크로소프트 사가 PDA 등의 핸드 헬드 PC용으로 개발한 운영체제  
마이크로소프트 윈도우 플랫폼을 축소한 버전  
32비트의 다중 작업 및 다중 스레딩 운영체제(Multi Threading OS)로, 일반 데스크 사용자들에게 익숙한 사용자 인터페이스를 제공하고, 엑셀, 마이크로소프트 워드, 인터넷 익스플로러, 마이크로소프트 응용 프로그램의 축소 버전과 이메일 클라이언트 포함  

### 핸드 헬드 (Hand Held)  
손에 쥘 수 있다는 의미  

### 플랫폼  
프로그램이 실행될 수 있는 기초를 이루는 컴퓨터 시스템  

### 다중 스레딩  
스레드(Thread)는 프로세스 내에서의 작업 단위  
시스템의 여러 자원을 할당받아 실행하는 프로그램의 단위  
하나 이상의 스레드가 존재하며, 그를 이용하여 작업을 수행하는 것  

## 유기 박막 트랜지스터 (OTFT; Organic Thin-Film Transistor)  
채널 층으로서 무기질(실리콘) 층 대신 유기 반도체 층을 사용한 박막 트랜지스터  
전체 구조는 실리콘 기반의 트랜지스터와 큰 차이 없음  
게이트에 전압을 가하면 절연막 때문에 전류가 흐르지 않고, 반도체에 전기장(전계)이 걸리므로 전계 효과 트랜지스터 역할을 함  
소자의 동작원리 : 게이트에 가해진 전압에 따라 절연체 부분이 전하가 없는 층(Depletion Layor), 또는 전하가 모인 층(Accumulation Layer)이 되어 소스와 드레인 사이에 흐르는 전류의 양이 제어됨. 이 전류양의 비를 점멸비라고 하며, 디스플레이 용도(ex: 컴퓨터 모니터)에서 중요한 역할  
OTFT 모니터는 밝고 컬러가 선명, 감응 속도가 빠름, 화면 기판으로 플라스틱을 사용할 수 있어 구부릴 수 있는 화면도 가능  

