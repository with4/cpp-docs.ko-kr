---
title: terminate(CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- terminate
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
- terminate
dev_langs:
- C++
helpviewer_keywords:
- terminate function
- exception handling, termination
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 302bb0096bd6b4d0b9e92c3508704f35f2c355c8
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="terminate-crt"></a>terminate(CRT)

호출 [중단](abort.md) 사용 하 여을 지정 하는 함수 또는 **set_terminate**합니다.

## <a name="syntax"></a>구문

```C
void terminate( void );
```

## <a name="remarks"></a>설명

**종료** 함수 c + + 예외 처리와 함께 사용 되 고 다음과 같은 경우에 호출 됩니다.

- throw된 C++ 예외에 대해 일치하는 catch 처리기를 찾을 수 없는 경우

- 스택 해제 중에 소멸자 함수가 예외를 throw한 경우

- 스택이 예외를 throw한 후에 손상된 경우

**종료** 호출 [중단](abort.md) 기본적으로 합니다. 자체 종료 함수를 작성 하 고 호출 하 여이 기본값을 변경할 수 있습니다 **set_terminate** 의 인수로 서 함수 이름으로 합니다. **종료** 에 대 한 인수로 주어진 마지막 함수를 호출 **set_terminate**합니다. 자세한 내용은 [처리되지 않은 C++ 예외](../../cpp/unhandled-cpp-exceptions.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**terminate**|\<eh.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```cpp
// crt_terminate.cpp
// compile with: /EHsc
#include <eh.h>
#include <process.h>
#include <iostream>
using namespace std;

void term_func();

int main()
{
    int i = 10, j = 0, result;
    set_terminate( term_func );
    try
    {
        if( j == 0 )
            throw "Divide by zero!";
        else
            result = i/j;
    }
    catch( int )
    {
        cout << "Caught some integer exception.\n";
    }
    cout << "This should never print.\n";
}

void term_func()
{
    cout << "term_func() was called by terminate().\n";

    // ... cleanup tasks performed here

    // If this function does not exit, abort is called.

    exit(-1);
}
```

```Output
term_func() was called by terminate().
```

## <a name="see-also"></a>참고자료

[예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
