---
title: ms_union | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.ms_union
dev_langs:
- C++
helpviewer_keywords:
- ms_union attribute
ms.assetid: bb548689-6962-457e-af56-8ffdf68987eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c20b795231cad936f30ef329f015b6ff691aa0d3
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606701"
---
# <a name="msunion"></a>ms_union
Nonencapsulated 공용 구조체의 네트워크 데이터 표현 맞춤을 제어합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ms_union]  
```  
  
## <a name="remarks"></a>설명  
 합니다 **ms_union** c + + 특성에 동일한 기능을 합니다 [ms_union](http://msdn.microsoft.com/library/windows/desktop/aa367100) MIDL 특성입니다.  
  
## <a name="example"></a>예  
 다음 코드의 배치를 보여 줍니다 **ms_union**:  
  
```cpp  
// cpp_attr_ref_ms_union.cpp  
// compile with: /LD  
#include <unknwn.h>  
[object, ms_union, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl {  
   HRESULT DisplayString([in, string] char * p1);  
};  
  
[export, switch_type(short)] union _WILLIE_UNION_TYPE  {  
   [case(24)]  
      float fMays;  
   [case(25)]  
      double dMcCovey;  
   [default]  
      int x;  
 };  
  
[public] typedef _WILLIE_UNION_TYPE WILLIE_UNION_TYPE;  
  
[module(name="ATLFIRELib")];  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|Nonencapsulated 공용 구조체|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|`dispinterface`|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   