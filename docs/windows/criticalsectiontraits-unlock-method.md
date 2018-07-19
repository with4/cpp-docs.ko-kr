---
title: 'Criticalsectiontraits:: Unlock 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35a632a6c88ed29ef5e30e942c1341246de75e71
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883500"
---
# <a name="criticalsectiontraitsunlock-method"></a>CriticalSectionTraits::Unlock 메서드
지정 된 임계 영역 개체의 해제 소유권 지원 되도록 CriticalSection 템플릿을 특수화입니다.  
  
## <a name="syntax"></a>구문  
  
```  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cs`  
 임계 영역 개체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 *형식* 한정자로 정의 `typedef CRITICAL_SECTION* Type;`합니다.  
  
 자세한 내용은 참조 하십시오. Windows API 설명서의 "동기화 함수" 섹션에서 "LeaveCriticalSection 함수"입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [CriticalSectionTraits 구조체](../windows/criticalsectiontraits-structure.md)