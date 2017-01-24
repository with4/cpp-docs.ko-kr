---
title: "_spawn, _wspawn 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_spawn"
  - "_tspawnlp"
  - "_tspawnlpe"
  - "_tspawnve"
  - "_tspawnvp"
  - "_tspawnvpe"
  - "_tspawnl"
  - "spawn"
  - "_tspawnv"
  - "_tspawnle"
  - "wspawn"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tspawnve 함수"
  - "_spawn 함수"
  - "_tspawnlpe 함수"
  - "tspawnvpe 함수"
  - "프로세스, 만들기"
  - "tspawnve 함수"
  - "_tspawnvp 함수"
  - "spawn 함수"
  - "tspawnl 함수"
  - "tspawnlp 함수"
  - "_tspawnvpe 함수"
  - "_tspawnl 함수"
  - "tspawnvp 함수"
  - "tspawnv 함수"
  - "프로세스, 새로 실행"
  - "_tspawnv 함수"
  - "tspawnle 함수"
  - "프로세스 만들기"
  - "_tspawnlp 함수"
  - "tspawnlpe 함수"
  - "_tspawnle 함수"
ms.assetid: bb47c703-5216-4e09-8023-8cf25bbf2cf9
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _spawn, _wspawn 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

각각의 `_spawn` 함수들은 새 프로세스들을 만들고 실행합니다:  
  
|||  
|-|-|  
|[\_spawnl, \_wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|[\_spawnv, \_wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|  
|[\_spawnle, \_wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|[\_spawnve, \_wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|  
|[\_spawnlp, \_wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|[\_spawnvp, \_wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|  
|[\_spawnlpe, \_wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|[\_spawnvpe, \_wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|  
  
 함수 이름 끝에 문자는 변형을 결정합니다.  
  
 `e`  
 `envp`환경 설정에 대한 포인터들의 배열은 새 프로세스에 전달 됩니다.  
  
 `l`  
 명령줄 인수들은 개별적으로 `_spawn` 함수로 전달됩니다.  이 접미사는 일반적으로 새 프로세스가 매개 변수를 미리 알고 있을 때, 사용 됩니다.  
  
 `p`  
 `PATH` 환경 변수는 실행 파일을 찾을 하는 데 사용 됩니다.  
  
 `v`  
 `argv`, 명령줄 인수에 대한 포인터들의 배열은 `_spawn`함수로 전달됩니다.  이 접미사는 일반적으로 새 프로세스에 대한 매개변수의 수가 유동적일 때 사용됩니다.  
  
## 설명  
 `_spawn` 함수는 새 프로세스를 각각 생성하고 실행합니다.  이것은 최근에 사용한 멀티 바이트 코드 페이지에 따라서 멀티 바이트 문자 시퀀스를 인식하는 멀티 바이트 문자 문자열 인수를 자동으로 적절하게 처리 합니다.  `_wspawn` 함수는 `_spawn` 함수의 와이드 문자 버전입니다; 이것은 멀티바이트 문자열을 처리하지 않습니다.  그렇지 않으면, `_wspawn` 함수는 `_spawn` 대응과 동일하게 동작합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tspawnl`|`_spawnl`|`_spawnl`|`_wspawnl`|  
|`_tspawnle`|`_spawnle`|`_spawnle`|`_wspawnle`|  
|`_tspawnlp`|`_spawnlp`|`_spawnlp`|`_wspawnlp`|  
|`_tspawnlpe`|`_spawnlpe`|`_spawnlpe`|`_wspawnlpe`|  
|`_tspawnv`|`_spawnv`|`_spawnv`|`_wspawnv`|  
|`_tspawnve`|`_spawnve`|`_spawnve`|`_wspawnve`|  
|`_tspawnvp`|`_spawnvp`|`_spawnvp`|`_wspawnvp`|  
|`_tspawnvpe`|`_spawnvpe`|`_spawnvpe`|`_wspawnvpe`|  
  
 새 프로세스를 로드하고 실행하기 위해 충분한 메모리가 필요합니다.  `mode` 인수는 `_spawn` 동안 혹은 그 이전에 호출 프로세스에 의해 수행되는 동작을 결정합니다.  `mode` 에 대한 다음 값은 Process.h에서 정의됩니다.  
  
 `_P_OVERLAY`  
 새로운 프로세스, 호출 프로세스를 제거하는데 사용하는 호출 프로세스 오버레이\(`_exec` 호출과 같은 효과\).  
  
 `_P_WAIT`  
 새 프로세스의 실행이 완료 될 때까지 호출 스레드를 일시 중단 \(동기적인 `_spawn`\).  
  
 `_P_NOWAIT` 또는  `_P_NOWAITO`  
 새로운 프로세스를 사용하여 계속 호출 프로스세스를 실행.\(비동기적 `_spawn`\)  
  
 `_P_DETACH`  
 호출 프로세스를 계속 실행합니다; 새 프로세스는 콘솔이나 키보드로 액세스 없이 백그라운드에서 실행됩니다.  새 프로세스 실패에 대하여 `_cwait` 를 호출합니다\(비동기적 `_spawn`\).  
  
 `cmdname` 인수는 새 프로세스로 실행되는 파일을 지정하고 전체 경로\(root로부터\), 부분적인 경로\(현제 작업 디렉터리\), 또는 단지 파일 이름을 지정할 수 있습니다.  만일 `cmdname` 은 파일 이름 확장명이 없거나 \(,\)을 사용하여 끝내지 않고, `_spawn` 함수 .com 파일 이름 확장명으로 처음 시도하고 그 후 .exe, .bat, 마지막으로 .cmd파일 확장명을 사용합니다.  
  
 만일 `cmdname` 이 파일 확장명을 가진다면, 오직 확장명만 사용됩니다.  만약 `cmdname` 가 마침표로 끝나면, `_spawn` 호출은 파일이름 확장명이 없는 `cmdname` 검색을 시도합니다.  `_spawnlp`, `_spawnlpe`, `_spawnvp`, 및  `_spawnvpe` 함수는 \(동일한 절차를 사용하여\) 디렉터리에 있는 `cmdname` 을 찾고 그 디렉터리는 `PATH` 환경 변수에 의해 지정됩니다.  
  
 만약 `cmdname` 이 드라이브 지정자 또는 모든 슬래시\(즉, 상대 경로일 경우에\)를 포함하고 , `_spawn` 는 지정된 파일 검색만을 호출합니다; 경로는 검색 되지 않습니다.  
  
 이전에는, 이들 함수들의 일부는 성공했을때 `errno` 을 0으로 설정했습니다; 현재는 C 표준에 의해 지정 된 대로, 성공했을때 동작이 `errno` 이 그대로 유지됩니다.  만일 이전 버전의 동작을 에뮬레이션 하는 경우, 이들 함수가 호출되기 바로 전에 `errno` 가 0으로 설정됩니다.  
  
> [!NOTE]
>  적합한 오버레이 초기화와 설정을 확인하기 위해 오버레이 루틴에 출입에 대한 `setjmp` 또는 `longjmp` 사용하지 마세요.  
  
## 생성된 프로세스에 대한 인수들  
 새로운 프로세스로 인수를 전달하려면, `_spawn` 호출에서 인수로써 문자열에 대한 하나 이상의 포인터를 제공합니다.  이 문자열은 생성된 프로세스에 대한 인수 리스트를 형성합니다.  새로운 프로세스에 대한 인수목록을 형상하는 문자열의 길이는 1024바이트를 초과할 수 없습니다.  각 문자열에 대한 종료 null 문자 \('\\0'\)은 개수에 포함 되지 않지만 공백 문자\(인수를 구분 하려면 자동 삽입\)는 포함됩니다.  
  
> [!NOTE]
>  문자열에 포함된 공백은 예기치 않은 동작을 발생시킬 수 있습니다; 예를 들어, `_spawn` 을 문자열 `"hi there"` 에 전달하는 것은 두 개의 인수, `"hi"` 및 `"there"`을 가져오는 새 프로세스에서 발생할 것입니다.  의도가 "hi there"인 파일을 여는 새로운 프로세스였다면, 프로세스는 실패할 것 입니다.  이것은 문자열을 인용하여 방지할 수 있습니다: `"\"hi there\""`.  
  
> [!IMPORTANT]
>  콘텐츠를 명시적으로 확인 하지 않은 채 `_spawn` 에 사용자 입력을 전달하지 않습니다.  `_spawn` 는 [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms682425) 호출에서 발생하므로 비정규화된 경로 이름이 잠재적인 보안 취약점이 될 수 있다는 것을 명심해야합니다.  
  
 몇가지 인수\(`_spawnl`, `_spawnle`, `_spawnlp`, 그리고 `_spawnlpe`\) 또는 포인터들의 배열 \(`_spawnv`, `_spawnve`, `_spawnvp`, 그리고 `_spawnvpe`\) 로써 인수 포인터들 전달 할 수 있습니다.  생성된 프로세스에 대해, `arg0` 또는 `argv`\[0\], 중 하나 이상의 인수를 전달 해야 합니다.  규칙에 따라, 이 인수는 명령줄에 형식에 대한 프로그램의 이름입니다.  다른 값은 오류를 발생 하지 않습니다.  
  
 사전에 인수의 갯수를 알고있는 경우 일반적으로 `_spawnl`, `_spawnle`, `_spawnlp`, 와 `_spawnlpe` 가 호출합니다.  이 `arg0` 인수는 일반적으로 `cmdname` 을 향하는 포인터입니다.  인수 `arg1` 는 `argn` 통한 새 인수 목록 구성 문자열에 대한 포인터입니다.  `argn` 다음에는 인수 목록의 끝을 표시하는 `NULL` 포인터가 와야 합니다.  
  
 새 프로세스에 대한 인수의 다양한 인수가 존재할 때, `_spawnv`, `_spawnve`, `_spawnvp`, 그리고 `_spawnvpe` 호출이 유용하게 사용됩니다.  인수에 대한 포인터들은 `argv` *.* 배열로 전달됩니다. 인수 `argv`\[0\]는 일반적으로 경로에 대 한 포인터 또는 프로그램 이름을 리얼 모드에서 보호 모드로 하고 `argv`\[1\]를 통해 `argv`\[`n`\]새 인수 목록 구성 문자열에 대 한 포인터입니다.  인수 `argv`\[`n` \+1\]은 인수 목록의 끝을 표시하는 `NULL` 포인터여야 합니다.  
  
## 생성된 프로세스의 환경  
 새 프로세스에서 `_spawn` 호출이 있을 때 열리는 파일들입니다.  `_spawnl`, `_spawnlp`, `_spawnv`, 와 `_spawnvp` 호출에서, 새 프로세스는 호출 프로세스의 환경을 상속을 합니다.  `envp` 인수를 통해 황경 설정의 목록을 전달함으로써 새로운 프로세스로 대체하기 위해 `_spawnle`, `_spawnlpe`, `_spawnve`, 와 `_spawnvpe` 호출을 사용할 수 있습니다.  인수 `envp` 는 문자 포인터의 배열이고 \(마지막 요소를 제외한\) null로 끝나는 문자열을 가리키는 각 요소는 환경 변수를 정의합니다.  이러한 문자열은 일반적으로 `NAME`\=`value` 양식을 가지고 있고 그 양식은 `NAME` 이 환경 변수 이름이고 `value` 는 변수를 설정 하는 문자열 값입니다. \(이 때 `value` 는 큰 따옴표로 묶이면 안 됩니다.\) 이 `envp` 배열의 마지막 요소는 `NULL`이어야 합니다.  그 `envp` 자체가 `NULL`일 때, 새 프로세스는 부모 프로세스의 환경 설정을 상속합니다.  
  
 `_spawn`  함수는 변환 모드를 포함하고, 새 프로세스를 대한 열린 파일에 관한 모든 정보를 전달할 수 있습니다.  환경에서 `C_FILE_INFO` 항목에 관한 리얼 모드에서 정보가 전달됩니다.  시작 코드는 정삭적으로 이 항목을 처리하고 이후 환경으로부터 이것을 삭제합니다.  하지만, 만일 `_spawn` 함수 비 C\-프로세스를 생성하고, 이 항목은 환경에서 남아있습니다.  인쇄 환경는 환경 정보가 리얼 모드에서 바이너리 형태로 전달되기 때문에 이 항목에 대한 문자열 정의에서 그래픽 문자를 보여줍니다.  정상 작업에서 다른 효과가 없어야 합니다.  보호 모드에서, 환경 정보는 텍스트 형식으로 전달되고 따라서 그래픽 문자들을 포함하지 않습니다.  
  
 명시적으로 플러시 \( `fflush` 또는 `_flushall`을 사용\)하거나 `_spawn` 함수 호출 전에 모든 스트림을 닫습니다.  
  
 새 프로세스는 단일 신호를 보존하지 않는  `_spawn`  루틴을 호출함으로써 생성됩니다.  대신, 생성된 프로세스는 기본값으로 신호 설정을 다시 설정합니다.  
  
## 출력 리디렉션  
 만일 GUI 응용프로그램 또는 DLL로부터 `_spawn` 을 호출하고 파이프로부터 출력을 리디렉션 하려는 경우, 두가지 옵션이 존재합니다:  
  
-   파이프를 생성하기 위해 Win32 API를 사용한 후, [AllocConsole](http://msdn.microsoft.com/library/windows/desktop/ms681944)을 호출하고, 시작 구조에서 핸들값을 설정하고 [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms682425)을 호출합니다.  
  
-   **cmd.exe \/c**\(또는 **command.exe \/c**\)을 사용하여 앱을 호출하고 파이프를 생성하는 [\_popen, \_wpopen](../c-runtime-library/reference/popen-wpopen.md) 호출입니다.  
  
## 예제  
  
```  
// crt_spawn.c  
// This program accepts a number in the range  
// 1-8 from the command line. Based on the number it receives,  
// it executes one of the eight different procedures that  
// spawn the process named child. For some of these procedures,  
// the CHILD.EXE file must be in the same directory; for  
// others, it only has to be in the same path.  
//  
  
#include <stdio.h>  
#include <process.h>  
  
char *my_env[] =  
{  
   "THIS=environment will be",  
   "PASSED=to child.exe by the",  
   "_SPAWNLE=and",  
   "_SPAWNLPE=and",  
   "_SPAWNVE=and",  
   "_SPAWNVPE=functions",  
   NULL  
};  
  
int main( int argc, char *argv[] )  
{  
   char *args[4];  
  
   // Set up parameters to be sent:   
   args[0] = "child";  
   args[1] = "spawn??";  
   args[2] = "two";  
   args[3] = NULL;  
  
   if (argc <= 2)  
   {  
      printf( "SYNTAX: SPAWN <1-8> <childprogram>\n" );  
      exit( 1 );  
   }  
  
   switch (argv[1][0])   // Based on first letter of argument   
   {  
   case '1':  
      _spawnl( _P_WAIT, argv[2], argv[2], "_spawnl", "two", NULL );  
      break;  
   case '2':  
      _spawnle( _P_WAIT, argv[2], argv[2], "_spawnle", "two",   
               NULL, my_env );  
      break;  
   case '3':  
      _spawnlp( _P_WAIT, argv[2], argv[2], "_spawnlp", "two", NULL );  
      break;  
   case '4':  
      _spawnlpe( _P_WAIT, argv[2], argv[2], "_spawnlpe", "two",   
                NULL, my_env );  
      break;  
   case '5':  
      _spawnv( _P_OVERLAY, argv[2], args );  
      break;  
   case '6':  
      _spawnve( _P_OVERLAY, argv[2], args, my_env );  
      break;  
   case '7':  
      _spawnvp( _P_OVERLAY, argv[2], args );  
      break;  
   case '8':  
      _spawnvpe( _P_OVERLAY, argv[2], args, my_env );  
      break;  
   default:  
      printf( "SYNTAX: SPAWN <1-8> <childprogram>\n" );  
      exit( 1 );  
   }  
   printf( "from SPAWN!\n" );  
}  
```  
  
  **자식 프로세스 출력**  
**SPAWN\!**   
## 참고 항목  
 [프로세스 및 환경 제어](../c-runtime-library/process-and-environment-control.md)   
 [abort](../c-runtime-library/reference/abort.md)   
 [atexit](../c-runtime-library/reference/atexit.md)   
 [\_exec, \_wexec 함수](../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../c-runtime-library/reference/exit-exit-exit.md)   
 [\_flushall](../c-runtime-library/reference/flushall.md)   
 [\_getmbcp](../c-runtime-library/reference/getmbcp.md)   
 [\_onexit, \_onexit\_m](../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_setmbcp](../c-runtime-library/reference/setmbcp.md)   
 [system, \_wsystem](../c-runtime-library/reference/system-wsystem.md)