# [Code_Engn]Basic_RCE_L06

생성일: 2022년 12월 12일 오후 5:19
태그: Rev

![Untitled](/IMG/6-0.png)

찾아야 하는것

- OEP
- Serial 코드

> OEP란 Original Entry Point를 말한다. 패킹된 파일을 실행할 때 자동적으로 시스템 내부에서 언패킹을 한다. 언패킹이 끝나면 복구한 원본코드를 동작시켜야 하는데 이 원본코드의 Entry Point를 OEP라고 한다.
> 

DIE로 파일 확인

![Untitled](/IMG/6-1.png)

확인해보니 UPX로 패킹되어 있었습니다.

먼저 언패킹을 해주겠습니다.

![Untitled](/IMG/6-2.png)

언패킹한 파일을 xdbg로 열어서 OEP를 확인 할 수 있었습니다.

![Untitled](/IMG/6-3.png)

- OEP : 00401360

프로그램을 실행시켜서 문자열참조로 검색을 해서 분기점을 찾았습니다.

![Untitled](/IMG/6-4.png)

코드를 보면 제가입력한 값이 특정 값이랑 비교가 되는걸 볼 수 있었습니다.

- Serial : AD46DFS547

이로써 OEP + Serial 인 플래그를 완성했습니다.

플래그 : 00401360AD46DFS547