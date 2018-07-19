---
title: 'Activationfactory:: Getiids 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetIids
dev_langs:
- C++
helpviewer_keywords:
- GetIids method
ms.assetid: 0983d709-d155-4d65-aae4-5b2c8bb0fede
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6f411f3b2f9e777a4e458b64176ace77a8d13e86
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855512"
---
# <a name="activationfactorygetiids-method"></a>ActivationFactory::GetIids 메서드
구현된 인터페이스 ID의 배열을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHOD(  
   GetIids  
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `iidCount`  
 이 작업이 완료될 때 `iids` 배열의 인터페이스 ID 수입니다.  
  
 `iids`  
 이 작업이 완료될 대 구현된 인터페이스 ID의 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다. E_OUTOFMEMORY는 가능한 실패 HRESULT입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ActivationFactory 클래스](../windows/activationfactory-class.md)