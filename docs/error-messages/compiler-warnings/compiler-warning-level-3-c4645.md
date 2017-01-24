---
title: "컴파일러 경고(수준 3) C4645 | Microsoft Docs"
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
  - "C4645"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4645"
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 3) C4645
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_declspec\(noreturn\)으로 선언된 함수에 return 문이 있습니다.  
  
 [return](../../cpp/return-statement-in-program-termination-cpp.md) 문이 [noreturn](../../cpp/noreturn.md) `__declspec` 한정자로 표시된 함수에 있습니다.`return` 문이 무시되었습니다.  
  
 다음 샘플에서는 C4645를 생성합니다.  
  
```  
// C4645.cpp // compile with:  /W3 void __declspec(noreturn) func() { return;   // C4645, delete this line to resolve } int main() { }  
```