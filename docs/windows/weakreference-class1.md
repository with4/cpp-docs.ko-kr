---
title: WeakReference 클래스 1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
dev_langs:
- C++
helpviewer_keywords:
- WeakReference class
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 78b9a62838508c2e97bdd04f56778a622343e6f1
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012292"
---
# <a name="weakreference-class1"></a>WeakReference 클래스 1
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
class WeakReference;  
```  
  
## <a name="remarks"></a>설명  
 나타냅니다는 *약한 참조* Windows 런타임 또는 클래식 COM.를 사용 하 여 사용할 수 있는 약한 참조는 액세스할 수 있거나 액세스할 수 없는 개체를 나타냅니다.  
  
 A **WeakReference** 개체를 유지 관리를 *강한 참조*, 개체에 대 한 포인터는 및 *강력한 참조 횟수*, 강력한의 복사본 수 인 참조 하 여 배포 된 `Resolve()` 메서드. 강력한 참조 횟수가 0이 아닌 이지만, 강력한 참조가 유효 하며 개체 액세스할 수 있습니다. 강력한 참조 횟수가 0 인 경우 강력한 참조가 올바르지 않습니다. 및 개체에 액세스할 수 없습니다.  
  
 A **WeakReference** 개체는 일반적으로 외부 스레드나 응용 프로그램에서 제어 하는 개체를 나타내는 데 사용 됩니다. 예를 들어, 생성 된 **WeakReference** 파일 개체에 대 한 참조에서 개체입니다. 파일이 열려 있는 동안 강력한 참조는 유효합니다. 그러나 파일이 닫히면 강력한 참조는 유효하지 않게 됩니다.  
  
 합니다 **WeakReference** 메서드는 스레드로부터 안전 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[WeakReference::WeakReference 생성자](../windows/weakreference-weakreference-constructor.md)|새 인스턴스를 초기화 합니다 **WeakReference** 클래스입니다.|  
|[WeakReference::~WeakReference 소멸자](../windows/weakreference-tilde-weakreference-destructor.md)|초기화 취소 (삭제)의 현재 인스턴스를 **WeakReference** 클래스입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[WeakReference::DecrementStrongReference 메서드](../windows/weakreference-decrementstrongreference-method.md)|현재는 강력한 참조 횟수를 감소 시킵니다 **WeakReference** 개체입니다.|  
|[WeakReference::IncrementStrongReference 메서드](../windows/weakreference-incrementstrongreference-method.md)|현재 강력한 참조 횟수를 증가 시킵니다 **WeakReference** 개체입니다.|  
|[WeakReference::Resolve 메서드](../windows/weakreference-resolve-method.md)|강력한 참조 횟수가 0이 아닌 경우 현재 강력한 참조 값으로 지정된 된 포인터를 설정 합니다.|  
|[WeakReference::SetUnknown 메서드](../windows/weakreference-setunknown-method.md)|현재 강력한 참조를 설정 합니다 **WeakReference** 개체를 지정 된 인터페이스 포인터입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `WeakReference`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)