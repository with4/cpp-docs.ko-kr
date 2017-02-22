---
title: "컴파일러 오류 C3246 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3246"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3246"
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3246
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': 'sealed'로 선언했으므로 'type'에서 상속할 수 없습니다.  
  
 [sealed](../../misc/sealed.md)로 표시된 클래스는 다른 클래스의 기본 클래스일 수 없습니다.  
  
 다음 샘플에서는 C3246을 생성합니다.  
  
```  
// C3246_2.cpp // compile with: /clr /LD ref class X sealed {}; ref class Y : public X {}; // C3246  
```  
  
 다음 샘플에서는 C3246을 생성합니다.  
  
```  
// C3246.cpp // compile with: /clr:oldSyntax /LD #using <mscorlib.dll> __sealed __gc class X {}; __gc class Y : public X {}; // C3246  
```