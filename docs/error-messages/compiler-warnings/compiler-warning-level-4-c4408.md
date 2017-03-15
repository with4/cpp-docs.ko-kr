---
title: "컴파일러 경고 (수준 4) C4408 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4408"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4408"
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4408
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

익명 구조체 또는 공용 구조체에서 데이터 멤버를 선언하지 않았습니다.  
  
 익명 구조체 또는 공용 구조체에 데이터 멤버가 하나 이상 있어야 합니다.  
  
 다음 샘플에서는 C4408 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4408.cpp  
// compile with: /W4 /LD  
static union  
{  
   // int i;  
};  
// a named union can have no data members  
// } MyUnion;  
```