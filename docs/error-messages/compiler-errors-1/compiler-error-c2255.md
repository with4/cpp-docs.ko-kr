---
title: "컴파일러 오류 C2255 | Microsoft Docs"
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
  - "C2255"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2255"
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2255
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'element': 클래스 정의 외부에서 사용할 수 없습니다.  
  
 예를 들어 비멤버 함수를 `friend`로 선언했습니다.  
  
 다음 샘플에서는 C2255를 생성합니다.  
  
```  
// C2255.cpp // compile with: /c class A { private: void func1(); friend void func2(); }; friend void func1() {}   // C2255 void func2(){}  
```