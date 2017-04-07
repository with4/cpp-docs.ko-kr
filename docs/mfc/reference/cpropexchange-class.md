---
title: "CPropExchange 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
dev_langs:
- C++
helpviewer_keywords:
- CPropExchange class
- OLE controls, persistence
- controls [MFC], OLE
ms.assetid: ed872180-e770-4942-892a-92139d501fab
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 655d8e2f074c3bd12b1b52ece74efb844c7a9904
ms.lasthandoff: 02/24/2017

---
# <a name="cpropexchange-class"></a>CPropExchange 클래스
OLE 컨트롤의 지속성 구현을 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class AFX_NOVTABLE CPropExchange  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|이진 대형 개체 (BLOB) 속성을 교환합니다.|  
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|Font 속성을 교환합니다.|  
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|컨트롤 사이의 파일 속성을 교환합니다.|  
|[CPropExchange::ExchangeProp](#exchangeprop)|모든 기본 제공 형식의 속성을 교환합니다.|  
|[CPropExchange::ExchangeVersion](#exchangeversion)|OLE 컨트롤의 버전 번호를 교환합니다.|  
|[CPropExchange::GetVersion](#getversion)|OLE 컨트롤의 버전 번호를 검색합니다.|  
|[CPropExchange::IsAsynchronous](#isasynchronous)|속성 교환은 비동기적으로 수행 하는 경우를 결정 합니다.|  
|[CPropExchange::IsLoading](#isloading)|속성은 되 고 있는지 여부를 나타냅니다. 컨트롤에 로드 하거나이를 저장 합니다.|  
  
## <a name="remarks"></a>주의  
 `CPropExchange`기본 클래스는 없습니다.  
  
 컨텍스트 및 속성 exchange의 방향을 설정합니다.  
  
 지 속성은 일반적으로 컨트롤 자체와 미디어 간에 해당 속성을 나타내는 컨트롤의 상태 정보를 교환 합니다.  
  
 파생 된 개체를 생성 하는 프레임 워크 `CPropExchange` 때 알림을 받을 OLE 컨트롤의 속성에서 로드 될 지 또는 저장소에 영구 저장된 합니다.  
  
 프레임 워크는이에 대 한 포인터를 전달 `CPropExchange` 개체를 컨트롤의 `DoPropExchange` 함수입니다. 마법사를 사용 하는 컨트롤, 컨트롤에 대 한 시작 파일을 만들려는 경우 `DoPropExchange` 함수 호출 `COleControl::DoPropExchange`합니다. 기본 클래스 버전 교환 컨트롤의 스톡 속성입니다. 사용자 컨트롤에 추가한 후 exchange 속성에 파생 된 클래스의 버전을 수정 합니다.  
  
 `CPropExchange`컨트롤의 속성을 serialize 하거나 부하 또는 컨트롤 생성 시 컨트롤의 속성을 초기화 데 사용할 수 있습니다. `ExchangeProp` 및 `ExchangeFontProp` 의 멤버 함수 `CPropExchange` 속성을 저장 하 고 다양 한 미디어에서 로드 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CPropExchange`, 문서를 참조 하십시오 [MFC ActiveX 컨트롤: 속성 페이지](../../mfc/mfc-activex-controls-property-pages.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CPropExchange`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxctl.h  
  
##  <a name="exchangeblobprop"></a>CPropExchange::ExchangeBlobProp  
 이진 대형 개체 (BLOB) 데이터를 저장 하는 속성을 serialize 합니다.  
  
```  
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,  
    HGLOBAL* phBlob,  
    HGLOBAL hBlobDefault = NULL) = 0;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `phBlob`  
 변수의 속성을 저장할 위치를 가리키는 포인터입니다 (변수가 일반적으로 클래스의 멤버).  
  
 `hBlobDefault`  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값은 읽거나 쓸 적절 한 변수에서 참조 처럼 `phBlob`합니다. 경우 `hBlobDefault` 를 지정 하면 속성의 기본값으로 사용 됩니다. 이 값은 컨트롤의 serialization이 실패 하면 어떤 이유로 든 하는 경우 사용 합니다.  
  
 함수 **CArchivePropExchange::ExchangeBlobProp**, **CResetPropExchange::ExchangeBlobProp**, 및 **CPropsetPropExchange::ExchangeBlobProp** 이 순수 가상 함수를 재정의 합니다.  
  
##  <a name="exchangefontprop"></a>CPropExchange::ExchangeFontProp  
 저장소 매체와 컨트롤 간의 font 속성을 교환합니다.  
  
```  
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,  
    CFontHolder& font,  
    const FONTDESC* pFontDesc,  
    LPFONTDISP pFontDispAmbient) = 0;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `font`  
 에 대 한 참조는 [CFontHolder](../../mfc/reference/cfontholder-class.md) 글꼴 속성을 포함 하는 개체입니다.  
  
 `pFontDesc`  
 에 대 한 포인터는 [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782) font 속성의 기본 상태를 초기화 하는 것에 대 한 값이 포함 된 구조 때 `pFontDispAmbient` 는 **NULL**합니다.  
  
 `pFontDispAmbient`  
 에 대 한 포인터는 **IFontDisp** font 속성의 기본 상태를 초기화 하는 데 사용할 수는 글꼴의 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 Font 속성 미디어에서 컨트롤에 로드 되 고, 글꼴 특성은 매체에서 검색 됩니다 및 `CFontHolder` 개체에서 참조 `font` 사람과 초기화 됩니다. Font 속성에 저장 하는 경우에 글꼴 개체에서 특성 매체에 기록 됩니다.  
  
 함수 **CArchivePropExchange::ExchangeFontProp**, **CResetPropExchange::ExchangeFontProp**, 및 **CPropsetPropExchange::ExchangeFontProp** 이 순수 가상 함수를 재정의 합니다.  
  
##  <a name="exchangepersistentprop"></a>CPropExchange::ExchangePersistentProp  
 컨트롤 및 파일 간의 속성을 교환합니다.  
  
```  
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,  
    LPUNKNOWN* ppUnk,  
    REFIID iid,  
    LPUNKNOWN pUnkDefault) = 0;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `ppUnk`  
 속성에 대 한 포인터를 포함 하는 변수에 대 한 포인터 **IUnknown** 인터페이스 (이 변수는 클래스의 멤버가 일반적으로).  
  
 `iid`  
 컨트롤에서 사용할 속성에는 인터페이스의 인터페이스 ID입니다.  
  
 `pUnkDefault`  
 속성의 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 컨트롤에는 속성이 파일에서 로드 되 고, 속성이 생성 되어 파일에서 초기화 됩니다. 속성에 저장 하는 경우 해당 값이 파일에 기록 됩니다.  
  
 함수 **CArchivePropExchange::ExchangePersistentProp**, **CResetPropExchange::ExchangePersistentProp**, 및 **CPropsetPropExchange::ExchangePersistentProp** 이 순수 가상 함수를 재정의 합니다.  
  
##  <a name="exchangeprop"></a>CPropExchange::ExchangeProp  
 속성 저장소 매체와 컨트롤 사이 교환합니다.  
  
```  
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,  
    VARTYPE vtProp,  
    void* pvProp,  
    const void* pvDefault = NULL) = 0 ;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pszPropName`  
 교환 되는 속성의 이름입니다.  
  
 `vtProp`  
 교환 되는 속성의 유형을 지정 하는 기호입니다. 가능한 값은 다음과 같습니다.  
  
|기호|속성 형식|  
|------------|-------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_BOOL`|**BOOL**|  
|`VT_BSTR`|`CString`|  
|`VT_CY`|**CY**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
  
 `pvProp`  
 속성의 값에 대 한 포인터입니다.  
  
 *pvDefault*  
 속성에 대 한 기본 값에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 Exchange에 성공 하면 0이 아닌 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 속성의 값 미디어에서 검색 되어 가리키는 개체에 저장 된 경우 속성은 미디어에서 컨트롤에 로드 되 고, `pvProp`합니다. 속성은 미디어에 저장 하려는 경우 개체의 값 가리키는 `pvProp` 매체에 기록 됩니다.  
  
 함수 **CArchivePropExchange::ExchangeProp**, **CResetPropExchange::ExchangeProp**, 및 **CPropsetPropExchange::ExchangeProp** 이 순수 가상 함수를 재정의 합니다.  
  
##  <a name="exchangeversion"></a>CPropExchange::ExchangeVersion  
 버전 번호의 지 속성을 처리 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,  
    DWORD dwVersionDefault,  
    BOOL bConvert);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwVersionLoaded*  
 로드 되는 영구 데이터의 버전 번호를 저장할 변수 참조입니다.  
  
 `dwVersionDefault`  
 컨트롤의 현재 버전 번호입니다.  
  
 `bConvert`  
 영구 데이터를 현재 버전으로 변환 또는 로드 된 동일한 버전으로 유지할 것인지를 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
##  <a name="getversion"></a>CPropExchange::GetVersion  
 컨트롤의 버전 번호를 검색 하려면이 함수를 호출 합니다.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>반환 값  
 컨트롤의 버전 번호입니다.  
  
##  <a name="isasynchronous"></a>CPropExchange::IsAsynchronous  
 속성 교환은 비동기적으로 수행 하는 경우를 결정 합니다.  
  
```  
BOOL IsAsynchronous();
```  
  
### <a name="return-value"></a>반환 값  
 속성이 있으면 TRUE를 반환 교환 비동기적으로, 그렇지 않으면 FALSE입니다.  
  
##  <a name="isloading"></a>CPropExchange::IsLoading  
 속성은 되 고 있는지 여부를 확인 하려면이 함수를 호출 컨트롤에 로드 하거나이를 저장 합니다.  
  
```  
BOOL IsLoading();
```  
  
### <a name="return-value"></a>반환 값  
 속성은 로드 되 고 0이 아닌 그렇지 않으면 0입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)




