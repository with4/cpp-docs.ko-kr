---
title: CComAutoCriticalSection 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae0c3cd1d00ce83a4e952d60a978663bfa76f814
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357231"
---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection 클래스
`CComAutoCriticalSection` 가져오기을 임계 영역 개체의 소유권을 해제 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComAutoCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|생성자입니다.|  
|[CComAutoCriticalSection:: ~ CComAutoCriticalSection](#dtor)|소멸자입니다.|  
  
## <a name="remarks"></a>설명  
 `CComAutoCriticalSection` 클래스와 유사한 [클래스](../../atl/reference/ccomcriticalsection-class.md)를 제외 하 고 `CComAutoCriticalSection` 자동 생성자에서 임계 영역 개체를 초기화 합니다.  
  
 일반적으로 사용 `CComAutoCriticalSection` 통해는 `typedef` 이름 [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection)합니다. 이 이름은 참조 `CComAutoCriticalSection` 때 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 사용 중입니다.  

  
 `Init` 및 `Term` 메서드에서 [클래스](../../atl/reference/ccomcriticalsection-class.md) 이 클래스를 사용 하는 경우 사용할 수 없는 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComAutoCriticalSection`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcore.h  
  
##  <a name="ccomautocriticalsection"></a>  CComAutoCriticalSection::CComAutoCriticalSection  
 생성자입니다.  
  
```
CComAutoCriticalSection();
```  
  
### <a name="remarks"></a>설명  
 Win32 함수를 호출 [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472)는 임계 영역 개체를 초기화 합니다.  
  
##  <a name="dtor"></a>  CComAutoCriticalSection:: ~ CComAutoCriticalSection  
 소멸자입니다.  
  
```
~CComAutoCriticalSection() throw();
```  
  
### <a name="remarks"></a>설명  
 소멸자 호출 [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), 임계 영역 개체에서 사용 하는 모든 시스템 리소스를 해제 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComFakeCriticalSection 클래스](../../atl/reference/ccomfakecriticalsection-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [CComCriticalSection 클래스](../../atl/reference/ccomcriticalsection-class.md)
