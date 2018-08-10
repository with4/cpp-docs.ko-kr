---
title: 'Srwlock:: Trylockexclusive 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
dev_langs:
- C++
helpviewer_keywords:
- TryLockExclusive method
ms.assetid: 661e8b19-3058-4511-8742-c9fbb90412c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 674a7dced019926e6ea07b41641eb42db70c45a0
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013482"
---
# <a name="srwlocktrylockexclusive-method"></a>SRWLock::TryLockExclusive 메서드
획득 하 려는 **SRWLock** 개체의 현재 또는 지정 된 단독 모드 **SRWLock** 개체입니다. 호출이 성공 하면 호출 스레드는 잠금 소유권을 받습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SyncLockExclusive TryLockExclusive();  
  
static SyncLockExclusive TryLockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *lock*  
 에 대 한 포인터를 **SRWLock** 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공한 경우는 **SRWLock** 개체 단독 모드 및 호출 스레드는 잠금 소유권을 받습니다. 그렇지 않은 경우는 **SRWLock** 개체 상태가 올바르지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [SRWLock 클래스](../windows/srwlock-class.md)