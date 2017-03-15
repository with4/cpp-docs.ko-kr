---
title: "컴파일러 오류 C3733 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3733"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3733"
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3733
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event': COM 이벤트를 지정하기 위한 구문이 잘못되었습니다. '\_\_interface'가 있습니까?  
  
 COM 이벤트에 잘못된 구문이 사용되었습니다.  이 오류를 해결하려면 이벤트 형식을 변경하거나 구문을 수정하여 COM 이벤트 규칙에 따르도록 하십시오.  
  
 다음 샘플에서는 C3733 오류가 발생하는 경우를 보여 줍니다.  
  
```  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[coclass, event_source(com), // change 'com' to 'native' to resolve  
uuid("00000000-0000-0000-0000-000000000001")]  
class A  
{  
   __event void func();   // C3733  
};  
  
int main()  
{  
}  
```