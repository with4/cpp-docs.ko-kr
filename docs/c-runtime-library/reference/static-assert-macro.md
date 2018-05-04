---
title: _STATIC_ASSERT 매크로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
- _STATIC_ASSERT
dev_langs:
- C++
helpviewer_keywords:
- _STATIC_ASSERT macro
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbbab8314a038d796ebd1a13342f3054e59f3e68
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="staticassert-macro"></a>_STATIC_ASSERT 매크로

컴파일 시 식을 평가 하 고 결과 오류를 생성 **FALSE**합니다.

## <a name="syntax"></a>구문

```C
_STATIC_ASSERT(
    booleanExpression
);
```

### <a name="parameters"></a>매개 변수

*booleanExpression* 에 0이 아닌 계산 되는 식 (포인터 포함) (**TRUE**) 또는 0 (**FALSE**).

## <a name="remarks"></a>설명

이 매크로 유사한는 [_ASSERT 및 _ASSERTE 매크로](assert-asserte-assert-expr-macros.md)제외 하 고 *booleanExpression* 런타임 대신 컴파일 타임에 계산 됩니다. 경우 *booleanExpression* 계산 **FALSE** (0), [컴파일러 오류 C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) 생성 됩니다.

## <a name="example"></a>예제

확인이 예제에서는 여부는 [sizeof](../../c-language/sizeof-operator-c.md) 는 **int** 2 바이트 보다 큰 크거나 여부와 [sizeof](../../c-language/sizeof-operator-c.md) 는 **긴** 는 1 바이트입니다. 프로그램이 컴파일되지 것입니다 및 기반인 [컴파일러 오류 C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) 때문에 **긴** 1 바이트 보다 큰 합니다.

```C
// crt__static_assert.c

#include <crtdbg.h>
#include <stdio.h>

_STATIC_ASSERT(sizeof(int) >= 2);
_STATIC_ASSERT(sizeof(long) == 1);  // C2466

int main()
{
    printf("I am sure that sizeof(int) will be >= 2: %d\n",
        sizeof(int));
    printf("I am not so sure that sizeof(long) == 1: %d\n",
        sizeof(long));
}
```

## <a name="requirements"></a>요구 사항

|매크로|필수 헤더|
|-----------|---------------------|
|**_STATIC_ASSERT**|\<crtdbg.h>|

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[_ASSERT, _ASSERTE, _ASSERT_EXPR 매크로](assert-asserte-assert-expr-macros.md)<br/>
