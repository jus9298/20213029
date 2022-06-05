# 20213029

#프로세스 명령어

1) top
* 실시간으로 CPU, Memory, Process 등 시스템의 상태를 빠르게 파악
* 옵션 없이 입력시 interval 간격으로 화면을 갱신하며 정보를 보여줌
* top 실행 전 옵션: 

-b 옵션: 순간의 정보 확인(batch 모드)

-n 옵션: top 실행 주기 설정(반복)

* top 실행 후 명령어: 

shift + p: CPU 사용률 내림차순

shift + m: 메모리 사용률 내림차순

shift + t: 프로세스가 돌아가고 있는 시간 순

k: kill.k 입력 후 PID(프로세스 ID) 번호 작성. signal은 kill signal인 9를 입력

f : sort field 선택 화면 -> q 누르면 RES순으로 정렬

a : 메모리 사용량에 따라 정렬

b : Batch 모드로 작동

1 : CPU Core별로 사용량을 보여줌

s: 보안모드 작동

space bar: refresh

h: 도움말

n: 반복 횟수 제한 

___

2) ps

* ps 옵션: System V, BSD, GNU에 따라 옵션 표기와 결과가 달라짐.

-A: 모든 프로세스 출력

a(BSD): 터미널과 연관된 프로세스 출력

-a: 세션 리더를 제외한 터미널에 종속되지 않은 모든 프로세스 출력

-e: 커널 프로세스를 제외한 모든 프로세스 출력

-f: 풀 포맷으로 보여줌. 유닉스 스타일로 출력해주는 옵션으로 UID(프로세스 소유자의 이름), PID, PPID(부모 프로세스 ID)등이 함께 표시된다.

-l(sys V)/l(BSD): 긴 포맷으로 보여줌. 프로세스의 정보를 길게 보여주는 옵션으로 우선순위와 관련된 PRI와 NI값을 확인할 수 있다.

-o 값: 출력 포맷을 지정하는 옵션. 값으로 PID, TTY(프로세스와 연결된 터미널), Time, cmd등을 지정할 수 있다. 

-M: 64비트 프로세스를 보여줌

-m: 프로세스와 커널 스레드를 보여줌

-p: 특정 PID를 지정할 때 사용

-r: 현재 실행 중인 프로세서를 보여줌

u(BSD): 프로세스의 소유자를 기준으로 출력(aux 등)

-u: 특정 사용자의 프로세스 정보 확인(지정하지 않을 시 현재 사용자)

x(BSD): 터미널에 종속되지 않은 프로세스 출력

-x: 로그인 상태에 있는 동안 아직 완료되지 않은 프로세서 확인

-C: 특정 이름의 프로세스 PID 출력

* 특정 프로세스 확인: System V: ps -ef| grep <프로세스>, BSD: ps aux| grep <프로세스>

___

3) ps와 top 차이

* ps는 ps시점에 proc에서 검색한 cpu 사용량
* top은 proc에서 일정 주기로 합산해 cpu 사용율 출력

___

4) kill

* kill 옵션/시그널(번호나 이름) PID
* kill -9 PID : 프로세스에 시그널을 보내는 명령어. 프로세스를 강제 종료
* 옵션

-l: signal의 종류 출력: 

SIGHUP(세션이 종료), SIGINT(종료 요청), SIGKILL(강제 종료), SIGSEGV(메모리 침범), SIGTERM(종료 요청), SIGTSTP(일시 중지 요청) 

___

5) jobs

* 작업이 중지된 상태, 백그라운드로 진행 중인 상태, 변경되었지만 보고되지 않은 상태 등을 표시하는 명령어.
* 각 작업에 번호가 붙어있어 kill %번호 등으로 사용할 수 있음.
* jobs *옵션* *jobID*
* jobs -x command *args*
* 옵션:

-l: PID를 추가하여 백그라운드 프로세스 출력

-n: 대표 프로세스 ID출력

-p: 각 프로세스 ID에 대해 한 행씩 출력

___

#vim에디터에서 매크로 사용법

1) 매크로 기록

* vim 중립모드에서 q를 누른 후 매크로 이름으로 사용할 알파벳 입력. -- recording -- 이 뜨면 기록 시작. 기록이 끝나고 다시 중립모드에서 q 입력.

2) 매크로 재생

* 중립모드에서 @입력후 매크로이름 입력. @@는 가장 마지막에 재생된 메크로가 실행 됨.

3) 매크로 저장

* ~/.vimrc 파일을 연 후 let @(매크로이름)=' 을 입력한 후 insert모드에서 ctrl-R ctrl-R (매크로이름) 을 입력하면 매크로의 내용이 입력됨. '로 닫아준다.

* 원하는숫자@매크로이름 입력시 매크로가 그 수만큼 반복됨













