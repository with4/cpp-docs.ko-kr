---
title: atexit | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- atexit
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
- atexit
dev_langs:
- C++
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a5dbe5e8bf71c268783893665e8e95bb587891a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="atexit"></a>atexit

종료 시 지정된 함수를 처리합니다.

## <a name="syntax"></a>구문

```C
int atexit(
   void (__cdecl *func )( void )
);
```

### <a name="parameters"></a>매개 변수

*func*<br/>
호출할 함수입니다.

## <a name="return-value"></a>반환 값

**atexit** 오류가 발생 한 경우 성공 하면 0 또는 0이 아닌 값을 반환 합니다.

## <a name="remarks"></a>설명

**atexit** 함수는 함수의 주소 전달 *func* 프로그램 정상적으로 종료 될 때 호출 되 합니다. 에 대 한 연속 호출은 **atexit** lifo (후입선출) 방식으로 순서 대로 실행 하는 함수의 레지스터를 만듭니다. 함수에 전달 된 **atexit** 매개 변수를 사용할 수 없습니다. **atexit** 및 **_onexit** 힙에 레지스터의 함수를 사용 하 여 합니다. 따라서 등록 가능한 함수의 수는 힙 메모리에 의해서만 제한됩니다.

코드는 **atexit** 함수 수 이미 언로드될 때 모든 DLL에서 종속성을 모두 포함할 수 없습니다는 **atexit** 함수를 호출 합니다.

ANSI 호환 응용 프로그램을 생성 하려면 ANSI 표준을 사용 하 여 **atexit** 함수 (유사한 대신 **_onexit** 함수).

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**atexit**|\<stdlib.h>|

## <a name="example"></a>예제

이 프로그램 푸시 4 개의 기능 때 실행할 함수 스택에 **atexit** 호출 됩니다. 프로그램이 종료되면 LIFO(후입선출) 방식으로 이러한 프로그램이 실행됩니다.

```C
// crt_atexit.c
#include <stdlib.h>
#include <stdio.h>

void fn1( void ), fn2( void ), fn3( void ), fn4( void );

int main( void )
{
   atexit( fn1 );
   atexit( fn2 );
   atexit( fn3 );
   atexit( fn4 );
   printf( "This is executed first.\n" );
}

void fn1()
{
   printf( "next.\n" );
}

void fn2()
{
   printf( "executed " );
}

void fn3()
{
   printf( "is " );
}

void fn4()
{
   printf( "This " );
}
```

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
