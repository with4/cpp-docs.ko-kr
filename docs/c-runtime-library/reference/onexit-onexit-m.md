---
title: _onexit, _onexit_m | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _onexit
- _onexit_m
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
apitype: DLLExport
f1_keywords:
- _onexit
- onexit_m
- onexit
- _onexit_m
dev_langs:
- C++
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c190ce2c78135625a502d7509e56771fd670aa3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="onexit-onexitm"></a>_onexit, _onexit_m

종료 시 호출할 루틴을 등록합니다.

## <a name="syntax"></a>구문

```C
_onexit_t _onexit(
   _onexit_t function
);
_onexit_t_m _onexit_m(
   _onexit_t_m function
);
```

### <a name="parameters"></a>매개 변수

*function*<br/>
종료 시 호출할 함수에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**_onexit** 성공 하는 경우 함수에 대 한 포인터를 반환 하거나 **NULL** 함수 포인터를 저장 공간이 없는 경우.

## <a name="remarks"></a>설명

**_onexit** 함수는 함수의 주소를 전달 됩니다 (*함수*)는 프로그램이 정상적으로 종료 될 때 호출 되 합니다. 에 대 한 연속 호출은 **_onexit** LIFO (마지막에-선입 선출) 순서로 실행 되는 함수의 레지스터를 만듭니다. 함수에 전달 된 **_onexit** 매개 변수를 사용할 수 없습니다.

경우에 때 **_onexit** DLL을 등록 된 루틴이 내에서 호출 **_onexit** 후 DLL에 실행의 언로드에서 **DllMain** DLL_PROCESS_DETACH를 사용 하 여 호출 됩니다.

**_onexit** Microsoft 확장입니다. ANSI 이식성이 필요한 경우에는 [atexit](atexit.md)을 사용하세요. **_onexit_m** 버전의 함수는 혼합된 모드를 사용 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_onexit**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_onexit.c

#include <stdlib.h>
#include <stdio.h>

/* Prototypes */
int fn1(void), fn2(void), fn3(void), fn4 (void);

int main( void )
{
   _onexit( fn1 );
   _onexit( fn2 );
   _onexit( fn3 );
   _onexit( fn4 );
   printf( "This is executed first.\n" );
}

int fn1()
{
   printf( "next.\n" );
   return 0;
}

int fn2()
{
   printf( "executed " );
   return 0;
}

int fn3()
{
   printf( "is " );
   return 0;
}

int fn4()
{
   printf( "This " );
   return 0;
}
```

### <a name="output"></a>출력

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[__dllonexit](../../c-runtime-library/dllonexit.md)<br/>
