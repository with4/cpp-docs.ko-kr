---
title: 동기화 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.synchronize
dev_langs:
- C++
helpviewer_keywords:
- synchronize attribute
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 304ceece506465df0a51c56b247407d351fd23b3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="synchronize"></a>synchronize
대상 방법에 대 한 액세스를 동기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[synchronize]  
  
```  
  
## <a name="remarks"></a>설명  
 **동기화** c + + 특성 개체의 대상 메서드에 동기화에 대 한 지원을 구현 합니다. 동기화 대상 방법에 대 한 액세스를 제어 하 여 여러 개체를 (예: 클래스의 메서드로) 공용 리소스를 사용할 수 있습니다.  
  
 이 특성에 의해 삽입 된 코드에서 적절 한 호출 `Lock` 대상 메서드의 시작 부분에서 메서드 (스레딩 모델에 의해 결정 됨). 메서드가 종료 될 때 `Unlock` 자동으로 호출 됩니다. 이러한 함수에 대 한 자세한 내용은 참조 하십시오. [CComAutoThreadModule::Lock](../atl/reference/ccomautothreadmodule-class.md#lock)  
  
 이 특성을 사용하려면 [coclass](../windows/coclass.md), [progid](../windows/progid.md)또는 [vi_progid](../windows/vi-progid.md) 특성(또는 이 중 하나를 암시하는 다른 특성)을 동일한 요소에 적용해야 합니다. 단일 특성을 사용하는 경우 다른 두 특성도 자동으로 적용됩니다. 예를 들어 **progid** 를 적용하면 **vi_progid** 및 **coclass** 도 적용됩니다.  
  
## <a name="example"></a>예제  
 다음 코드에 대 한 동기화를 제공 합니다.는 `UpdateBalance` 의 메서드는 `CMyClass` 개체입니다.  
  
```  
// cpp_attr_ref_synchronize.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="SYNC")];  
  
[coclass,  
 threading(both),  
 vi_progid("MyProject.MyClass"),  
 progid("MyProject.MyClass.1"),  
 uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")  
]  
class CMyClass {  
   float m_nBalance;  
  
   [synchronize]  
   void UpdateBalance(float nAdjust) {  
      m_nBalance += nAdjust;  
   }  
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|메서드 클래스, 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|다음 중 하나 이상: **coclass**, **progid**또는 **vi_progid**.|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [COM 특성](../windows/com-attributes.md)   
