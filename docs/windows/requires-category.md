---
title: requires_category | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.requires_category
dev_langs:
- C++
helpviewer_keywords:
- requires_category attribute
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3a6822773292fd651eaae3be5c00fb2b693a80a9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882318"
---
# <a name="requirescategory"></a>requires_category
대상 클래스의 필수 구성 요소 범주를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
     [ requires_category(   
  requires_category  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *requires_category*  
 필요한 범주의 ID입니다.  
  
## <a name="remarks"></a>설명  
 **requires_category** c + + 특성 대상 클래스에 필요한 구성 요소 범주를 지정 합니다. 자세한 내용은 참조 [REQUIRED_CATEGORY](../atl/reference/category-macros.md#required_category)합니다.  
  
 이 특성을 사용하려면 [coclass](../windows/coclass.md), [progid](../windows/progid.md)또는 [vi_progid](../windows/vi-progid.md) 특성(또는 이 중 하나를 암시하는 다른 특성)을 동일한 요소에 적용해야 합니다.  
  
## <a name="example"></a>예제  
 다음 코드는 개체가 컨트롤 범주를 구현 해야 합니다.  
  
```  
// cpp_attr_ref_requires_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLibrary")];  
  
[ coclass, requires_category("CATID_Control"),  
  uuid("1e1a2436-f3ea-4ff3-80bf-5409370e8144")]  
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
 [COM 특성](../windows/com-attributes.md)   
 [implements_category](../windows/implements-category.md)   
