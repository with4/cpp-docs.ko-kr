---
title: "Module:: genericreleasenotifier 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier class
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c87205d1d52c8273ac7eea55fcc5385810349f1f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier 클래스
현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다. 이벤트 처리기는 람다, 함수 또는 함수 포인터에 의해 지정됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<  
   typename T  
>  
class GenericReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 이벤트 처리기의 위치를 포함하는 데이터 멤버 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::GenericReleaseNotifier 생성자](../windows/module-genericreleasenotifier-genericreleasenotifier-constructor.md)|Module::GenericReleaseNotifier 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::Invoke 메서드](../windows/module-genericreleasenotifier-invoke-method.md)|현재 Module::GenericReleaseNotifier 개체에 연결된 이벤트 처리기를 호출합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::callback_ 데이터 멤버](../windows/module-genericreleasenotifier-callback-data-member.md)|현재 Module::GenericReleaseNotifier 개체에 연결된 람다, 함수 또는 함수 포인터 이벤트 처리기를 보유합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ReleaseNotifier`  
  
 `GenericReleaseNotifier`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [Module 클래스](../windows/module-class.md)