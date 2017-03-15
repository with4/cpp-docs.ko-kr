---
title: "컴파일러 경고 (수준 1) C4683 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4683"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4683"
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 경고 (수준 1) C4683
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**'**   
 ***function* ': 이벤트 소스에 'out' 매개 변수가 있으므로 이벤트 처리기를 여러 개 후크하는 경우 주의해야 합니다.**  
  
 두 개 이상의 이벤트 싱크가 COM 이벤트 소스를 수신하는 경우 out 매개 변수의 값이 무시됩니다.  
  
 다음과 같은 상황에서 메모리 누수가 발생합니다.  
  
1.  메서드에 예를 들어 BSTR\*와 같이 내부적으로 할당된 out 매개 변수가 있는 경우  
  
2.  이벤트에 둘 이상의 처리기가 있는 경우\(멀티캐스트 이벤트인 경우\)  
  
 누수의 원인은 out 매개 변수가 둘 이상의 처리기에 의해 설정되지만 마지막 처리기에 의해서만 호출 사이트로 반환되기 때문입니다.  
  
 다음 샘플에서는 C4683 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4683.cpp  
// compile with: /W1 /LD  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[ module(name="xx") ];  
  
[ object ]  
__interface I {  
   HRESULT f([out] int* pi);  
   // try the following line instead  
   // HRESULT f(int* pi);  
};  
  
[ coclass, event_source(com) ]  
struct E {  
   __event __interface I;   // C4683  
};  
```