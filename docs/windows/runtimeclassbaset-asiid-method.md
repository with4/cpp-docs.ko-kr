---
title: 'Runtimeclassbaset:: Asiid 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35d218666f785685e95d737574ff44e276ce84b3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892132"
---
# <a name="runtimeclassbasetasiid-method"></a>RuntimeClassBaseT::AsIID 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename T>  
__forceinline static HRESULT AsIID(  
   _In_ T* implements,  
   REFIID riid,  
   _Deref_out_ void **ppvObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 매개 변수로 지정 된 인터페이스 ID를 구현 하는 형식은 `riid`합니다.  
  
 `implements`  
 템플릿 매개 변수로 지정 된 형식의 변수 `T`합니다.  
  
 `riid`  
 검색할 인터페이스 ID입니다.  
  
 `ppvObject`  
 에 대 한 포인터-에-a-포인터 인터페이스 매개 변수로 지정 된이 작업이 성공한 경우 `riid`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 그렇지 않으면 오류를 설명 하는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 지정 된 인터페이스 ID에 대 한 포인터를 검색합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [RuntimeClassBaseT 구조체](../windows/runtimeclassbaset-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)