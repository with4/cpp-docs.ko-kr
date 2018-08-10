---
title: 'Interfacetraits:: Casttobase 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
dev_langs:
- C++
helpviewer_keywords:
- CastToBase method
ms.assetid: 0591a017-0adf-4358-b946-eb0a307ce7f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 32c45c5445b6258f1ed2e1da220b2899a76aa9c9
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017073"
---
# <a name="interfacetraitscasttobase-method"></a>InterfaceTraits::CastToBase 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template<typename T>  
static __forceinline Base* CastToBase(  
   _In_ T* ptr  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 매개 변수의 유형을 *ptr*합니다.  
  
 *ptr*  
 형식에 대 한 포인터 *T*합니다.  
  
## <a name="return-value"></a>반환 값  
 에 대 한 포인터 `Base`합니다.  
  
## <a name="remarks"></a>설명  
 지정된 된 포인터에 대 한 포인터를 캐스팅 `Base`합니다.  
  
 에 대 한 자세한 내용은 `Base`에서 공용 Typedefs 섹션을 참조 하세요 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)