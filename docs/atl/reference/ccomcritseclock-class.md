---
title: "CComCritSecLock 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
dev_langs: C++
helpviewer_keywords: CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3fb2bad67c6488f13297783a578118ebc022c4bd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomcritseclock-class"></a>CComCritSecLock 클래스
이 클래스는 잠금 및 임계 영역 개체 잠금 해제에 대 한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class TLock> class CComCritSecLock
```  
  
#### <a name="parameters"></a>매개 변수  
 *TLock*  
 개체 잠금 또는 잠금 해제 수입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComCritSecLock::CComCritSecLock](#ctor)|생성자입니다.|  
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComCritSecLock::Lock](#lock)|임계 영역 개체를 잠그려고이 메서드를 호출 합니다.|  
|[CComCritSecLock::Unlock](#unlock)|임계 영역 개체의 잠금을 해제 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스를 사용 하 여 잠금와 보다 더 안전한 방식으로 개체를 해제 하는 [클래스 클래스](../../atl/reference/ccomcriticalsection-class.md) 또는 [CComAutoCriticalSection 클래스](../../atl/reference/ccomautocriticalsection-class.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="ctor"></a>CComCritSecLock::CComCritSecLock  
 생성자입니다.  
  
```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```  
  
### <a name="parameters"></a>매개 변수  
 *cs*  
 임계 영역 개체입니다.  
  
 `bInitialLock`  
 초기 잠금 상태: **true** 잠겨 의미 합니다.  
  
### <a name="remarks"></a>설명  
 임계 영역 개체를 초기화합니다.  
  
##  <a name="dtor"></a>CComCritSecLock:: ~ CComCritSecLock  
 소멸자입니다.  
  
```
~CComCritSecLock() throw();
```  
  
### <a name="remarks"></a>설명  
 임계 영역 개체의 잠금을 해제합니다.  
  
##  <a name="lock"></a>CComCritSecLock::Lock  
 임계 영역 개체를 잠그려고이 메서드를 호출 합니다.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>반환 값  
 실패 시 오류 HRESULT 또는 개체를 성공적으로 잠근 경우 S_OK 반환 합니다.  
  
### <a name="remarks"></a>설명  
 개체를 이미 잠근 경우 디버그 빌드에 어설션 오류가 발생 합니다.  
  
##  <a name="unlock"></a>CComCritSecLock::Unlock  
 임계 영역 개체의 잠금을 해제 하려면이 메서드를 호출 합니다.  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>설명  
 개체가 이미 잠긴 없는 경우 디버그 빌드에 어설션 오류가 발생 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 클래스](../../atl/reference/ccomcriticalsection-class.md)   
 [CComAutoCriticalSection 클래스](../../atl/reference/ccomautocriticalsection-class.md)
