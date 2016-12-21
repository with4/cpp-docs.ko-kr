---
title: "컴파일러 오류 C3229 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3229"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3229"
ms.assetid: f2d90923-aa8b-444f-ab10-1f37dbb864e1
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3229
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 제네릭 형식 매개 변수에 대한 간접 참조는 허용되지 않습니다.  
  
 `*`, `^` 또는 `&`와 제네릭 매개 변수를 사용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3229를 생성합니다.  
  
```  
// C3229.cpp // compile with: /clr /c generic <class T> ref class C { T^ t;   // C3229 }; // OK generic <class T> ref class D { T u; };  
```  
  
## 예제  
 다음 샘플에서는 C3229를 생성합니다.  
  
```  
// C3229_b.cpp // compile with: /clr /c generic <class T>   // OK ref class Utils { static void sort(T elems[], size_t size);   // C3229 static void sort2(T elems, size_t size);   // OK };  
```