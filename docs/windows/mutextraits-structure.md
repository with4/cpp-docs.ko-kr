---
title: MutexTraits 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
dev_langs:
- C++
helpviewer_keywords:
- MutexTraits structure
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: deebac1516724469882391c3c856a9ed7a588c88
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018980"
---
# <a name="mutextraits-structure"></a>MutexTraits 구조체
일반적인 특성을 정의 합니다 [뮤텍스](../windows/mutex-class1.md) 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
struct MutexTraits : HANDLENullTraits;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[MutexTraits::Unlock 메서드](../windows/mutextraits-unlock-method.md)|공유 리소스의 한 독점적인 제어권을 해제합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `HANDLENullTraits`  
  
 `MutexTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers::HandleTraits 네임스페이스](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)