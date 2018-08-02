---
title: 'Criticalsection:: Trylock 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
dev_langs:
- C++
helpviewer_keywords:
- TryLock method
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e1b9d238d4f5475475e5dc367aae196937630a0e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465424"
---
# <a name="criticalsectiontrylock-method"></a>CriticalSection::TryLock 메서드
임계 영역을 차단 하지 않고 입력 하려고 합니다. 호출이 성공 하면 호출 스레드가 중요 섹션의 소유권을 갖습니다.  
  
## <a name="syntax"></a>구문  
  
```  
SyncLock TryLock();  
  
static SyncLock TryLock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *cs*  
 사용자가 지정한 임계 영역 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 중요 섹션은 성공적으로 입력 한 경우 0이 아닌 값 또는 현재 스레드에 이미 중요 섹션을 소유 합니다. 다른 스레드가 중요 섹션을 이미 소유 하는 경우 0입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 **TryLock** 함수는 현재 임계 영역 개체에 영향을 줍니다. 두 번째 **TryLock** 함수는 사용자가 지정한 임계 영역에 영향을 줍니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [CriticalSection 클래스](../windows/criticalsection-class.md)