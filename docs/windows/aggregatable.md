---
title: "집계할 수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.aggregatable
dev_langs:
- C++
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ec044e18fdd8bcd21fbad8d2e46c847c876cc00d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="aggregatable"></a>aggregatable
클래스에서 집계를 지원 하는지 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ aggregatable(   
   value  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *값* (선택 사항)  
 매개 변수를 나타내는 COM 개체를 집계할 수 있습니다.  
  
-   **하지** COM 개체를 집계할 수 없습니다.  
  
-   **허용** 집계할 수 또는 COM 개체를 직접 만들 수 있습니다. 이 값이 기본값입니다.  
  
-   **항상** COM 개체가 직접 만들 수 없습니다 및 집계할 수만 있습니다. 호출 하는 경우 `CoCreateInstance` 집계 개체를 지정 해야이 개체에 대 한 **IUnknown** 인터페이스 (제어용 **IUnknown**).  
  
## <a name="remarks"></a>설명  
 **집계할 수** c + + 특성에 동일한 기능을는 [집계할 수](http://msdn.microsoft.com/library/windows/desktop/aa366721) MIDL 특성입니다. 즉, 컴파일러는 통과 **집계할 수** 를 통해 생성 된.idl 파일 특성입니다.  
  
 이 특성을 사용하려면 [coclass](../windows/coclass.md), [progid](../windows/progid.md)또는 [vi_progid](../windows/vi-progid.md) 특성(또는 이 중 하나를 암시하는 다른 특성)을 동일한 요소에 적용해야 합니다. 단일 특성을 사용하는 경우 다른 두 특성도 자동으로 적용됩니다. 예를 들어 **progid** 를 적용하면 **vi_progid** 및 **coclass** 도 적용됩니다.  
  
 **ATL 프로젝트**  
  
 ATL을 사용하는 프로젝트 내에서 이 특성을 사용하는 경우 특성의 동작이 변경됩니다. 앞에서 설명한 동작 외에도 특성에도 추가 다음 매크로 중 하나는 대상 클래스:  
  
|매개 변수 값|삽입 된 매크로|  
|---------------------|--------------------|  
|**하지**|[DECLARE_NOT_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_not_aggregatable)|  
|**허용**|[DECLARE_POLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_poly_aggregatable)|  
|**항상**|[DECLARE_ONLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_only_aggregatable)|  
  
## <a name="example"></a>예  
  
```  
// cpp_attr_ref_aggregatable.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="MyModule")];  
  
[ coclass, aggregatable(allowed),  
  uuid("1a8369cc-1c91-42c4-befa-5a5d8c9d2529")]  
class CMyClass {};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**class**, `struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|다음 중 하나 이상: **coclass**, **progid**또는 **vi_progid**.|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
 [집계](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
