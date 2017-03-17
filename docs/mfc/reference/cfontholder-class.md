---
title: "CFontHolder 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
dev_langs:
- C++
helpviewer_keywords:
- custom fonts
- CFontHolder class
- fonts, ActiveX controls
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
caps.latest.revision: 19
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
ms.openlocfilehash: fdfa16756ff218159087969f2a4967ed5e76a445
ms.lasthandoff: 02/24/2017

---
# <a name="cfontholder-class"></a>CFontHolder 클래스
스톡 글꼴 속성을 구현하고 Windows 글꼴 개체 및 `IFont` 인터페이스의 기능을 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CFontHolder  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CFontHolder::CFontHolder](#cfontholder)|`CFontHolder` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFontHolder::GetDisplayString](#getdisplaystring)|컨테이너의 속성 브라우저에 표시 되는 문자열을 검색 합니다.|  
|[CFontHolder::GetFontDispatch](#getfontdispatch)|글꼴의 반환 `IDispatch` 인터페이스입니다.|  
|[CFontHolder::GetFontHandle](#getfonthandle)|Windows 글꼴에 대 한 핸들을 반환합니다.|  
|[CFontHolder::InitializeFont](#initializefont)|초기화는 `CFontHolder` 개체입니다.|  
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|관련된 글꼴에 대 한 정보를 검색합니다.|  
|[CFontHolder::ReleaseFont](#releasefont)|연결을 끊습니다는 `CFontHolder` 에서 개체는 `IFont` 및 `IFontNotification` 인터페이스입니다.|  
|[CFontHolder::Select](#select)|장치 컨텍스트에 글꼴 리소스를 선택합니다.|  
|[CFontHolder::SetFont](#setfont)|연결 된 `CFontHolder` 개체는 `IFont` 인터페이스입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CFontHolder::m_pFont](#m_pfont)|에 대 한 포인터는 `CFontHolder` 개체의 `IFont` 인터페이스입니다.|  
  
## <a name="remarks"></a>주의  
 `CFontHolder`기본 클래스는 없습니다.  
  
 컨트롤에 대 한 사용자 지정 글꼴 속성을 구현 하려면이 클래스를 사용 합니다. 이러한 속성을 만드는 방법에 대 한 정보를 문서를 참조 하십시오. [ActiveX 컨트롤: 글꼴 사용 하 여](../../mfc/mfc-activex-controls-using-fonts.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CFontHolder`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxctl.h  
  
##  <a name="cfontholder"></a>CFontHolder::CFontHolder  
 `CFontHolder` 개체를 생성합니다.  
  
```  
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```  
  
### <a name="parameters"></a>매개 변수  
 *pNotify*  
 글꼴에 대 한 포인터 `IPropertyNotifySink` 인터페이스입니다.  
  
### <a name="remarks"></a>주의  
 호출 해야 `InitializeFont` 를 사용 하기 전에 결과 개체를 초기화 합니다.  
  
##  <a name="getdisplaystring"></a>CFontHolder::GetDisplayString  
 컨테이너의 속성 브라우저에 표시 될 수 있는 문자열을 검색 합니다.  
  
```  
BOOL GetDisplayString(CString& strValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `strValue`  
 에 대 한 참조는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 문자열 표시를 보유 하는 것입니다.  
  
### <a name="return-value"></a>반환 값  
 문자열은 성공적으로 검색 합니다. 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="getfontdispatch"></a>CFontHolder::GetFontDispatch  
 글꼴의 dispatch 인터페이스에 대 한 포인터를 검색 하려면이 함수를 호출 합니다.  
  
```  
LPFONTDISP GetFontDispatch();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CFontHolder` 개체의 **IFontDisp** 인터페이스입니다. 호출 하는 함수 `GetFontDispatch` 호출 해야 `IUnknown::Release` 사용을 완료 하는 경우이 인터페이스 포인터입니다.  
  
### <a name="remarks"></a>주의  
 호출 `InitializeFont` 호출 하기 전에 `GetFontDispatch`합니다.  
  
##  <a name="getfonthandle"></a>CFontHolder::GetFontHandle  
 Windows 글꼴에 대 한 핸들을 가져오려면이 함수를 호출 합니다.  
  
```  
HFONT GetFontHandle();

 
HFONT GetFontHandle(
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>매개 변수  
 `cyLogical`  
 높이 컨트롤을 그리는 사각형의 논리 단위에서입니다.  
  
 `cyHimetric`  
 높이 `MM_HIMETRIC` 컨트롤의 단위입니다.  
  
### <a name="return-value"></a>반환 값  
 Font 개체;에 대 한 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 비율 `cyLogical` 및 `cyHimetric` 계산 하는 데 적절 하 게 표시 크기 논리 단위에서에 표시 되는 글꼴의 포인트 크기에 대 한 `MM_HIMETRIC` 단위:  
  
 표시 크기 = ( `cyLogical`  /  `cyHimetric`) X 글꼴 크기  
  
 화면에 대 한 올바른 크기가 글꼴에 핸들을 반환 하는 매개 변수가 없는 버전입니다.  
  
##  <a name="initializefont"></a>CFontHolder::InitializeFont  
 초기화는 `CFontHolder` 개체입니다.  
  
```  
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,  
    LPDISPATCH pFontDispAmbient = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFontDesc`  
 글꼴 설명 구조에 대 한 포인터 ( [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782)) 글꼴 특성을 지정 하는 합니다.  
  
 `pFontDispAmbient`  
 컨테이너의 앰비언트 글꼴 속성에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 경우 `pFontDispAmbient` 없는 **NULL**, `CFontHolder` 개체의 복제본에 연결 되어는 `IFont` 컨테이너의 앰비언트 글꼴 속성에 의해 사용 되는 인터페이스입니다.  
  
 경우 `pFontDispAmbient` 는 **NULL**, 새 Font 개체를 가리키는 글꼴 설명에서 만들어지거나 `pFontDesc` 또는 `pFontDesc` 는 **NULL**에서 기본 설명 합니다.  
  
 이 함수를 생성 한 후에 호출을 `CFontHolder` 개체입니다.  
  
##  <a name="m_pfont"></a>CFontHolder::m_pFont  
 에 대 한 포인터는 `CFontHolder` 개체의 `IFont` 인터페이스입니다.  
  
```  
LPFONT m_pFont;  
```  
  
##  <a name="querytextmetrics"></a>CFontHolder::QueryTextMetrics  
 가 나타내는 실제 글꼴에 대 한 정보를 검색 된 `CFontHolder` 개체입니다.  
  
```  
void QueryTextMetrics(LPTEXTMETRIC lptm);
```  
  
### <a name="parameters"></a>매개 변수  
 `lptm`  
 에 대 한 포인터는 [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) 에서 정보를 수신 하는 구조입니다.  
  
##  <a name="releasefont"></a>CFontHolder::ReleaseFont  
 연결을 끊습니다이 함수는 `CFontHolder` 개체에서 해당 `IFont` 인터페이스입니다.  
  
```  
void ReleaseFont();
```  
  
##  <a name="select"></a>CFontHolder::Select  
 지정 된 장치 컨텍스트에 컨트롤의 글꼴을 선택 하려면이 함수를 호출 합니다.  
  
```  
CFont* Select(
    CDC* pDC,  
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 장치 컨텍스트에 되는 글꼴을 선택 합니다.  
  
 `cyLogical`  
 높이 컨트롤을 그리는 사각형의 논리 단위에서입니다.  
  
 `cyHimetric`  
 높이 `MM_HIMETRIC` 컨트롤의 단위입니다.  
  
### <a name="return-value"></a>반환 값  
 대체 되는 글꼴에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 참조 [GetFontHandle](#getfonthandle) 대 한 설명은 `cyLogical` 및 `cyHimetric` 매개 변수입니다.  
  
##  <a name="setfont"></a>CFontHolder::SetFont  
 모든 기존 글꼴을 해제 하 고 연결 하는 `CFontHolder` 개체는 `IFont` 인터페이스입니다.  
  
```  
void SetFont(LPFONT pNewFont);
```  
  
### <a name="parameters"></a>매개 변수  
 *pNewFont*  
 새 포인터 `IFont` 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPropExchange 클래스](../../mfc/reference/cpropexchange-class.md)

