<aside>
<h2>💡 Critical Section(임계 영역)</h2>

</aside>

- 여러 프로세스가 데이터를 공유하며 수행될 때
- 각 프로세스에서 공유 데이터를 접근하는 프로그램 코드 블록
- 즉 여러 프로세스가 동일 자원을 동시에 참조하여(공유하는 변수명, 파일 등)이 오염될 위험 가능성이 있는 영역
- 다시 말해 공유 자원 접근 순서에 따라 실행 결과가 달라지는 프로그램의 코드 영역 → 임계 구역 안에서 race condition이 발생

<br>

<aside>
<h2>💡 Critical Section 해결 조건</h2>

</aside>

- 다음 3가지 조건 만족이 필요
1. 상호 배제
- 한 프로세스가 임계 구역에 들어가면 다른 프로세스는 임계 구역에 들어갈 수 없음
2. 한정 대기
- 상호 배제 때문에 기다리게 되는 프로세스가 무한 대기하지 않아야 함
- 즉 특정 프로세스가 critical section에 진입하지 못하면 안됨
3. 진행의 융통성
- critical section에 프로세스가 없다면  어떤 프로세스라도 들어가서 자원을 활용할 수 있음
- 즉 두 프로세스가 자원을 번갈아 쓴다고 가정할 때 한 쪽에서 자원을 안 쓰고 있다고 해서 다른 한 쪽 프로세스가 자원을 쓰고 싶어도 자신의 턴이 아니라고 기다리는 것은 효율적이지 못하다는 것
