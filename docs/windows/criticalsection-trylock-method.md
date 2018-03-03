---
title: "Criticalsection:: Trylock 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
dev_langs:
- C++
helpviewer_keywords:
- TryLock method
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2bd717e3a91d2e0210adced36e33a89f3752fa8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectiontrylock-method"></a>CriticalSection::TryLock 메서드
임계 영역을 차단 하지 않고 입력 하려고 합니다. 호출이 성공 하면 호출 스레드에서 임계 영역의 소유권을 갖습니다.  
  
## <a name="syntax"></a>구문  
  
```  
SyncLock TryLock();  
  
static SyncLock TryLock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cs`  
 사용자가 지정한 임계 영역 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 임계 영역 성공적으로 입력 하는 경우 0이 아닌 값 또는 현재 스레드에 이미 임계 영역을 소유 합니다. 다른 스레드가 이미 임계 영역을 소유 하는 경우 0입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 **TryLock** 함수는 현재 임계 영역 개체에 영향을 줍니다. 두 번째 **TryLock** 함수는 사용자가 지정한 임계 영역에 영향을 줍니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [CriticalSection 클래스](../windows/criticalsection-class.md)