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
ms.openlocfilehash: 8f937bf3da7aab803164ca968ba9fa3de227ce03
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463526"
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
 *iidCount*  
 이 작업이 완료 되 면 인터페이스 Id 수는 *iid* 배열입니다.  
  
 *iid*  
 이 작업이 완료될 대 구현된 인터페이스 ID의 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다. E_OUTOFMEMORY는 가능한 실패 HRESULT입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ActivationFactory 클래스](../windows/activationfactory-class.md)