---
title: "컴파일러 오류 C2929 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2929"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2929"
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2929
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 명시적 인스턴스화. 템플릿\-클래스 멤버의 인스턴스화를 명시적으로 강제하고 억제할 수 없습니다.  
  
 인스턴스화되지 않도록 하는 동시에 식별자를 명시적으로 인스턴스화할 수 없습니다.  
  
 다음 샘플에서는 C2929를 생성합니다.  
  
```  
// C2929.cpp // compile with: /c template<typename T> class A { public: A() {} }; template A<int>::A(); extern template A<int>::A();   // C2929  
```