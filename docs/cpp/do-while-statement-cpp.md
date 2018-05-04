---
title: 수행-while 문 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- do_cpp
dev_langs:
- C++
helpviewer_keywords:
- do keyword [C++], do-while
- do-while keyword [C++]
- do keyword [C++]
- while keyword [C++], do-while
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81ed3628b75b98bdf7883de275ccd8f74a066abd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="do-while-statement-c"></a>do-while 문(C++)
실행는 *문을* 지정된 된 종료 조건 될 때까지 반복 해 서 (는 *식*) 0으로 계산 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
do  
   statement  
while ( expression ) ;  
```  
  
## <a name="remarks"></a>설명  
 종료 조건은 각 루프를 실행한 후 테스트되므로 `do-while` 루프는 종료 식의 값에 따라 한 번 이상 실행됩니다. `do-while` 문을 종료할 수도 있습니다는 [나누기](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md), 또는 [반환](../cpp/return-statement-cpp.md) 문은 문 본문 내에서 실행 됩니다.  
  
 *expression*은 산술 형식이나 포인터 형식이어야 합니다. 다음과 같이 실행됩니다.  
  
1.  문 본문이 실행됩니다.  
  
2.  다음으로, *expression*이 평가됩니다. *expression*이 false인 경우 `do-while` 문이 종료되고 프로그램의 다음 문으로 제어가 전달됩니다. *expression*이 true(0이 아님)인 경우에는 프로세스가 1단계부터 반복됩니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 `do-while` 문을 보여 줍니다.  
  
```  
// do_while_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        printf_s("\n%d",i++);  
    } while (i < 3);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [반복 문](../cpp/iteration-statements-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [while 문(C++)](../cpp/while-statement-cpp.md)   
 [for 문(C++)](../cpp/for-statement-cpp.md)   
 [범위 기반 for 문(C++)](../cpp/range-based-for-statement-cpp.md)