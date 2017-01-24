---
title: "컴파일러 오류 C2770 | Microsoft Docs"
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
  - "C2770"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2770"
ms.assetid: 100001b5-80b0-4971-8ff6-9023f443c926
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2770
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'template'에 대한 명시적 template\_or\_generic 인수가 잘못되었습니다.  
  
 명시적 템플릿 또는 제네릭 인수가 있는 함수 템플릿 후보로 인해 허용되지 않는 함수 형식이 발생했습니다.  
  
 다음 샘플에서는 C2770 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2770.cpp  
#include <stdio.h>  
template <class T>  
int f(typename T::B*);   // expects type with member B  
  
struct Err {};  
  
int main() {  
   f<int>(0);   // C2770 int has no B  
   // try the following line instead  
   f<OK>(0);  
}  
```