---
title: "컴파일러 오류 C3418 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3418"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3418"
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 오류 C3418
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

액세스 지정자 'specifier'는 지원되지 않습니다.  
  
 CLR 액세스 지정자를 잘못 지정했습니다.  자세한 내용은 [형식 멤버 표시 유형](../../misc/type-and-member-visibility.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3418을 생성합니다.  
  
```  
// C3418.cpp // compile with: /clr /c ref struct m { internal public:   // C3418 void test(){} }; ref struct n { internal:   // OK void test(){} };  
```