---
title: "컴파일러 오류 C3484 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3484"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3484"
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3484
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

반환 형식 앞에 '\-\>'가 필요합니다.  
  
 람다 식의 반환 형식 앞에 `->`를 제공해야 합니다.  
  
### 이 오류를 해결하려면  
  
-   반환 형식 앞에 `->`를 제공합니다.  
  
## 예제  
 다음 예제에서는 C3484를 생성합니다.  
  
```  
// C3484a.cpp int main() { return []() . int { return 42; }(); // C3484 }  
```  
  
## 예제  
 다음 예제에서는 람다 식의 반환 형식 앞에 `->`를 제공하여 C3484를 해결합니다.  
  
```  
// C3484b.cpp int main() { return []() -> int { return 42; }(); }  
```  
  
## 참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)