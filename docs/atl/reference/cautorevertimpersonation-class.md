---
title: "CAutoRevertImpersonation 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
dev_langs:
- C++
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b1982fc3c8b0d46dfd636cab63be82509fa07f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation 클래스
이 클래스 되돌립니다 [CAccessToken](../../atl/reference/caccesstoken-class.md) 범위를 벗어나면 nonimpersonating 상태로 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```
class CAutoRevertImpersonation
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|생성 된 `CAutoRevertImpersonation` 개체|  
|[CAutoRevertImpersonation:: ~ CAutoRevertImpersonation](#dtor)|개체를 제거 하 고 액세스 토큰 가장을 되돌립니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAutoRevertImpersonation::Attach](#attach)|액세스 토큰의 가장 되돌리기 작업을 자동화 합니다.|  
|[CAutoRevertImpersonation::Detach](#detach)|자동 가장 버전을 취소합니다.|  
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|이 개체와 연결 된 액세스 토큰 현재를 검색 합니다.|  
  
## <a name="remarks"></a>설명  
 [액세스 토큰](http://msdn.microsoft.com/library/windows/desktop/aa374909) 프로세스 또는 스레드의 보안 컨텍스트를 설명 하 고 Windows NT 또는 Windows 2000 시스템에 로그온 한 각 사용자에 게 할당 하는 개체입니다. 이러한 액세스 토큰으로 나타낼 수 있습니다는 `CAccessToken` 클래스입니다.  
  
 액세스 토큰을 가장 하는 경우가 가끔 있습니다. 이 클래스는 편의 위해 제공 되지만 액세스 토큰;의 가장을 수행 하지 않습니다. 또한 자동 조항이 nonimpersonated 상태로 수행합니다. 즉, 토큰 액세스 가장 다양 한 방법으로 수행할 수 있습니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows sdk에서입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="attach"></a>CAutoRevertImpersonation::Attach  
 액세스 토큰의 가장 되돌리기 작업을 자동화 합니다.  
  
```
void Attach(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pAT`  
 주소는 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체를 자동으로 되돌릴 수  
  
### <a name="remarks"></a>설명  
 경우에이 메서드를 사용 해야는 [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) null 개체가 만들어진 `CAccessToken` 포인터 또는 [분리](#detach) 이전에 호출 되었습니다. 단순한 경우에 대 한이 메서드를 사용 하는 데 필요한있지 않습니다.  
  
##  <a name="cautorevertimpersonation"></a>CAutoRevertImpersonation::CAutoRevertImpersonation  
 `CAutoRevertImpersonation` 개체를 생성합니다.  
  
```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pAT`  
 주소는 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체를 자동으로 되돌릴 수 있습니다.  
  
### <a name="remarks"></a>설명  
 액세스 토큰의 실제 가장 수행 해야 별도로 및 가급적 만들기 전에 `CAutoRevertImpersonation` 개체입니다. 이 가장 때를 자동으로 되돌릴 수는 `CAutoRevertImpersonation` 범위를 벗어나면 합니다.  
  
##  <a name="dtor"></a>CAutoRevertImpersonation:: ~ CAutoRevertImpersonation  
 개체를 제거 하 고 액세스 토큰 가장을 되돌립니다.  
  
```
~CAutoRevertImpersonation() throw();
```  
  
### <a name="remarks"></a>설명  
 에 적용 된 모든 가장 현재 되돌립니다는 [CAccessToken](../../atl/reference/caccesstoken-class.md) 통해 또는 생성 시 제공 된 개체는 [연결](#attach) 메서드. 하지 않으면 `CAccessToken` 는 연결, 소멸자에 영향을 주지 않습니다.  
  
##  <a name="detach"></a>CAutoRevertImpersonation::Detach  
 자동 가장 버전을 취소합니다.  
  
```
const CAccessToken* Detach() throw();
```  
  
### <a name="return-value"></a>반환 값  
 이전에 연관 된 주소 [CAccessToken](../../atl/reference/caccesstoken-class.md), 또는 다른 설명이 없는 존재 하는 경우 NULL입니다.  
  
### <a name="remarks"></a>설명  
 호출 **분리** 방지는 `CAutoRevertImpersonation` 개체에 적용 된 모든 가장 현재으로 되돌릴는 [CAccessToken](../../atl/reference/caccesstoken-class.md) 이 개체와 연결 된 개체입니다. `CAutoRevertImpersonation`영향을 주지 파괴 하거나를 동일한 문서나 다른 클라우드에 다시 연결할 수 `CAccessToken` 개체 사용 하 여 [연결](#attach)합니다.  
  
##  <a name="getaccesstoken"></a>CAutoRevertImpersonation::GetAccessToken  
 이 개체와 연결 된 액세스 토큰 현재를 검색 합니다.  
  
```
const CAccessToken* GetAccessToken() throw();
```  
  
### <a name="return-value"></a>반환 값  
 이전에 연관 된 주소 [CAccessToken](../../atl/reference/caccesstoken-class.md), 또는 다른 설명이 없는 존재 하는 경우 NULL입니다.  
  
### <a name="remarks"></a>설명  
 가장의 버전을 포함 하는 목적에 대 한이 메서드를 호출 하면는 `CAccessToken` 개체는 [분리](#detach) 메서드를 대신 사용 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATLSecurity 샘플](../../visual-cpp-samples.md)   
 [액세스 토큰](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [클래스 개요](../../atl/atl-class-overview.md)
