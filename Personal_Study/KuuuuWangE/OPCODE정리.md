# 명령어 정리

>   필요시 검색이 용이하도록 미리 정리



## 데이터 조작

-   MOV
    -   데이터 이동
-   PUSH
    -   오퍼랜드 내용을 스택에 쌓아둠
-   POP
    -   스택으로부터 갑슬 뽑아낸다.
-   XCHG
    -   첫 번째 오퍼랜드와 두번째 오퍼랜드 교환
-   IN
    -   오퍼랜드로 지시된 포트로부터 AX에 데이터 입력
-   OUT
    -   오퍼랜드가 지시한 포트로 AXdml epdlxj cnffur
-   XLAT
    -   BX:AL이 지시한 테이블의 내용을 AL로 로드
-   LEA
    -   메모리의 오프셋값을 레지스터로 로드
-   LDS
    -   REG < MEM , DS < MEM+2
-   LES
    -   REG < MEM, ES < MEM+2
-   LAHF
    -   플래그의 내용을 AH의 특정 비트로 로드
-   SAHF
    -   AH의 특정 비트가 플래그 레지스터로 전송
-   PUSHF
    -   플래그 레지스터의 내용을 스택에 쌓음
-   POPF
    -   스택으로부터 플래그 레지스터로 뽑음



## 연산

-   ADD
    -   캐리를 포함하지 않은 덧셈
-   SBB
    -   캐리를 포함한 뺄셈
-   DEC
    -   오퍼랜드 내용 1 감소
-   NEG
    -   오패른드의 2의 보수 (부호 반전)
-   CMP
    -   두 개의 오퍼랜드 비교
-   ADC
    -   캐리를 포함한 덧셈
-   INC
    -   오퍼랜드 내용 1 증가
-   AAA
    -   덧셈 결과 AL값을 UNPACK 10진수로 보정
-   DAA
    -   덧셈 결과의 AL값을 PACK 10진수로 보정
-   SUB
    -   캐리를 포함하지 않은 뺄셈
-   AAS
    -   뺄셈 결과 AL값을 UNPACK 10진수로 보정
-   DAS
    -   뺄셈 결과의 AL값을 PACK 10진수로 보정
-   MUL
    -   AX와 오퍼랜드를 곱셈하여 결과를 AX 또는 DX:AX에 저장
-   IMUL
    -   부호화된 곱셈
-   AAM
    -   곰셈 결과 AX값을 UNPACK 10진수로 보정
-   DIV
    -   AX 또는 DX:AX 내용을 오퍼랜드로 나눔, 몫은 AL, AX 나머지는 AH, DX로 저장
-   IDIV
    -   부호화된 나눗셈
-   AAD
    -   나눗셈 결과 AX 값을 UNPACK 10진수로 보정
-   CBW
    -   AL의 바이트 데이터를 부호 비트를 포함하여 AX 워드로 화강
-   CWD
    -   AX의 워드 데이터를 부호를 포함하여 DX:AX의 더블 워드로 변환



## 논리

-   NOT
    -   오퍼랜드의 1의 보수 (비트 반전)
-   SHL/SAL
    -   외쪽으로 오퍼랜드만큼 자리 이동 (최하위 비트 0)
-   SHR
    -   오른쪽으로 오퍼랜드만큼 자리 이동 (최상위 비트 0)
-   SAR
    -   오플ㄴ쪽 자리이동, 최상위 비트 유지
-   ROL
    -   왼쪽으로 오퍼랜드만큼 회전 이동
-   ROR
    -   오른쪽으로 오퍼랜드만큼 회전 이동
-   RCL
    -   캐리를 포함하여 왼쪽으로 오퍼랜드만큼 회전 이동
-   RCR
    -   캐리를 포함하여 오른쪽으로 오퍼랜드만큼 회전 이동
-   AND
    -   논리 AND
-   TEST
    -   첫 번재 오퍼랜드와 두 번재 오퍼랜드를 AND 하여 그 결과로 플래그 세트
-   OR
    -   논리 OR
-   XOR
    -   베타 논리 합 (OR)



## 문자열

-   REP
    -   REP 뒤에 오는 스트링 명령을 CX가 0이 될 때까지 반복
-   MOVS
    -   DS:SI가 지시한 메모리 데이터를 ES:DI가 지시한 메모리로 전송
-   CMPS
    -   DS:SI와 ES:DI가 지시한 메모리 내용 비교하고 결과에 따라 플래그 설정
-   SCAS
    -   AL 또는 AX와 ES:DI가 지시한 메모리 내용을 비교하고 결과에 따라 플래그 설정
-   LODS
    -   SI 내용을 AL 또는 AX로 로드
-   STOS
    -   AL 또는 AX를 ES:DI가 지시하는 메모리에 저장



## 제어

-   CALL
    -   프로시저 호출
-   JMP
    -   무조건 부기
-   RET
    -   CALL로 스택에 PUSH된 주소로 복귀
-   JE/JZ
    -   결과가 0이면 분기
-   JL/JNGE
    -   결과가 작으면 분기 (부호화된 수)
-   JB/JNAE
    -   결과가 작으면 분기 (부호화 안 된 수)
-   JBE/JNA
    -   결과가 작거나 같으면 분기 (부호화 안 된 수)
-   JP/JPE
    -   패리티 플래그가 1이면 분기
-   JO
    -   오버플로우가 발생하면 분기
-   JS
    -   부호 플래그가 1이면 분기
-   JNE/JNZ
    -   결과가 0 이 아니면 분기
-   JNL/JGE
    -   결과가 크거나 같으면 분기 (부호화된 수)
-   JNLE/JG
    -   결과가 크면 분기 (부호화된 수)
-   JNB/JAE
    -   결과가 크거나 같으면 분기 (부호화 안 된 수)
-   JNBE/JA
    -   결과가 크면 분기 (부호화 안 된 수)
-   JNP/JPO
    -   패리티 플래그가 0이면 분기
-   JNO
    -   오버플로가 아닌 경우 분기
-   JNS
    -   부호 플래그가 0이면 분기
-   LOOP
    -   CX를 1감소하면서 0 이 될 때가지 지정된 라벨로 분기
-   LOPPZ/LOOPE
    -   제로 플래그가 1이고 CX가 0이면 지정된 라벨로 분기
-   LOOPNZ/LOOPNE
    -   제로 플래그가 0이고 CX가 0이면 지정된 라벨로 분기
-   JCXZ
    -   CX가 0이면 분기
-   INT
    -   인터럽트 실행
-   INTO
    -   오버플로우가 발생하면 인터럽트 실행
-   IRET
    -   인터럽트 복귀 (리턴)



## 프로세스 제어

-   CLC
    -   캐리 플래그 클리어
-   CMC
    -   캐리 플래그 반전
-   CLD
    -   디렉션 플래그 클리어
-   CLI
    -   인터럽트 플래그 클리어
-   HLT
    -   정지
-   LOCK
    -   
-   STC
    -   캐리 플래그 셋
-   NOP
    -   아무것도 실행안함
-   STD
    -   디렉션 플래그 셋
-   STI
    -   인터럽트 인에이블 플래그 셋
-   WAIT
    -   프로세스 일시 정지 상태
-   ESC
    -   이스케이프 명령



## 8086 어셈블리 지시어

-   DB
-   DW
-   DD
-   DQ
-   DT
-   EQU
-   =
-   EVEN
-   PAGE
-   TITLE

