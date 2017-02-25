---
title: "심각한 오류 C1094 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1094"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1094"
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 심각한 오류 C1094
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\-Zmval1' : 명령줄 옵션이 미리 컴파일된 헤더\('\-Zmval2'\)를 빌드하는 데 사용한 값과 일치하지 않습니다.  
  
 [\/Yc](../../build/reference/yc-create-precompiled-header-file.md)에 전달된 값은 [\/Yu](../../build/reference/yu-use-precompiled-header-file.md)에 전달된 값과 동일해야 합니다. **\/Zm** 값은 미리 컴파일된 동일한 헤더 파일을 사용하거나 생성하는 모든 컴파일에서 동일해야 합니다.  
  
 다음 샘플에서는 C1094 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C1094.h  
int func1();  
```  
  
 두 번째 코드 파일:  
  
```  
// C1094.cpp  
// compile with: /Yc"C1094.h" /Zm200  
int u;  
int main() {  
   int sd = 32;  
}  
#include "C1094.h"  
```  
  
 두 번째 코드 파일:  
  
```  
// C1094b.cpp  
// compile with: /Yu"C1094.h" /Zm300 /c  
#include "C1094.h"   // C1094 compile with /Zm200  
void Test() {}  
```