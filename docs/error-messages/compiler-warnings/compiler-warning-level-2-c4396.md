---
title: "컴파일러 경고(수준 2) C4396 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4396"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4396"
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 경고(수준 2) C4396
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"name": friend 선언이 함수 템플릿의 특수화를 참조하는 경우 인라인 지정자를 사용할 수 없습니다.  
  
 함수 템플릿의 특수화에서 [인라인](../../misc/inline-inline-forceinline.md) 지정자를 지정할 수 없습니다. 컴파일러가 C4396 경고를 실행하고 인라인 지정자를 무시합니다.  
  
### 이 오류를 해결하려면  
  
-   friend 함수 선언에서 `inline`, `__inline` 또는 `__forceinline` 지정자를 제거합니다.  
  
## 예제  
 다음 코드 예제에서는 `inline` 지정자를 사용하는 잘못된 friend 함수 선언을 보여 줍니다.  
  
```  
// C4396.cpp // compile with: /W2 /c class X; template<class T> void Func(T t, int i); class X { friend inline void Func<char>(char t, int i);  //C4396 // try the following line instead //    friend void Func<char>(char t, int i); int i; };  
```