---
title: "집계 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.aggregates"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregates 특성"
  - "집계[C++]"
  - "aggregate 개체 [C++], aggregates 특성"
  - "집계[C++]"
ms.assetid: 67a084c9-941f-474b-a029-9c93b38ebe9a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 집계
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

개체가 CLSID에 의해 지정된 개체를 집계함을 나타냅니다.  
  
## 구문  
  
```  
  
[ aggregates(  
clsid,  
variable_name  
) ]  
  
```  
  
#### 매개 변수  
 `clsid`  
 집계할 수 있는 개체의 CLSID를 지정합니다.  
  
 `variable_name`  
 삽입될 변수의 이름입니다. 이 변수는 집계 중인 개체의 **IUnknown**을 포함합니다.  
  
## 설명  
 개체에 적용하는 경우는 **aggregates** C\+\+ 특성은 집계 중인 개체에 대해 외부 래퍼를 구현합니다\(`clsid`에 의해 지정됨\).  
  
 이 특성을 사용하려면 [coclass](../windows/coclass.md), [progid](../windows/progid.md) 또는 [vi\_progid](../windows/vi-progid.md) 특성\(또는 이 중 하나를 암시하는 다른 특성\)을 동일한 요소에 적용해야 합니다. 단일 특성을 사용하는 경우 다른 두 특성도 자동으로 적용됩니다. 예를 들어 **progid**를 적용하면 **vi\_progid** 및 **coclass**도 적용됩니다.  
  
 **ATL 프로젝트**  
  
 ATL을 사용하는 프로젝트 내에서 이 특성을 사용하는 경우 특성의 동작이 변경됩니다. 먼저 다음 항목이 대상 개체의 COM 맵에 추가됩니다.  
  
```  
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(_m_spAttrXXX, clsid)  
```  
  
 두 번째로 [DECLARE\_GET\_CONTROLLING\_UNKNOWN](../Topic/DECLARE_GET_CONTROLLING_UNKNOWN.md) 매크로도 추가됩니다.  
  
## 예제  
  
```  
// cpp_attr_ref_aggregates.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
// requires 'aggregatable.dll'  
// see aggregatable attribute to create 'aggregatable.dll'  
class DECLSPEC_UUID("1a8369cc-1c91-42c4-befa-5a5d8c9d2529") CMyClass;  
  
[module (name="MYObject")];  
[object, uuid("ab006d85-e754-47c5-9ef4-2744ff32a20c")]  
__interface IObject  
{  
};  
  
[ coclass, aggregates(__uuidof(CMyClass)),   
  uuid("91cb2c06-8931-432a-baac-206e55c4edfb")]  
struct CObject : IObject  
{  
   int i;  
};  
```  
  
## 요구 사항  
  
### 특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**class**, `struct`|  
|**반복 가능**|예|  
|**필수 특성**|다음 중 하나 이상: **coclass**, **progid** 또는 **vi\_progid**.|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## 참고 항목  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [집계](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
 [Aggregatable](http://msdn.microsoft.com/library/windows/desktop/aa366721)   
 [COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)