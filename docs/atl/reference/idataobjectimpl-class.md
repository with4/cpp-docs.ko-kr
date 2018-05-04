---
title: IDataObjectImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl::DAdvise
- ATLCTL/ATL::IDataObjectImpl::DUnadvise
- ATLCTL/ATL::IDataObjectImpl::EnumDAdvise
- ATLCTL/ATL::IDataObjectImpl::EnumFormatEtc
- ATLCTL/ATL::IDataObjectImpl::FireDataChange
- ATLCTL/ATL::IDataObjectImpl::GetCanonicalFormatEtc
- ATLCTL/ATL::IDataObjectImpl::GetData
- ATLCTL/ATL::IDataObjectImpl::GetDataHere
- ATLCTL/ATL::IDataObjectImpl::QueryGetData
- ATLCTL/ATL::IDataObjectImpl::SetData
dev_langs:
- C++
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3ffcdd8cc8320b2534d928171fe75619062b300
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl 클래스
이 클래스는 단일형 데이터 전송 지원 및 연결 관리에 대 한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>  
class IDataObjectImpl
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IDataObjectImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IDataObjectImpl::DAdvise](#dadvise)|데이터 개체와 advise 싱크 간의 연결을 만듭니다. 따라서 advise 싱크를를 개체의 변경 알림을 받을 수 있습니다.|  
|[IDataObjectImpl::DUnadvise](#dunadvise)|통해 이전에 설정 된 연결을 종료 `DAdvise`합니다.|  
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|현재 자문 연결을 통해 반복 하는 열거자를 만듭니다.|  
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|반복 하는 열거자를 만듭니다는 **FORMATETC** 데이터 개체에서 지 원하는 구조입니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IDataObjectImpl::FireDataChange](#firedatachange)|각 advise 싱크 변경 알림을 다시 보냅니다.|  
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|논리적으로 동일한 검색 **FORMATETC** 는 더 복잡 한 구조입니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IDataObjectImpl::GetData](#getdata)|클라이언트에 데이터 개체에서 데이터를 전송합니다. 데이터에 설명 되어 한 **FORMATETC** 구조체이 고이 통해 전송 되는 **STGMEDIUM** 구조입니다.|  
|[IDataObjectImpl::GetDataHere](#getdatahere)|비슷한 `GetData`클라이언트를 할당 해야 점을 제외 하 고는 **STGMEDIUM** 구조입니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IDataObjectImpl::QueryGetData](#querygetdata)|데이터 개체에 특정 지원 하는지 여부를 결정 **FORMATETC** 데이터 전송에 대 한 구조입니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IDataObjectImpl::SetData](#setdata)|데이터 개체에는 클라이언트에서 데이터를 전송합니다. ATL 구현은 **E_NOTIMPL**합니다.|  
  
## <a name="remarks"></a>설명  
 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) 인터페이스 단일형 데이터 전송 지원 하기 위해 메서드를 제공 합니다. `IDataObject` 표준 형식 구조를 사용 하 여 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 및 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 검색 하 고 데이터를 저장 합니다.  
  
 `IDataObject` 또한 데이터 변경 알림을 처리 하는 싱크를 알리기 위해 연결을 관리 합니다. 클라이언트에서 데이터 개체에서 데이터 변경 알림을 수신 하도록 클라이언트를 구현 해야 합니다는 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) advise 싱크 라는 개체의 인터페이스에 있습니다. 클라이언트는 다음 호출 하는 경우 **IDataObject::DAdvise**, 데이터 개체와 advise 싱크 간의 연결입니다.  
  
 클래스 `IDataObjectImpl` 의 기본 구현을 제공 `IDataObject` 구현 **IUnknown** 디버그에서 장치 정보 덤프를 전송 하 여 빌드합니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="dadvise"></a>  IDataObjectImpl::DAdvise  
 데이터 개체와 advise 싱크 간의 연결을 만듭니다.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>설명  
 따라서 advise 싱크를를 개체의 변경 알림을 받을 수 있습니다.  
  
 연결을 종료 하려면 호출 [DUnadvise](#dunadvise)합니다.  
  
 참조 [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) in the Windows SDK입니다.  
  
##  <a name="dunadvise"></a>  IDataObjectImpl::DUnadvise  
 통해 이전에 설정 된 연결을 종료 [DAdvise](#dadvise)합니다.  
  
```
HRESULT DUnadvise(DWORD dwConnection);
```  
  
### <a name="remarks"></a>설명  
 참조 [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) in the Windows SDK입니다.  
  
##  <a name="enumdadvise"></a>  IDataObjectImpl::EnumDAdvise  
 현재 자문 연결을 통해 반복 하는 열거자를 만듭니다.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>설명  
 참조 [IDataObject::EnumDAdvise](http://msdn.microsoft.com/library/windows/desktop/ms680127) in the Windows SDK입니다.  
  
##  <a name="enumformatetc"></a>  IDataObjectImpl::EnumFormatEtc  
 반복 하는 열거자를 만듭니다는 **FORMATETC** 데이터 개체에서 지 원하는 구조입니다.  
  
```
HRESULT EnumFormatEtc(  
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```  
  
### <a name="remarks"></a>설명  
 참조 [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) in the Windows SDK입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
##  <a name="firedatachange"></a>  IDataObjectImpl::FireDataChange  
 현재 관리 중인 각 advise 싱크 변경 알림을 다시 보냅니다.  
  
```
HRESULT FireDataChange();
```  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="getcanonicalformatetc"></a>  IDataObjectImpl::GetCanonicalFormatEtc  
 논리적으로 동일한 검색 **FORMATETC** 는 더 복잡 한 구조입니다.  
  
```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IDataObject::GetCanonicalFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms680685) in the Windows SDK입니다.  
  
##  <a name="getdata"></a>  IDataObjectImpl::GetData  
 클라이언트에 데이터 개체에서 데이터를 전송합니다.  
  
```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```  
  
### <a name="remarks"></a>설명  
 *pformatetcIn* 매개 변수는 저장소 미디어 종류입니다. 지정 해야 **TYMED_MFPICT**합니다.  
  
 참조 [idataobject:: Getdata](http://msdn.microsoft.com/library/windows/desktop/ms678431) in the Windows SDK입니다.  
  
##  <a name="getdatahere"></a>  IDataObjectImpl::GetDataHere  
 비슷한 `GetData`클라이언트를 할당 해야 점을 제외 하 고는 **STGMEDIUM** 구조입니다.  
  
```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IDataObject::GetDataHere](http://msdn.microsoft.com/library/windows/desktop/ms687266) in the Windows SDK입니다.  
  
##  <a name="querygetdata"></a>  IDataObjectImpl::QueryGetData  
 데이터 개체에 특정 지원 하는지 여부를 결정 **FORMATETC** 데이터 전송에 대 한 구조입니다.  
  
```
HRESULT QueryGetData(FORMATETC* pformatetc);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) in the Windows SDK입니다.  
  
##  <a name="setdata"></a>  IDataObjectImpl::SetData  
 데이터 개체에는 클라이언트에서 데이터를 전송합니다.  
  
```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IDataObject::SetData](http://msdn.microsoft.com/library/windows/desktop/ms686626) in the Windows SDK입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
