---
title: "source (C++) | Microsoft Docs"
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
  - "vc-attr.source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "source attribute"
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# source (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스에 COM 개체의 소스 인터페이스의 연결 지점 지정합니다.  속성 또는 메서드를 개체 또는 VARIANT는 이벤트의 소스인 멤버를 반환 하는 나타냅니다.  
  
## 구문  
  
```  
  
      [ source(  
   interfaces  
) ]  
```  
  
#### 매개 변수  
 `interfaces`  
 소스를 적용 하는 시기를 지정 하는 하나 이상의 인터페이스를 클래스에 특성입니다.  원본 속성이 나 메서드를 적용 하면이 매개 변수는 사용 되지 않습니다.  
  
## 설명  
 **원본** C\+\+ 특성을 동일한 기능을가지고 있는  [소스](http://msdn.microsoft.com/library/windows/desktop/aa367166) MIDL 속성.  
  
 사용할 수 있는  [기본](../windows/default-cpp.md) 개체에 대 한 기본 소스 인터페이스를 지정 하는 특성입니다.  
  
## 예제  
  
```  
// cpp_attr_ref_source.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid(11111111-1111-1111-1111-111111111111)]  
__interface b  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]  
   HRESULT get_I([out, retval]long *i);  
};  
  
[object, uuid(11111111-1111-1111-1111-111111111131)]  
__interface c  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]   
   HRESULT et_I([out, retval]long *i);  
};  
  
[coclass, default(c), uuid(11111111-1111-1111-1111-111111111132)]  
class N : public b  
{  
};  
  
[coclass, source(c), default(b, c), uuid(11111111-1111-1111-1111-111111111133)]  
class NN : public b  
{  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**class**, `struct`,`interface`|  
|**반복 가능**|아니요|  
|**필수 특성**|**coclass** \(클래스 또는 구조체에 적용 하는 경우\)|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [coclass](../windows/coclass.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)