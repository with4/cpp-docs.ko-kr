---
title: "컴파일러 오류 C2457 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2457"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2457"
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2457
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'macro': 미리 정의된 매크로는 함수 본문 외부에 사용할 수 없습니다.  
  
 전역 범위에서 [\_\_FUNCTION\_\_](../../preprocessor/predefined-macros.md)과 같은 미리 정의된 매크로를 사용하려고 했습니다.  
  
## 예제  
 다음 샘플에서는 C2457 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2457.cpp  
#include <stdio.h>  
  
__FUNCTION__;   // C2457, cannot be global  
  
int main()   
{  
    printf_s("\n%s",__FUNCTION__);   // OK  
}  
```