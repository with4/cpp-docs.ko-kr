---
title: "CAutoRevertImpersonation 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 22
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: f86f1e5067583b3c4c615c8ca3095e8b67b3fffe
ms.lasthandoff: 02/24/2017

---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation 클래스
이 클래스는 되돌려집니다 [CAccessToken](../../atl/reference/caccesstoken-class.md) nonimpersonating 상태로 범위를 벗어나면 개체입니다.  
  
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
|[CAutoRevertImpersonation::Attach](#attach)|자동화는 가장 액세스 토큰의 버전을 변경 합니다.|  
|[CAutoRevertImpersonation::Detach](#detach)|자동 가장 되돌리기를 취소합니다.|  
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|이 개체와 연결 된 액세스 토큰 현재를 검색 합니다.|  
  
## <a name="remarks"></a>주의  
 [액세스 토큰](http://msdn.microsoft.com/library/windows/desktop/aa374909) 는 프로세스 또는 스레드의 보안 컨텍스트를 설명 하 고 Windows NT 또는 Windows 2000 시스템에 로그온 한 각 사용자에 게 할당 하는 개체입니다. 이러한 액세스 토큰으로 나타낼 수는 `CAccessToken` 클래스입니다.  
  
 액세스 토큰을 가장 하는 경우가 있습니다. 이 클래스는 편의 위해 제공 되지만 액세스 토큰의 가장을 수행 하지 않습니다. 또한 nonimpersonated 상태로 자동 버전을 변경만 수행합니다. 즉, 가장 토큰 액세스는 여러 가지 방법으로 수행할 수 있습니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="attach"></a>CAutoRevertImpersonation::Attach  
 자동화는 가장 액세스 토큰의 버전을 변경 합니다.  
  
```
void Attach(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pAT`  
 주소는 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체를 자동으로 되돌릴 수  
  
### <a name="remarks"></a>주의  
 경우에이 메서드를 사용 해야는 [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) null 개체를 만든 `CAccessToken` 포인터 경우 [분리](#detach) 이미 호출 되었습니다. 간단한 경우에이 메서드를 사용 하는 데 필요한있지 않습니다.  
  
##  <a name="cautorevertimpersonation"></a>CAutoRevertImpersonation::CAutoRevertImpersonation  
 `CAutoRevertImpersonation` 개체를 생성합니다.  
  
```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pAT`  
 주소는 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체를 자동으로 되돌릴 수 있습니다.  
  
### <a name="remarks"></a>주의  
 액세스 토큰의 실제 가장 별도로 수행 해야 및 가급적 이면 작성 하기 전에 `CAutoRevertImpersonation` 개체입니다. 이 가장이 자동으로 되돌려집니다 때는 `CAutoRevertImpersonation` 개체가 범위를 벗어난 있습니다.  
  
##  <a name="dtor"></a>CAutoRevertImpersonation:: ~ CAutoRevertImpersonation  
 개체를 제거 하 고 액세스 토큰 가장을 되돌립니다.  
  
```
~CAutoRevertImpersonation() throw();
```  
  
### <a name="remarks"></a>주의  
 에 적용 된 모든 가장 현재 되돌립니다는 [CAccessToken](../../atl/reference/caccesstoken-class.md) 통해 또는 생성 시 제공 된 개체는 [연결](#attach) 메서드. 없으면 `CAccessToken` 은 연결 된 소멸자가 영향을 주지 않습니다.  
  
##  <a name="detach"></a>CAutoRevertImpersonation::Detach  
 자동 가장 되돌리기를 취소합니다.  
  
```
const CAccessToken* Detach() throw();
```  
  
### <a name="return-value"></a>반환 값  
 이전에 연결 된 주소 [CAccessToken](../../atl/reference/caccesstoken-class.md), 또는 다른 설명이 없는 경우 NULL입니다.  
  
### <a name="remarks"></a>주의  
 호출 **분리** 방지는 `CAutoRevertImpersonation` 개체에 적용 된 모든 가장 현재으로 되돌릴는 [CAccessToken](../../atl/reference/caccesstoken-class.md) 이 개체와 연결 된 개체입니다. `CAutoRevertImpersonation`그런 다음 영향을 주지 소멸 하거나 같은 또는 다른에 다시 연결 될 `CAccessToken` 개체를 사용 하 여 [연결](#attach)합니다.  
  
##  <a name="getaccesstoken"></a>CAutoRevertImpersonation::GetAccessToken  
 이 개체와 연결 된 액세스 토큰 현재를 검색 합니다.  
  
```
const CAccessToken* GetAccessToken() throw();
```  
  
### <a name="return-value"></a>반환 값  
 이전에 연결 된 주소 [CAccessToken](../../atl/reference/caccesstoken-class.md), 또는 다른 설명이 없는 경우 NULL입니다.  
  
### <a name="remarks"></a>주의  
 가장의 버전을 포함 하는 목적으로이 메서드를 호출 하는 경우는 `CAccessToken` 개체는 [분리](#detach) 메서드를 대신 사용 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATLSecurity 샘플](../../visual-cpp-samples.md)   
 [액세스 토큰](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [클래스 개요](../../atl/atl-class-overview.md)

