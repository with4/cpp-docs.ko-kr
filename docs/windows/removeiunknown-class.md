---
title: RemoveIUnknown 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
dev_langs:
- C++
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eb005bc3cbf411a7d5b5ddbfa44cd6aecf802105
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="removeiunknown-class"></a>RemoveIUnknown 클래스
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename T  
>  
struct RemoveIUnknown;  
  
template <  
   typename T  
>  
class RemoveIUnknown : public T;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 클래스입니다.  
  
## <a name="remarks"></a>설명  
 에 해당 하는 형식을 만들 수는 `IUnknown`-기반된 형식 않았으나 비가상 `QueryInterface`, `AddRef`, 및 `Release` 멤버 함수입니다.  
  
 기본적으로 COM 메서드 제공 가상 `QueryInterface`, `AddRef`, 메서드를 놓습니다. 그러나 `ComPtr` 가상 메서드는 오버 헤드가 필요 하지 않습니다. `RemoveIUnknown` 개인, 비가상 제공 하 여 오버 헤드를 제거 `QueryInterface`, `AddRef`, 및 `Release` 메서드.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`ReturnType`|템플릿 매개 변수와 해당 형식에 대 한 동의어 `T` 되었지만 비가상 IUnknown 멤버입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `T`  
  
 `RemoveIUnknown`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)