---
title: "컴파일러 오류 C2283 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2283"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2283"
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2283
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 순수 지정자 또는 추상 재정의 지정자는 명명되지 않은 struct에 사용할 수 없습니다.  
  
 명명되지 않은 클래스 또는 구조체의 멤버 함수가 허용되지 않는 순수 지정자를 사용하여 선언됩니다.  
  
 다음 샘플에서는 C2283을 생성합니다.  
  
```  
// C2283.cpp // compile with: /c struct { virtual void func() = 0;   // C2283 }; struct T { virtual void func() = 0;   // OK };  
```