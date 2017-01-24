---
title: "Lvalue 및 Rvalue | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "L-value"
  - "R-value"
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Lvalue 및 Rvalue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모든 C\+\+ 식은 lvalue 또는 rvalue입니다.  lvalue는 단일 식을 넘어 지속되는 개체를 참조합니다.  lvalue를 이름이 있는 개체로 생각할 수 있습니다.  수정할 수 없는\(`const`\) 변수를 비롯한 모든 변수가 lvalue입니다.  rvalue는 rvalue를 사용하는 식 외에서는 유지되지 않는 임시 값입니다.  lvalue와 rvalue 간의 차이를 더 자세히 알아보려면 다음 예제를 참조하십시오.  
  
```  
// lvalues_and_rvalues1.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main()  
{  
   int x = 3 + 4;  
   cout << x << endl;  
}  
```  
  
 이 예제에서 `x`는 이를 정의하는 식 외에도 지속되기 때문에 lvalue입니다.  `3 + 4` 식은 이 식을 정의하는 식 외에서는 유지되지 않는 임시 값으로 계산되기 때문에 rvalue입니다.  
  
 다음 예제에서는 lvalue 및 rvalue에 대한 여러 가지 올바른 사용과 올바르지 않은 사용의 예를 보여 줍니다.  
  
```  
// lvalues_and_rvalues2.cpp  
int main()  
{  
   int i, j, *p;  
  
   // Correct usage: the variable i is an lvalue.  
   i = 7;  
  
   // Incorrect usage: The left operand must be an lvalue (C2106).  
   7 = i; // C2106  
   j * 4 = 7; // C2106  
  
   // Correct usage: the dereferenced pointer is an lvalue.  
   *p = i;   
  
   const int ci = 7;  
   // Incorrect usage: the variable is a non-modifiable lvalue (C3892).  
   ci = 9; // C3892  
  
   // Correct usage: the conditional operator returns an lvalue.  
   ((i < 3) ? i : j) = 7;  
}  
```  
  
> [!NOTE]
>  이 항목의 예제는 연산자가 오버로드되지 않을 때 올바른 사용과 올바르지 않은 사용의 예를 보여 줍니다.  연산자를 오버로드하여 `j * 4`와 같은 식을 lvalue로 만들 수 있습니다.  
  
 용어 *lvalue* 및 *rvalue*는 개체 참조를 참조할 때 자주 사용됩니다.  참조에 대한 자세한 내용은 [Lvalue 참조 선언자: &](../cpp/lvalue-reference-declarator-amp.md) 및 [Rvalue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하십시오.  
  
## 참고 항목  
 [기본 개념](../cpp/basic-concepts-cpp.md)   
 [Lvalue 참조 선언자: &](../cpp/lvalue-reference-declarator-amp.md)   
 [Rvalue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)