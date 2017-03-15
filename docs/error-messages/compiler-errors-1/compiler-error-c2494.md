---
title: "컴파일러 오류 C2494 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2494"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2494"
ms.assetid: 5dfd07ab-351d-49c9-b54e-f0a104776ab8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2494
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'keyword'은\(는\) 필터 식 또는 \_\_finally\/finally 블록 내부에서 호출할 수 없습니다.  
  
 `keyword`를 `__finally` 또는 finally 블록에 사용할 수 없습니다.  
  
 다음 샘플에서는 C2494 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2494.cpp  
#include <malloc.h>  
  
int main() {  
   __try {}  
   __except ( _alloca(100), 1 ) {}   // C2494  
   __try {}  
   __finally {  
      _alloca(100);   // C2494  
   }  
}  
```  
  
 **\/clr**를 사용하는 경우에도 C2494가 발생할 수 있습니다.  
  
```  
// C2494b.cpp  
// compile with: /clr  
#include <malloc.h>  
  
int main() {  
   char * buf;  
   try {}  
   catch (char * buf2) {}  
   finally {  
      _alloca(100);   // C2494  
   }  
}  
```