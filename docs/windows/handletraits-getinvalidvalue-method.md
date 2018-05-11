---
title: 'Handletraits:: Getinvalidvalue 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- GetInvalidValue method
ms.assetid: e95d2cc1-e70f-463f-8ff0-183cdeac1138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 190c327a404d19da86fdb86c32411a8ffeb06e7c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="handletraitsgetinvalidvalue-method"></a>HANDLETraits::GetInvalidValue 메서드
잘못 된 핸들을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
inline static HANDLE GetInvalidValue();  
```  
  
## <a name="return-value"></a>반환 값  
 항상 INVALID_HANDLE_VALUE를 반환합니다. (INVALID_HANDLE_VALUE가 Windows에 의해 정의 됨).  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [HANDLETraits 구조체](../windows/handletraits-structure.md)