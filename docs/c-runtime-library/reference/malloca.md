---
title: _malloca | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _malloca
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
- malloca
- _malloca
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7ef8f17af191d9af288e9d59f43f3e48cd869ed1
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="malloca"></a>_malloca

스택에 메모리를 할당합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_alloca](alloca.md) 버전입니다.

## <a name="syntax"></a>구문

```C
void *_malloca(
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
스택에서 할당할 바이트입니다.

## <a name="return-value"></a>반환 값

**_malloca** 일상적인 반환은 **void** 모든 종류의 개체를 저장 하기 위한 맞도록로 할당된 된 공간에 대 한 포인터입니다. 경우 *크기* 은 0으로, **_malloca** 길이가 0 인 항목을 할당 하 고 해당 항목에 대 한 유효한 포인터를 반환 합니다.

공간을 할당할 수 없는 경우 스택 오버플로 예외가 생성됩니다. 스택 오버플로 예외는 C++ 예외가 아니며 구조적 예외입니다. C++ 예외 처리를 사용하는 대신 [SEH(구조적 예외 처리)](../../cpp/structured-exception-handling-c-cpp.md)를 사용해야 합니다.

## <a name="remarks"></a>설명

**_malloca** 할당 *크기* 프로그램 스택이 또는 요청 특정 제공한 바이트 크기를 초과 하는 경우 힙 바이트 **_ALLOCA_S_THRESHOLD**합니다. 차이 **_malloca** 및 **_alloca** 은 **_alloca** 스택의 크기에 관계 없이 항상 할당 합니다. 와 달리 **_alloca**, 필요 하지 않거나에 대 한 호출을 허용 하 **무료** 하므로 할당 된 메모리를 확보 하기 **_malloca** 사용 해야 [_freea](freea.md)메모리를 확보 합니다. 디버그 모드에서 **_malloca** 항상 힙에서 메모리를 할당 합니다.

명시적으로 호출 제한은 **_malloca** 예외 핸들러에서 (EH). x86급 프로세서에서 실행되는 EH 루틴은 고유한 메모리 프레임에서 작동합니다. 즉, 바깥쪽 함수 스택 포인터의 현재 위치를 기반으로 하지 않는 메모리 공간에서 해당 작업을 수행합니다. 가장 일반적인 구현에는 Windows NT SEH(구조적 예외 처리) 및 C++ catch 절 식이 포함됩니다. 따라서 명시적으로 호출 **_malloca** 호출 EH 루틴을 반환 하는 동안 프로그램 오류에 다음과 같은 시나리오 결과 중 하나:

- Windows NT SEH 예외 필터 식: **__except** (`_malloca ()` )

- Windows NT SEH 최종 예외 처리기: **__finally** {`_malloca ()` }

- C++ EH catch 절 식

그러나 **_malloca** 에서 호출할 수 있습니다에서 직접 호출 하는 응용 프로그램에서 제공 콜백을 또는 EH 루틴 내에서 앞에 나열 된 EH 시나리오 중 하나입니다.

> [!IMPORTANT]
> Windows XP의 경우 **_malloca** 라고 try/catch 블록 내 호출 해야 [_resetstkoflw](resetstkoflw.md) catch 블록에서 합니다.

위의 제한을 사용 하는 경우 외에도 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 옵션을 **_malloca** 에 사용할 수 없는 **__except** 블록입니다. 자세한 내용은 [/clr Restrictions](../../build/reference/clr-restrictions.md)을 참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_malloca**|\<malloc.h>|

## <a name="example"></a>예제

```C
// crt_malloca_simple.c
#include <stdio.h>
#include <malloc.h>

void Fn()
{
   char * buf = (char *)_malloca( 100 );
   // do something with buf
   _freea( buf );
}

int main()
{
   Fn();
}
```

## <a name="example"></a>예제

```C
// crt_malloca_exception.c
// This program demonstrates the use of
// _malloca and trapping any exceptions
// that may occur.

#include <windows.h>
#include <stdio.h>
#include <malloc.h>

int main()
{
    int     size;
    int     numberRead = 0;
    int     errcode = 0;
    void    *p = NULL;
    void    *pMarker = NULL;

    while (numberRead == 0)
    {
        printf_s("Enter the number of bytes to allocate "
                 "using _malloca: ");
        numberRead = scanf_s("%d", &size);
    }

    // Do not use try/catch for _malloca,
    // use __try/__except, since _malloca throws
    // Structured Exceptions, not C++ exceptions.

    __try
    {
        if (size > 0)
        {
            p =  _malloca( size );
        }
        else
        {
            printf_s("Size must be a positive number.");
        }
        _freea( p );
    }

    // Catch any exceptions that may occur.
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )
    {
        printf_s("_malloca failed!\n");

        // If the stack overflows, use this function to restore.
        errcode = _resetstkoflw();
        if (errcode)
        {
            printf("Could not reset the stack!");
            _exit(1);
        }
    };
}
```

### <a name="input"></a>입력

```Input
1000
```

### <a name="sample-output"></a>샘플 출력

```Output
Enter the number of bytes to allocate using _malloca: 1000
```

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
