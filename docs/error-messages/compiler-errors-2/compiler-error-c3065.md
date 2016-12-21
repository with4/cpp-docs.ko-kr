---
title: "컴파일러 오류 C3065 | Microsoft Docs"
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
  - "C3065"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3065"
ms.assetid: e7a0bc69-1c68-459e-a7c4-93c65609ff7c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3065
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

클래스 범위가 아닌 범위에서는 속성을 선언할 수 없습니다.  
  
 [property](../../cpp/property-cpp.md) \_\_declspec 한정자가 클래스 외부에서 사용되었습니다.  속성은 클래스 내부에서만 선언할 수 있습니다.  
  
 다음 샘플에서는 C3065를 생성합니다.  
  
```  
// C3065.cpp // compile with: /c __declspec(property(get=get_i)) int i;   // C3065 class x { public: __declspec(property(get=get_i)) int i;   // OK };  
```