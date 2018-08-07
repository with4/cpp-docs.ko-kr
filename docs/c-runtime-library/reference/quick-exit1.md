---
title: quick_exit1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- quick_exit
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
- quick_exit
- process/quick_exit
- stdlib/quick_exit
dev_langs:
- C++
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de3eb88093db0eea470a0c1d775516574c466ddd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405733"
---
# <a name="quickexit"></a>quick_exit

프로그램이 정상 종료되게 합니다.

## <a name="syntax"></a>구문

```C
__declspec(noreturn) void quick_exit(
    int status
);
```

### <a name="parameters"></a>매개 변수

*status*<br/>
호스트 환경에 반환될 상태 코드입니다.

## <a name="return-value"></a>반환 값

**quick_exit** 함수는 호출자에 반환할 수 없습니다.

## <a name="remarks"></a>설명

**quick_exit** 함수로 인해 프로그램이 정상 종료 합니다. 호출 하 여 등록 된 함수가 없는 **atexit**, **_onexit** 하 여 등록 된 신호 처리기 또는 **신호** 함수입니다. 경우 동작이 정의 되지 않습니다 **quick_exit** 는 둘 이상의 한 번 호출 되거나 호출 하는 경우는 **종료** 함수 호출 또한 됩니다.

**quick_exit** 함수 방식으로, lifo (후입선출) 순서, 통해 등록 된 함수 호출 **at_quick_exit**될 때 이미 호출 된 함수는 함수가 등록 된 점을 제외 하 고, 합니다.  함수 호출을 종료하는 등록된 함수를 호출하는 동안 [longjmp](longjmp.md)가 호출되면 동작이 정의되지 않습니다.

등록된 된 함수가 호출 된 후 **quick_exit** 호출 **_Exit** 를 사용 하 여는 *상태* 호스트 환경에 제어를 반환할 값입니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**quick_exit**|\<process.h> 또는 \<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
