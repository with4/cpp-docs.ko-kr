---
title: "컴파일러 경고 (수준 3) C4280 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4280"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4280"
ms.assetid: 153fb639-3ee1-4fee-baf9-71420abcf3f6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4280
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator –\>'가 'type' 형식을 통해 재귀적으로 적용되었습니다.  
  
 코드에 자신을 호출하는 **operator–\>**를 잘못 사용했습니다.  
  
 다음 샘플에서는 C4280 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4280.cpp  
// compile with: /W3 /WX  
struct A  
{  
   int z;  
   A& operator ->();  
};  
  
void f(A y)  
{  
   int i = y->z; // C4280  
}  
```