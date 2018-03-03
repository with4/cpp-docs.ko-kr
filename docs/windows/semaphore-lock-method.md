---
title: "Semaphore:: lock 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 0eef6ede-dc7d-4f09-a6c8-2f7d39d65bfa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11531a07f161722947d03a53392b8315b7593958
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="semaphorelock-method"></a>Semaphore::Lock 메서드
현재 개체 또는 지정된 핸들에 연결된 Semaphore 개체가 신호가 있는 상태가 되거나 지정된 제한 시간 간격이 경과할 때까지 기다립니다.  
  
## <a name="syntax"></a>구문  
  
```  
SyncLock Lock(  
   DWORD milliseconds = INFINITE  
);  
  
static SyncLock Lock(  
   HANDLE h,  
   DWORD milliseconds = INFINITE  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `milliseconds`  
 제한 시간 간격(밀리초)입니다. 기본값은 INFINITE으로, 무제한 대기합니다.  
  
 `h`  
 Semaphore 개체에 대한 핸들입니다.  
  
## <a name="return-value"></a>반환 값  
 Details::SyncLockWithStatusT\<HandleTraits::SemaphoreTraits >  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
[Semaphore 클래스](../windows/semaphore-class.md)
 