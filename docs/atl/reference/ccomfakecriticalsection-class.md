---
title: "CComFakeCriticalSection 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 2c1269288e03a8ac9f359dad9acf1a81ddbc84c2
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="ccomfakecriticalsection-class"></a>CComFakeCriticalSection 클래스
이 클래스와 같은 방법으로 제공 [클래스](../../atl/reference/ccomcriticalsection-class.md) 하지만 임계 영역을 제공 하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComFakeCriticalSection
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComFakeCriticalSection::Init](#init)|없는 임계 영역 이므로 일어나지 않습니다.|  
|[CComFakeCriticalSection::Lock](#lock)|없는 임계 영역 이므로 일어나지 않습니다.|  
|[CComFakeCriticalSection::Term](#term)|없는 임계 영역 이므로 일어나지 않습니다.|  
|[CComFakeCriticalSection::Unlock](#unlock)|없는 임계 영역 이므로 일어나지 않습니다.|  
  
## <a name="remarks"></a>주의  
 `CComFakeCriticalSection`메서드를에 반영 [클래스](../../atl/reference/ccomcriticalsection-class.md)합니다. 그러나 `CComFakeCriticalSection` 임계;에서는 이므로 해당 메서드는 아무것도 수행 합니다.  
  
 일반적으로 사용 `CComFakeCriticalSection` 통해는 `typedef` 이름, 하거나 `AutoCriticalSection` 또는 `CriticalSection`합니다. 사용 하는 경우 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 또는 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), 두 가지 모두 `typedef` 이름이 참조 `CComFakeCriticalSection`합니다. 사용 하는 경우 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), 참조 [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) 및 `CComCriticalSection`각각.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcore.h  
  
##  <a name="init"></a>CComFakeCriticalSection::Init  
 없는 임계 영역 이므로 일어나지 않습니다.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>반환 값  
 S_OK 반환 합니다.  
  
##  <a name="lock"></a>CComFakeCriticalSection::Lock  
 없는 임계 영역 이므로 일어나지 않습니다.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>반환 값  
 S_OK 반환 합니다.  
  
##  <a name="term"></a>CComFakeCriticalSection::Term  
 없는 임계 영역 이므로 일어나지 않습니다.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>반환 값  
 S_OK 반환 합니다.  
  
##  <a name="unlock"></a>CComFakeCriticalSection::Unlock  
 없는 임계 영역 이므로 일어나지 않습니다.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>반환 값  
 S_OK 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

