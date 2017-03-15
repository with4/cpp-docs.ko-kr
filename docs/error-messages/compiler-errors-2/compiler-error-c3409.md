---
title: "컴파일러 오류 C3409 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3409"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3409"
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 컴파일러 오류 C3409
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

빈 특성 블록을 사용할 수 없습니다.  
  
 대괄호가 컴파일러에 의해 [attribute](../../windows/cpp-attributes-reference.md) 블록으로 해석되었지만 특성이 없습니다.  
  
 람다 식 정의에 대괄호를 사용할 경우 컴파일러에서 이 오류가 발생할 수 있습니다.  이 오류는 컴파일러에서 대괄호가 람다 식 정의의 일부인지 또는 특성 블록의 일부인지를 결정할 수 없을 때 발생합니다.  람다 식에 대한 자세한 내용은 [람다 식](../../cpp/lambda-expressions-in-cpp.md)을 참조하십시오.  
  
### 이 오류를 해결하려면  
  
1.  대괄호가 특성 블록의 일부인 경우:  
  
    1.  특성 블록에서 하나 이상의 특성을 제공합니다.  
  
    2.  특성 블록을 제거합니다.  
  
2.  대괄호가 람다 식의 일부인 경우:  
  
    1.  람다 식이 올바른 구문 규칙을 따르는지 확인합니다.  
  
         람다 식 구문에 대한 자세한 내용은 [람다 식 구문](../../cpp/lambda-expression-syntax.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 C3409 오류가 생성됩니다.  
  
```  
// C3409.cpp  
// compile with: /c  
#include <windows.h>  
[]   // C3409  
class a {};  
  
// OK  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface x {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class b : public x {};  
```  
  
## 예제  
 다음 예제에서는 람다 식에서 `mutable` 사양을 사용하지만 매개 변수 목록을 제공하기 않기 때문에 C3409 오류가 발생합니다.  컴파일러에서 대괄호가 람다 식 정의의 일부인지 또는 특성 블록의 일부인지를 결정할 수 없습니다.  
  
```  
// C3409b.cpp  
  
int main()  
{  
   [] mutable {}();  
}  
```  
  
## 참고 항목  
 [특성](../../windows/cpp-attributes-reference.md)   
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)   
 [람다 식 구문](../../cpp/lambda-expression-syntax.md)