---
title: "컴파일러 오류 C2531 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2531"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2531"
ms.assetid: c49afe15-55f8-4dc8-ac01-bf653622a7db
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2531
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 비트 필드에 대한 참조가 잘못되었습니다.  
  
 비트 필드에 대한 참조를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2531 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2531.cpp  
// compile with: /c  
class P {  
   int &b1 : 10;   // C2531  
   int b2 : 10;   // OK  
};  
```