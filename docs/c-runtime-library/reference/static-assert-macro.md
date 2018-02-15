---
title: "_STATIC_ASSERT 매크로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f62f2f2f5a0d78a0b77cb21d869be209d9293bd0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="staticassert-macro"></a>_STATIC_ASSERT 매크로
컴파일 시 식을 계산하고 결과가 `FALSE`인 경우 오류를 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
_STATIC_ASSERT(  
    booleanExpression  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `booleanExpression`  
 0이 아닌 값(`TRUE`) 또는 0(`FALSE`)으로 계산되는 식(포인터 포함)입니다.  
  
## <a name="remarks"></a>설명  
 이 매크로는 `booleanExpression`이 런타임이 아닌 컴파일 시간에 계산된다는 점을 제외하고 [_ASSERT 및 _ASSERTE 매크로](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)와 비슷합니다. `booleanExpression`이 `FALSE`(0)로 계산되면 [컴파일러 오류 C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md)가 생성됩니다.  
  
## <a name="example"></a>예  
 이 예에서는 `sizeof`의 `int` 값이 2바이트 이상인지의 여부와 `sizeof`의 `long` 값이 1바이트인지 여부를 검사합니다. `long`은 1바이트보다 크므로 프로그램은 컴파일되지 않으며 [컴파일러 오류 C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md)이 생성됩니다.  
  
```  
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
|`_STATIC_ASSERT`|\<crtdbg.h>|  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_ASSERT, _ASSERTE, _ASSERT_EXPR 매크로](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)