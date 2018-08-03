---
title: 'Criticalsectiontraits:: Getinvalidvalue 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- GetInvalidValue method
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf0d52769052a36c0b494d19204dd6c07f0b2404
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463387"
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>CriticalSectionTraits::GetInvalidValue 메서드
전문적으로 다루는 **CriticalSection** 템플릿 서식 파일은 항상 유효한 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
inline static Type GetInvalidValue();  
```  
  
## <a name="return-value"></a>반환 값  
 잘못 된 중요 한 섹션에 대 한 포인터를 항상 반환합니다.  
  
## <a name="remarks"></a>설명  
 합니다 *형식* 한정자로 정의 된 `typedef CRITICAL_SECTION* Type;`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [CriticalSectionTraits 구조체](../windows/criticalsectiontraits-structure.md)