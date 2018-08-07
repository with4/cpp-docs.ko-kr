---
title: while 문 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- while_cpp
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e226fdf4f8978172a187e1bfa8d53655ce368f5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463303"
---
# <a name="while-statement-c"></a>while 문 (C++)
실행 *문을* 까지 반복 해 서 *식* 0으로 계산 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
while ( expression )  
   statement  
```  
  
## <a name="remarks"></a>설명  
 테스트 *식* 루프를 실행 하기 전에 수행 하므로 **하는 동안** 루프는 0 번 이상 실행 합니다. *식* 정수 계열 형식, 포인터 형식, 또는 정수를 변환 하는 명확한 변환 사용 하 여 클래스 형식 또는 포인터 형식 이어야 합니다.  
  
 **하는 동안** 루프 종료할 수도 있습니다는 [중단](../cpp/break-statement-cpp.md)를 [goto](../cpp/goto-statement-cpp.md), 또는 [반환](../cpp/return-statement-cpp.md) 문 내에서 본문이 실행 됩니다. 사용 하 여 [계속](../cpp/continue-statement-cpp.md) 종료 하지 않고 현재 반복을 종료 하는 **하는 동안** 루프입니다. **계속** 의 다음 반복으로 제어를 전달 합니다 **하는 동안** 루프입니다.  
  
 다음 코드에서는 한 **동안** 문자열에서 후행 trim 루프 밑줄:  
  
```cpp 
// while_statement.cpp  
  
#include <string.h>  
#include <stdio.h>  
char *trim( char *szSource )  
{  
    char *pszEOS = 0;  
  
    //  Set pointer to character before terminating NULL  
    pszEOS = szSource + strlen( szSource ) - 1;  
  
    //  iterate backwards until non '_' is found   
    while( (pszEOS >= szSource) && (*pszEOS == '_') )  
        *pszEOS-- = '\0';  
  
    return szSource;  
}  
int main()  
{  
    char szbuf[] = "12345_____";  
  
    printf_s("\nBefore trim: %s", szbuf);  
    printf_s("\nAfter trim: %s\n", trim(szbuf));  
}  
```  
  
 루프의 맨 위에 있는 종료 조건이 평가 됩니다. 뒤에 밑줄이 있으면 루프 실행 하지 않습니다.  
  
## <a name="see-also"></a>참고자료  
 [반복 문](../cpp/iteration-statements-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [do-while 문(C++)](../cpp/do-while-statement-cpp.md)   
 [for 문(C++)](../cpp/for-statement-cpp.md)   
 [범위 기반 for 문(C++)](../cpp/range-based-for-statement-cpp.md)