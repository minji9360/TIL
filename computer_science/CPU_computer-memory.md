# Computer Architecture  
__하드웨어__
- 중앙처리장치(CPU)
- 기억장치 : RAM, HDD, 캐시 등
- 입출력 장치 : 마우스, 키보드, 프린터 등  

__소프트웨어__
- 시스템 소프트웨어 : 운영체제(Windows, Unix, Linux), 컴파일러
- 응용 소프트웨어 : 엑셀, 파워포인트, 게임 등

## 중앙처리장치  
= CPU (Central Processing Unit)  
= 마이크로 프로세서  
= 프로세서 (처리장치)  
= 집적회로 (IC)  
> 모두 같은 의미는 아니지만, 정보처리산업기사 시험에서는 중앙처리장치를 칭하는 말로 표현되는 듯 하다.
  

### 3대 기능
- 연산장치
- 제어장치
	- 주기억장치에 기억된 명령을 꺼내서 해독하고, 시스템 전체에 지시 신호를 내는 장치
	- 명령 코드가 명령을 수행할 수 있게 필요한 제엉 기능을 제공
- 기억장치  

### 구성 요소
![CPU_내부](https://t1.daumcdn.net/cfile/tistory/1351F51F4C916CBD48)  
<span style="color: gray">출처 : https://lomars.tistory.com/entry/CPU%EA%B5%AC%EC%A1%B0</span>

## 주기억장치  
- 주기억장치
	- 고속
	- 고가
	- 소용량
	- CPU가 직접 접근해서 명령이나 데이터를 가져갈 수 있음
	- RAM, ROM, ~~자기코어~~ 과거
- 보조기억장치
	- 저속
	- 저가
	- 대용량
	- CPU가 직접 접근하지 않고 보조기억장치의 데이터를 주기억장치에 옮겨서 CPU로 전달
	- 하드디스크, DVD-ROM, 플래시메모리 등 RAM과 ROM을 제외한 모든 기억장치

### ROM (Read Only Memory)
__ROM__
- 읽기 전용 기억장치
- 비휘발성 기억장치  
(컴퓨터 메인보드에 붙어 있는 배터리가 전기를 공급해줘서 전원을 꺼도 메모리가 날아가지 않음.  
 만약 컴퓨터를 1년간 안켜서 배터리가 방전된다면 메모리가 날아갈 것)  
- BIOS(Basic Input Output System), POST(Power On Self Test), 모니터 프로그램 등을 저장  

__Mask ROM__
- 반도체 공장에서 필요한 프로그램들이 저장된 채 생산
- 한 번 입력된 데이터는 수정할 수 없는 ROM

__PROM__  
- 빈 ROM으로, 사용자가 한 번만 내용을 기입할 수 있지만 수정하거나 지울 수는 없다.  

__EP ROM__  
- 자외선(UV)을 이용해 메모리를 여러번 수정 가능  

__EEP ROM__
- 전기적인 방법을 이용해 메모리를 여러번 수정 가능  

### RAM (Random Access Memory)
- 읽고 쓰기가 자유로움
- 휘발성 기억장치
- 현재 실행 중인 program과 data를 임시 저장  
- 최소 3개의 입력 단자 (읽기 신호, 쓰기 신호, 주소 버스 + 칩 선택 신호)

![DRAM_SRAM_차이](https://t1.daumcdn.net/cfile/tistory/23076C42572D226839)  
<span style="color:gray">출처 : https://nyamtutorial.tistory.com/61</span>  

### 자기코어
- 전류 일치 기술
- 파괴성 (DRO : Destruction Read Out) 메모리
- 자료 읽은 후 재저장 필요
