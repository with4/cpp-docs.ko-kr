---
title: 'Semaphore:: lock 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 0eef6ede-dc7d-4f09-a6c8-2f7d39d65bfa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: be7a2b7bbac8affd0bc668113cac30f4bed96a6b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017297"
---
# <a name="semaphorelock-method"></a>Semaphore::Lock 메서드
현재 개체를 때까지 대기 또는 **세마포** 개체와 연결 된 지정된 된 핸들에 신호를 받은 상태 이거나 지정한 시간 제한 간격이 경과 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SyncLock Lock(  
   DWORD milliseconds = INFINITE  
);  
  
static SyncLock Lock(  
   HANDLE h,  
   DWORD milliseconds = INFINITE  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *시간 (밀리초)*  
 제한 시간 간격(밀리초)입니다. 기본값은 INFINITE으로, 무제한 대기합니다.  
  
 *h*  
 에 대 한 핸들을 **세마포** 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 `Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [Semaphore 클래스](../windows/semaphore-class.md)