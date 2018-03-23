---
title: 'Module:: create 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Create
dev_langs:
- C++
helpviewer_keywords:
- Create method
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e566b34140c0b82072c8469cd8d965f807e244ec
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="modulecreate-method"></a>Module::Create 메서드
모듈의 인스턴스를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW static Module& Create();  
template<typename T>  
WRL_NOTHROW static Module& Create(  
   T callback  
);  
template<typename T>  
WRL_NOTHROW static Module& Create(  
   _In_ T* object,  
   _In_ void (T::* method)()  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 모듈 유형입니다.  
  
 `callback`  
 모듈의 마지막 인스턴스 개체가 해제 될 때 호출 됩니다.  
  
 `object`  
 `object` 및 `method` 조합 하 여 매개 변수가 사용 됩니다. 요소 마지막 인스턴스 개체는 모듈의 마지막 인스턴스 개체가 해제 될 때입니다.  
  
 `method`  
 `object` 및 `method` 조합 하 여 매개 변수가 사용 됩니다. 모듈의 마지막 인스턴스 개체가 해제 될 때 마지막 인스턴스 개체의 메서드를 가리킵니다.  
  
## <a name="return-value"></a>반환 값  
 모듈에 대 한 참조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
[Module 클래스](../windows/module-class.md)

 