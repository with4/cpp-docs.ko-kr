---
title: "컴파일러 오류 C2309 | Microsoft Docs"
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
  - "C2309"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2309"
ms.assetid: 6303d5b5-72cf-42b8-92ce-b1eb48e80d48
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2309
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

catch 처리기에 괄호로 묶은 예외 선언이 와야 합니다.  
  
 catch 처리기에 괄호로 묶은 형식이 사용되지 않습니다.  
  
 다음 샘플에서는 C2309 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2309.cpp  
// compile with: /EHsc  
#include <eh.h>  
class C {};  
int main() {  
   try {  
      throw "ooops!";  
   }  
   catch C {}   // C2309  
   // try the following line instead  
   // catch( C ) {}  
}  
```