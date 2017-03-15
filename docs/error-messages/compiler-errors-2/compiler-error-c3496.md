---
title: "컴파일러 오류 C3496 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3496"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3496"
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3496
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'this'는 항상 값으로 캡처됩니다. '&'가 무시되었습니다.  
  
 참조에 의해 `this` 포인터를 캡처할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   값으로 `this` 포인터를 캡처합니다.  
  
## 예제  
 다음 예제에서는 `this` 포인터에 대한 참조가 람다 식의 캡처 목록에 나타나므로 C3496을 생성합니다.  
  
```  
// C3496.cpp // compile with: /c class C { void f() { [&this] {}(); // C3496 } };  
```  
  
## 참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)