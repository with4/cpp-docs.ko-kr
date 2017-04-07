---
title: "IDataObjectImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: afd5fe7cf9bbac582e59ed46dc33e99de5fc2876
ms.lasthandoff: 02/24/2017

---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl 클래스
이 클래스는 단일형 데이터 전송 지원 하 고 연결을 관리 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
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
|[IDataObjectImpl::DAdvise](#dadvise)|데이터 개체와 advise 싱크 간의 연결을 만듭니다. 그러면 advise 싱크 개체의 변경 알림을 받을 수 있습니다.|  
|[IDataObjectImpl::DUnadvise](#dunadvise)|통해 이전에 설정 된 연결을 종료 `DAdvise`합니다.|  
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|현재 자문 연결을 반복 하는 열거자를 만듭니다.|  
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|반복 하는 열거자를 만듭니다는 **FORMATETC** 데이터 개체에서 지 원하는 구조입니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IDataObjectImpl::FireDataChange](#firedatachange)|변경 알림을 각 advise 싱크를 다시 보냅니다.|  
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|논리적으로 동일한 검색 **FORMATETC** 는 좀 더 복잡 한 구조입니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IDataObjectImpl::GetData](#getdata)|클라이언트에 데이터 개체에서 데이터를 전송합니다. 데이터에 설명 되어는 **FORMATETC** 구조체를 통해 전송 되는 **STGMEDIUM** 구조입니다.|  
|[IDataObjectImpl::GetDataHere](#getdatahere)|유사한 `GetData`클라이언트를 할당 해야 하는 제외 하 고는 **STGMEDIUM** 구조입니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IDataObjectImpl::QueryGetData](#querygetdata)|데이터 개체는 특정 지원 하는지 여부를 결정 **FORMATETC** 구조 데이터를 전송 합니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IDataObjectImpl::SetData](#setdata)|데이터 개체에는 클라이언트에서 데이터를 전송합니다. ATL 구현은 **E_NOTIMPL**합니다.|  
  
## <a name="remarks"></a>주의  
 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) 인터페이스 단일형 데이터 전송 지원 하기 위한 메서드를 제공 합니다. `IDataObject`표준 형식 구조를 사용 하 여 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 및 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 검색 하 고 데이터를 저장 합니다.  
  
 `IDataObject`또한 데이터 변경 알림을 처리 하는 싱크를 알리기 위해 연결을 관리 합니다. 클라이언트에서 데이터 개체에서 데이터 변경 알림을 수신 하도록 클라이언트를 구현 해야는 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) advise 싱크 라는 개체에 대 한 인터페이스입니다. 클라이언트를 다음으로 호출 **IDataObject::DAdvise**, 데이터 개체와 advise 싱크 간의 연결입니다.  
  
 클래스 `IDataObjectImpl` 의 기본 구현을 제공 `IDataObject` 구현 **IUnknown** 장치에서 디버그 덤프를 정보를 전송 하 여 빌드합니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="dadvise"></a>IDataObjectImpl::DAdvise  
 데이터 개체와 advise 싱크 간의 연결을 만듭니다.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>주의  
 그러면 advise 싱크 개체의 변경 알림을 받을 수 있습니다.  
  
 연결을 종료 하려면 호출 [DUnadvise](#dunadvise)합니다.  
  
 참조 [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="dunadvise"></a>IDataObjectImpl::DUnadvise  
 통해 이전에 설정 된 연결을 종료 [DAdvise](#dadvise)합니다.  
  
```
HRESULT DUnadvise(DWORD dwConnection);
```  
  
### <a name="remarks"></a>주의  
 참조 [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="enumdadvise"></a>IDataObjectImpl::EnumDAdvise  
 현재 자문 연결을 반복 하는 열거자를 만듭니다.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>주의  
 참조 [IDataObject::EnumDAdvise](http://msdn.microsoft.com/library/windows/desktop/ms680127) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="enumformatetc"></a>IDataObjectImpl::EnumFormatEtc  
 반복 하는 열거자를 만듭니다는 **FORMATETC** 데이터 개체에서 지 원하는 구조입니다.  
  
```
HRESULT EnumFormatEtc(  
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```  
  
### <a name="remarks"></a>주의  
 참조 [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
##  <a name="firedatachange"></a>IDataObjectImpl::FireDataChange  
 현재 관리 되는 각 advise 싱크를 다시 변경 알림을 보냅니다.  
  
```
HRESULT FireDataChange();
```  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="getcanonicalformatetc"></a>IDataObjectImpl::GetCanonicalFormatEtc  
 논리적으로 동일한 검색 **FORMATETC** 는 좀 더 복잡 한 구조입니다.  
  
```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IDataObject::GetCanonicalFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms680685) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getdata"></a>IDataObjectImpl::GetData  
 클라이언트에 데이터 개체에서 데이터를 전송합니다.  
  
```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```  
  
### <a name="remarks"></a>주의  
 *pformatetcIn* 매개 변수는 저장소 미디어 종류입니다. 지정 해야 **TYMED_MFPICT**합니다.  
  
 참조 [idataobject:: Getdata](http://msdn.microsoft.com/library/windows/desktop/ms678431) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getdatahere"></a>IDataObjectImpl::GetDataHere  
 유사한 `GetData`클라이언트를 할당 해야 하는 제외 하 고는 **STGMEDIUM** 구조입니다.  
  
```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IDataObject::GetDataHere](http://msdn.microsoft.com/library/windows/desktop/ms687266) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="querygetdata"></a>IDataObjectImpl::QueryGetData  
 데이터 개체는 특정 지원 하는지 여부를 결정 **FORMATETC** 구조 데이터를 전송 합니다.  
  
```
HRESULT QueryGetData(FORMATETC* pformatetc);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setdata"></a>IDataObjectImpl::SetData  
 데이터 개체에는 클라이언트에서 데이터를 전송합니다.  
  
```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IDataObject::SetData](http://msdn.microsoft.com/library/windows/desktop/ms686626) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

