---
title: exit, _Exit, _exit | Microsoft 문서
ms.custom: ''
ms.date: 1/02/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _exit
- exit
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
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e682d10fe15b611ff9ceb363d7d8593e41f386d6
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="exit-exit-exit"></a>exit, _Exit, _exit

호출 프로세스를 종료합니다. **종료** 함수; 정리 후 종료 **_exit** 및 **_Exit** 즉시 종료 합니다.

> [!NOTE]
> 테스트 또는 디버깅 시나리오에서 유니버설 Windows 플랫폼 (UWP) 앱을 제외 하 고 종료 하려면이 메서드를 사용 하지 마십시오. 스토어 앱을 닫으려면 프로그래밍 또는 UI 방식으로에 따라 허용 되지 않습니다는 [Microsoft 스토어 정책](/legal/windows/agreements/store-policies)합니다. 자세한 내용은 참조 [UWP 앱 수명 주기](/windows/uwp/launch-resume/app-lifecycle)합니다. Windows 10 앱에 대한 자세한 내용은 [Windows 10 앱에 대한 방법 가이드](http://go.microsoft.com/fwlink/p/?linkid=619133)를 참조하세요.

## <a name="syntax"></a>구문

```C
void exit(
   int const status
);
void _Exit(
   int const status
);
void _exit(
   int const status
);
```

### <a name="parameters"></a>매개 변수

*상태* 종료 상태 코드입니다.

## <a name="remarks"></a>설명

**종료**, **_Exit** 및 **_exit** 함수 호출 프로세스를 종료 합니다. **종료** 소멸자를 호출 하는 함수 스레드 로컬 개체에 대 한 호출-마지막에서 첫 번째 아웃 (후입선출) 순서로-함수를 사용 하 여 등록 **atexit** 및 **_onexit**, 프로세스를 종료 하기 전에 모든 파일 버퍼를 플러시합니다. **_Exit** 및 **_exit** 스레드 로컬 개체를 삭제 하거나 처리 하지 않고 프로세스를 종료 하는 함수 **atexit** 또는 **_onexit**함수 않고 스트림 버퍼를 플러시하지 합니다.

하지만 **종료**, **_Exit** 및 **_exit** 호출은 값에 값을 반환 하지 *상태* 호스트 환경에 사용할 수 또는 프로세스가 종료 된 후 있을 경우 호출 하는 프로세스를 대기 합니다. 일반적으로 호출자에 게 집합은 *상태* 정상 종료, 0 또는 다른 값으로 오류를 나타내는 값입니다. *상태* 값은 운영 체제 일괄 처리 명령에 사용할 수 있는 **ERRORLEVEL** 두 상수 중 하나로 표시 됩니다: **EXIT_SUCCESS**, 이며 값을 나타냅니다 0 또는 **EXIT_FAILURE**, 1의 값을 나타냅니다.

**종료**, **_Exit**, **_exit**, **quick_exit**, **_cexit**, 및 **_c_exit** 함수는 다음과 같이 작동 합니다.

|함수|설명|
|--------------|-----------------|
|**exit**|전체 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|
|**_Exit**|최소 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|
|**_exit**|최소 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|
|**quick_exit**|빠른 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|
|**_cexit**|전체 C 라이브러리 종료 절차를 수행하고 호출자에게 반환됩니다. 프로세스를 종료하지 않습니다.|
|**_c_exit**|최소 C 라이브러리 종료 절차를 수행하고 호출자에게 반환됩니다. 프로세스를 종료하지 않습니다.|

호출 하는 경우는 **종료**, **_Exit** 또는 **_exit** 함수 호출의 시간에 존재 하는 임시 또는 자동 개체에 대 한 소멸자가 호출 되지 않습니다. 자동 개체에는 함수에 정의 된 static이 아닌 로컬 개체가입니다. 임시 개체는 함수 호출에서 반환 된 값과 같은 컴파일러에 의해 만들어지는 개체입니다. 호출 하기 전에 자동 개체를 삭제 하려면 **종료**, **_Exit**, 또는 **_exit**, 명시적으로 다음과 같이 개체에 대 한 소멸자를 호출 합니다.

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

사용 하지 마십시오 **DLL_PROCESS_ATTACH** 호출할 **종료** 에서 **DllMain**합니다. 종료 하 고 **DLLMain** 함수, 반환 **FALSE** 에서 **DLL_PROCESS_ATTACH**합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**종료**, **_Exit**, **_exit**|\<process.h> 또는 \<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_exit.c
// This program returns an exit code of 1. The
// error code could be tested in a batch file.

#include <stdlib.h>

int main( void )
{
   exit( 1 );
}
```

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_cexit, _c_exit](cexit-c-exit.md)<br/>
[_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[quick_exit](quick-exit1.md)<br/>
[_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
