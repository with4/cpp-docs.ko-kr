---
title: "Synclockwithstatust:: Islocked 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs: C++
helpviewer_keywords: IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05892ef6448821783fb7017ac8373423e5d37783
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="synclockwithstatustislocked-method"></a>SyncLockWithStatusT::IsLocked 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
bool IsLocked() const;  
```  
  
## <a name="remarks"></a>설명  
 SyncLockWithStatusT 된; 리소스를 소유 하는지 여부를 나타냅니다. SyncLockWithStatusT 개체 즉, *잠긴*합니다.  
  
## <a name="return-value"></a>반환 값  
 **true 이면** SyncLockWithStatusT 개체가 고, 그렇지 않으면 잠긴 **false**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>참고 항목  
 [SyncLockWithStatusT 클래스](../windows/synclockwithstatust-class.md)