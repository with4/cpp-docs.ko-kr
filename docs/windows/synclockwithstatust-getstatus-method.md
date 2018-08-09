---
title: 'Synclockwithstatust:: Getstatus 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
dev_langs:
- C++
helpviewer_keywords:
- GetStatus method
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4677239bbcaff0c72eb11ade259f47531a616f19
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649638"
---
# <a name="synclockwithstatustgetstatus-method"></a>SyncLockWithStatusT::GetStatus 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>반환 값  
 기반이 되는 개체에서 대기 작업의 결과 **SyncLockWithStatusT** 와 같은 클래스를 [뮤텍스](../windows/mutex-class1.md) 또는 [세마포](../windows/semaphore-class.md)합니다. 영 (0) 신호를 받은 상태를 반환 하는 대기 작업을 나타냅니다. 그렇지 않은 경우 경과 된 시간 제한 값과 같은 다른 상태가 발생 합니다.  
  
## <a name="remarks"></a>설명  
 현재 대기 상태를 검색 **SyncLockWithStatusT** 개체입니다.  
  
 기본 값을 검색 하는 getstatus () 함수 [status_](../windows/synclockwithstatust-status-data-member.md) 데이터 멤버입니다. 개체에 기반 하는 경우는 **SyncLockWithStatusT** 잠금 작업을 수행 하는 클래스, 개체 먼저 개체를 사용할 수 있을 때까지 대기 합니다. 대기 작업의 결과에 저장 되는 `status_` 데이터 멤버입니다. 가능한 값은 `status_` 데이터 멤버는 대기 작업의 반환 값입니다. 자세한 내용은 참조 반환 값은 `WaitForSingleObjectEx()` MSDN 라이브러리의 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>참고 항목  
 [SyncLockWithStatusT 클래스](../windows/synclockwithstatust-class.md)