---
title: "COleDispatchDriver 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDispatchDriver
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchDriver class
- Automation clients, implementing Automation
- OLE dispatch interface
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 51fc2064e2f4b51b4f4328afb03920dab27ef74b
ms.lasthandoff: 02/24/2017

---
# <a name="coledispatchdriver-class"></a>COleDispatchDriver 클래스
OLE 자동화의 클라이언트 쪽을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleDispatchDriver  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleDispatchDriver::COleDispatchDriver](#coledispatchdriver)|`COleDispatchDriver` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleDispatchDriver::AttachDispatch](#attachdispatch)|연결 된 `IDispatch` 연결을는 `COleDispatchDriver` 개체입니다.|  
|[COleDispatchDriver::CreateDispatch](#createdispatch)|만듭니다는 `IDispatch` 연결에 연결 된 `COleDispatchDriver` 개체입니다.|  
|[COleDispatchDriver::DetachDispatch](#detachdispatch)|분리 된 `IDispatch` 해제 하지 않고 연결 합니다.|  
|[COleDispatchDriver::GetProperty](#getproperty)|자동화 속성을 가져옵니다.|  
|[COleDispatchDriver::InvokeHelper](#invokehelper)|자동화 메서드를 호출 하기 위한 도우미입니다.|  
|[COleDispatchDriver::ReleaseDispatch](#releasedispatch)|릴리스는 `IDispatch` 연결 합니다.|  
|[COleDispatchDriver::SetProperty](#setproperty)|자동화 속성을 설정합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[COleDispatchDriver::operator =](#operator_eq)|소스 값으로 복사는 `COleDispatchDriver` 개체입니다.|  
|[COleDispatchDriver::operator LPDISPATCH](#operator_lpdispatch)|기본 액세스 `IDispatch` 포인터입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleDispatchDriver::m_bAutoRelease](#m_bautorelease)|해제할지 여부를 지정 하는 `IDispatch` 중 `ReleaseDispatch` 또는 개체 소멸 합니다.|  
|[COleDispatchDriver::m_lpDispatch](#m_lpdispatch)|에 대 한 포인터를 나타냅니다는 `IDispatch` 이에 연결 된 인터페이스 `COleDispatchDriver`합니다.|  
  
## <a name="remarks"></a>주의  
 `COleDispatchDriver`기본 클래스는 없습니다.  
  
 OLE 디스패치 인터페이스 개체의 메서드 및 속성에 대 한 액세스를 제공합니다. 멤버 함수 `COleDispatchDriver` 연결, 분리, 작성 및 유형의 디스패치 연결 해제 `IDispatch`합니다. 다른 멤버 함수 호출을 간소화 하기 위해 가변 인수 목록을 사용할 **idispatch:: Invoke**합니다.  
  
 이 클래스를 직접 사용할 수 있지만 주로 클래스 추가 마법사에서 만든 클래스에 의해서만 사용 됩니다. 새 클래스에서 파생 되는 형식 라이브러리를 가져와서 새 c + + 클래스를 만들 때 `COleDispatchDriver`합니다.  
  
 사용 하 여 대 한 자세한 내용은 `COleDispatchDriver`, 다음 문서를 참조 합니다.  
  
- [자동화 클라이언트](../../mfc/automation-clients.md)  
  
- [자동화 서버](../../mfc/automation-servers.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `COleDispatchDriver`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
  
##  <a name="a-nameattachdispatcha--coledispatchdriverattachdispatch"></a><a name="attachdispatch"></a>COleDispatchDriver::AttachDispatch  
 `AttachDispatch` 멤버 함수를 호출하여 `IDispatch` 개체에 대한 `COleDispatchDriver` 포인터를 연결합니다. 자세한 내용은 참조 [IDispatch 인터페이스를 구현](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)합니다.  
  
```  
void AttachDispatch(
        LPDISPATCH lpDispatch,  
        BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDispatch`  
 `IDispatch` 개체에 연결될 OLE `COleDispatchDriver` 개체에 대한 포인터입니다.  
  
 `bAutoRelease`  
 이 개체가 범위를 벗어날 때 디스패치를 해제할지 여부를 지정합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 `IDispatch` 개체에 이미 연결된 모든 `COleDispatchDriver` 포인터를 해제합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&3;](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]  
  
##  <a name="a-namecoledispatchdrivera--coledispatchdrivercoledispatchdriver"></a><a name="coledispatchdriver"></a>COleDispatchDriver::COleDispatchDriver  
 `COleDispatchDriver` 개체를 생성합니다.  
  
```  
COleDispatchDriver();  
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);  
  COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDispatch`  
 `IDispatch` 개체에 연결될 OLE `COleDispatchDriver` 개체에 대한 포인터입니다.  
  
 `bAutoRelease`  
 이 개체가 범위를 벗어날 때 디스패치를 해제할지 여부를 지정합니다.  
  
 `dispatchSrc`  
 기존에 대 한 참조가 `COleDispatchDriver` 개체입니다.  
  
### <a name="remarks"></a>주의  
 폼 `COleDispatchDriver`( `LPDISPATCH``lpDispatch`, **BOOL**`bAutoRelease` = **TRUE**) 연결 하는 [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) 인터페이스입니다.  
  
 폼 `COleDispatchDriver`( **const**`COleDispatchDriver`& `dispatchSrc`) 복사 하는 기존 `COleDispatchDriver` 개체 및 참조 횟수를 증가 시킵니다.  
  
 폼 `COleDispatchDriver`만듭니다 ()는 `COleDispatchDriver` 개체 하지만 연결 되어 있지 않습니다는 `IDispatch` 인터페이스입니다. 사용 하기 전에 `COleDispatchDriver`연결 해야 인수 없이 ()는 `IDispatch` 중 하나를 사용 하 여 [COleDispatchDriver::CreateDispatch](#createdispatch) 또는 [COleDispatchDriver::AttachDispatch](#attachdispatch)합니다. 자세한 내용은 참조 [IDispatch 인터페이스를 구현](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [COleDispatchDriver::CreateDispatch](#createdispatch)합니다.  
  
##  <a name="a-namecreatedispatcha--coledispatchdrivercreatedispatch"></a><a name="createdispatch"></a>COleDispatchDriver::CreateDispatch  
 만듭니다는 [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) 인터페이스 개체에 연결 된 `COleDispatchDriver` 개체입니다.  
  
```  
BOOL CreateDispatch(
        REFCLSID clsid,  
        COleException* pError = NULL);

 
BOOL CreateDispatch(
    LPCTSTR lpszProgID,  
    COleException* pError = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 만들려는 `IDispatch` 연결 개체의 클래스 ID입니다.  
  
 `pError`  
 만들기에서 발생하는 상태 코드를 포함할, OLE 예외 개체에 대한 포인터입니다.  
  
 `lpszProgID`  
 디스패치 개체를 만들려는 자동화 개체의 프로그래밍 ID(예: "Excel.Document.5")에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아닌 값이고, 실패하면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&4;](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]  
  
##  <a name="a-namedetachdispatcha--coledispatchdriverdetachdispatch"></a><a name="detachdispatch"></a>COleDispatchDriver::DetachDispatch  
 현재 분리 `IDispatch` 이 개체에서 연결 합니다.  
  
```  
LPDISPATCH DetachDispatch();
```  
  
### <a name="return-value"></a>반환 값  
 이전에 연결 된 OLE에 대 한 포인터 `IDispatch` 개체입니다.  
  
### <a name="remarks"></a>주의  
 `IDispatch` 해제 되지 않습니다.  
  
 에 대 한 자세한 내용은 `LPDISPATCH` 입력, 참조 [IDispatch 인터페이스를 구현](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&5;](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]  
  
##  <a name="a-namegetpropertya--coledispatchdrivergetproperty"></a><a name="getproperty"></a>COleDispatchDriver::GetProperty  
 지정 된 개체 속성을 가져옵니다 `dwDispID`합니다.  
  
```  
void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDispID`  
 검색할 속성을 식별 합니다.  
  
 `vtProp`  
 검색할 속성을 지정 합니다. 가능한 값에 대 한 설명 섹션을 참조 하십시오. [COleDispatchDriver::InvokeHelper](#invokehelper)합니다.  
  
 `pvProp`  
 속성 값을 받을 변수 주소입니다. 지정한 형식과 일치 해야 `vtProp`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&6;](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]  
  
##  <a name="a-nameinvokehelpera--coledispatchdriverinvokehelper"></a><a name="invokehelper"></a>COleDispatchDriver::InvokeHelper  
 `dwDispID`를 통해 지정된 컨텍스트에서 `wFlags`를 통해 지정된 개체 메서드 또는 속성을 호출합니다.  
  
```  
void AFX_CDECL InvokeHelper(
        DISPID dwDispID,  
        WORD wFlags,  
        VARTYPE vtRet,  
        void* pvRet,  
        const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDispID`  
 호출할 메서드 또는 속성을 식별합니다.  
  
 `wFlags`  
 **IDispatch::Invoke**호출의 컨텍스트를 설명하는 플래그입니다. 입니다. 가능한 값의 목록에 대 한 참조는 `wFlags` 매개 변수 [idispatch:: Invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `vtRet`  
 반환 값 형식을 지정합니다. 가능한 값은 설명 섹션을 참조하세요.  
  
 `pvRet`  
 속성 값이나 반환 값을 받을 변수의 주소입니다. `vtRet`를 통해 지정된 형식과 일치해야 합니다.  
  
 `pbParamInfo`  
 `pbParamInfo`뒤에 매개 변수 형식을 지정하는 바이트의 null로 종료된 문자열에 대한 포인터입니다.  
  
 *...*  
 `pbParamInfo`에 지정된 형식의 매개 변수에 대한 변수 목록입니다.  
  
### <a name="remarks"></a>주의  
 `pbParamInfo` 매개 변수는 메서드나 속성에 전달되는 매개 변수 형식을 지정합니다. 인수의 변수 목록은 구문 선언에서 **...** 로 표시됩니다.  
  
 `vtRet` 인수의 가능한 값은 `VARENUM` 열거형에서 가져옵니다. 다음과 같은 값을 사용할 수 있습니다.  
  
|기호|반환 형식|  
|------------|-----------------|  
|`VT_EMPTY`|`void`|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**날짜**|  
|`VT_BSTR`|`BSTR`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 `pbParamInfo` 인수는 **VTS_** 상수의 공백으로 구분된 목록입니다. 공백(쉼표가 아님)으로 구분된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정합니다. 가능한 값 나열 되는 [EVENT_CUSTOM](event-maps.md#event_custom) 매크로입니다.  
  
 이 함수는 매개 변수를 **VARIANTARG** 값으로 변환하고 나서 [IDispatch::Invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx) 메서드를 호출합니다. `Invoke` 호출에 실패하면 이 함수가 예외를 throw합니다. 경우는 `SCODE` (상태 코드)가 반환한 **idispatch:: Invoke** 는 `DISP_E_EXCEPTION`,이 함수는 [COleException](../../mfc/reference/coleexception-class.md) 개체, 그렇지 않으면 throw는 [COleDispatchException](../../mfc/reference/coledispatchexception-class.md)합니다.  
  
 자세한 내용은 참조 [VARIANTARG](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [IDispatch 인터페이스를 구현](http://msdn.microsoft.com/library/windows/desktop/ms221037\(v=vs.85\).aspx), [idispatch:: Invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx), 및 [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [COleDispatchDriver::CreateDispatch](#createdispatch)합니다.  
  
##  <a name="a-namembautoreleasea--coledispatchdrivermbautorelease"></a><a name="m_bautorelease"></a>COleDispatchDriver::m_bAutoRelease  
 경우 **TRUE**, 액세스 한 COM 개체가 [m_lpDispatch](#m_lpdispatch) 자동으로 릴리스될 때 [ReleaseDispatch](#releasedispatch) 라고 경우 또는이 `COleDispatchDriver` 개체는 소멸 됩니다.  
  
```  
BOOL m_bAutoRelease;  
```  
  
### <a name="remarks"></a>주의  
 기본적으로 `m_bAutoRelease` 로 설정 된 **TRUE** 생성자에 있습니다.  
  
 COM 개체 해제에 대 한 자세한 내용은 참조 하십시오. [참조 카운팅 구현](http://msdn.microsoft.com/library/windows/desktop/ms693431) 및 [iunknown:: Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&9;](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]  
  
##  <a name="a-namemlpdispatcha--coledispatchdrivermlpdispatch"></a><a name="m_lpdispatch"></a>COleDispatchDriver::m_lpDispatch  
 에 대 한 포인터는 `IDispatch` 이에 연결 된 인터페이스 `COleDispatchDriver`합니다.  
  
```  
LPDISPATCH m_lpDispatch;  
```  
  
### <a name="remarks"></a>주의  
 `m_lpDispatch` 데이터 멤버는 형식의 공용 변수 `LPDISPATCH`합니다.  
  
 자세한 내용은 참조 [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [COleDispatchDriver::AttachDispatch](#attachdispatch)합니다.  
  
##  <a name="a-nameoperatoreqa--coledispatchdriveroperator-"></a><a name="operator_eq"></a>COleDispatchDriver::operator =  
 소스 값으로 복사는 `COleDispatchDriver` 개체입니다.  
  
```  
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `dispatchSrc`  
 기존에 대 한 포인터 `COleDispatchDriver` 개체입니다.  
  
##  <a name="a-nameoperatorlpdispatcha--coledispatchdriveroperator-lpdispatch"></a><a name="operator_lpdispatch"></a>COleDispatchDriver::operator LPDISPATCH  
 기본 액세스 `IDispatch` 의 포인터는 `COleDispatchDriver` 개체입니다.  
  
```  
operator LPDISPATCH();
```   
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&8;](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]  
  
##  <a name="a-namereleasedispatcha--coledispatchdriverreleasedispatch"></a><a name="releasedispatch"></a>COleDispatchDriver::ReleaseDispatch  
 릴리스는 `IDispatch` 연결 합니다. 자세한 내용은 참조 [IDispatch 인터페이스를 구현 합니다.](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)  
  
```  
void ReleaseDispatch();
```  
  
### <a name="remarks"></a>주의  
 이 함수를 호출 하는이 연결에 대 한 자동 릴리스를 설정한 경우 **IDispatch::Release** 인터페이스를 해제 하기 전에 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [COleDispatchDriver::AttachDispatch](#attachdispatch)합니다.  
  
##  <a name="a-namesetpropertya--coledispatchdriversetproperty"></a><a name="setproperty"></a>COleDispatchDriver::SetProperty  
 `dwDispID`에서 지정한 OLE 개체 속성을 설정합니다.  
  
```  
void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDispID`  
 설정할 속성을 확인합니다.  
  
 `vtProp`  
 설정할 속성의 유형을 지정합니다. 가능한 값에 대 한 설명 섹션을 참조 하십시오. [COleDispatchDriver::InvokeHelper](#invokehelper)합니다.  
  
 *...*  
 `vtProp`에서 지정한 유형의 단일 매개 변수  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&7;](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CALCDRIV](../../visual-cpp-samples.md)   
 [ACDUAL MFC 샘플](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)

