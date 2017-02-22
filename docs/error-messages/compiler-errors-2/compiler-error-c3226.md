---
title: "컴파일러 오류 C3226 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3226"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3226"
ms.assetid: 636106ca-6f4e-4303-a6a0-8803221ec67d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3226
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

제네릭 선언 내부에서는 템플릿을 선언할 수 없습니다.  
  
 제네릭 클래스 내부에서는 제네릭 선언을 사용합니다.  
  
 다음 샘플에서는 C3226을 생성합니다.  
  
```  
// C3226.cpp // compile with: /clr generic <class T> ref class C { template <class T1>   // C3226 ref struct S1 {}; };  
```  
  
 다음 샘플에는 가능한 해결 방법을 보여 줍니다.  
  
```  
// C3226b.cpp // compile with: /clr /c generic <class T> ref class C { generic <class T1> ref struct S1 {}; };  
```