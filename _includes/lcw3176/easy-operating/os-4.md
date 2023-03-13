### 이찬우

# CPU 스케줄링
## 스케줄링 단계
### 고수준
- 시스템 내의 전체 작업 갯수 조절

### 중간 수준
- 중지와 활성화로 활성화된 프로세스 갯수 조절, 과부하 방지
- 고수준과 저수준의 완충 역할

### 저수준
- 프로세스별 CPU 할당 및 상태 결정
- 짧은 시간동안 처리, 단기 스케줄링이라고도 불림

## 스케줄링 방식
### 선점형
- CPU 사용권 빼앗을 수 있음
- 인터럽트, 대화형 시스템, 시분할 시스템

### 비선점형
- CPU 사용권 뺏을 수 없음
- 일괄 작업 시스템

## 생각한 점들
### 스레드의 우선순위
- 프로세스는 OS의 CPU 스케줄러가 우선순위를 관리함
- 그러면 프로세스 안의 스레드는 우선순위가 어떻게 관리될까

### 자바
- 우선순위 스케줄링, 라운드 로빈 두 가지 방식 사용
- 사용자는 우선순위 스케줄링 영역만 조절 가능

```java
thread.setPriority(1~10);
thread.setPriority(Thread.MIN_PRIORITY);
thread.setPriority(Thread.NORM_PRIORITY);
thread.setPriority(Thread.MAX_PRIORITY);
```

### C#
- UI 스레드와 작업 스레드가 별도로 존재
- UI 스레드에는 다른 스레드가 접근 불가, Dispatcher.invoke 등의 함수를 통해 큐에 삽입, 작업 요청

### 안드로이드
- UI 스레드, 바인더 스레드, 워커 스레드 등 존재
- UI 스레드는 C#과 비슷한 속성을 가짐, 메인스레드 만이 UI 조작 가능, 싱글 스레드
- 바인더 스레드는 IPC, 워커 스레드는 긴 기간의 작업 처리