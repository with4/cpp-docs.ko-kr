---
title: 'Module:: registerobjects 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterObjects
dev_langs:
- C++
helpviewer_keywords:
- RegisterObjects method
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bdaa1b23bbefb64071e5f1f330c8708f9f9516ad
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605268"
---
# <a name="moduleregisterobjects-method"></a>Module::RegisterObjects 메서드
다른 응용 프로그램에 연결할 수 있도록 COM 또는 Windows 런타임 개체를 등록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RegisterObjects(  
   ModuleBase* module,   
   const wchar_t* serverName);  
```  
  
### <a name="parameters"></a>매개 변수  
 *모듈*  
 COM 또는 Windows 런타임 개체의 배열입니다.  
  
 *서버 이름*  
 개체를 생성한 서버의 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 시 S_OK이고, 그렇지 않으면 작업이 실패한 이유를 나타내는 HRESULT입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
## <a name="see-also"></a>참고 항목
[Module 클래스](../windows/module-class.md)