---
title: WeakReference Class1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
dev_langs:
- C++
helpviewer_keywords:
- WeakReference class
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8985434365cb8144fc2ee3680ef19c5b8ed99301
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="weakreference-class1"></a>WeakReference Class1
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class WeakReference;  
```  
  
## <a name="remarks"></a>설명  
 나타냅니다는 *약한 참조* Windows 런타임 또는 클래식 COM.와 함께 사용할 수 있는 약한 참조는 액세스할 수 있거나 액세스할 수 없는 개체를 나타냅니다.  
  
 A `WeakReference` 개체를 유지 관리는 *강력한 참조*, 되는 개체에 대 한 포인터와 *강력한 참조 횟수*, 배포 된 강력한 참조의 복사본 개수는 Resolve() 메서드입니다. 강력한 참조 횟수가 0이 아닌 이지만, 강력한 참조가 유효 하며 액세스할 수 있는 개체입니다. 강력한 참조 횟수가 0 인 경우 강력한 참조가 유효 하며 개체를 액세스할 수 없습니다.  
  
 WeakReference 개체는 일반적으로 외부 스레드나 응용 프로그램에서 제어 하는 개체를 나타내는 데 사용 됩니다. 예를 들어 파일 개체에 대 한 참조에서 WeakReference 개체를 생성 합니다. 파일이 열려 있는 동안 강력한 참조는 유효합니다. 그러나 파일이 닫히면 강력한 참조는 유효하지 않게 됩니다.  
  
 WeakReference 메서드는 스레드로부터 안전 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[WeakReference::WeakReference 생성자](../windows/weakreference-weakreference-constructor.md)|WeakReference 클래스의 새 인스턴스를 초기화합니다.|  
|[WeakReference::~WeakReference 소멸자](../windows/weakreference-tilde-weakreference-destructor.md)|초기화를 취소 (제거) WeakReference 클래스의 현재 인스턴스.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[WeakReference::DecrementStrongReference 메서드](../windows/weakreference-decrementstrongreference-method.md)|현재 WeakReference 개체의 강력한 참조 횟수를 줄입니다.|  
|[WeakReference::IncrementStrongReference 메서드](../windows/weakreference-incrementstrongreference-method.md)|현재 WeakReference 개체의 강력한 참조 횟수를 증가 시킵니다.|  
|[WeakReference::Resolve 메서드](../windows/weakreference-resolve-method.md)|강력한 참조 개수가 0이 아닌 경우 현재 강력한 참조 값으로 지정된 된 포인터를 설정 합니다.|  
|[WeakReference::SetUnknown 메서드](../windows/weakreference-setunknown-method.md)|지정 된 인터페이스 포인터를 현재 WeakReference 개체의 강력한 참조를 설정합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `WeakReference`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)