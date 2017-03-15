---
title: "컴파일러 경고(수준 3) C4646 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4646"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4646"
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고(수준 3) C4646
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_declspec\(noreturn\)으로 선언된 함수에 void가 아닌 반환 형식이 있습니다.  
  
 [noreturn](../../cpp/noreturn.md) `__declspec` 한정자로 표시한 함수에는 [void](../../cpp/void-cpp.md) 반환 형식이 있어야 합니다.  
  
 다음 샘플에서는 C4646을 생성합니다.  
  
```  
// C4646.cpp // compile with: /W3 /WX int __declspec(noreturn) TestFunction() {   // C4646  make return type void }  
```