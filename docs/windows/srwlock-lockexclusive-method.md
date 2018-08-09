---
title: 'Srwlock:: Lockexclusive 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
dev_langs:
- C++
helpviewer_keywords:
- LockExclusive method
ms.assetid: f361b672-fca6-45cc-a9b4-310cc0d23fdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a32fe0e66a8f61bc17e4512f63705635cd8b5263
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643678"
---
# <a name="srwlocklockexclusive-method"></a>SRWLock::LockExclusive 메서드
획득 한 **SRWLock** 단독 모드의 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
SyncLockExclusive LockExclusive();  
  
static SyncLockExclusive LockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *lock*  
 에 대 한 포인터를 **SRWLock** 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 **SRWLock** 단독 모드의 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [SRWLock 클래스](../windows/srwlock-class.md)