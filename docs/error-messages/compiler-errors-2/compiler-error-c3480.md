---
title: "컴파일러 오류 C3480 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3480"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3480"
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3480
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': 람다 캡처 변수는 바깥쪽 함수 범위에 속해야 합니다.  
  
 람다 캡처 변수가 바깥쪽 함수 범위에 속하지 않습니다.  
  
### 이 오류를 해결하려면  
  
-   람다 식의 캡처 목록에서 변수를 제거합니다.  
  
## 예제  
 `global` 변수가 바깥쪽 함수 범위에 속하지 않으므로 다음 예제에서는 C3480을 생성합니다.  
  
```  
// C3480a.cpp int global = 0; int main() { [&global] { global = 5; }(); // C3480 }  
```  
  
## 예제  
 다음 예제에서는 람다 식의 캡처 목록에서 `global` 변수를 제거하여 C3480을 해결합니다.  
  
```  
// C3480b.cpp int global = 0; int main() { [] { global = 5; }(); }  
```  
  
## 참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)