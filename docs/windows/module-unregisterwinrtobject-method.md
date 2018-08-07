---
title: 'Module:: unregisterwinrtobject 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterWinRTObject
dev_langs:
- C++
helpviewer_keywords:
- UnregisterWinRTObject method
ms.assetid: 32334aa7-2293-40d2-9a89-4b02e2e31f3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5bf681acc485b08448fcb4e936ca1096a8137384
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607474"
---
# <a name="moduleunregisterwinrtobject-method"></a>Module::UnregisterWinRTObject 메서드
다른 응용 프로그램과 연결할 수 있도록 하나 이상의 Windows 런타임 개체를 등록 취소 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
virtual HRESULT UnregisterWinRTObject(  
   unsigned int,  
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *쿠키*  
 등록이 해지된 클래스 개체를 식별하는 값에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [Module 클래스](../windows/module-class.md)