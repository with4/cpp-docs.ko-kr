---
title: "컴파일러 오류 C3706 | Microsoft Docs"
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
  - "C3706"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3706"
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3706
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': COM 이벤트를 발생시키려면 COM 인터페이스이어야 합니다.  
  
 COM 이벤트를 발생시키는 데 사용하는 이벤트 인터페이스는 COM 인터페이스여야 합니다.  이 경우 Visual C\+\+ 특성을 사용하여 인터페이스를 정의하거나 \#import의 embedded\_idl 특성을 사용하여 형식 라이브러리에서 [\#import](../../preprocessor/hash-import-directive-cpp.md)로 인터페이스를 가져와야 합니다.  
  
 COM 이벤트를 사용하는 데에는 아래 샘플에 나타나 있는 ATL 헤더 파일의 `#include` 줄이 필요합니다.  이 오류를 해결하려면 [object](../../windows/object-cpp.md), [dual](../../windows/dual.md), [dispinterface](../../windows/dispinterface.md) 특성 중 하나를 인터페이스 정의에 적용하여 `IEvents`\(이벤트 인터페이스\)를 COM 인터페이스로 만드십시오.  
  
 MIDL로 생성된 헤더 파일에서 인터페이스를 가져온 경우 컴파일러는 이를 COM 인터페이스로 인식하지 않습니다.  
  
 다음 샘플에서는 C3706 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3706.cpp  
// compile with: /c  
// C3706 expected  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];  
  
// Uncomment the following line to resolve.  
// [object, uuid="12341234-1234-1234-1234-123412341237"]  
__interface IEvents : IUnknown {  
   HRESULT event1(/*[in]*/ int i);   // uncomment [in]  
};  
  
[dual, uuid="12341234-1234-1234-1234-123412341235"]  
__interface IBase {  
   HRESULT fireEvents();  
};  
  
[coclass, event_source(com), uuid="12341234-1234-1234-1234-123412341236"]  
class CEventSrc : public IBase {  
   public:  
   __event __interface IEvents;  
  
   HRESULT fireEvents() {  
      HRESULT hr = IEvents_event1(123);  
      return hr;  
   }  
};  
```