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
ms.openlocfilehash: c0d49a6f0b5172b0971f755fc61b7767f0f4427d
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603305"
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
  
### <a name="parameters"></a>매개 변수  
 *T*  
 모듈 유형입니다.  
  
 *콜백*  
 모듈의 마지막 인스턴스 개체가 해제 될 때 호출 됩니다.  
  
 *object*  
 합니다 *개체* 하 고 *메서드* 조합 하 여 매개 변수를 사용 합니다. 요소 마지막 인스턴스 개체 모듈의 마지막 인스턴스 개체가 해제 될 때입니다.  
  
 *method*  
 합니다 *개체* 하 고 *메서드* 조합 하 여 매개 변수를 사용 합니다. 모듈의 마지막 인스턴스 개체가 해제 될 때 마지막 인스턴스 개체의 메서드를 가리킵니다.  
  
## <a name="return-value"></a>반환 값  
 모듈에 대 한 참조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
[Module 클래스](../windows/module-class.md)