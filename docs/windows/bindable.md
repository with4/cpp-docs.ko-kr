---
title: "바인딩 가능한 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.bindable
dev_langs:
- C++
helpviewer_keywords:
- bindable attribute
ms.assetid: a2360f92-927b-4af8-98cc-6eca7f4ec954
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5266bca832a128242bcbbc8904ad9650e4432fe2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="bindable"></a>bindable
속성이 데이터 바인딩을 지원 하는지 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[bindable]  
  
```  
  
## <a name="remarks"></a>설명  
 **바인딩 가능한** c + + 특성에 동일한 기능을는 [바인딩 가능한](http://msdn.microsoft.com/library/windows/desktop/aa366738) MIDL 특성입니다. 정의 된 속성에 사용할 수 있습니다는 [propget](../windows/propget.md), [propput](../windows/propput.md), 또는 [propputref](../windows/propputref.md) 특성 또는 사용자를 수동으로 정의할 수는 바인딩할 수 있는 방법입니다.  
  
 MFC 샘플은 다음의 사용을 보여 줍니다. **바인딩 가능한**:  
  
-   [컨트롤 샘플: MFC 기반 ActiveX 컨트롤](http://msdn.microsoft.com/en-us/a44adf86-0ba0-4504-bedb-512b6cba2e63)  
  
-   [CIRC 샘플: ActiveX 컨트롤](http://msdn.microsoft.com/en-us/9ba34d04-280e-49f4-90ae-41a6be44c95b)  
  
-   [도구 설명 및 도움말 TESTHELP 샘플: ActiveX 컨트롤](http://msdn.microsoft.com/en-us/d822861d-c6f0-4d0a-ad11-970eebb1e8cd)  
  
## <a name="example"></a>예  
 다음 코드는 사용 하는 방법을 보여 줍니다. **바인딩 가능한** 속성:  
  
```  
// cpp_attr_ref_bindable.cpp  
// compile with: /LD  
#include <windows.h>  
[  
   uuid("479B29E3-9A2C-11D0-B696-00A0C903487A"),  
   dispinterface,  
   helpstring("property demo Interface")  
]  
__interface IPropDemo : IDispatch {  
  
   [propget, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);  
   [propput, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([in] long nSize);  
   [id(3), bindable, propget] HRESULT Object([out, retval] IDispatch **ppObj);  
   [id(3), bindable, propputref] HRESULT Object([in] IDispatch* pObj);     
   [id(-552), helpstring("method AboutBox")] HRESULT AboutBox();  
};  
  
[ module(name="PropDemoLib", uuid="479B29E2-9A2C-11D0-B696-00A0C903487A", version="1.0", helpstring="property demo") ];  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [메서드 특성](../windows/method-attributes.md)   
 [defaultbind](../windows/defaultbind.md)   
 [displaybind](../windows/displaybind.md)   
 [immediatebind](../windows/immediatebind.md)   
 [requestedit](../windows/requestedit.md)   
