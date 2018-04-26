---
title: _cwait | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: ef1e3c2566c9ee8628f077c11e7987f27dfb51d5
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="cwait"></a>_cwait

다른 프로세스가 종료될 때까지 기다립니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
intptr_t _cwait(
   int *termstat,
   intptr_t procHandle,
   int action
);
```

### <a name="parameters"></a>매개 변수

*termstat*<br/>
지정된 프로세스의 결과 코드가 저장되는 버퍼에 대한 포인터이거나 NULL입니다.

*procHandle*<br/>
대기 중인 프로세스에 대 한 핸들 (하기 전에 종료 되어야 하는 프로세스, 즉 **_cwait** 반환할 수 있습니다).

*action*<br/>
NULL: Windows 운영 체제 응용 프로그램;에서 무시 다른 응용 프로그램에 대 한: 작업에서 수행 하는 코드 *procHandle*합니다.

## <a name="return-value"></a>반환 값

지정한 프로세스가 성공적으로 완료 되 면 지정된 된 프로세스의 핸들을 반환 하 고 설정 *termstat* 지정한 프로세스에서 반환 되는 결과 코드를 합니다. 그렇지 않으면-1을 반환 하 고 설정 **errno** 다음과 같습니다.

|값|설명|
|-----------|-----------------|
|**ECHILD**|지정 된 프로세스가 존재 *procHandle* 이 잘못 되었거나에 대 한 호출에서 [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx) 또는 [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx) API에 실패 했습니다.|
|**EINVAL**|*동작* 올바르지 않습니다.|

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**_cwait** 에서 제공 되는 지정된 된 프로세스의 프로세스 ID의 종료 부분이 끝났으면은 *procHandle*합니다. 값 *procHandle* 에 전달 되는 **_cwait** 에 대 한 호출에서 반환 되는 값 이어야 합니다는 [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) 함수는 지정된 된 프로세스를 생성 합니다. 프로세스 ID 하기 전에 종료 하는 경우 **_cwait** 호출 **_cwait** 즉시 반환 합니다. **_cwait** 다른 모든 알려진된 프로세스를 기다리는 프로세스에 의해 사용할 수 유효한 핸들 (*procHandle*) 있습니다.

*termstat* 지정된 된 프로세스의 반환 코드를 저장할 버퍼를 가리킵니다. 값 *termstat* 지정된 된 프로세스는 Windows를 호출 하 여 정상적으로 종료 여부를 나타내는 [ExitProcess](http://msdn.microsoft.com/library/windows/desktop/ms682658.aspx) API입니다. **ExitProcess** 지정된 된 프로세스 호출 하는 경우 내부적으로 호출 **종료** 또는 **_exit**에서 반환 **주**의 끝에 도달 하거나 **주** . 통해 다시 전달 되는 값에 대 한 자세한 내용은 *termstat*, 참조 [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx)합니다. 경우 **_cwait** 에 대 한 NULL 값을 사용 하 여 호출 *termstat*, 지정된 된 프로세스의 반환 코드가 저장 되지 않습니다.

*동작* 부모-자식 관계 이러한 환경에서 구현 되지 않기 때문에 Windows 운영 체제에 의해 매개 변수가 무시 됩니다.

하지 않는 한 *procHandle* -1 또는-2 (현재 프로세스 또는 스레드 핸들) 핸들을 닫아야 합니다. 따라서 이 경우 반환된 핸들을 사용하지 마세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_cwait**|\<process.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_cwait.c
// compile with: /c
// This program launches several processes and waits
// for a specified process to finish.

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
   if ( argc == 1 )
   {
      // Spawn processes in numeric order
      for ( c = 0; c < 4; c++ ) {
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

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
