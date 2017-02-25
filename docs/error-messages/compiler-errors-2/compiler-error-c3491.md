---
title: "컴파일러 오류 C3491 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3491"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3491"
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3491
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': 변경 불가능한 람다에서 값 방식 캡처를 수정할 수 없습니다.  
  
 변경할 수 없는 람다 식은 값으로 캡처되는 변수 값을 수정할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   `mutable` 키워드를 사용하여 람다 식을 선언합니다. 또는  
  
-   람다 식의 캡처 목록에 변수를 참조로 전달합니다.  
  
## 예제  
 다음 예제에서는 변경할 수 없는 람다 식의 본문에서 `m` 캡처 변수를 수정하기 때문에 C3491을 생성합니다.  
  
```  
// C3491a.cpp int main() { int m = 55; [m](int n) { m = n; }(99); // C3491 }  
```  
  
## 예제  
 다음 예제에서는 `mutable` 키워드로 람다 식을 선언하여 C3491을 해결합니다.  
  
```  
// C3491b.cpp int main() { int m = 55; [m](int n) mutable { m = n; }(99); }  
```  
  
## 참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)