---
title: "CComGITPtr 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComGITPtr
- ATLBASE/ATL::CComGITPtr
- ATLBASE/ATL::CComGITPtr::CComGITPtr
- ATLBASE/ATL::CComGITPtr::Attach
- ATLBASE/ATL::CComGITPtr::CopyTo
- ATLBASE/ATL::CComGITPtr::Detach
- ATLBASE/ATL::CComGITPtr::GetCookie
- ATLBASE/ATL::CComGITPtr::Revoke
- ATLBASE/ATL::CComGITPtr::m_dwCookie
dev_langs:
- C++
helpviewer_keywords:
- CComGITPtr class
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c001d0d1ca8e756b24d97051d100e7d71723569c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomgitptr-class"></a>CComGITPtr 클래스
이 클래스는 인터페이스 포인터를 처리 하기 위한 메서드 및 전역 인터페이스 테이블 (GIT)를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
class CComGITPtr
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 GIT에 저장 될 인터페이스 포인터의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComGITPtr::CComGITPtr](#ccomgitptr)|생성자입니다.|  
|[CComGITPtr:: ~ CComGITPtr](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComGITPtr::Attach](#attach)|(GIT) 전역 인터페이스 테이블에 인터페이스 포인터를 등록 하려면이 메서드를 호출 합니다.|  
|[CComGITPtr::CopyTo](#copyto)|전달 된 포인터에 전역 인터페이스 테이블 (GIT)에서 인터페이스를 복사 하려면이 메서드를 호출 합니다.|  
|[CComGITPtr::Detach](#detach)|이 메서드는 인터페이스를 분리할를 호출 하는 `CComGITPtr` 개체입니다.|  
|[CComGITPtr::GetCookie](#getcookie)|호출에서 쿠키를 반환 하려면이 메서드는 `CComGITPtr` 개체입니다.|  
|[CComGITPtr::Revoke](#revoke)|전역 인터페이스 테이블 (GIT)에서 인터페이스를 제거 하려면이 메서드를 호출 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[DWORD CComGITPtr::operator](#operator_dword)|쿠키를 반환 된 `CComGITPtr` 개체입니다.|  
|[CComGITPtr::operator =](#operator_eq)|대입 연산자입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComGITPtr::m_dwCookie](#m_dwcookie)|쿠키입니다.|  
  
## <a name="remarks"></a>설명  
 자유 스레드된 마샬러를 집계 하 고 다른 개체에서 가져온 인터페이스 포인터를 사용 해야 하는 개체는 인터페이스 올바르게 마샬링 되므로 추가 단계를 수행 해야 합니다. 일반적으로이 사용할 때마다 GIT에서 포인터를 가져오는 및 GIT에 인터페이스 포인터를 저장 해야 합니다. 클래스 `CComGITPtr` GIT에 저장 된 인터페이스 포인터를 사용할 수 있도록 제공 됩니다.  
  
> [!NOTE]
>  전역 인터페이스 테이블 시설은 버전 1.1 dcom Windows 95 및 이상, Windows 98, Windows NT 4.0 서비스 팩 3 이상 및 Windows 2000에서 사용할 수만 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="attach"></a>CComGITPtr::Attach  
 (GIT) 전역 인터페이스 테이블에 인터페이스 포인터를 등록 하려면이 메서드를 호출 합니다.  
  
```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 GIT에 추가 될 인터페이스 포인터입니다.  
  
 `dwCookie`  
 인터페이스 포인터를 식별 하는 데 사용 되는 쿠키입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 디버그 빌드에 어설션 오류가 발생은 쿠키 NULL과 같으면 또는 GIT 유효 하지 않을 경우 발생 합니다.  
  
##  <a name="ccomgitptr"></a>CComGITPtr::CComGITPtr  
 생성자입니다.  
  
```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `p`  
 (GIT) 전역 인터페이스 테이블에 저장 되는 인터페이스 포인터입니다.  
  
 [in] `git`  
 기존에 대 한 참조 `CComGITPtr` 개체입니다.  
  
 [in] `dwCookie`  
 인터페이스 포인터를 식별 하는 데 사용 되는 쿠키입니다.  
  
 [in] `rv`  
 소스 `CComGITPtr` 개체에서 데이터를 이동 합니다.  
  
### <a name="remarks"></a>설명  
 새 `CComGITPtr` 개체, 필요에 따라 기존를 사용 하 여 `CComGITPtr` 개체입니다.  
  
 사용 하 여 생성자 `rv` 는 이동 생성자입니다. 원본에서 데이터를 이동할 `rv`, 차례로 `rv` 지워집니다.  
  
##  <a name="dtor"></a>CComGITPtr:: ~ CComGITPtr  
 소멸자입니다.  
  
```
~CComGITPtr() throw();
```  
  
### <a name="remarks"></a>설명  
 (GIT) 전역 인터페이스 테이블에서 제거 하는 인터페이스를 사용 하 여 [CComGITPtr::Revoke](#revoke)합니다.  
  
##  <a name="copyto"></a>CComGITPtr::CopyTo  
 전달 된 포인터에 전역 인터페이스 테이블 (GIT)에서 인터페이스를 복사 하려면이 메서드를 호출 합니다.  
  
```
HRESULT CopyTo(T** pp) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pp`  
 인터페이스를 수신 하는 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 GIT에서 인터페이스는 전달 된 포인터에 복사 됩니다. 포인터가 더 이상 필요한 경우 호출자에 의해 해제 되어야 합니다.  
  
##  <a name="detach"></a>CComGITPtr::Detach  
 이 메서드는 인터페이스를 분리할를 호출 하는 `CComGITPtr` 개체입니다.  
  
```
DWORD Detach() throw();
```  
  
### <a name="return-value"></a>반환 값  
 쿠키를 반환 된 `CComGITPtr` 개체입니다.  
  
### <a name="remarks"></a>설명  
 GIT에서 인터페이스를 제거 하려면 호출자에 게이 사용 하 여 [CComGITPtr::Revoke](#revoke)합니다.  
  
##  <a name="getcookie"></a>CComGITPtr::GetCookie  
 호출에서 쿠키를 반환 하려면이 메서드는 `CComGITPtr` 개체입니다.  
  
```
DWORD GetCookie() const;
```  
  
### <a name="return-value"></a>반환 값  
 쿠키를 반환합니다.  
  
### <a name="remarks"></a>설명  
 쿠키는 인터페이스와 해당 위치를 확인 하는 데 사용 하는 변수입니다.  
  
##  <a name="m_dwcookie"></a>CComGITPtr::m_dwCookie  
 쿠키입니다.  
  
```
DWORD m_dwCookie;
```  
  
### <a name="remarks"></a>설명  
 쿠키는 인터페이스와 해당 위치를 확인 하는 데 사용 하는 멤버 변수입니다.  
  
##  <a name="operator_eq"></a>CComGITPtr::operator =  
 대입 연산자입니다.  
  
```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `p`  
 인터페이스에 대 한 포인터입니다.  
  
 [in] `git`  
 `CComGITPtr` 개체에 대한 참조입니다.  
  
 [in] `dwCookie`  
 인터페이스 포인터를 식별 하는 데 사용 되는 쿠키입니다.  
  
 [in] `rv`  
 `CComGITPtr` 에서 데이터를 이동 합니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 반환 `CComGITPtr` 개체입니다.  
  
### <a name="remarks"></a>설명  
 에 새 값을 할당 한 `CComGITPtr` 전역 인터페이스 테이블에 대 한 참조 또는 기존 개체에서 개체입니다.  
  
##  <a name="operator_dword"></a>DWORD CComGITPtr::operator  
 와 연관 된 쿠키를 반환 합니다.는 `CComGITPtr` 개체입니다.  
  
```  
operator DWORD() const;
```  
  
### <a name="remarks"></a>설명  
 쿠키는 인터페이스와 해당 위치를 확인 하는 데 사용 하는 변수입니다.  
  
##  <a name="revoke"></a>CComGITPtr::Revoke  
 (GIT) 전역 인터페이스 테이블에서 현재 인터페이스를 제거 하려면이 메서드를 호출 합니다.  
  
```
HRESULT Revoke() throw();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 GIT에서 인터페이스를 제거합니다.  
  
## <a name="see-also"></a>참고 항목  
 [자유 스레드된 마샬러](../../atl/atl-and-the-free-threaded-marshaler.md)   
 [아파트 간 인터페이스 액세스](http://msdn.microsoft.com/library/windows/desktop/ms682353)   
 [전역 인터페이스 테이블을 사용 하는 경우](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [클래스 개요](../../atl/atl-class-overview.md)
