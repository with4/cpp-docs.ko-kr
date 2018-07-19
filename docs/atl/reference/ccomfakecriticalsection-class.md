---
title: CComFakeCriticalSection 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a042e52439579cfb1b4145b1691f5a00128754c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358617"
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
|[CComFakeCriticalSection::Init](#init)|가 nothing 되기 때문에 중요 한 섹션이 없습니다.|  
|[CComFakeCriticalSection::Lock](#lock)|가 nothing 되기 때문에 중요 한 섹션이 없습니다.|  
|[CComFakeCriticalSection::Term](#term)|가 nothing 되기 때문에 중요 한 섹션이 없습니다.|  
|[CComFakeCriticalSection::Unlock](#unlock)|가 nothing 되기 때문에 중요 한 섹션이 없습니다.|  
  
## <a name="remarks"></a>설명  
 `CComFakeCriticalSection` 메서드를에 반영 [클래스](../../atl/reference/ccomcriticalsection-class.md)합니다. 그러나 `CComFakeCriticalSection` 임계 영역; 제공 하지 않습니다, 따라서 해당 메서드는 아무것도 수행 합니다.  
  
 일반적으로 사용 `CComFakeCriticalSection` 통해는 `typedef` 이름을 하거나 `AutoCriticalSection` 또는 `CriticalSection`합니다. 사용 하는 경우 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 또는 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), 둘 다에 해당 `typedef` 이름이 참조 `CComFakeCriticalSection`합니다. 사용 하는 경우 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), 참조 [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) 및 `CComCriticalSection`각각.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcore.h  
  
##  <a name="init"></a>  CComFakeCriticalSection::Init  
 가 nothing 되기 때문에 중요 한 섹션이 없습니다.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>반환 값  
 S_OK 반환 합니다.  
  
##  <a name="lock"></a>  CComFakeCriticalSection::Lock  
 가 nothing 되기 때문에 중요 한 섹션이 없습니다.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>반환 값  
 S_OK 반환 합니다.  
  
##  <a name="term"></a>  CComFakeCriticalSection::Term  
 가 nothing 되기 때문에 중요 한 섹션이 없습니다.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>반환 값  
 S_OK 반환 합니다.  
  
##  <a name="unlock"></a>  CComFakeCriticalSection::Unlock  
 가 nothing 되기 때문에 중요 한 섹션이 없습니다.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>반환 값  
 S_OK 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
