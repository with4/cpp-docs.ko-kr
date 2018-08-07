---
title: Module::GenericReleaseNotifier::GenericReleaseNotifier 생성자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier, constructor
ms.assetid: feb5b687-a4b0-4809-9022-8f292181b7a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb07c7f53e27e380ba5775369611299cad0f60d4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875060"
---
# <a name="modulegenericreleasenotifiergenericreleasenotifier-constructor"></a>Module::GenericReleaseNotifier::GenericReleaseNotifier 생성자
Module::GenericReleaseNotifier 클래스의 새 인스턴스를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      GenericReleaseNotifier(  
   T callback,   
   bool release  
) throw() : ReleaseNotifier(release), callback_(callback);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `callback`  
 람다, 함수 또는 함수 포인터 이벤트 처리기 함수 괄호 연산자와 함께 호출할 수 있는 (`()`).  
  
 `release`  
 지정 `true` 내부 호출을 사용 하도록 설정 하려면 [모듈:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) 메서드도 있습니다; 그렇지 않으면 지정 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Module::GenericReleaseNotifier 클래스](../windows/module-genericreleasenotifier-class.md)