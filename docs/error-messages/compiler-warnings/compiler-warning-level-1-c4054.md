---
title: "컴파일러 경고(수준 1) C4054 | Microsoft Docs"
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
  - "C4054"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4054"
ms.assetid: bdd7f6d5-f6f2-44a7-a013-39f309de7a29
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4054
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'conversion': 'type1' 함수 포인터에서 'type2' 데이터 포인터로 캐스팅되었습니다.  
  
 함수 포인터가 데이터 포인터에 캐스팅됩니다\(잘못일 수 있음\). \/Za가 지정된 경우에는 수준 1이고 \/Ze가 지정된 경우에는 수준 4입니다.  
  
 다음 샘플에서는 C4054를 생성합니다.  
  
```  
// C4054.c // compile with: /W1 /Za /c int (*pfunc)(); int* f() { return (int*)pfunc;   // C4054 }  
```  
  
 \/Ze가 지정된 경우에는 이 경고가 수준 4입니다.  
  
```  
// C4054b.c // compile with: /W4 /c int (*pfunc)(); int* f() { return (int*)pfunc;   // C4054 }  
```