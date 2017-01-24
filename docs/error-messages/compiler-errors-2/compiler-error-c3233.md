---
title: "컴파일러 오류 C3233 | Microsoft Docs"
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
  - "C3233"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3233"
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3233
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 제네릭 형식 매개 변수에 이미 제약 조건이 적용되었습니다.  
  
 제네릭 매개 변수를 둘 이상의 `where` 절에 포함할 수 없습니다.  
  
 다음 샘플에서는 C3233을 생성합니다.  
  
```  
// C3233.cpp // compile with: /clr /LD interface struct C {}; interface struct D {}; generic <class T> where T : C where T : D ref class E {};   // C3233  
```