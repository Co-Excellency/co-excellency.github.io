### 김남영

# 운영체제

## 운영체제란 무엇인가
- 사용자에게 편리한 인터페이스 환경을 제공하고 컴퓨터 시스템의 자원을 효율적으로 관리하는 소프트웨어

<br>

<img src="https://user-images.githubusercontent.com/89288109/208413192-58fd6c5f-830a-464f-b7d0-56b306296b0d.png">

- 다양한 인터페이스를 제공하는 것을 그림을 통해 알 수 있다.

<br>

## 운영체제의 역할
- 자원 관리 및 보호
- 하드웨어 및 사용자 인터페이스 제공


<br>

## 커널과 인터페이스

<br>

### 커널
- 프로세스, 메모리, 저장장치 관리 같은 운영체제의 핵심 기능을 모아 놓은 것.
- 자동차의 엔진과 비슷한 개념.

<br>

<img src = "https://user-images.githubusercontent.com/89288109/208414700-2ff0718a-e509-4cf5-82d4-b0a44f910444.png">

<br>

#### 시스템 호출
- 커널에 직접 접근 보다 간접 접근
- 커널을 보호하기 위한 인터페이스
- 커널을 직접 건드리는 것은 위험하다.

<br>

#### 드라이버
- 커널과 하드웨어의 인터페이스
- 마찬가지로 추상화 시켜놓았다고 생각
- 하지만 커널과 하드웨어는 직접적으로 연결되기도 한다.

<br>

### 커널의 구성

<br>

#### 단일형 구조 커널
- 하나로 다 뭉친 모듈
- 비용이 적게 들지만, 단점이 너무 많다.
- 버그, 오류 처리 힘듬 이식성 낮음 등등..

<br>

<img src = "https://user-images.githubusercontent.com/89288109/208417188-275d5daa-8ed3-432f-b645-898896a9a7b4.png">

#### 계층형 구조 커널
- 비슷한 기능의 모듈을 하나의 계층으로 만듬
- 계층 간 통신으로 OS를 구현
- 오류 수정 시 특정 계층만 수정하므로 용이하므로 디버깅이 쉬움
- 현대 OS 대부분의 구조

<br>

<img src = "https://user-images.githubusercontent.com/89288109/208417386-2d416ffc-253d-4a9f-a770-f12d1ee25812.png">

#### 마이크로 구조 커널
- 커널 자체가 커질 경우를 대비
- 각 모듈은 독립적인 작동, 하나의 모듈이 말썽이어도 OS가 멈추지 않음.
- 모듈 간 정보 교환은 프로세스 간 통신으로 이루어짐.

<br>


#### 가상머신
- C와 다르게 Java는 어느 OS에서도 작동한다. 바로 가상머신 덕분!
- 운영 체제 위에 가상머신을 만들고 그 위에 응용 프로그램을 작동시키자.
- 동일한 환경에서 작동하는 것처럼 보인다.
- 하지만 가상머신을 통해서만 응용 프로그램이 작동하므로 느려진다는 단점이 있다.


<br>

## 폰노이만 구조
- 모든 프로그램은 메모리에 올라와야 실행할 수 있다.
- 예전에는 컴퓨터의 전선을 연결하여 회로룰 구성하는 형태였기에, 다른 용도로 사용하려면 전선의 연결을 바꾸어야 했다.

<br>

## CPU

<br>

### CPU의 기본 구성
- 산술논리 연산 장치
  - 사칙연산 같은 산술 연산과 OR, AND 논리 연산
- 제어 장치
  - CPU에서 작업을 지시하는 부분
- 레지스터
  - CPU 내에 데이터를 임시로 보관하는 곳

<br>

## 버스
- CPU와 메모리, 주변장치 간 데이터를 주고 받을 때 사용한다.
- 제어, 주소, 데이터 버스

<br>

## 메모리의 종류
- RAM 
  - 읽거나 쓰기 가능
- ROM
  - 읽기만 가능

<br>

## 부팅
- 운영체제도 소프트웨어이므로 실행하려면 메모리에 올라와야 한다.
- 그 과정을 부팅이라고 한다.

<img src = "https://user-images.githubusercontent.com/89288109/208420246-f01bbd2b-1fb6-44a7-950b-f52fcb1f7f15.png">

<br>

## 버퍼
- 속도의 차이가 있는 두 장치 간 차이를 완화하는 역할
- 작업 속도가 다른 장치들의 속도 차이를 개선하기 위한 기술
- CPU 내부 버스, 시스템 버스, 메모리, 하드디스크의 속도 차이.

<br>

## 캐시
- 메모리와 CPU 간 속도 차이를 완화하기 위해 메모리의 데이터를 미리 가져와 저장하는 임시 장소
- CPU가 메모리에 접근하기 전 일단 캐시를 방문해 데이터가 있는지 찾는다.
- 있으면 캐시 히트
- 없으면 캐시 미스
- 일반적인 컴퓨터의 캐시 적중률은 90%

<br>

## 인터럽트
- CPU가 일을 직접하는 것이 아니라, 저장장치 데이터 이동을 독립적으로 운영
- 입출력 관리자에게 데이터 전송만 지시
- 완료 신호를 CPU에게 보냄 => 요 신호가 인터럽트

<br>

### 직접 메모리 접근
- 효율성을 높이기 위해 입출력 관리자가 데이터의 입출력 책임을 맡음.
- 이러한 책임 및 권한을 일컫는다.

### 메모리 매핑 출력
- 직접 메모리 접근으로 메모리가 복잡해졌다.
- CPU가 사용하는지 입출력 장치가 사용하는지 
데이터가 섞여 있음.
- 이때 메모리를 나누어서 관리하자.

### 사이클 훔치기
- 동시에 메모리 접근을 하면 안되므로, 
- 상황 별로 메모리 사용 권한을 양보하자~

<br>

## 병렬 처리
- 동시에 여러 개의 명령을 처리하여 작업의 능률을 올리는 방식

### 병렬 처리의 고려 사항
- 상호 의존성이 없어야 한다.
- 각 단계의 시간을 일정하게 맞추자.
- 전체 작업 시간을 몇 단계로 나눌지 따져보기.
