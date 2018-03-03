---
title: "Interfacetraits:: Cancastto 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d8dfe6c1873d9cf897494eb6157c2be3baeb435
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
  
#### <a name="parameters"></a>매개 변수  
 `ptr`  
 형식에 대 한 포인터의 이름입니다.  
  
 `riid`  
 인터페이스 ID의 `Base`합니다.  
  
 `ppv`  
 이 작업은 성공 하는 경우 `ppv` 로 지정 된 인터페이스를 가리키는 `Base`합니다. 그렇지 않으면 `ppv` 로 설정 된 `nullptr`합니다.  
  
## <a name="return-value"></a>반환 값  
 `true`이 작업을 완료 하 고 `ptr` 에 대 한 포인터로 캐스팅 `Base`, 그렇지 않으면 `false` 합니다.  
  
## <a name="remarks"></a>설명  
 지정된 된 포인터에 대 한 포인터로 캐스팅 될 수 있는지 여부를 나타냅니다. `Base`합니다.  
  
 에 대 한 자세한 내용은 `Base`, 공용 Typedefs 섹션을 참조 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)