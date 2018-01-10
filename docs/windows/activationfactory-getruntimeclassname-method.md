---
title: "Activationfactory:: Getruntimeclassname 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName
dev_langs: C++
helpviewer_keywords: GetRuntimeClassName method
ms.assetid: 74e34f0a-9c51-4b40-89f5-45c6c5886ece
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2d4c90c9025a38a46a65ecff7ad5b706420ccd96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="activationfactorygetruntimeclassname-method"></a>ActivationFactory::GetRuntimeClassName 메서드
현재 ActivationFactory 인스턴스화하는 개체의 런타임 클래스 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `runtimeName`  
 이 작업이 완료 될 때 현재 ActivationFactory 인스턴스화하는 개체의 런타임 클래스 이름을 포함 하는 문자열에 대 한 핸들입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ActivationFactory 클래스](../windows/activationfactory-class.md)