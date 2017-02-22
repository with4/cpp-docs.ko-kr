---
title: "컴파일러 오류 C2821 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2821"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2821"
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2821
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator new'에 대한 첫째 형식 매개 변수는 'unsigned int'이어야 합니다.  
  
 [operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md)의 첫 번째 형식 매개 변수는 부호 없는 `int`여야 합니다.  
  
 다음 샘플에서는 C2821 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2821.cpp  
// compile with: /c  
void * operator new( /* unsigned int,*/ void * );   // C2821  
void * operator new( unsigned int, void * );  
```