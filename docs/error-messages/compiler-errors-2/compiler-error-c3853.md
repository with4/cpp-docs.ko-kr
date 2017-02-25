---
title: "컴파일러 오류 C3853 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3853"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3853"
ms.assetid: 5b71805d-52b4-44ec-80ae-37c68d876f6a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3853
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\=': 참조 함수를 통해 참조를 다시 할당하거나 초기화할 수 없습니다.  
  
 함수가 lvalue가 아니므로 함수를 통해 참조를 할당할 수 없습니다.  
  
 다음 샘플에서는 C3853 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C3853.cpp  
// compile with: /EHsc  
#include <iostream>  
int afunc(int i)  
{  
   return i;  
}  
  
typedef int (& rFunc_t)(int);  
  
int main()  
{  
   rFunc_t rf = afunc;   // OK binding a reference to function  
   rf = afunc;   // C3853, can't reassign to a ref that's an lvalue  
   int i = 99;  
   int & ri = i;  
   std::cout << i << std::endl;  
   ri = 0;   // OK, i = 88;  
   std::cout << i << std::endl;  
}  
```