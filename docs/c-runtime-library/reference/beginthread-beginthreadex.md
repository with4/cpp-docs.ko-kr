---
title: "_beginthread, _beginthreadex | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _beginthread
- _beginthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- beginthread
- _beginthread
- beginthreadex
- _beginthreadex
dev_langs:
- C++
helpviewer_keywords:
- _beginthread function
- threading [C++], creating threads
- beginthreadex function
- _beginthreadex function
- beginthread function
ms.assetid: 0df64740-a978-4358-a88f-fb0702720091
caps.latest.revision: 36
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 3c556e6460f1a39bab23f2612cbf820e284d7605
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="beginthread-beginthreadex"></a>_beginthread, _beginthreadex
스레드를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
uintptr_t _beginthread( // NATIVE CODE  
   void( __cdecl *start_address )( void * ),  
   unsigned stack_size,  
   void *arglist   
);  
uintptr_t _beginthread( // MANAGED CODE  
   void( __clrcall *start_address )( void * ),  
   unsigned stack_size,  
   void *arglist   
);  
uintptr_t _beginthreadex( // NATIVE CODE  
   void *security,  
   unsigned stack_size,  
   unsigned ( __stdcall *start_address )( void * ),  
   void *arglist,  
   unsigned initflag,  
   unsigned *thrdaddr   
);  
uintptr_t _beginthreadex( // MANAGED CODE  
   void *security,  
   unsigned stack_size,  
   unsigned ( __clrcall *start_address )( void * ),  
   void *arglist,  
   unsigned initflag,  
   unsigned *thrdaddr   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `start_address`  
 새 스레드의 실행을 시작하는 루틴의 시작 주소입니다. `_beginthread`의 경우 호출 규칙은 [__cdecl](../../cpp/cdecl.md)(네이티브 코드용) 또는 [__clrcall](../../cpp/clrcall.md)(관리 코드용)입니다. `_beginthreadex`의 경우 호출 규칙은 [__stdcall](../../cpp/stdcall.md)(네이티브 코드용) 또는 [__clrcall](../../cpp/clrcall.md)(관리 코드용)입니다.  
  
 `stack_size`  
 새 스레드의 스택 크기 또는 0입니다.  
  
 `arglist`  
 새 스레드에 전달할 인수 목록 또는 NULL입니다.  
  
 `Security`  
 반환된 핸들이 자식 프로세스에 의해 상속되는지 여부를 결정하는 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) 구조에 대한 포인터입니다. `Security` 가 NULL인 경우 핸들을 상속할 수 없습니다. Windows 95 응용 프로그램에서 NULL이어야 합니다.  
  
 `initflag`  
 새 스레드의 초기 상태를 제어하는 플래그입니다. `initflag` 를 `0` 으로 설정하여 즉시 실행하거나 `CREATE_SUSPENDED` 로 설정하여 일시 중단된 상태로 스레드를 만듭니다. 스레드를 실행하려면 [ResumeThread](http://msdn.microsoft.com/library/windows/desktop/ms685086.aspx) 를 사용합니다. `initflag` 를 스택의 초기 예약 크기(바이트)로 사용하려면 `STACK_SIZE_PARAM_IS_A_RESERVATION` 를 `stack_size` 으로 설정합니다. 이 플래그를 지정하지 않으면 `stack_size` 는 커밋 크기를 지정합니다.  
  
 `thrdaddr`  
 스레드 식별자를 수신하는 32비트 변수를 가리킵니다. NULL인 경우는 사용되지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 이러한 함수가 각각 새로 만든 스레드에 대한 핸들을 반환하지만 새로 만든 스레드가 너무 빨리 종료되는 경우 `_beginthread` 가 올바른 핸들을 반환할 수 없습니다. 설명 단원의 설명을 참조하세요. 오류로 인해 `_beginthread`가 -1L로 반환되고 `errno`는 스레드가 많을 경우 `EAGAIN`에 설정되고, 인수가 잘못되거나 스택 크기가 잘못된 경우`EINVAL`에 설정되며, 리소스(즉, 메모리)가 부족할 경우`EACCES`에 설정됩니다. 오류 발생 시 `_beginthreadex` 에서 0을 반환하고 `errno` 및 `_doserrno` 가 설정됩니다.  
  
 `startaddress`이 NULL인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 -1을 반환합니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
 `uintptr_t`에 대한 자세한 내용은 [표준 형식](../../c-runtime-library/standard-types.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_beginthread` 함수는 `start_address`에서 루틴 실행을 시작하는 스레드를 만듭니다. `start_address` 의 루틴은 `__cdecl` (네이티브 코드) 또는 `__clrcall` (관리 코드) 호출 규칙을 사용해야 하며, 반환 값이 없어야 합니다. 스레드가 루틴에서 반환되면 자동으로 종료됩니다. 스레드에 대한 자세한 내용은 [이전 코드를 위한 다중 스레드 지원(Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)을 참조하세요.  
  
 `_beginthreadex`는 `_beginthread`보다 Win32 [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453.aspx) API와 더 비슷합니다. `_beginthreadex` 와 `_beginthread` 의 차이점은 다음과 같습니다.  
  
-   `_beginthreadex` 에는 세 가지 추가 매개 변수인 `initflag`, `security`및 `threadaddr`이 있습니다. 새 스레드는 지정된 보안 또는 일시 중단된 상태로 만들 수 있으며, 스레드 식별자인 `thrdaddr`를 사용하여 액세스할 수 있습니다.  
  
-   `start_address` 에 전달되는 `_beginthreadex` 의 루틴은 `__stdcall` (네이티브 코드) 또는 `__clrcall` (관리 코드) 호출 규칙을 사용해야 하며, 스레드 종료 코드를 반환해야 합니다.  
  
-   `_beginthreadex` 는 실패 시 -1L이 아닌 0을 반환합니다.  
  
-   `_beginthreadex` 를 사용하여 생성된 스레드는 [_endthreadex](../../c-runtime-library/reference/endthread-endthreadex.md)에 대한 호출로 종료됩니다.  
  
 `_beginthreadex` 함수를 사용하면 `_beginthread` 보다 스레드를 만드는 방법을 더 자세하게 제어할 수 있습니다. `_endthreadex` 함수는 더 유연하기도 합니다. 예를 들어, `_beginthreadex`를 사용하면 보안 정보를 사용하고 스레드의 초기 상태(실행 중 또는 일시 중단됨)를 설정하고 새로 만든 스레드의 스레드 식별자를 가져올 수 있습니다. `_beginthreadex` 로 작업할 수 없는 동기화 API로 `_beginthread`에서 반환된 스레드 핸들을 사용할 수도 있습니다.  
  
 `_beginthreadex` 보다 `_beginthread`를 사용하는 것이 더 안전합니다. `_beginthread` 에 의해 생성된 스레드가 빨리 종료되는 경우 `_beginthread` 의 호출자로 반환된 핸들이 잘못되거나 다른 스레드를 가리킬 수 있습니다. 그러나 `_beginthreadex` 에 의해 반환된 핸들은 `_beginthreadex`의 호출자에 의해 닫혀야 하므로 `_beginthreadex` 가 오류를 반환하지 않은 경우 유효한 핸들이어야 합니다.  
  
 [_endthread](../../c-runtime-library/reference/endthread-endthreadex.md) 또는 `_endthreadex` 를 명시적으로 호출하여 스레드를 종료할 수 있지만 스레드가 매개 변수로 전달된 루틴에서 반환되면 `_endthread` 또는 `_endthreadex` 는 자동으로 호출됩니다. `_endthread` 또는 `_endthreadex` 에 대한 호출로 스레드를 종료하면 스레드에 할당된 리소스의 올바른 복구를 보장하는 데 도움이 됩니다.  
  
 `_endthread` 는 스레드 핸들을 자동으로 닫지만, `_endthreadex` 는 그렇지 않습니다. 따라서 `_beginthread` 및 `_endthread`를 사용할 때는 Win32 [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) API를 호출해서 스레드 핸들을 명시적으로 닫지 마세요. 이 동작은 Win32 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) API와 다릅니다.  
  
> [!NOTE]
>  Libcmt.lib로 연결된 실행 파일의 경우 런타임 시스템이 할당된 리소스를 회수할 수 있도록 Win32 `ExitThread` API를 호출하지 마세요. `_endthread` 및 `_endthreadex` 는 할당된 스레드 리소스를 회수한 다음 `ExitThread`를 호출합니다.  
  
 `_beginthread` 또는 `_beginthreadex` 가 호출되면 운영 체제가 스택 할당을 처리합니다. 스레드 스택의 주소를 이러한 함수 중 하나에 전달할 필요가 없습니다. 또한 `stack_size` 인수는 0일 수 있습니다. 이 경우 운영 체제는 주 스레드에 지정된 스택과 동일한 값을 사용합니다.  
  
 `arglist` 는 새로 만든 스레드에 전달되는 매개 변수입니다. 일반적으로 문자열과 같은 데이터 항목의 주소입니다. 필요 없을 경우`arglist` 가 NULL일 수 있지만 `_beginthread` 및 `_beginthreadex` 에는 새로운 스레드로 전달할 값이 있어야 합니다. 임의의 스레드가 `abort`, `exit`, `_exit`또는 `ExitProcess`를 호출하면 모든 스레드가 종료됩니다.  
  
 새 스레드의 로캘은 부모 스레드에서 상속됩니다. 전역으로 또는 새 스레드에 대해서만 [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md) 을 호출하여 각 스레드에 대한 로캘을 사용하도록 설정한 경우 스레드는 `setlocale` 또는 `_wsetlocale`을 호출하여 해당 로캘을 해당 부모와 독립적으로 변경할 수 있습니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
 혼합형 및 순수형 코드의 경우 `_beginthread` 및 `_beginthreadex` 각각에 두 개의 오버로드가 있습니다. 하나는 네이티브 호출 규칙 함수 포인터를 사용하고 다른 하나는 `__clrcall` 함수 포인터를 사용합니다. 첫 번째 오버로드는 응용 프로그램 도메인에 안전하지 않고 어떤 방법으로도 안전할 수 없습니다. 혼합형 또는 순수형 코드를 작성하는 경우 새 스레드가 관리되는 리소스에 액세스하기 전에 올바른 응용 프로그램 도메인에 들어가는지 확인해야 합니다. 이 작업은 예를 들어 [call_in_appdomain 함수](../../dotnet/call-in-appdomain-function.md)를 사용하여 수행할 수 있습니다. 두 번째 오버로드는 응용 프로그램 도메인에 영향을 주지 않습니다. 새로 생성된 스레드는 항상 `_beginthread` 또는 `_beginthreadex`호출자의 응용 프로그램 도메인에서 종료됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_beginthread`|\<process.h>|  
|`_beginthreadex`|\<process.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 다중 스레드 버전의 유일한 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 입니다.  
  
 `_beginthread` 또는 `_beginthreadex`를 사용하려면 응용 프로그램이 다중 스레드 C 런타임 라이브러리 중 하나와 링크로 연결해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `_beginthread` 및 `_endthread`를 사용합니다.  
  
```  
// crt_BEGTHRD.C  
// compile with: /MT /D "_X86_" /c  
// processor: x86  
#include <windows.h>  
#include <process.h>    /* _beginthread, _endthread */  
#include <stddef.h>  
#include <stdlib.h>  
#include <conio.h>  
  
void Bounce( void * );  
void CheckKey( void * );  
  
// GetRandom returns a random integer between min and max.  
#define GetRandom( min, max ) ((rand() % (int)(((max) + 1) - (min))) + (min))  
// GetGlyph returns a printable ASCII character value  
#define GetGlyph( val ) ((char)((val + 32) % 93 + 33))  
  
BOOL repeat = TRUE;                 // Global repeat flag   
HANDLE hStdOut;                     // Handle for console window  
CONSOLE_SCREEN_BUFFER_INFO csbi;    // Console information structure  
  
int main()  
{  
    int param = 0;  
    int * pparam = &param;  
  
    // Get display screen's text row and column information.  
    hStdOut = GetStdHandle( STD_OUTPUT_HANDLE );  
    GetConsoleScreenBufferInfo( hStdOut, &csbi );  
  
    // Launch CheckKey thread to check for terminating keystroke.  
    _beginthread( CheckKey, 0, NULL );  
  
    // Loop until CheckKey terminates program or 1000 threads created.   
    while( repeat && param < 1000 )  
    {  
        // launch another character thread.  
        _beginthread( Bounce, 0, (void *) pparam );  
  
        // increment the thread parameter  
        param++;  
  
        // Wait one second between loops.  
        Sleep( 1000L );  
    }  
}  
  
// CheckKey - Thread to wait for a keystroke, then clear repeat flag.  
void CheckKey( void * ignored )  
{  
    _getch();  
    repeat = 0;    // _endthread implied  
}  
  
// Bounce - Thread to create and and control a colored letter that moves  
// around on the screen.  
//  
// Params: parg - the value to create the character from  
void Bounce( void * parg )  
{  
    char       blankcell = 0x20;  
    CHAR_INFO  ci;  
    COORD      oldcoord, cellsize, origin;  
    DWORD      result;  
    SMALL_RECT region;  
  
    cellsize.X = cellsize.Y = 1;  
    origin.X = origin.Y = 0;  
  
    // Generate location, letter and color attribute from thread argument.  
    srand( _threadid );  
    oldcoord.X = region.Left = region.Right =   
        GetRandom(csbi.srWindow.Left, csbi.srWindow.Right - 1);  
    oldcoord.Y = region.Top = region.Bottom =   
        GetRandom(csbi.srWindow.Top, csbi.srWindow.Bottom - 1);  
    ci.Char.AsciiChar = GetGlyph(*((int *)parg));  
    ci.Attributes = GetRandom(1, 15);  
  
    while (repeat)  
    {  
        // Pause between loops.  
        Sleep( 100L );  
  
        // Blank out our old position on the screen, and draw new letter.  
        WriteConsoleOutputCharacterA(hStdOut, &blankcell, 1, oldcoord, &result);  
        WriteConsoleOutputA(hStdOut, &ci, cellsize, origin, &region);  
  
        // Increment the coordinate for next placement of the block.  
        oldcoord.X = region.Left;  
        oldcoord.Y = region.Top;  
        region.Left = region.Right += GetRandom(-1, 1);  
        region.Top = region.Bottom += GetRandom(-1, 1);  
  
        // Correct placement (and beep) if about to go off the screen.  
        if (region.Left < csbi.srWindow.Left)  
            region.Left = region.Right = csbi.srWindow.Left + 1;  
        else if (region.Right >= csbi.srWindow.Right)  
            region.Left = region.Right = csbi.srWindow.Right - 2;  
        else if (region.Top < csbi.srWindow.Top)  
            region.Top = region.Bottom = csbi.srWindow.Top + 1;  
        else if (region.Bottom >= csbi.srWindow.Bottom)  
            region.Top = region.Bottom = csbi.srWindow.Bottom - 2;  
  
        // If not at a screen border, continue, otherwise beep.  
        else  
            continue;  
        Beep((ci.Char.AsciiChar - 'A') * 100, 175);  
    }  
    // _endthread given to terminate  
    _endthread();  
}  
```  
  
 아무 키나 눌러 샘플 응용 프로그램을 종료합니다.  
  
## <a name="example"></a>예제  
 다음 샘플 코드는 동기화 API `_beginthreadex` WaitForSingleObject [와 함께](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx)에 의해 반환되는 스레드 핸들 사용 방법을 보여 줍니다. 주 스레드는 두 번째 스레드가 종료할 때까지 기다린 다음 계속합니다. 두 번째 스레드가 `_endthreadex`를 호출하면 스레드 개체가 신호를 받은 상태로 전환됩니다. 그러면 기본 스레드를 계속 실행할 수 있습니다. `_beginthread` 는 신호된 상태로 설정되기 전에 스레드 개체를 소멸하는 `_endthread`을 호출하기 때문에 이 작업은 `_endthread` 및 `CloseHandle`로 수행할 수 없습니다.  
  
```  
// crt_begthrdex.cpp  
// compile with: /MT  
#include <windows.h>  
#include <stdio.h>  
#include <process.h>  
  
unsigned Counter;   
unsigned __stdcall SecondThreadFunc( void* pArguments )  
{  
    printf( "In second thread...\n" );  
  
    while ( Counter < 1000000 )  
        Counter++;  
  
    _endthreadex( 0 );  
    return 0;  
}   
  
int main()  
{   
    HANDLE hThread;  
    unsigned threadID;  
  
    printf( "Creating second thread...\n" );  
  
    // Create the second thread.  
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc, NULL, 0, &threadID );  
  
    // Wait until second thread terminates. If you comment out the line  
    // below, Counter will not be correct because the thread has not  
    // terminated, and Counter most likely has not been incremented to  
    // 1000000 yet.  
    WaitForSingleObject( hThread, INFINITE );  
    printf( "Counter should be 1000000; it is-> %d\n", Counter );  
    // Destroy the thread object.  
    CloseHandle( hThread );  
}  
```  
  
```Output  
Creating second thread...  
In second thread...  
Counter should be 1000000; it is-> 1000000  
```  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [_endthread, _endthreadex](../../c-runtime-library/reference/endthread-endthreadex.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)
