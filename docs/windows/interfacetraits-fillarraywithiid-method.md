---
title: 'Interfacetraits:: Fillarraywithiid 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: 73583177-adc9-4fcb-917d-fa7e6d07c990
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ef552e5025a18eb4c778f9d08389d2b7e3634d5
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605658"
---
# <a name="interfacetraitsfillarraywithiid-method"></a>InterfaceTraits::FillArrayWithIid 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *index*  
 0부터 시작 인덱스 값이 포함 된 필드에 대 한 포인터입니다.  
  
 *iid*  
 인터페이스 Id의 배열입니다.  
  
## <a name="remarks"></a>설명  
 인터페이스 ID를 할당 `Base` 인덱스 인수에 의해 지정 된 배열 요소에 있습니다.  
  
 이 API의 이름, 달리 하나만 배열 요소가 수정 되; 전체 배열 되지 않습니다.  
  
 에 대 한 자세한 내용은 `Base`에서 공용 Typedefs 섹션을 참조 하세요 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)