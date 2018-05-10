---
title: 'Activationfactory:: Gettrustlevel 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1e4dfbfbc146663722eba1302b27e96812d684f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="activationfactorygettrustlevel-method"></a>ActivationFactory::GetTrustLevel 메서드
현재 ActivationFactory 인스턴스화하는 개체의 신뢰 수준을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `trustLvl`  
 이 작업이 완료될 때 ActivationFactory가 인스턴스화하는 런타임 클래스의 신뢰 수준입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 어설션 오류가 발생하고 `trustLvl`이 FullTrust로 설정됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ActivationFactory 클래스](../windows/activationfactory-class.md)