---
title: "컴파일러 경고 (수준 1) C4929 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4929"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4929"
ms.assetid: 95f8ab4f-4468-4caa-acd5-8f4592f03b3c
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# 컴파일러 경고 (수준 1) C4929
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'file': 형식 라이브러리에 공용 구조체가 있습니다. 'embedded\_idl' 한정자가 무시됩니다.  
  
 공용 구조체가 형식 라이브러리에 존재하므로 [\#import](../../preprocessor/hash-import-directive-cpp.md)의 embedded\_idl 특성이 형식 라이브러리에 적용되지 않습니다.  이 경고를 해결하려면 embedded\_idl을 사용하지 마십시오.  
  
## 예제  
 다음 샘플에서는 구성 요소를 정의합니다.  
  
```  
// C4929a.cpp  
// compile with: /LD /link /TLBOUT:C4929a.tlb  
#include <objbase.h>  
[module(name="Test")];  
[public, switch_type(short)] typedef union _TD_UNION_TYPE   {  
   [case(24)]  
      float fM;  
   [case(25)]  
      double dMN;  
   [default]  
      int x;  
} TD_UNION_TYPE;  
  
[export, public] typedef struct _TDW_TYPE {  
   [switch_is(sU)] TD_UNION_TYPE w;  
      short sU;  
} TD_TYPE;  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I {  
   HRESULT f(TD_TYPE*);  
};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct C : I {  
   HRESULT f(TD_TYPE*) { return 0; }  
};  
```  
  
## 예제  
 다음 샘플에서는 C4929 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4929b.cpp  
// compile with: /c /W1  
#import "C4929a.tlb" embedded_idl   // C4929  
```