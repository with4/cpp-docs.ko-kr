---
title: 문 (c + +)를 계속 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- continue_cpp
dev_langs:
- C++
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b153c9f5dfae93f1a5cb83dc2b9bcfc09e77af07
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="continue-statement-c"></a>continue 문 (C++)
가장 작은 바깥쪽의 제어 식이 강제로 전송 컨트롤의 [않습니다](../cpp/do-while-statement-cpp.md), [에 대 한](../cpp/for-statement-cpp.md), 또는 [동안](../cpp/while-statement-cpp.md) 루프입니다.  
  
## <a name="syntax"></a>구문  
  
```  
continue;  
```  
  
## <a name="remarks"></a>설명  
 현재 반복에서 나머지 모든 문은 실행되지 않습니다. 루프의 다음 반복은 다음과 같이 결정됩니다.  
  
-   `do` 또는 `while` 루프 내에서 다음 반복은 `do` 또는 `while` 문의 제어 식의 다시 계산에 의해 시작됩니다.  
  
-   `for` 루프(`for`(`init-expr`; `cond-expr`; `loop-expr`) 구문 사용)에서 `loop-expr` 절이 실행됩니다. 그런 다음 `cond-expr` 절이 다시 계산되고 해당 결과에 따라 루프가 종료되거나 다른 반복이 발생합니다.  
  
 다음 예제에서는 `continue` 문을 사용하여 코드 섹션을 건너뛰고 루프의 다음 반복을 시작하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
  
```  
// continue_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        i++;  
        printf_s("before the continue\n");  
        continue;  
        printf("after the continue, should never print\n");  
     } while (i < 3);  
  
     printf_s("after the do loop\n");  
}  
```  
  
```Output  
before the continue  
before the continue  
before the continue  
after the do loop  
```  
  
## <a name="see-also"></a>참고 항목  
 [점프 문](../cpp/jump-statements-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)