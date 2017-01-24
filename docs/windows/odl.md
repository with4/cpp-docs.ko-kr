---
title: "odl | Microsoft Docs"
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
  - "vc-attr.odl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "odl attribute"
ms.assetid: 75dcb314-b50f-4a63-9180-507ac1bc78f3
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# odl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인터페이스와 개체 설명 언어 \(ODL\) 인터페이스를 식별합니다.  MIDL 컴파일러에 필요 하지 않은 여  **odl** 특성입니다. 오래 된.odl 파일 호환에 대 한 인식.  
  
## 구문  
  
```  
  
[odl]  
  
```  
  
## 설명  
 **Odl** C\+\+ 특성을 동일한 기능을가지고 있는  [odl](http://msdn.microsoft.com/library/windows/desktop/aa367126) MIDL 속성입니다.  
  
## 예제  
  
```  
// cpp_attr_ref_odl.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLIb")];  
  
[odl, oleautomation, dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyInterface  
{  
   HRESULT x();  
};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000002")]  
class cmyClass : public IMyInterface  
{  
public:  
   HRESULT x(){}  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|`interface`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)