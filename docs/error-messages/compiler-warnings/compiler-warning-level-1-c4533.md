---
title: "컴파일러 경고 (수준 1) C4533 | Microsoft Docs"
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
  - "C4533"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4533"
ms.assetid: 359fecda-d540-46e5-b214-dbabe9ef50d2
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4533
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' 초기화가 'instruction'에 의해 생략되었습니다.  
  
 프로그램 명령으로 제어 흐름이 변경되어 변수를 초기화하는 명령이 실행되지 않았습니다.  다음 샘플에서는 C4533 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4533.cpp  
// compile with: /W1  
#include <stdio.h>  
  
struct A  
{  
   int m_data;  
};  
  
int main()  
{  
   if (1)  
   {  
      goto Label;  
   }  
  
   A a = { 100 };  
  
   Label:   // C4533  
      printf("\n%d", a.m_data);   // prints an uninitialized value  
}  
```