---
title: "컴파일러 오류 C3705 | Microsoft Docs"
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
  - "C3705"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3705"
ms.assetid: 8361017d-5782-4214-a9d7-e9825fd29bc8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3705
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 이벤트 인터페이스를 찾을 수 없습니다.  
  
 COM 이벤트를 사용할 이벤트 인터페이스를 정의해야 합니다.  COM 이벤트를 사용하는 데에는 아래 샘플에 나타나 있는 ATL 헤더 파일의 `#include` 줄이 필요합니다.  이 오류를 해결하려면 샘플 코드에서 `IEvents` 인터페이스 정의를 주석으로 처리하지 마십시오.  
  
 다음 샘플에서는 C3705 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3705.cpp  
// compile with: /c  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];  
  
// Uncomment the following 4 lines to resolve.  
// [object, uuid("00000000-0000-0000-0000-000000000003")]  
// __interface IEvents : IUnknown {  
//    HRESULT event1([in] int i);  
// };  
  
[dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IBase {  
   HRESULT fireEvents();  
};  
  
[coclass, event_source(com), uuid("00000000-0000-0000-0000-000000000002")]  
class CEventSrc : public IBase {  
public:  
   __event __interface IEvents;   // C3705 uncomment IEvents to resolve  
   HRESULT fireEvents() {  
      HRESULT hr = IEvents_event1(123);  
      return hr;  
   }  
};  
```