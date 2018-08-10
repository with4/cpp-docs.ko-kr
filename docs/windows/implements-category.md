---
title: implements_category | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.implements_category
dev_langs:
- C++
helpviewer_keywords:
- implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 28df44096f3b61eb4ada17ec824292281edee602
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013716"
---
# <a name="implementscategory"></a>implements_category
대상 클래스에서 구현 되는 구성 요소 범주를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[ implements_category(  
   implements_category="uuid"  
) ]  
```  
  
### <a name="parameters"></a>매개 변수  
 *implements_category*  
 구현 된 범주의 ID입니다.  
  
## <a name="remarks"></a>설명  
 합니다 **implements_category** c + + 특성 대상 클래스에 의해 구현 된 구성 요소 범주를 지정 합니다. 범주 지도 만들고 지정 된 별도 항목을 추가 하 여 이렇게 합니다 **implements_category** 특성입니다. 자세한 내용은 [구성 요소 범주 및 수행할 해당 작동 방법 이란?](http://msdn.microsoft.com/library/windows/desktop/ms694322)합니다.  
  
 이 특성을 사용하려면 [coclass](../windows/coclass.md), [progid](../windows/progid.md)또는 [vi_progid](../windows/vi-progid.md) 특성(또는 이 중 하나를 암시하는 다른 특성)을 동일한 요소에 적용해야 합니다. 단일 특성을 사용하는 경우 다른 두 특성도 자동으로 적용됩니다. 예를 들어 있으면 `progid` 적용 됩니다 `vi_progid` 및 `coclass` 도 적용 됩니다.  
  
## <a name="example"></a>예  
 다음 코드를 다음 구현 된 개체가 지정 된 `Control` 범주입니다.  
  
```cpp  
// cpp_attr_ref_implements_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLib")];  
[ coclass, implements_category("CATID_Control"),  
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]  
class CMyClass {};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, **구조체**|  
|**반복 가능**|예|  
|**필수 특성**|다음 중 하나: `coclass`, `progid`, 또는 `vi_progid`|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [COM 특성](../windows/com-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [IMPLEMENTED_CATEGORY](../atl/reference/category-macros.md#implemented_category)   