---
title: "Srwlockexclusivetraits:: Unlock 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 7fd6b0fb-8b88-4a43-aa74-0d7fe47a0da6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9b6c9fab4863c1d77e61a3cc5f48806a1d2ea8a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="srwlockexclusivetraitsunlock-method"></a>SRWLockExclusiveTraits::Unlock 메서드
지정된 된 SRWLock 개체의 한 독점적인 제어권을 해제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
inline static void Unlock(  
   _In_ Type srwlock  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `srwlock`  
 SRWLock 개체에 대 한 핸들입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [SRWLockExclusiveTraits 구조체](../windows/srwlockexclusivetraits-structure.md)