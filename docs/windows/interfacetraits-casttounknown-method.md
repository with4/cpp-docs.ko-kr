---
title: "Interfacetraits:: Casttounknown 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
dev_langs: C++
helpviewer_keywords: CastToUnknown method
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e14c5e70c4854e1f3263a26a0075373248ae9d90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="interfacetraitscasttounknown-method"></a>InterfaceTraits::CastToUnknown 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<  
   typename T  
>  
static __forceinline IUnknown* CastToUnknown(  
   _In_ T* ptr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 매개 변수 형식의 `ptr`합니다.  
  
 `ptr`  
 입력에 대 한 포인터 `T`합니다.  
  
## <a name="return-value"></a>반환 값  
 올는 IUnknown에 대 한 포인터 `Base` 파생 됩니다.  
  
## <a name="remarks"></a>설명  
 지정된 된 포인터를 IUnknown에 대 한 포인터를 캐스팅합니다.  
  
 에 대 한 자세한 내용은 `Base`, 공용 Typedefs 섹션을 참조 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)