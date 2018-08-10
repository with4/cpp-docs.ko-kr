---
title: 'Module:: registercomobject 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- RegisterCOMObject method
ms.assetid: 59f223dc-03c6-429d-95da-b74b3f73b702
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 61ebc6b7bfb0571ba1f2ce1957d916ecb4c790c7
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010986"
---
# <a name="moduleregistercomobject-method"></a>Module::RegisterCOMObject 메서드
다른 응용 프로그램이 COM 개체에 연결할 수 있도록 이 개체를 하나 이상 등록합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
WRL_NOTHROW virtual HRESULT RegisterCOMObject(  
   const wchar_t* serverName,  
   IID* clsids,  
   IClassFactory** factories,  
   DWORD* cookies,  
   unsigned int count);  
  
```  
  
### <a name="parameters"></a>매개 변수  
 *서버 이름*  
 서버의 정규화된 이름입니다.  
  
 *clsid*  
 등록할 CLSID의 배열입니다.  
  
 *팩터리*  
 가용성을 게시하고 있는 클래스 개체의 IUnknown 인터페이스 배열입니다.  
  
 *쿠키*  
 작업이 완료되면 등록된 클래스 개체를 식별하는 값에 대한 포인터 배열입니다. 이러한 값은 나중에 등록을 해지하는 데 사용됩니다.  
  
 *count*  
 등록할 CLSID 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공할 경우 S_OK이고, 그렇지 않으면 작업에 실패한 이유를 나타내는 CO_E_OBJISREG와 같은 HRESULT가 발생합니다.  
  
## <a name="remarks"></a>설명  
 COM 개체는 CLSCTX 열거형의 CLSCTX_LOCAL_SERVER 열거자를 사용하여 등록됩니다.  
  
 현재는 결합 하 여 등록된 된 개체에는 연결 유형을 지정 *comflag* 템플릿 매개 변수 및 REGCLS 열거형의 열거자입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [Module 클래스](../windows/module-class.md)