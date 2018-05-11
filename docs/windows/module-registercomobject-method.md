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
ms.openlocfilehash: c002dd64049006c8ee74c709c585a3a9d0f253a5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="moduleregistercomobject-method"></a>Module::RegisterCOMObject 메서드
다른 응용 프로그램이 COM 개체에 연결할 수 있도록 이 개체를 하나 이상 등록합니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW virtual HRESULT RegisterCOMObject(  
   const wchar_t* serverName,  
   IID* clsids,  
   IClassFactory** factories,  
   DWORD* cookies,  
   unsigned int count);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `serverName`  
 서버의 정규화된 이름입니다.  
  
 `clsids`  
 등록할 CLSID의 배열입니다.  
  
 `factories`  
 가용성을 게시하고 있는 클래스 개체의 IUnknown 인터페이스 배열입니다.  
  
 `cookies`  
 작업이 완료되면 등록된 클래스 개체를 식별하는 값에 대한 포인터 배열입니다. 이러한 값은 나중에 등록을 해지하는 데 사용됩니다.  
  
 `count`  
 등록할 CLSID 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공할 경우 S_OK이고, 그렇지 않으면 작업에 실패한 이유를 나타내는 CO_E_OBJISREG와 같은 HRESULT가 발생합니다.  
  
## <a name="remarks"></a>설명  
 COM 개체는 CLSCTX 열거형의 CLSCTX_LOCAL_SERVER 열거자를 사용하여 등록됩니다.  
  
 등록된 개체에 대한 연결 유형은 현재 `comflag` 템플릿 매개 변수 및 REGCLS 열거형의 REGCLS_SUSPENDED 열거자의 조합으로 지정됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [Module 클래스](../windows/module-class.md)