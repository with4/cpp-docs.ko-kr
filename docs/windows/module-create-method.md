---
title: 'Module:: create 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Create
dev_langs:
- C++
helpviewer_keywords:
- Create method
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99ede64c239909956f1f767db34a2a6a14c02314
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874891"
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

 