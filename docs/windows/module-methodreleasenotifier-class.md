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
ms.openlocfilehash: 4009be162423d9fe558dba04d7e88a7f539c4eaa
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602989"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier 클래스
현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다. 이벤트 처리기 개체와 해당 포인터를-a-메서드 멤버 지정 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename T>  
class MethodReleaseNotifier : public ReleaseNotifier;  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 멤버 함수가 이벤트 처리기 개체의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::MethodReleaseNotifier 생성자](../windows/module-methodreleasenotifier-methodreleasenotifier-constructor.md)|새 인스턴스를 초기화 합니다 **module:: methodreleasenotifier** 클래스입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::Invoke 메서드](../windows/module-methodreleasenotifier-invoke-method.md)|현재 연결 된 이벤트 처리기를 호출 **module:: methodreleasenotifier** 개체입니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::method_ 데이터 멤버](../windows/module-methodreleasenotifier-method-data-member.md)|현재 이벤트 처리기에 대 한 포인터를 보유 **module:: methodreleasenotifier** 개체입니다.|  
|[Module::MethodReleaseNotifier::object_ 데이터 멤버](../windows/module-methodreleasenotifier-object-data-member.md)|멤버 함수가 이벤트 처리기를 현재 개체에 대 한 포인터를 보유 **module:: methodreleasenotifier** 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ReleaseNotifier`  
  
 `MethodReleaseNotifier`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [Module 클래스](../windows/module-class.md)