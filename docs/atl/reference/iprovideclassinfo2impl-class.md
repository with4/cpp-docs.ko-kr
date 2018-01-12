---
title: "IProvideClassInfo2Impl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
dev_langs: C++
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6fe466608acaecfaf6219b6d15d27e0611ac2511
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl 클래스
이 클래스의 기본 구현을 제공는 [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) 및 [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) 메서드.  
  
## <a name="syntax"></a>구문  
  
```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>  
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```  
  
#### <a name="parameters"></a>매개 변수  
 *pcoclsid*  
 Coclass의 식별자에 대 한 포인터입니다.  
  
 *psrcid*  
 Dispinterface 나가는 coclass' 기본에 대 한 식별자에 대 한 포인터입니다.  
  
 `plibid`  
 인터페이스에 대 한 정보를 포함 하는 형식 라이브러리의 LIBID에 대 한 포인터입니다. 서버 수준의 형식 라이브러리는 기본적으로 전달 됩니다.  
  
 `wMajor`  
 형식 라이브러리의 주 버전입니다. 기본값은 1입니다.  
  
 `wMinor`  
 형식 라이브러리의 부 버전입니다. 기본값은 0입니다.  
  
 `tihclass`  
 Coclass의 형식 정보를 관리 하는 데 사용 되는 클래스입니다. 기본값은 `CComTypeInfoHolder`입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="constructors"></a>생성자  
  
|name|설명|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|검색 한 **ITypeInfo** coclass의 형식 정보에 대 한 포인터입니다.|  
|[IProvideClassInfo2Impl::GetGUID](#getguid)|개체의 나가는 dispinterface에 대 한 GUID를 검색합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::_tih](#_tih)|Coclass에 대 한 형식 정보를 관리합니다.|  
  
## <a name="remarks"></a>설명  
 [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) 확장 [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) 추가 하 여는 `GetGUID` 메서드. 이 메서드는 클라이언트를 기본 이벤트 집합에 대 한 개체의 나가는 인터페이스 IID를 검색할 수 있습니다. 클래스 `IProvideClassInfo2Impl` 의 기본 구현을 제공는 **IProvideClassInfo** 및 `IProvideClassInfo2` 메서드.  
  
 `IProvideClassInfo2Impl`형식의 정적 멤버가 포함 된 `CComTypeInfoHolder` coclass에 대 한 형식 정보를 관리 하는 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="getclassinfo"></a>IProvideClassInfo2Impl::GetClassInfo  
 검색 한 `ITypeInfo` coclass의 형식 정보에 대 한 포인터입니다.  
  
```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>설명  
 참조 [IProvideClassInfo::GetClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms690192) in the Windows SDK입니다.  
  
##  <a name="getguid"></a>IProvideClassInfo2Impl::GetGUID  
 개체의 나가는 dispinterface에 대 한 GUID를 검색합니다.  
  
```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```  
  
### <a name="remarks"></a>설명  
 참조 [IProvideClassInfo2::GetGUID](http://msdn.microsoft.com/library/windows/desktop/ms679721) in the Windows SDK입니다.  
  
##  <a name="iprovideclassinfo2impl"></a>IProvideClassInfo2Impl::IProvideClassInfo2Impl  
 생성자입니다.  
  
```
IProvideClassInfo2Impl();
```  
  
### <a name="remarks"></a>설명  
 호출 `AddRef` 에 [_tih](#_tih) 멤버입니다. 소멸자 호출 **릴리스**합니다.  
  
##  <a name="_tih"></a>IProvideClassInfo2Impl::_tih  
 이 정적 데이터 멤버는 클래스 템플릿 매개 변수 인스턴스의 `tihclass`, 기본적으로 `CComTypeInfoHolder`합니다.  
  
```
static  tihclass
    _tih;
```     
  
### <a name="remarks"></a>설명  
 `_tih`coclass에 대 한 형식 정보를 관리합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
