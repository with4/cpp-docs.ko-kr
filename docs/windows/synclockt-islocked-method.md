---
title: 'Synclockt:: Islocked 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: a81fea43-f99a-4708-812a-7fd6af500d3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5bfbd3418af731edf826debd9d6663095be706b8
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641521"
---
# <a name="synclocktislocked-method"></a>SyncLockT::IsLocked 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
bool IsLocked() const;  
```  
  
## <a name="return-value"></a>반환 값  
 **true** 경우는 **SyncLockT** 개체가 고, 그렇지 않으면 잠긴 **false**합니다.  
  
## <a name="remarks"></a>설명  
 나타냅니다 여부 현재 **SyncLockT** 리소스를 소유 하는 개체입니다. 즉, **SyncLockT** 개체가 *잠겨*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>참고 항목  
 [SyncLockT 클래스](../windows/synclockt-class.md)