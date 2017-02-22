---
title: "bindable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.bindable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bindable attribute"
ms.assetid: a2360f92-927b-4af8-98cc-6eca7f4ec954
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# bindable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

속성이 데이터 바인딩을 지원합니다.  
  
## 구문  
  
```  
  
[bindable]  
  
```  
  
## 설명  
 **바인딩할 수 있는** C\+\+ 특성을 동일한 기능을가지고 있는  [바인딩할 수 있는](http://msdn.microsoft.com/library/windows/desktop/aa366738) MIDL 속성.  정의 된 속성을 사용할 수 있습니다의  [propget](../windows/propget.md),  [propput](../windows/propput.md), 또는  [propputref](../windows/propputref.md) 특성 또는 바인딩 방법을 정의할 수 있습니다 직접.  
  
 다음 MFC 샘플 사용을 표시  **바인딩할 수 있는**:  
  
-   [컨트롤 샘플: MFC 기반 ActiveX 컨트롤](http://msdn.microsoft.com/ko-kr/a44adf86-0ba0-4504-bedb-512b6cba2e63)  
  
-   [CIRC 샘플: ActiveX 컨트롤](http://msdn.microsoft.com/ko-kr/9ba34d04-280e-49f4-90ae-41a6be44c95b)  
  
-   [TESTHELP 샘플: 도구 설명 및 도움말을 가진 ActiveX 컨트롤](http://msdn.microsoft.com/ko-kr/d822861d-c6f0-4d0a-ad11-970eebb1e8cd)  
  
## 예제  
 다음 코드에서는 사용 방법을 보여 줍니다.  **바인딩할 수 있는** 속성:  
  
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
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [defaultbind](../windows/defaultbind.md)   
 [displaybind](../windows/displaybind.md)   
 [immediatebind](../windows/immediatebind.md)   
 [requestedit](../windows/requestedit.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)