---
title: "컴파일러 경고 (수준 2) C4146 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4146
dev_langs: C++
helpviewer_keywords: C4146
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d7a9a67beb4dc122c25318c1796e22a4c35dbe38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4146"></a>컴파일러 경고 (수준 2) C4146
단항 빼기 연산자 결과 역시 unsigned 부호 없는 형식에 적용  
  
 부호 없는 형식은만 음수가 아닌 값을 사용할 수 있으므로 단항 마이너스 (부정)은 일반적으로 의미가 부호 없는 형식에 적용할 경우. 피연산자와 결과 모두는 음수가 아니어야 합니다.  
  
 실제로, 프로그래머가-2147483648는 최소 정수 값을 표현 하는 경우 발생 합니다. -2147483648으로 두 단계로 식을 처리 하기 때문에이 값을 쓸 수 없습니다.  
  
1.  숫자 2147483648 평가 됩니다. 2147483647 최대 정수 값 보다 크기 때문에 2147483648의 형식이 [int](../../c-language/integer-types.md), 하지만 `unsigned int`합니다.  
  
2.  단항 마이너스 2147483648 되기도 부호 결과인 값에 적용 됩니다.  
  
 부호 없는 형식의 결과 예기치 않은 동작이 발생할 수 있습니다. 비교에서 결과 사용 하는 경우 부호 없는 비교를 사용할 수도 있습니다 예를 들어 다른 피연산자가는 `int`합니다. 다음 예제에서는 프로그램에서 한 줄을 출력 하는 이유 설명 되었습니다.  
  
 필요한 두 번째 줄 `1 is greater than the most negative int`, 때문에 인쇄 되지 `((unsigned int)1) > 2147483648` 은 false입니다.  
  
 INT_MIN는 형식을 있는 limits.h에서 사용 하 여 C4146를 방지할 수 있습니다 **int 서명**합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4146 오류가 생성 됩니다.  
  
```  
// C4146.cpp  
// compile with: /W2  
#include <stdio.h>  
  
void check(int i)   
{  
    if (i > -2147483648)   // C4146  
        printf_s("%d is greater than the most negative int\n", i);  
}  
  
int main()   
{  
    check(-100);  
    check(1);  
}  
```