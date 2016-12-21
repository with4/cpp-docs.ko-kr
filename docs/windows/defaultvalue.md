---
title: "defaultvalue | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.defaultvalue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "defaultvalue attribute"
ms.assetid: efa5d050-b2cc-4d9e-9b8e-79954f218d3a
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# defaultvalue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

입력 된 선택적 매개 변수에 대 한 기본값을 지정할 수 있습니다.  
  
## 구문  
  
```  
  
[ defaultvalue= value ]  
```  
  
#### 매개 변수  
 *value*  
 매개 변수에 대한 기본값입니다.  
  
## 설명  
 **Defaultvalue** C\+\+ 특성을 동일한 기능을가지고 있는  [defaultvalue](http://msdn.microsoft.com/library/windows/desktop/aa366793) MIDL 속성입니다.  
  
## 예제  
 다음 코드 사용 하 여 인터페이스 메서드를 보여 줍니다 있는  **defaultvalue** 특성:  
  
```  
// cpp_attr_ref_defaultvalue.cpp  
// compile with: /LD  
#include <windows.h>  
  
[export] typedef long HRESULT;  
[export, ptr, string] typedef unsigned char * MY_STRING_TYPE;  
  
[  uuid("479B29EE-9A2C-11D0-B696-00A0C903487A"),  
   dual, oleautomation,  
   helpstring("IFireTabCtrl Interface"),  
   helpcontext(122), pointer_default(unique) ]  
  
__interface IFireTabCtrl : IDispatch {  
   [bindable, propget] HRESULT get_Size([out, retval, defaultvalue("33")] long *nSize);  
   [bindable, propput] HRESULT put_Size([in] int nSize);  
};  
  
[ module(name="ATLFIRELib", uuid="479B29E1-9A2C-11D0-B696-00A0C903487A",  
      version="1.0", helpstring="ATLFire 1.0 Type Library") ];  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 매개 변수|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [아웃](../windows/out-cpp.md)   
 [retval](../windows/retval.md)   
 [in](../windows/in-cpp.md)   
 [pointer\_default](../windows/pointer-default.md)   
 [unique](../windows/unique-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)