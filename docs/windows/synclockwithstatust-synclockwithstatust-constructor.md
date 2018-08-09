---
title: 'Synclockwithstatust:: Synclockwithstatust 생성자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT, constructor
ms.assetid: 5d2fb820-ae1b-495f-8084-ebb4fecc3104
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 21ce2054cabf257594cb3fa376236b9a1e504a59
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647757"
---
# <a name="synclockwithstatustsynclockwithstatust-constructor"></a>SyncLockWithStatusT::SyncLockWithStatusT 생성자
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
SyncLockWithStatusT(  
   _Inout_ SyncLockWithStatusT&& other  
);  
  
explicit SyncLockWithStatusT(  
   typename SyncTraits::Type sync,  
   DWORD status  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *other*  
 다른 rvalue 참조 **SyncLockWithStatusT** 개체입니다.  
  
 *sync*  
 다른에 대 한 참조가 **SyncLockWithStatusT** 개체입니다.  
  
 *status*  
 값을 [status_](../windows/synclockwithstatust-status-data-member.md) 의 데이터 멤버는 *다른* 매개 변수 또는 *동기화* 매개 변수입니다.  
  
## <a name="remarks"></a>설명  
 새 인스턴스를 초기화 합니다 **SyncLockWithStatusT** 클래스입니다.  
  
 첫 번째 생성자는 현재 초기화 **SyncLockWithStatusT** 개체에서 다른 **SyncLockWithStatusT** 매개 변수에서 지정한 *다른*, 고 다른 무효화 **SyncLockWithStatusT** 개체입니다. 두 번째 생성자는 **보호**, 및 현재 초기화 **SyncLockWithStatusT** 유효 하지 않은 상태로 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>참고 항목  
 [SyncLockWithStatusT 클래스](../windows/synclockwithstatust-class.md)   
 [SyncLockWithStatusT::GetStatus 메서드](../windows/synclockwithstatust-getstatus-method.md)