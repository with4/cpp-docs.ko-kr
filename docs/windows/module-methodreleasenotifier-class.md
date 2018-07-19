---
title: 'Module:: methodreleasenotifier 클래스 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier class
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 217e58f73130922d45f0d303e1e91858e8c2272f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880829"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier 클래스
현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다. 이벤트 처리기는 멤버의 포인터-에-a-메서드 멤버 및 개체에서 지정 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename T>  
class MethodReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 멤버 함수가 이벤트 처리기 개체의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::MethodReleaseNotifier 생성자](../windows/module-methodreleasenotifier-methodreleasenotifier-constructor.md)|Module:: methodreleasenotifier 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::Invoke 메서드](../windows/module-methodreleasenotifier-invoke-method.md)|현재 module:: methodreleasenotifier 개체와 연결 된 이벤트 처리기를 호출 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::method_ 데이터 멤버](../windows/module-methodreleasenotifier-method-data-member.md)|현재 Module::MethodReleaseNotifier 개체의 이벤트 처리기에 대한 포인터를 보유합니다.|  
|[Module::MethodReleaseNotifier::object_ 데이터 멤버](../windows/module-methodreleasenotifier-object-data-member.md)|멤버 함수가 현재 Module::MethodReleaseNotifier 개체의 이벤트 처리기인 개체에 대한 포인터를 보유합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ReleaseNotifier`  
  
 `MethodReleaseNotifier`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [Module 클래스](../windows/module-class.md)