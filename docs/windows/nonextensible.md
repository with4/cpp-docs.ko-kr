---
title: "nonextensible | Microsoft Docs"
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
  - "vc-attr.nonextensible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nonextensible attribute"
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# nonextensible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정 하는 `IDispatch` 구현 속성만 포함 됩니다 및 메서드는 인터페이스 설명에 나열 된 및 런타임에 추가 하는 멤버로 확장할 수 없습니다.  
  
## 구문  
  
```  
  
[nonextensible]  
  
```  
  
## 설명  
 **Nonextensible** C\+\+ 특성을 동일한 기능을가지고 있는  [nonextensible](http://msdn.microsoft.com/library/windows/desktop/aa367120) MIDL 속성입니다.  
  
 사용 하 여  **nonextensible** 도 필요의  [oleautomation](../windows/oleautomation.md) 특성입니다.  
  
## 예제  
 용도 중 하나는 다음 코드를 보여 줍니다 있는  **nonextensible** 특성:  
  
```  
// cpp_attr_ref_nonextensible.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export] typedef long HRESULT;  
  
[dual, nonextensible, ms_union, oleautomation,   
uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   HRESULT procedure (int i);   
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|`interface`|  
|**반복 가능**|아니요|  
|**필수 특성**|**이중** 및  **oleautomation**, 또는  **dispinterface**|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)