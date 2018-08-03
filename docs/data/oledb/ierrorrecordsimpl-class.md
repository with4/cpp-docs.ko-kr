---
title: IErrorRecordsImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IErrorRecordsImpl
- ATL.IErrorRecordsImpl
- IErrorRecordsImpl
- GetErrorDescriptionString
- IErrorRecordsImpl.GetErrorDescriptionString
- IErrorRecordsImpl::GetErrorDescriptionString
- GetErrorGUID
- IErrorRecordsImpl.GetErrorGUID
- IErrorRecordsImpl::GetErrorGUID
- GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpContext
- IErrorRecordsImpl.GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpFile
- GetErrorHelpFile
- IErrorRecordsImpl.GetErrorHelpFile
- IErrorRecordsImpl.GetErrorSource
- GetErrorSource
- IErrorRecordsImpl::GetErrorSource
- IErrorRecordsImpl.AddErrorRecord
- AddErrorRecord
- IErrorRecordsImpl::AddErrorRecord
- ATL::IErrorRecordsImpl::GetBasicErrorInfo
- IErrorRecordsImpl::GetBasicErrorInfo
- GetBasicErrorInfo
- ATL.IErrorRecordsImpl.GetBasicErrorInfo
- IErrorRecordsImpl.GetBasicErrorInfo
- ATL::IErrorRecordsImpl::GetCustomErrorObject
- IErrorRecordsImpl::GetCustomErrorObject
- ATL.IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetCustomErrorObject
- GetCustomErrorObject
- GetErrorInfo
- IErrorRecordsImpl.GetErrorInfo
- IErrorRecordsImpl::GetErrorInfo
- IErrorRecordsImpl::GetErrorParameters
- ATL.IErrorRecordsImpl.GetErrorParameters
- IErrorRecordsImpl.GetErrorParameters
- GetErrorParameters
- ATL::IErrorRecordsImpl::GetErrorParameters
- IErrorRecordsImpl::GetRecordCount
- ATL::IErrorRecordsImpl::GetRecordCount
- IErrorRecordsImpl.GetRecordCount
- ATL.IErrorRecordsImpl.GetRecordCount
- IErrorRecordsImpl::m_rgErrors
- IErrorRecordsImpl.m_rgErrors
- ATL.IErrorRecordsImpl.m_rgErrors
- m_rgErrors
- ATL::IErrorRecordsImpl::m_rgErrors
dev_langs:
- C++
helpviewer_keywords:
- IErrorRecordsImpl class
- GetErrorDescriptionString method
- GetErrorGUID method
- GetErrorHelpContext method
- GetErrorHelpFile method
- GetErrorSource method
- AddErrorRecord method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetRecordCount method
- m_rgErrors
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7339b345ad63f59a2db24251c06b80774305ab00
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338121"
---
# <a name="ierrorrecordsimpl-class"></a>IErrorRecordsImpl 클래스
OLE DB 구현 [IErrorRecords](https://msdn.microsoft.com/library/ms718112.aspx) 레코드를 추가 하 고 데이터 멤버에서 레코드를 검색 하는 인터페이스를 ([m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) 형식의 **CAtlArray <** `RecordClass`**>**.  
  
## <a name="syntax"></a>구문

```cpp
template <class T, class RecordClass = ATLERRORINFO>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 파생 된 클래스 `IErrorRecordsImpl`합니다.  
  
 *RecordClass*  
 OLE DB 오류 개체를 나타내는 클래스입니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[GetErrorDescriptionString](#geterrordescriptionstring)|오류 레코드에서 오류 설명 문자열을 가져옵니다.|  
|[GetErrorGUID](#geterrorguid)|오류 레코드에서 오류를 GUID를 가져옵니다.|  
|[GetErrorHelpContext](#geterrorhelpcontext)|오류 레코드에서 도움말 컨텍스트 ID를 가져옵니다.|  
|[GetErrorHelpFile](#geterrorhelpfile)|오류 레코드에서 도움말 파일의 전체 경로 이름을 가져옵니다.|  
|[GetErrorSource](#geterrorsource)|오류 레코드에서 오류 소스 코드를 가져옵니다.|  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[AddErrorRecord](#adderrorrecord)|OLE DB 오류 개체에 레코드를 추가합니다.|  
|[GetBasicErrorInfo](#getbasicerrorinfo)|반환 코드 및 공급자 특정 오류 번호와 같은 오류에 대 한 기본 정보를 반환 합니다.|  
|[GetCustomErrorObject](#getcustomerrorobject)|인터페이스를 사용자 지정 오류 개체에 대 한 포인터를 반환합니다.|  
|[GetErrorInfo](#geterrorinfo)|반환 된 [IErrorInfo](https://msdn.microsoft.com/library/ms718112.aspx) 지정된 된 레코드에 대 한 인터페이스 포인터입니다.|  
|[GetErrorParameters](#geterrorparameters)|오류 매개 변수를 반환합니다.|  
|[GetRecordCount](#getrecordcount)|OLE DB 레코드 개체의 레코드 수를 반환 합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_rgErrors](#rgerrors)|오류 레코드의 배열입니다.|  

## <a name="geterrordescriptionstring"></a> Ierrorrecordsimpl:: Geterrordescriptionstring
오류 레코드에서 오류 설명 문자열을 가져옵니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
LPOLESTR GetErrorDescriptionString(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *rCurError*  
 `ERRORINFO` 레코드는 `IErrorInfo` 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 오류를 설명 하는 문자열에 대 한 포인터입니다.  
  
## <a name="geterrorguid"></a> Ierrorrecordsimpl:: Geterrorguid
오류 레코드에서 오류를 GUID를 가져옵니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
REFGUID GetErrorGUID(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *rCurError*  
 `ERRORINFO` 레코드는 `IErrorInfo` 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 오류에 대 한 GUID에 대 한 참조입니다.  

## <a name="geterrorhelpcontext"></a> Ierrorrecordsimpl:: Geterrorhelpcontext
오류 레코드에서 도움말 컨텍스트 ID를 가져옵니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
DWORD GetErrorHelpContext(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *rCurError*  
 `ERRORINFO` 레코드는 `IErrorInfo` 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 오류에 대 한 도움말 컨텍스트 ID입니다.  

## <a name="geterrorhelpfile"></a> Ierrorrecordsimpl:: Geterrorhelpfile
오류 레코드에서 도움말 파일의 경로 이름을 가져옵니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
LPOLESTR GetErrorHelpFile(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *rCurError*  
 `ERRORINFO` 레코드는 `IErrorInfo` 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 오류에 대 한 도움말 파일의 경로 이름을 포함 하는 문자열에 대 한 포인터입니다.

## <a name="geterrorsource"></a> Ierrorrecordsimpl:: Geterrorsource
오류 레코드에서 오류를 발생 시킨 소스 코드를 가져옵니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
LPOLESTR GetErrorSource(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *rCurError*  
 `ERRORINFO` 레코드는 `IErrorInfo` 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 오류에 대 한 소스 코드를 포함 하는 문자열에 대 한 포인터입니다. 

## <a name="adderrorrecord"></a> Ierrorrecordsimpl:: Adderrorrecord
OLE DB 오류 개체에 레코드를 추가합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD(AddErrorRecord )(ERRORINFO *pErrorInfo,  
   DWORD dwLookupID,  
   DISPPARAMS *pdispparams,  
   IUnknown *punkCustomError,  
   DWORD dwDynamicErrorID);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IErrorRecords::AddErrorRecord](https://msdn.microsoft.com/library/ms725362.aspx) 에 *OLE DB Programmer's Reference*합니다.  

## <a name="getbasicerrorinfo"></a> Ierrorrecordsimpl:: Getbasicerrorinfo
반환 코드 및 공급자 특정 오류 번호와 같은 오류에 대 한 기본 정보를 반환 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD(GetBasicErrorInfo )(ULONG ulRecordNum,  
   ERRORINFO *pErrorInfo);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/library/ms723907.aspx) 에 *OLE DB Programmer's Reference*합니다. 

## <a name="getcustomerrorobject"></a> Ierrorrecordsimpl:: Getcustomerrorobject
인터페이스를 사용자 지정 오류 개체에 대 한 포인터를 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD(GetCustomErrorObject )(ULONG ulRecordNum,  
   REFIID riid,  
   IUnknown **ppObject);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/library/ms725417.aspx) 에 *OLE DB Programmer's Reference*합니다.  

## <a name="geterrorinfo"></a> Ierrorrecordsimpl:: Geterrorinfo
반환 된 [IErrorInfo](https://msdn.microsoft.com/library/ms718112.aspx) 지정된 된 레코드에 대 한 인터페이스 포인터입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD(GetErrorInfo )(ULONG ulRecordNum,  
   LCID lcid,  
   IErrorInfo **ppErrorInfo);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/library/ms711230.aspx) 에 *OLE DB Programmer's Reference*합니다.

## <a name="geterrorparameters"></a> Ierrorrecordsimpl:: Geterrorparameters
오류 매개 변수를 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD(GetErrorParameters )(ULONG ulRecordNum,  
   DISPPARAMS *pdispparams);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/library/ms715793.aspx) 에 *OLE DB Programmer's Reference*합니다.  

## <a name="getrecordcount"></a> Ierrorrecordsimpl:: Getrecordcount
OLE DB 레코드 개체의 레코드 수를 반환 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
STDMETHOD(GetRecordCount )(ULONG *pcRecords);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IErrorRecords::GetRecordCount](https://msdn.microsoft.com/library/ms722724.aspx) 에 *OLE DB Programmer's Reference*합니다.  

## <a name="rgerrors"></a> Ierrorrecordsimpl:: M_rgerrors
오류 레코드의 배열입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
CAtlArray< RecordClass > m_rgErrors;  
```  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)