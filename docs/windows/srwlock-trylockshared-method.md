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
ms.openlocfilehash: 19ff9324f946f48f201678f9c9e7403ba774b2c0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892285"
---
# <a name="srwlocktrylockshared-method"></a>SRWLock::TryLockShared 메서드
현재 또는 지정된 SRWLock 개체에 대해 공유 모드의 SRWLock 개체를 가져오기 위한 시도입니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `lock`  
 SRWLock 개체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 공유 모드 및 호출하는 스레드의 SRWLock 개체가 잠금에 대한 소유권을 갖습니다. 그렇지 않으면 상태가 유효하지 않은 SRWLock 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [SRWLock 클래스](../windows/srwlock-class.md)