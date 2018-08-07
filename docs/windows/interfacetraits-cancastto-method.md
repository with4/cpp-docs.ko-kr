---
title: 'Interfacetraits:: Cancastto 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: df603fe8d4c063c014118caf89a74a40e73cbe5b
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607831"
---
# <a name="interfacetraitscancastto-method"></a>InterfaceTraits::CanCastTo 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename T>  
static __forceinline bool CanCastTo(  
   _In_ T* ptr,  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *ptr*  
 이름 형식에 대 한 포인터입니다.  
  
 *riid*  
 인터페이스 ID의 `Base`합니다.  
  
 *ppv*  
 이 작업에 성공 하면 *ppv* 로 지정 된 인터페이스를 가리키는 `Base`합니다. 그렇지 않으면 *ppv* 로 설정 된 **nullptr**합니다.  
  
## <a name="return-value"></a>반환 값  
 **true** 이 작업이 완료 되 고 *ptr* 포인터로 캐스팅 됩니다 `Base`이 고, 그렇지 않으면 **false** 합니다.  
  
## <a name="remarks"></a>설명  
 지정된 된 포인터에 대 한 포인터로 캐스팅 될 수 있는지 여부를 나타내는 `Base`합니다.  
  
 에 대 한 자세한 내용은 `Base`를 참조 합니다 **공용 Typedefs** 섹션 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)