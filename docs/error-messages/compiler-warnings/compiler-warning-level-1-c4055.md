---
title: "컴파일러 경고(수준 1) C4055 | Microsoft Docs"
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
  - "C4055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4055"
ms.assetid: f04b13ca-88a7-4f2b-8065-42e73e5ac353
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'conversion': 'type1' 데이터 포인터에서 'type2' 함수 포인터로 캐스팅되었습니다.  
  
 데이터 포인터가 함수 포인터로 잘못 캐스팅된 것 같습니다.  \/Za가 지정된 경우에는 수준 1이고 \/Ze가 지정된 경우에는 수준 4입니다.  
  
 다음 샘플에서는 C4055를 생성합니다.  
  
```  
// C4055.c // compile with: /Za /W1 /c typedef int (*PFUNC)(); int *pi; PFUNC f() { return (PFUNC)pi;   // C4055 }  
```  
  
 \/Ze가 지정된 경우에는 이 경고가 수준 4입니다.  
  
```  
// C4055b.c // compile with: /W4 /c typedef int (*PFUNC)(); int *pi; PFUNC f() { return (PFUNC)pi;   // C4055 }  
```