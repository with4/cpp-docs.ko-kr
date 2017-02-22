---
title: "컴파일러 오류 C2148 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2148"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2148"
ms.assetid: e510c2c9-7b57-4ce8-be03-ba363e2cc5d9
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C2148
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

배열의 전체 크기는 0x7fffffff바이트를 초과할 수 없습니다.  
  
 배열이 크기 제한을 초과합니다.  배열의 크기를 줄이십시오.  
  
## 예제  
 다음 샘플에서는 C2148 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2148.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( ) {  
   char MyArray[0x7ffffffff];   // C2148  
   char * MyArray2 = (char *)malloc(0x7fffffff);  
  
   if (MyArray2)  
      printf_s("It worked!");  
   else  
      printf_s("It didn't work.");  
}  
```