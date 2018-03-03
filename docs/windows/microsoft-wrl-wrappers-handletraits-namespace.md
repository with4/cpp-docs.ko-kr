---
title: Microsoft::WRL::Wrappers::HandleTraits Namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
dev_langs:
- C++
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aec9ff1b4294257f692d76a96960820379116b0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits 네임스페이스
일반 핸들 기반 리소스 종류의 특징을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
namespace Microsoft::WRL::Wrappers::HandleTraits;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="structures"></a>구조체  
  
|이름|설명|  
|----------|-----------------|  
|[CriticalSectionTraits 구조체](../windows/criticalsectiontraits-structure.md)|특수화는 `CriticalSection` 는 잘못 된 임계 영역 또는 중요 한 섹션을 해제 하는 함수를 지원 하기 위해 개체입니다.|  
|[EventTraits 구조체](../windows/eventtraits-structure.md)|특성을 정의 `Event` 클래스 핸들입니다.|  
|[FileHandleTraits 구조체](../windows/filehandletraits-structure.md)|열려 있는 파일 핸들의 특성을 정의합니다.|  
|[HANDLENullTraits 구조체](../windows/handlenulltraits-structure.md)|초기화 되지 않은 상태로 핸들의 일반적인 특성을 정의합니다.|  
|[HANDLETraits 구조체](../windows/handletraits-structure.md)|핸들의 일반적인 특성을 정의합니다.|  
|[MutexTraits 구조체](../windows/mutextraits-structure.md)|일반적인 특성 정의 [뮤텍스](../windows/mutex-class1.md) 클래스입니다.|  
|[SemaphoreTraits 구조체](../windows/semaphoretraits-structure.md)|Semaphore 개체의 일반적인 특성을 정의합니다.|  
|[SRWLockExclusiveTraits 구조체](../windows/srwlockexclusivetraits-structure.md)|일반적인 특성에 설명 된 `SRWLock` 배타적 잠금 모드에서는 클래스입니다.|  
|[SRWLockSharedTraits 구조체](../windows/srwlocksharedtraits-structure.md)|일반적인 특성에 설명 된 `SRWLock` 공유 잠금 모드에서는 클래스입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)