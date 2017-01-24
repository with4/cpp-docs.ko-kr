---
title: "컴파일러 오류 C2764 | Microsoft Docs"
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
  - "C2764"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2764"
ms.assetid: 3754f5af-e094-4425-be20-d0c9a9b5baec
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2764
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'param' : 템플릿 매개 변수는 부분 특수화 'specialization'에 사용하거나 추론할 수 없습니다.  
  
 부분 특수화에 템플릿 매개 변수가 사용되지 않았습니다.  템플릿 매개 변수를 추론할 수 없으므로 부분 특수화를 사용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C2764 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2764.cpp  
#include <stdio.h>  
template <class T1, class T2>  
struct S  {  
   int m_i;  
};  
  
template <class T1, class T2>  
struct S<int, T2*> {   // C2764  
// try the following line instead  
// struct S<T1(*)(T2), T2*> {  
   char m_c;  
};  
  
int main() {  
   S<int, char> s1;  
   S<void (*)(short), short *> s2;  
   s2.m_c = 10;  
   s1.m_i = s2.m_c;  
   printf_s("%d\n", s1.m_i);  
}  
```