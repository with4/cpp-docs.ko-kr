---
title: 'Module:: getclassobject 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetClassObject
dev_langs:
- C++
helpviewer_keywords:
- GetClassObject method
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 63ff6c63702cda709f4431d9c7e5be5a4bdb8449
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602655"
---
# <a name="modulegetclassobject-method"></a>Module::GetClassObject 메서드
클래스 팩터리의 캐시를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
 HRESULT GetClassObject(  
   REFCLSID clsid,  
   REFIID riid,  
   _Deref_out_ void **ppv,  
   wchar_t* serverName = nullptr  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *clsid*  
 클래스 ID입니다.  
  
 *riid*  
 요청하는 인터페이스 ID입니다.  
  
 *ppv*  
 반환된 개체에 대한 포인터입니다.  
  
 *서버 이름*  
 에 지정 된 서버 이름을 합니다 `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`, 또는 `ActivatableClass` 매크로 또는 **nullptr** 기본 서버 이름을 가져올 수 합니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 Windows 런타임이 아닌 COM에만이 메서드를 사용 합니다. 이 메서드는만 노출 `IClassFactory` 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [Module 클래스](../windows/module-class.md)