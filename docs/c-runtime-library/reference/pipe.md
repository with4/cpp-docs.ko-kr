---
title: _pipe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _pipe
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- pipe
- _pipe
dev_langs: C++
helpviewer_keywords:
- pipes, creating
- _pipe function
- pipes
- pipe function
ms.assetid: 8d3e9800-4041-44b5-9e93-2df0b0354a75
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a14fa401b2a46bbfb3d5aafcda4d05c0167b3d9b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="pipe"></a>_pipe
읽기 및 쓰기용 파이프를 만듭니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
int _pipe(  
   int *pfds,  
   unsigned int psize,  
   int textmode   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pfds`[2]  
 읽기 및 쓰기 파일 설명자를 저장할 배열입니다.  
  
 `psize`  
 예약할 메모리의 양입니다.  
  
 `textmode`  
 파일 모드입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 0을 반환합니다. 오류를 나타내는 데-1 반환 합니다. 오류 시 `errno`는 다음 값 중 하나로 설정됩니다.  
  
-   `EMFILE` - 파일 설명자를 더 이상 사용할 수 없음을 나타냅니다.  
  
-   `ENFILE` - 시스템 파일 테이블 오버플로를 나타냅니다.  
  
-   `EINVAL` - 배열 `pfds`가 null 포인터이거나 `textmode`에 대한 잘못된 값이 전달되었음을 나타냅니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_pipe` 함수는 프로그램이 다른 프로그램에 정보를 전달하는 데 사용하는 인위적인 I/O 채널인 *파이프*를 만듭니다. 파이프는 파일 포인터나 파일 설명자 또는 두 항목을 모두 포함하며, 표준 라이브러리 입력 및 출력 함수를 사용하여 읽거나 쓸 수 있으므로 파일과 비슷합니다. 그러나 파이프는 특정 파일 또는 장치를 나타내지 않습니다. 대신 전적으로 운영 체제에 의해 제어되며 프로그램의 자체 메모리와는 독립적인 임시 저장소를 나타냅니다.  
  
 `_pipe`는 `_open`과 비슷하지만 읽기 및 쓰기용으로 파이프를 열며 하나가 아닌 두 개의 파일 설명자를 반환합니다. 프로그램은 파이프 양쪽을 모두 사용할 수도 있고 필요하지 않은 쪽을 닫을 수도 있습니다. 예를 들어 Windows의 명령 프로세서는 `PROGRAM1 | PROGRAM2` 등의 명령을 실행할 때 파이프를 만듭니다.  
  
 `PROGRAM1`의 표준 출력 설명자는 파이프의 쓰기 설명자에 연결됩니다. `PROGRAM2`의 표준 입력 설명자는 파이프의 읽기 설명자에 연결됩니다. 따라서 다른 프로그램에 정보를 전달하기 위해 임시 파일을 만들 필요가 없습니다.  
  
 `_pipe` 함수는 파이프에 대한 파일 설명자 두 개를 `pfds` 인수에서 반환합니다. 요소 `pfds`[0]은 읽기 설명자를 포함하며 요소 `pfds`[1]은 쓰기 설명자를 포함합니다. 파이프 파일 설명자도 다른 파일 설명자와 같은 방식으로 사용됩니다. 하위 수준 입력 및 출력 함수인 `_read` 및 `_write`는 파이프에서 읽고 파이프에 쓸 수 있습니다. 파이프 끝 조건을 검색하려면 읽은 바이트 수로 0을 반환하는 `_read` 요청을 확인합니다.  
  
 `psize` 인수는 파이프용으로 예약할 메모리의 양(바이트)을 지정합니다. `textmode` 인수는 파이프에 대한 변환 모드를 지정합니다. 매니페스트 상수 `_O_TEXT`는 텍스트 변환을 지정하고 상수 `_O_BINARY`는 이진 변환을 지정합니다. 텍스트 및 이진 모드에 대한 설명은 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)을 참조하세요. `textmode` 인수가 0이면 `_pipe`는 기본 모드 변후 [_fmode](../../c-runtime-library/fmode.md)에 의해 지정된 기본 변환 모드를 사용합니다.  
  
 다중 스레드 프로그램에서는 잠금이 수행되지 않습니다. 반환되는 파일 설명자는 새로 열리며, `_pipe` 호출이 완료될 때까지는 스레드에서 참조해서는 안 됩니다.  
  
 부모 프로세스와 자식 프로세스 간의 통신에 `_pipe` 함수를 사용하려면 각 프로세스의 파이프에서 설명자가 하나만 열려 있어야 합니다. 열려 있는 설명자는 서로 반대여야 합니다. 즉, 부모 프로세스에서 읽기 설명자가 열려 있으면 자식 프로세스에서는 쓰기 설명자가 열려 있어야 합니다. 이 작업을 수행하는 가장 쉬운 방법은 `textmode`를 사용하여 `_O_NOINHERIT` 플래그를 `OR`(`|`)로 설정하는 것입니다. 그런 후에 `_dup` 또는 `_dup2`를 사용하여 자식 프로세스에 전달할 파이프 설명자의 상속 가능한 복사본을 만듭니다. 마지막으로 원래 설명자를 닫고 자식 프로세스를 생성합니다. 생성 호출이 종료되면 부모 프로세스에서 중복 설명자를 닫습니다. 자세한 내용은 이 문서 뒷부분의 예제 2를 참조하세요.  
  
 Windows 운영 체제에서는 모든 설명자가 닫히면 파이프가 삭제됩니다. 모든 읽기 설명자가 닫힌 파이프에 쓰는 경우에는 오류가 발생합니다. 파이프에 대한 모든 읽기 및 쓰기 작업은 I/O 요청을 완료하기에 충분한 데이터 또는 버퍼 공간이 있을 때까지 대기합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_pipe`|\<io.h>|\<fcntl.h>,1 \<errno.h>2|  
  
 `_O_BINARY` 및 `_O_TEXT` 정의의 경우 1입니다.  
  
 `errno` 정의의 경우 2입니다.  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example-1"></a>예제 1  
  
```C  
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
  
```Output  
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
  
## <a name="example-2"></a>예제 2  
 이 예제는 기본 필터 응용 프로그램입니다. 이 응용 프로그램은 생성된 응용 프로그램의 stdout를 필터로 이동하는 파이프를 만든 후 crt_pipe_beeper 응용 프로그램을 생성합니다. 필터는 ASCII 7(경고음) 문자를 제거합니다.  
  
```C  
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
  
```C  
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
  
```Output  
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
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)