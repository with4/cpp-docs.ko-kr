---
title: "_STATIC_ASSERT 매크로 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_STATIC_ASSERT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_STATIC_ASSERT 매크로"
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _STATIC_ASSERT 매크로
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일 시간에 식을 계산하고 결과가 `FALSE`일 때 에러를 생성합니다.  
  
## 구문  
  
```  
_STATIC_ASSERT(  
    booleanExpression  
);  
```  
  
#### 매개 변수  
 `booleanExpression`  
 0이 아닌 값\(`TRUE`\) 또는 0\(`FALSE`\)으로 계산된 식\(포인터 포함\)입니다.  
  
## 설명  
 이 매크로는 `booleanExpression`이 런타임 시간 대신 컴파일 시간에 계산된 것을 제외하고 [\_ASSERT and \_ASSERTE macros](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)와 비슷합니다.  `booleanExpression`가 `FALSE`\(0\)으로 계산했을 경우, [컴파일러 오류 C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md)이 생성됩니다.  
  
## 예제  
 이 예에서, `int`의 `sizeof`값이 2바이트 이상인지의 여부와 `long`의 `sizeof`값이 1바이트인지의 여부를 검사합니다.  `long`가 1바이트보다 크기 때문에, 프로그램은 컴파일되지 않고 [컴파일러 오류 C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md)를 생성할 것입니다.  
  
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
  
## 요구 사항  
  
|매크로|필수 헤더|  
|---------|-----------|  
|`_STATIC_ASSERT`|\<crtdbg.h\>|  
  
## 해당 .NET Framework 항목  
 [System::Diagnostics::Debug:: 어설션](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [\_ASSERT, \_ASSERTE, \_ASSERT\_EXPR 매크로](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)