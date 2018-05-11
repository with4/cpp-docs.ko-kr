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
ms.openlocfilehash: 097bf70ebd280d9494ff70ea1d80f53615f3d898
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="moduleregisterwinrtobject-method"></a>Module::RegisterWinRTObject 메서드
다른 응용 프로그램에 연결할 수 있도록 하나 이상의 Windows 런타임 개체를 등록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RegisterWinRTObject(const wchar_t* serverName,  
   wchar_t** activatableClassIds,  
   WINRT_REGISTRATION_COOKIE* cookie,  
   unsigned int count)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `serverName`  
 이 작업으로 영향을 받는 개체의 하위 집합을 지정하는 이름입니다.  
  
 `activatableClassIds`  
 등록할 활성화 가능한 CLSID 배열입니다.  
  
 `cookie`  
 등록된 클래스 개체를 식별하는 값입니다. 이 값은 나중에 등록을 해지할 때 사용됩니다.  
  
 `count`  
 등록할 개체의 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고 그렇지 않으면 작업에 실패한 이유를 나타내는 CO_E_OBJISREG와 같은 HRESULT 오류가 발생합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [Module 클래스](../windows/module-class.md)