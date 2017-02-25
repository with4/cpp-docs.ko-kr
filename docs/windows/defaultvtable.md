---
title: "defaultvtable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.defaultvtable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "defaultvtable attribute"
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# defaultvtable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본 vtable 인터페이스는 COM 개체에 대 한 인터페이스를 정의합니다.  
  
## 구문  
  
```  
  
      [ defaultvtable(  
   interface  
) ]  
```  
  
#### 매개 변수  
 `interface`  
 원하는 기본 vtable을 COM 개체에 대해 지정 된 인터페이스입니다.  
  
## 설명  
 **Defaultvtable** C\+\+ 특성을 동일한 기능을가지고 있는  [defaultvtable](http://msdn.microsoft.com/library/windows/desktop/aa366795) MIDL 속성입니다.  
  
## 예제  
 다음 코드 사용 하 여 클래스에 특성을 보여 줍니다.  **defaultvtable** 는 기본 인터페이스를 지정 합니다.  
  
```  
// cpp_attr_ref_defaultvtable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI1 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface IMyI2 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000003")]  
__interface IMyI3 {  
   HRESULT x();  
};  
  
[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),  
uuid("00000000-0000-0000-0000-000000000004")]  
class CMyC3 : public IMyI3 {};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**,`struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|**coclass**|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)