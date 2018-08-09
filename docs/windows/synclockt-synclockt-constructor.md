---
title: 'Synclockt:: | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT, constructor
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6d4ff3393e30e72bc3378837ff11c41927249d1f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014197"
---
# <a name="synclocktsynclockt-constructor"></a>SyncLockT::SyncLockT 생성자
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SyncLockT(  
   _Inout_ SyncLockT&& other  
);  
  
explicit SyncLockT(  
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *other*  
 다른 rvalue 참조 **SyncLockT** 개체입니다.  
  
 *sync*  
 다른 참조 `SyncLockWithStatusT` 개체입니다.  
  
## <a name="remarks"></a>설명  
 새 인스턴스를 초기화 합니다 **SyncLockT** 클래스입니다.  
  
 첫 번째 생성자는 현재 초기화 **SyncLockT** 개체에서 다른 **SyncLockT** 매개 변수로 지정 된 개체 *다른*, 기타 무효화한다음 **SyncLockT** 개체입니다. 두 번째 생성자는 **보호**, 및 현재 초기화 **SyncLockT** 유효 하지 않은 상태로 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>참고 항목  
 [SyncLockT 클래스](../windows/synclockt-class.md)