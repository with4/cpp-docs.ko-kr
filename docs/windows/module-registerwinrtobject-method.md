---
title: 'Module:: registerwinrtobject 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterWinRTObject
dev_langs:
- C++
helpviewer_keywords:
- RegisterWinRTObject method
ms.assetid: a2782c9c-b9c5-4e4b-9c8d-ef513aea20c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b5605b68c569d4579324b51eaad42b1e9532011
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017417"
---
# <a name="moduleregisterwinrtobject-method"></a>Module::RegisterWinRTObject 메서드
다른 응용 프로그램에 연결할 수 있도록 하나 이상의 Windows 런타임 개체를 등록 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RegisterWinRTObject(const wchar_t* serverName,  
   wchar_t** activatableClassIds,  
   WINRT_REGISTRATION_COOKIE* cookie,  
   unsigned int count)  
```  
  
### <a name="parameters"></a>매개 변수  
 *서버 이름*  
 이 작업으로 영향을 받는 개체의 하위 집합을 지정하는 이름입니다.  
  
 *activatableClassIds*  
 등록할 활성화 가능한 CLSID 배열입니다.  
  
 *쿠키*  
 등록된 클래스 개체를 식별하는 값입니다. 이 값은 나중에 등록을 해지할 때 사용됩니다.  
  
 *count*  
 등록할 개체의 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고 그렇지 않으면 작업에 실패한 이유를 나타내는 CO_E_OBJISREG와 같은 HRESULT 오류가 발생합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [Module 클래스](../windows/module-class.md)