---
title: "컴파일러 오류 C2251 | Microsoft Docs"
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
  - "C2251"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2251"
ms.assetid: fefe050c-f8d3-4316-b237-8007dbcdd3bf
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2251
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

네임스페이스 'namespace'에 멤버 'member'가 없습니다. 'member'를 사용하시겠습니까?  
  
 컴파일러에서 지정된 네임스페이스의 식별자를 찾을 수 없습니다.  
  
 다음 샘플에서는 C2251을 생성합니다.  
  
```  
// C2251.cpp // compile with: /c namespace A { namespace B { void f1(); } using namespace B; } void A::f1() {}   // C2251 void A::B::f1() {}   // OK  
```