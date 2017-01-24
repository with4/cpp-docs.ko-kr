---
title: "컴파일러 오류 C3280 | Microsoft Docs"
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
  - "C3280"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3280"
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3280
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': 관리되는 형식의 멤버\-함수는 관리되지 않는 함수로 컴파일할 수 없습니다.  
  
 관리되는 클래스 멤버 함수를 관리되지 않는 함수로 컴파일할 수 없습니다.  
  
 다음 샘플에서는 C3280을 생성합니다.  
  
```  
// C3280_2.cpp // compile with: /clr ref struct A { void func(); }; #pragma managed(push,off) void A::func()   // C3280 { } #pragma managed(pop)  
```  
  
 다음 샘플에서는 C3280을 생성합니다.  
  
```  
// C3280.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __gc struct A { void func(); }; #pragma managed(push,off) void A::func()   // C3280 { } #pragma managed(pop)  
```