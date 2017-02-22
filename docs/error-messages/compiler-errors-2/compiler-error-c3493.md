---
title: "컴파일러 오류 C3493 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3493"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3493"
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3493
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 기본 캡처 모드가 없기 때문에 'var'을 암시적으로 캡처할 수 없습니다.  
  
 빈 람다 식 캡처 `[]`는 람다 식에서 명시적으로 또는 암시적으로 변수를 캡처하지 않도록 지정합니다.  
  
### 이 오류를 해결하려면  
  
-   기본 캡처 모드를 제공합니다. 또는  
  
-   하나 이상의 변수를 명시적으로 캡처합니다.  
  
## 예제  
 다음 예제에서는 외부 변수를 수정하지만 빈 캡처 절을 지정하기 때문에 C3493을 생성합니다.  
  
```  
// C3493a.cpp int main() { int m = 55; [](int n) { m = n; }(99); // C3493 }  
```  
  
## 예제  
 다음 예제에서는 참조 방식을 기본 캡처 모드로 지정하여 C3493을 해결합니다.  
  
```  
// C3493b.cpp int main() { int m = 55; [&](int n) { m = n; }(99); }  
```  
  
## 참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)