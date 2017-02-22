---
title: "컴파일러 오류 C3050 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3050"
ms.assetid: ee090a0b-29cc-4215-a2f9-d82af79b8e82
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1': ref 클래스는 'type1'에서 상속될 수 없습니다.  
  
 `System::ValueType`이 참조 형식에 대한 기본 클래스가 될 수 없습니다.  
  
 다음 샘플에서는 C3050을 생성합니다.  
  
```  
// C3050.cpp // compile with: /clr /LD ref struct X : System::ValueType {};   // C3050 ref struct Y {};   // OK  
```