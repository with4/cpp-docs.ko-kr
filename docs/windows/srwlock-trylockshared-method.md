---
title: 'Srwlock:: Trylockshared 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
dev_langs:
- C++
helpviewer_keywords:
- TryLockShared method
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 289fa1fbec61140e213bef7219e440c8177e19e5
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645814"
---
# <a name="srwlocktrylockshared-method"></a>SRWLock::TryLockShared 메서드
획득 하 려는 **SRWLock** 개체를 현재 또는 지정 된 공유 모드로 **SRWLock** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *lock*  
 에 대 한 포인터를 **SRWLock** 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공한 경우는 **SRWLock** 개체 공유 모드 및 호출 스레드는 잠금 소유권을 받습니다. 그렇지 않은 경우는 **SRWLock** 개체 상태가 올바르지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [SRWLock 클래스](../windows/srwlock-class.md)