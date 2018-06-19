---
title: ModuleBase 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
dev_langs:
- C++
helpviewer_keywords:
- ModuleBase class
ms.assetid: edce7591-6893-46f7-94a7-382827775548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bfee0c0cd7ff7bd7f4525a291184f08f1e2898e5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878738"
---
# <a name="modulebase-class"></a>ModuleBase 클래스
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class ModuleBase;  
```  
  
## <a name="remarks"></a>설명  
 기본 클래스를 나타냅니다는 [모듈](../windows/module-class.md) 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[ModuleBase::ModuleBase 생성자](../windows/modulebase-modulebase-constructor.md)|클래스의 인스턴스를 초기화합니다.|  
|[ModuleBase::~ModuleBase 소멸자](../windows/modulebase-tilde-modulebase-destructor.md)|Module 클래스의 현재 인스턴스 초기화를 해제합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ModuleBase::DecrementObjectCount 메서드](../windows/modulebase-decrementobjectcount-method.md)|구현 된 경우 개체 수가 감소 모듈에서 추적 합니다.|  
|[ModuleBase::IncrementObjectCount 메서드](../windows/modulebase-incrementobjectcount-method.md)|구현 된 경우 모듈에 의해 추적 되는 개체의 수를 증가 시킵니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ModuleBase`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)