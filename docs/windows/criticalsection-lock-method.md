---
title: 'Criticalsection:: Lock 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1a4fee4991459ddbab0ac370f025776529a6bd1e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464550"
---
# <a name="criticalsectionlock-method"></a>CriticalSection::Lock 메서드
지정된 임계 영역 개체의 소유권을 기다립니다. 함수가 호출 스레드가 소유권을 부여받는 시기를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *cs*  
 사용자가 지정한 임계 영역 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 현재 임계 영역의 잠금을 해제하는 데 사용할 수 있는 잠금 개체입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 **잠금** 함수는 현재 임계 영역 개체에 영향을 줍니다. 두 번째 **잠금** 함수는 사용자가 지정한 임계 영역에 영향을 줍니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [CriticalSection 클래스](../windows/criticalsection-class.md)