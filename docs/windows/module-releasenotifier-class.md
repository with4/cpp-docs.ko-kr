---
title: 'Module:: releasenotifier 클래스 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- ReleaseNotifier class
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1deeb3076d3f1bfc2243ec333f258f543a37fceb
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608393"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier 클래스
모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class ReleaseNotifier;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Module::ReleaseNotifier::~ReleaseNotifier 소멸자](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|현재 인스턴스 초기화를 해제 합니다 **module:: releasenotifier** 클래스입니다.|  
|[Module::ReleaseNotifier::ReleaseNotifier 생성자](../windows/module-releasenotifier-releasenotifier-constructor.md)|새 인스턴스를 초기화 합니다 **module:: releasenotifier** 클래스입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Module::ReleaseNotifier::Invoke 메서드](../windows/module-releasenotifier-invoke-method.md)|구현될 때 모듈의 마지막 개체가 해제되면 이벤트 처리기를 호출합니다.|  
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|현재 삭제 **module:: releasenotifier** 개체의 매개 변수를 사용 하 여 생성 된 경우 개체 **true**합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ReleaseNotifier`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [Module 클래스](../windows/module-class.md)