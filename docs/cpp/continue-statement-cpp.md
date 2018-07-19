---
title: continue 문 (c + +) | Microsoft Docs
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
ms.openlocfilehash: 97422a09f890686c4d414eea13da7db891494cc4
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944773"
---
# <a name="continue-statement-c"></a>continue 문 (C++)
가장 작은 바깥쪽의 제어 식으로 강제로 전송 [마십시오](../cpp/do-while-statement-cpp.md)를 [에 대 한](../cpp/for-statement-cpp.md), 또는 [하는 동안](../cpp/while-statement-cpp.md) 루프입니다.  
  
## <a name="syntax"></a>구문  
  
```  
continue;  
```  
  
## <a name="remarks"></a>설명  
 현재 반복에서 나머지 모든 문은 실행되지 않습니다. 루프의 다음 반복은 다음과 같이 결정됩니다.  
  
-   에 **수행** 또는 **하는 동안** 루프의 제어 식 내에서 시작 된 다음 반복 합니다 **수행** 또는 **하는 동안** 문.  
  
-   에 **에 대 한** 루프 (구문을 사용 하 여 `for`(`init-expr`; `cond-expr`; `loop-expr`)), `loop-expr` 절이 실행 됩니다. 그런 다음 `cond-expr` 절이 다시 계산되고 해당 결과에 따라 루프가 종료되거나 다른 반복이 발생합니다.  
  
 다음 예제와 방법을 **계속** 문은 코드 섹션을 건너뛰고 루프의 다음 반복이 시작에 사용할 수 있습니다.  
  
## <a name="example"></a>예  
  
```cpp 
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