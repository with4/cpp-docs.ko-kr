---
title: "컴파일러 오류 C3702 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3702"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3702"
ms.assetid: 14fcc20e-4404-45d7-be54-e4f09332fa5a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3702
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': COM 이벤트에는 ATL이 있어야 합니다.  
  
 필요한 ATL 헤더 파일을 포함하지 않은 채 COM 이벤트를 사용하려고 했습니다.  
  
 다음 샘플에서는 C3702 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3702.cpp  
// uncomment the following line to resolve  
// #define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(dll, name=idid, uuid="12341234-1234-1234-1234-123412341234")];  
  
[object]  
__interface IEvents : IUnknown  
{  
   HRESULT event1([in] int i);  
};  
  
[dual]  
__interface IBase  
{  
   HRESULT fireEvents();  
};  
  
[coclass, event_source(com)]  
class CEventSrc : public IBase  
{  
   public:  
   __event __interface IEvents;  
  
   HRESULT fireEvents()  
   {  
      HRESULT hr = IEvents_event1(123);  
      return hr;  
   }  
};   // C3702  
  
int main() {  
}  
```