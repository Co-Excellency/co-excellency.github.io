### 이찬우

# 프로세스
## 프로세스와 프로그램의 관계
- 프로세스: 프로그램 + 프로세스 제어 블록(PCB)
- 프로그램: 프로그램 - 프로세스 제어 블록(PCB)

## 프로세스의 네 가지 상태
### 생성 상태
- 메모리에 올라와 실행 준비 완료, PCB 생성
### 준비 상태
- CPU 사용권 대기 상태
### 실행 상태
- CPU 사용권을 얻어 작업 수행 중인 상태
- 시간 내에 작업 완료 못하면 준비 상태로 변경, 다시 대기
### 완료 상태
- PCB가 사라진 상태

## CPU 스케줄러
### 디스패치
- 준비 상태의 프로세스 중 하나를 골라 실행 상태로 바꾸는 작업

## 프로세스의 다섯 가지 상태 (활성 상태)
- 네 가지 상태 + 대기 상태
### 대기 상태
- 입출력 요청 시 입출력이 완료될때 까지 기다리는 상태
- 입출력 완료 시 준비 상태로 변경

## 보류 상태, 휴식 상태
### 휴식 상태
- 실행을 잠시 멈춘 상태

### 보류 상태
- 작업이 보류된 상태
- 메모리 부족, 프로그램 오류, 바이러스로 판단, 입출력 지연, 긴 주기의 프로세스 등등

## 용어 정리
### 디스패치
- CPU 스케줄러가 준비 상태의 프로세스 중 하나를 골라 실행 상태로 바꾸는 작업, PID를 통해 이루어짐

### PID
- 프로세스 고유 식별 아이디, 구분자

## 생각한 점들
### Sleep 함수
```c++
// 1초 쉬는 코드

::Sleep(1000)

```
#### 작동 방식
1. 1초동안 OS의 CPU 스케줄러에서 제외됨
2. 1초 후에 다시 스케줄러에 등록됨

#### 위험 요소
- 스케줄러에서 제외 / 등록되는 시간
- 프로세스 상태가 전환되는 시간 등등
- 정밀한 시간 계산이 아님
- OS의 상황에 따라 랜덤하게 시간이 변동됨

#### 생각해 본 해결 방안
- 임베디드 환경에서 아이디어 착안
- 보드의 크리스탈(발진기)의 클럭에 맞춰서 타이머 or 인터럽트 구현
- CPU의 클럭 계산에 따른 코드 구현 시 보다 정밀할 것으로 예상 
