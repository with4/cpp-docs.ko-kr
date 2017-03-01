---
title: "_cwait | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _cwait
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cwait
dev_langs:
- C++
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 9f58035cc3e3159dc8bb54860e3c8e7454f35b51
ms.lasthandoff: 02/24/2017

---
# <a name="cwait"></a>_cwait
다른 프로세스가 종료될 때까지 기다립니다.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
intptr_t _cwait(   
   int *termstat,  
   intptr_t procHandle,  
   int action   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `termstat`  
 지정된 프로세스의 결과 코드가 저장되는 버퍼에 대한 포인터이거나 NULL입니다.  
  
 `procHandle`  
 대기 중인 프로세스에 대한 핸들입니다(즉, `_cwait`를 반환하기 전에 종료되어야 하는 프로세스).  
  
 `action`  
 NULL: Windows 운영 체제 응용 프로그램에서 무시합니다. 다른 응용 프로그램의 경우: `procHandle`에 대해 수행할 작업 코드입니다.  
  
## <a name="return-value"></a>반환 값  
 지정된 프로세스가 성공적으로 완료되면 지정된 프로세스의 핸들을 반환하고 `termstat`를 지정한 프로세스에서 반환한 결과 코드로 설정합니다. 그렇지 않으면 –1을 반환하고 다음과 같이 `errno`를 설정합니다.  
  
|값|설명|  
|-----------|-----------------|  
|`ECHILD`|지정된 프로세스가 없으며 `procHandle`이 잘못되었거나 [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx) 또는 [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx) API에 대한 호출이 실패했습니다.|  
|`EINVAL`|`action`이 잘못되었습니다.|  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_cwait` 함수는 `procHandle`에서 제공하는 지정된 프로세스의 프로세스 ID가 종료될 때까지 기다립니다. `_cwait`에 전달된 `procHandle`의 값은 지정된 프로세스를 만든 [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) 함수에 대한 호출에서 반환한 값이어야 합니다. `_cwait`가 호출되기 전에 프로세스 ID가 종료되면 `_cwait`가 즉시 반환됩니다. `_cwait`는 모든 프로세스에서 유효한 핸들(`procHandle`)이 있는 다른 모든 알려진 프로세스를 기다리는 데 사용할 수 있습니다.  
  
 `termstat`는 지정된 프로세스의 반환 코드가 저장될 버퍼를 가리킵니다. `termstat`의 값은 지정된 프로세스가 Windows [ExitProcess](http://msdn.microsoft.com/library/windows/desktop/ms682658.aspx) API를 호출하여 정상적으로 종료되었는지 여부를 나타냅니다. 지정된 프로세스가 `ExitProcess` 또는 `exit`를 호출하거나, `_exit`에서 반환되거나, `main`의 끝에 도달한 경우 `main`가 내부적으로 호출됩니다. `termstat`을 통해 다시 전달되는 값에 대한 자세한 내용은 [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx)를 참조하세요. `_cwait`의 NULL 값을 사용하여 `termstat`를 호출하면 지정된 프로세스의 반환 코드가 저장되지 않습니다.  
  
 이러한 환경에서는 부모-자식 관계가 구현되지 않으므로 Windows 운영 체제에서는 `action` 매개 변수를 무시합니다.  
  
 `procHandle`이 -1 또는 -2(현재 프로세스 또는 스레드에 대한 핸들)가 아닌 경우 핸들이 닫힙니다. 따라서 이 경우 반환된 핸들을 사용하지 마세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_cwait`|\<process.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
  
      // crt_cwait.c  
// compile with: /c  
// This program launches several processes and waits  
// for a specified process to finish.  
//  
#define _CRT_RAND_S  
  
#include <windows.h>  
#include <process.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <time.h>  
  
// Macro to get a random integer within a specified range  
#define getrandom( min, max ) (( (rand_s (&number), number) % (int)((( max ) + 1 ) - ( min ))) + ( min ))  
  
struct PROCESS  
{  
   int     nPid;  
   char    name[40];  
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };  
  
int main( int argc, char *argv[] )  
{  
   int termstat, c;  
   unsigned int number;  
  
   srand( (unsigned)time( NULL ) );    // Seed randomizer  
  
   // If no arguments, this is the calling process  
   if( argc == 1 )  
   {  
      // Spawn processes in numeric order  
      for( c = 0; c < 4; c++ ){  
         _flushall();  
         process[c].nPid = _spawnl( _P_NOWAIT, argv[0], argv[0],   
                             process[c].name, NULL );  
      }  
  
      // Wait for randomly specified process, and respond when done   
      c = getrandom( 0, 3 );  
      printf( "Come here, %s.\n", process[c].name );  
      _cwait( &termstat, process[c].nPid, _WAIT_CHILD );  
      printf( "Thank you, %s.\n", process[c].name );  
  
   }  
   // If there are arguments, this must be a spawned process   
   else  
   {  
      // Delay for a period that's determined by process number  
      Sleep( (argv[1][0] - 'A' + 1) * 1000L );  
      printf( "Hi, Dad. It's %s.\n", argv[1] );  
   }  
}  
```  
  
```Output  
Hi, Dad. It's Ann.  
Come here, Ann.  
Thank you, Ann.  
Hi, Dad. It's Beth.  
Hi, Dad. It's Carl.  
Hi, Dad. It's Dave.  
```  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 [System::Diagnostics::Process::WaitForExit](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.waitforexit.aspx)  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)
