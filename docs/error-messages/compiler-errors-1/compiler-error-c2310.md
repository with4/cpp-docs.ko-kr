---
title: "컴파일러 오류 C2310 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2310"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2310"
ms.assetid: 1969c682-b97e-43fb-b9a9-f783e7ff1710
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2310
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

catch 처리기는 형식을 하나 지정해야 합니다.  
  
 catch 처리기가 형식을 여러 개 지정하거나 하나도 지정하지 않았습니다.  
  
 다음 샘플에서는 C2310 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2310.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try {  
      throw "Out of memory!";  
   }  
   catch( int ,int) {}   // C2310 two types  
   // try the following line instead  
   // catch( int)  {}  
}  
```