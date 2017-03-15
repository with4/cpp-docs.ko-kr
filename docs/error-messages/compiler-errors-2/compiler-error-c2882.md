---
title: "컴파일러 오류 C2882 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2882"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2882"
ms.assetid: 617018ee-5a0d-4b8d-9612-77e8ae52679b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2882
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name' : 식에서 네임스페이스 식별자를 잘못 사용했습니다.  
  
 식에서 네임스페이스 이름을 사용하려고 했습니다.  
  
 다음 샘플에서는 C2882 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2882.cpp  
// compile with: /c  
namespace A {  
   int k;  
}  
  
int i = A;   // C2882, can't assign A to i  
```