---
title: "컴파일러 오류 C2233 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2233"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2233"
ms.assetid: 236bdf0b-9607-4f26-a249-d8def0b1333c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2233
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 크기가 0인 배열을 포함하는 개체 배열을 사용할 수 없습니다.  
  
 배열에 있는 각 개체에는 요소가 하나 이상 포함되어야 합니다.  
  
 다음 샘플에서는 C2233 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2233.cpp  
// compile with: /c  
class A {  
   char somearray[1];  
};  
  
class B {  
   char zeroarray[];  
};  
  
A array[100];   // OK  
B array2[100];   // C2233  
```