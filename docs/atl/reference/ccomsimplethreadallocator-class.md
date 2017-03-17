---
title: "CComSimpleThreadAllocator 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 377e7f2fa6d8377d46e98b52e9c8f075b10956a8
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsimplethreadallocator-class"></a>CComSimpleThreadAllocator 클래스
이 클래스는 클래스에 대 한 스레드 선택을 관리 `CComAutoThreadModule`합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComSimpleThreadAllocator
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComSimpleThreadAllocator::GetThread](#getthread)|스레드를 선택 합니다.|  
  
## <a name="remarks"></a>주의  
 `CComSimpleThreadAllocator`에 대 한 스레드 선택을 관리 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)합니다. `CComSimpleThreadAllocator::GetThread`단순히 각 스레드를 순환 하 고 끝점으로 시퀀스를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="getthread"></a>CComSimpleThreadAllocator::GetThread  
 시퀀스의 다음 스레드를 지정 하 여 스레드를 선택 합니다.  
  
```
int GetThread(CComApartment* /* pApt */, int nThreads);
```  
  
### <a name="parameters"></a>매개 변수  
 `pApt`  
 ATL의 기본 구현에서 사용 되지 않습니다.  
  
 `nThreads`  
 EXE 모듈에서 스레드의 최대 수입니다.  
  
### <a name="return-value"></a>반환 값  
 0 사이의 정수 및 ( `nThreads` – 1). EXE 모듈에서 스레드 중 하나를 식별합니다.  
  
### <a name="remarks"></a>주의  
 재정의할 수 있습니다 `GetThread` 선택의 다른 메서드를 제공 하거나 변경 하려면 사용 된 `pApt` 매개 변수입니다.  
  
 `GetThread`에 의해 호출 됩니다 [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComApartment 클래스](../../atl/reference/ccomapartment-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

