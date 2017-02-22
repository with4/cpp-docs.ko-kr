---
title: "컴파일러 경고(수준 1) C4678 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4678"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4678"
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 경고(수준 1) C4678
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 클래스 'base\_type'이 'derived\_type'보다 액세스하기 어렵습니다.  
  
 public 형식이 전용 형식에서 파생됩니다. 참조된 어셈블리에서 public 형식을 인스턴스화할 경우 전용 기본 형식의 멤버에 액세스할 수 없습니다.  
  
 C4678은 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.**\/clr**을 사용하는 경우 파생 클래스보다 액세스하기 어려운 기본 클래스를 포함하면 오류가 발생합니다.  
  
 다음 샘플에서는 C4678을 생성합니다.  
  
```  
// C4678.cpp // compile with: /clr:oldSyntax /LD /W1 #using <mscorlib.dll> private __gc struct privateG { // try the following line instead // public __gc struct privateG { public: int i; }; public __gc struct V: public privateG {   // C4678 public: int j; };  
```