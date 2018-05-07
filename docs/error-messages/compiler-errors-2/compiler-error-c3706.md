---
title: 컴파일러 오류 C3706 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3706
dev_langs:
- C++
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cb54dfce6a6974fcf09886f2d13047cdab53ced
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3706"></a>컴파일러 오류 C3706
'function': COM 이벤트를 발생 시키려면 COM 인터페이스 이어야 합니다  
  
 COM 이벤트를 발생 하는 데 사용 하는 이벤트 인터페이스는 COM 인터페이스 이어야 합니다. 이 경우 인터페이스 하거나 Visual c + + 특성을 사용 하 여 정의 해야 하거나 사용 하 여 가져올 [#import](../../preprocessor/hash-import-directive-cpp.md) #import의 embedded_idl 특성을 가진 형식 라이브러리에서.  
  
 `#include` 아래 예제에 표시 된 ATL 헤더 파일의 선은 COM 이벤트를 사용 하기 위해 필요 합니다. 이 오류를 해결 하려면 `IEvents` (이벤트 인터페이스)는 COM 인터페이스에서 다음 중 하나를 적용 하 여 인터페이스 정의 특성: [개체](../../windows/object-cpp.md), [이중](../../windows/dual.md), 또는 [ dispinterface](../../windows/dispinterface.md)합니다.  
  
 MIDL에서 생성 하는 헤더 파일에서 인터페이스가 경우 컴파일러는 인식 하지 COM 인터페이스.  
  
 다음 샘플에서는 C3706 오류가 생성 됩니다.  
  
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