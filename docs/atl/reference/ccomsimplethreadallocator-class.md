---
title: "CComSimpleThreadAllocator 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 244443692478d0391c2079e55995c1fef1e1655e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
  
## <a name="remarks"></a>설명  
 `CComSimpleThreadAllocator`에 대 한 스레드 선택을 관리 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)합니다. `CComSimpleThreadAllocator::GetThread`단순히 각 스레드를 순환 하 고 시퀀스의 다음 하나를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="getthread"></a>CComSimpleThreadAllocator::GetThread  
 시퀀스에 있는 다음 스레드를 지정 하 여 스레드를 선택 합니다.  
  
```
int GetThread(CComApartment* /* pApt */, int nThreads);
```  
  
### <a name="parameters"></a>매개 변수  
 `pApt`  
 ATL의 기본 구현에서 사용 되지 않습니다.  
  
 `nThreads`  
 EXE 모듈에 있는 스레드의 최대 수입니다.  
  
### <a name="return-value"></a>반환 값  
 0 사이의 정수 및 ( `nThreads` -1). EXE 모듈에서 스레드 중 하나를 식별합니다.  
  
### <a name="remarks"></a>설명  
 재정의할 수 있습니다 `GetThread` 선택의 다른 메서드를 제공 하거나 변경 하려면의 사용은 `pApt` 매개 변수입니다.  
  
 `GetThread`호출한 [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComApartment 클래스](../../atl/reference/ccomapartment-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
