---
title: "컴파일러 경고 (수준 2) C4146 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4146"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4146"
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 2) C4146
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

단항 마이너스 연산자가 부호 없는 형식에 적용되었습니다. 결과는 역시 unsigned입니다.  
  
 부호 없는 형식에는 음수가 아닌 값만 사용할 수 있으므로 부호 없는 형식에 단항 마이너스\(부정 연산자\)를 적용하는 것은 적절하지 않습니다.  피연산자와 결과 모두 음수가 아닙니다.  
  
 실제로, 이 경고는 프로그래머가 최소 정수 값인 \-2147483648을 나타내려고 할 때 발생합니다.  이 식은 두 단계로 처리되므로 이 값을 –2147483648로 쓸 수 없습니다.  
  
1.  숫자 2147483648이 계산됩니다.  이 값은 최대 정수 값인 2147483647보다 크기 때문에 2147483648의 형식은 [int](../../c-language/integer-types.md)가 아니라 `unsigned int`입니다.  
  
2.  부호 없는 결과인 이 값에 단항 마이너스가 적용되어 2147483648이 되기도 합니다.  
  
 부호 없는 형식의 결과로 인해 예기치 않은 동작이 발생할 수 있습니다.  예를 들어, 다른 피연산자가 `int`인 경우에는 이 결과를 비교에 사용한 다음에 부호 없는 비교를 사용할 수도 있습니다.  따라서 아래에 있는 예제 문제는 한 줄만 인쇄하게 됩니다.  
  
 `((unsigned int)1) > 2147483648` 이 false이므로 예상했던 둘째 줄인 `1 is greater than the most negative int`는 인쇄되지 않습니다.  
  
 **signed int** 형식을 사용하는 limits.h에서 INT\_MIN을 사용하면 C4146을 방지할 수 있습니다.  
  
## 예제  
 다음 샘플에서는 C4146 오류가 발생하는 경우를 보여 줍니다.  
  
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