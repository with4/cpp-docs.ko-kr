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
ms.openlocfilehash: 1cc9ee8a63d7403c3de408c924eeab07f1d0efa1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892659"
---
# <a name="srwlocktrylockexclusive-method"></a>SRWLock::TryLockExclusive 메서드
현재 또는 지정 된 SRWLock 개체에 대 한 단독 모드의 SRWLock 개체를 얻으려고 합니다. 호출이 성공 하면 호출 스레드는 잠금의 소유권을 갖습니다.  
  
## <a name="syntax"></a>구문  
  
```  
SyncLockExclusive TryLockExclusive();  
  
static SyncLockExclusive TryLockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `lock`  
 SRWLock 개체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 단독 모드가 고 호출 스레드에 SRWLock 개체 잠금 소유권을 가져옵니다. 그렇지 않으면 상태가 유효하지 않은 SRWLock 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [SRWLock 클래스](../windows/srwlock-class.md)