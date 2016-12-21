---
title: "컴파일러 오류 C3232 | Microsoft Docs"
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
  - "C3232"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3232"
ms.assetid: 3119b3a9-0eff-4a3f-b805-e4d160af9e39
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3232
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'param': 정규화된 이름에는 제네릭 형식 매개 변수를 사용할 수 없습니다.  
  
 제네릭 형식 매개 변수가 잘못 사용되었습니다.  
  
 다음 샘플에서는 C3232를 생성합니다.  
  
```  
// C3232.cpp // compile with: /clr generic <class T> ref class C { typename T::TYPE t;   // C3232 };  
```