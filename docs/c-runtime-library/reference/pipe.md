---
title: "_pipe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_pipe"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "pipe"
  - "_pipe"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_pipe 함수"
  - "pipe 함수"
  - "파이프"
  - "파이프, 만들기"
ms.assetid: 8d3e9800-4041-44b5-9e93-2df0b0354a75
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _pipe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

읽기 및 쓰기에 대한 파이프를 만듭니다.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
  
      int _pipe(  
int *pfds,  
unsigned int psize,  
int textmode   
);  
```  
  
#### 매개 변수  
 `pfds`\[2\]  
 파일 기술자를 읽고 쓸 배열입니다.  
  
 `psize`  
 예약 하는 메모리의 양입니다.  
  
 `textmode`  
 파일 모드입니다.  
  
## 반환 값  
 성공하면 0를 반환합니다.  오류를 나타내기 위해 \-1을 반환합니다.  오류 발생 시 아래 값 중 하나의 `errno` 가 설정됩니다.  
  
-   `EMFILE` : 파일 기술자를 사용할 수 없습니다.  
  
-   `ENFILE` : 시스템 파일 테이블이 오버플로우 되었습니다.  
  
-   `EINVAL` :  `pfds`  배열이 null 포인터이거나  `textmode` 에 잘못된 값이 전달되었습니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `_pipe`  함수는 한 프로그램에서 다른 프로그램에서 정보를 전달하기 위한 인공 I\/O 채널인 *파이프*를 생성합니다.  파이프는 파일 포인터와 파일 기술자 혹은 양쪽 모두를 가지고 있으며, 표준 라이브러리 입출력 함수를 이용하여 읽거나 쓸 수 있다는 점에서 파일과 비슷합니다.  그러나 파이프는 특정 파일이나 장치를 나타내지 않습니다.  대신, 이것은 프로그램의 메모리와 별개인 메모리의 임시 저장소를 나타내며, 전적으로 운영 체제에 의해 제어됩니다.  
  
 `_pipe`는  `_open` 과 유사하지만, 읽기와 쓰기를 위한 파이프를 열며 한 개가 아니라 두 개의 파일 기술자를 반환합니다.  프로그램은 파이프 2개를 모두 사용할 수도 있고 필요하지 않은 쪽을 닫을 수도 있습니다.  예를 들어, Windows 명령 프로세서는  `PROGRAM1 | PROGRAM2` 와 같은 명령을 실행할 때 파이프를 생성합니다.  
  
 `PROGRAM1` 의 표준 출력 기술자는 파이프의 쓰기 기술자와 연결되어 있습니다.   `PROGRAM2` 의 표준 입력 기술자는 파이프의 읽기 기술자와 연결되어 있습니다.  이렇게 하면 다른 프로그램으로 정보를 전달하기 위해 임시 파일을 만들 필요가 없습니다.  
  
 `_pipe`  함수는  `pfds`  인수 내의 2개의 파일 기술자를 반환합니다.   `pfds` \[0\] 요소는 읽기 기술자를 포함하며,  `pfds` \[1\] 요소는 쓰기 기술자를 포함합니다.  파이프 파일 기술자는 다른 파일 기술자와 동일하게 사용됩니다. \(낮은 수준의 입출력 함수인  `_read`  및  `_write` 는 파이프에 쓰거나 읽을 수 있습니다.\) 파이프의 종료 상태를 확인하려면, 읽은 바이트 수로 0을 반환하는  `_read`  요청을 확인하십시오.  
  
 `psize`  인수는 파이프에 할당할 메모리의 양을 지정합니다.   `textmode`  인수는 파이프의 변환 모드를 지정합니다.  매니페스트 상수인  `_O_TEXT` 는 텍스트 변환을 지정하며,  `_O_BINARY`  상수는 이진 변환을 지정합니다. \(텍스트 및 바이너리 모드에 대한 설명은 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md) 을 참조하십시오.\)  `textmode`  인수가 0일 경우,  `_pipe` 는 기본 모드 변수 [\_fmode](../../c-runtime-library/fmode.md)에 의해 지정된 기본 변환 모드를 사용합니다.  
  
 다중 스레드 프로그램에서는 잠금이 수행되지 않습니다.  반환된 파일 기술자는 새로 열리고  `_pipe`  호출이 완료될 때까지 어떤 스레드에서도 참조될 수 없습니다.  
  
 부모 프로세스와 자식 프로세스간 통신을 위해  `_pipe`  함수를 사용하려면 각 프로세스 파이프에 단 하나의 기술자만이 열려 있어야 합니다.  각 기술자는 서로 반대여야 합니다: 부모가 읽기 기술자를 열었다면, 자식은 쓰기 기술자를 열어야 합니다.  가장 쉬운 방법은  `OR`  \(  `|`\)를 `_O_NOINHERIT` 플래그에 `textmode` 로 이용하는 것입니다.  그 후,  `_dup`  혹은  `_dup2` 를 사용하여 자식에게 전달할 수 있는 파이프 기술자의 상속 가능한 복사본을 생성하십시오.  원래 기술자를 종료한 이후에 자식 프로세스를 생성하십시오.  생성 호출이 반환되면, 부모 프로세스에 중복된 기술자를 종료하십시오.  자세한 내용은 이 문서의 뒷부분에 나오는 예제 2를 참조하십시오.  
  
 Windows 운영 체제에서 모든 기술자가 종료되었을 때 파이프는 소멸됩니다. \(파이프의 모든 읽기 기술자가 종료된 후 파이프에 쓰려고 하면 오류가 발생합니다.\) 파이프에 대한 모든 읽기나 쓰기 작업은 I\/O 요청을 완료하기에 충분한 데이터나 버퍼 공간이 있을 때까지 대기합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_pipe`|\<io.h\>|\<fcntl.h\>1, \<errno.h\>2|  
  
 1  `_O_BINARY`  및  `_O_TEXT`  의 정의.  
  
 2 `errno` 정의.  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제 1  
  
```  
// crt_pipe.c  
/* This program uses the _pipe function to pass streams of  
 * text to spawned processes.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <io.h>  
#include <fcntl.h>  
#include <process.h>  
#include <math.h>  
  
enum PIPES { READ, WRITE }; /* Constants 0 and 1 for READ and WRITE */  
#define NUMPROBLEM 8  
  
int main( int argc, char *argv[] )  
{  
  
   int fdpipe[2];  
   char hstr[20];  
   int pid, problem, c;  
   int termstat;  
  
   /* If no arguments, this is the spawning process */  
   if( argc == 1 )  
   {  
  
      setvbuf( stdout, NULL, _IONBF, 0 );  
  
      /* Open a set of pipes */  
      if( _pipe( fdpipe, 256, O_BINARY ) == -1 )  
          exit( 1 );  
  
      /* Convert pipe read descriptor to string and pass as argument   
       * to spawned program. Program spawns itself (argv[0]).  
       */  
      _itoa_s( fdpipe[READ], hstr, sizeof(hstr), 10 );  
      if( ( pid = _spawnl( P_NOWAIT, argv[0], argv[0],   
            hstr, NULL ) ) == -1 )  
          printf( "Spawn failed" );  
  
      /* Put problem in write pipe. Since spawned program is   
       * running simultaneously, first solutions may be done   
       * before last problem is given.  
       */  
      for( problem = 1000; problem <= NUMPROBLEM * 1000; problem += 1000)  
      {  
  
         printf( "Son, what is the square root of %d?\n", problem );  
         _write( fdpipe[WRITE], (char *)&problem, sizeof( int ) );  
  
      }  
  
      /* Wait until spawned program is done processing. */  
      _cwait( &termstat, pid, WAIT_CHILD );  
      if( termstat & 0x0 )  
         printf( "Child failed\n" );  
  
      _close( fdpipe[READ] );  
      _close( fdpipe[WRITE] );  
  
   }  
  
   /* If there is an argument, this must be the spawned process. */  
   else  
   {  
  
      /* Convert passed string descriptor to integer descriptor. */  
      fdpipe[READ] = atoi( argv[1] );  
  
      /* Read problem from pipe and calculate solution. */  
      for( c = 0; c < NUMPROBLEM; c++ )  
      {  
  
        _read( fdpipe[READ], (char *)&problem, sizeof( int ) );  
        printf( "Dad, the square root of %d is %3.2f.\n",  
                 problem, sqrt( ( double )problem ) );  
  
      }  
   }  
}  
```  
  
## 샘플 출력  
  
```  
Son, what is the square root of 1000?  
Son, what is the square root of 2000?  
Son, what iDad, the square root of 1000 is 31.62.  
Dad, the square root of 2000 is 44.72.  
s the square root of 3000?  
Dad, the square root of 3000 is 54.77.  
Son, what is the square root of 4000?  
Dad, the square root of 4000 is 63.25.  
Son, what is the square root of 5000?  
Dad, the square root of 5000 is 70.71.  
Son, what is the square root of 6000?  
SonDad, the square root of 6000 is 77.46.  
, what is the square root of 7000?  
Dad, the square root of 7000 is 83.67.  
Son, what is the square root of 8000?  
Dad, the square root of 8000 is 89.44.  
```  
  
## 예제 2  
 이것은 기본 필터 응용 프로그램입니다.  이 프로그램은 필터에 생성된 응용 프로그램의 stdout를 지시하는 파이프를 만든 후 응용 프로그램 crt\_pipe\_beeper를 생성합니다.  필터는 ASCII 7 \(경고음\) 문자를 제거합니다.  
  
```  
// crt_pipe_beeper.c  
  
#include <stdio.h>  
#include <string.h>  
  
int main()  
{  
   int   i;  
   for(i=0;i<10;++i)  
      {  
         printf("This is speaker beep number %d...\n\7", i+1);  
      }  
   return 0;  
}  
```  
  
 실제 필터 응용 프로그램:  
  
```  
// crt_pipe_BeepFilter.C  
// arguments: crt_pipe_beeper.exe  
  
#include <windows.h>  
#include <process.h>  
#include <memory.h>  
#include <string.h>  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
  
#define   OUT_BUFF_SIZE 512  
#define   READ_FD 0  
#define   WRITE_FD 1  
#define   BEEP_CHAR 7  
  
char szBuffer[OUT_BUFF_SIZE];  
  
int Filter(char* szBuff, ULONG nSize, int nChar)  
{  
   char* szPos = szBuff + nSize -1;  
   char* szEnd = szPos;  
   int nRet = nSize;  
  
   while (szPos > szBuff)  
   {  
      if (*szPos == nChar)  
         {  
            memmove(szPos, szPos+1, szEnd - szPos);  
            --nRet;  
         }  
      --szPos;  
   }  
   return nRet;  
}  
  
int main(int argc, char** argv)  
{  
   int nExitCode = STILL_ACTIVE;  
   if (argc >= 2)  
   {  
      HANDLE hProcess;  
      int fdStdOut;  
      int fdStdOutPipe[2];  
  
      // Create the pipe  
      if(_pipe(fdStdOutPipe, 512, O_NOINHERIT) == -1)  
         return   1;  
  
      // Duplicate stdout file descriptor (next line will close original)  
      fdStdOut = _dup(_fileno(stdout));  
  
      // Duplicate write end of pipe to stdout file descriptor  
      if(_dup2(fdStdOutPipe[WRITE_FD], _fileno(stdout)) != 0)  
         return   2;  
  
      // Close original write end of pipe  
      _close(fdStdOutPipe[WRITE_FD]);  
  
      // Spawn process  
      hProcess = (HANDLE)_spawnvp(P_NOWAIT, argv[1],   
       (const char* const*)&argv[1]);  
  
      // Duplicate copy of original stdout back into stdout  
      if(_dup2(fdStdOut, _fileno(stdout)) != 0)  
         return   3;  
  
      // Close duplicate copy of original stdout  
      _close(fdStdOut);  
  
      if(hProcess)  
      {  
         int nOutRead;  
         while   (nExitCode == STILL_ACTIVE)  
         {  
            nOutRead = _read(fdStdOutPipe[READ_FD],   
             szBuffer, OUT_BUFF_SIZE);  
            if(nOutRead)  
            {  
               nOutRead = Filter(szBuffer, nOutRead, BEEP_CHAR);  
               fwrite(szBuffer, 1, nOutRead, stdout);  
            }  
  
            if(!GetExitCodeProcess(hProcess,(unsigned long*)&nExitCode))  
               return 4;  
         }  
      }  
   }  
   return nExitCode;  
}  
```  
  
## Output  
  
```  
This is speaker beep number 1...  
This is speaker beep number 2...  
This is speaker beep number 3...  
This is speaker beep number 4...  
This is speaker beep number 5...  
This is speaker beep number 6...  
This is speaker beep number 7...  
This is speaker beep number 8...  
This is speaker beep number 9...  
This is speaker beep number 10...  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)