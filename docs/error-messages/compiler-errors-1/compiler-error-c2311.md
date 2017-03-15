---
title: "컴파일러 오류 C2311 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2311"
ms.assetid: 1aff9bd5-ed0b-4db6-bbc0-01ac89850cf2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2311
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'exception': '...'에 의해 줄 번호에서 catch되었습니다.  
  
 줄임표\(...\)에 대한 catch 처리기는 throw에 대한 마지막 처리기여야 합니다.  
  
 다음 샘플에서는 C2311 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2311.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try {  
      throw "ooops!";  
   }  
   catch( ... ) {}  
   catch( int ) {}   // C2311  ellipsis handler not last catch  
}  
```