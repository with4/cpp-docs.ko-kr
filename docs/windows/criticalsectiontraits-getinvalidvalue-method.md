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
ms.openlocfilehash: d72c9dce0765029ee31e079315baec72afd16a46
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883149"
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>CriticalSectionTraits::GetInvalidValue 메서드
서식 파일 항상 유효 하지 않은 있도록 CriticalSection 템플릿을 특수화 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
inline static Type GetInvalidValue();  
```  
  
## <a name="return-value"></a>반환 값  
 항상 유효 하지 않은 중요 한 섹션에 대 한 포인터를 반환합니다.  
  
## <a name="remarks"></a>설명  
 *형식* 한정자로 정의 `typedef CRITICAL_SECTION* Type;`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [CriticalSectionTraits 구조체](../windows/criticalsectiontraits-structure.md)